---
title: "Local NuGet Feed"
date: 2026-06-21
---


## Local NuGet feed

This tutorial shows how to create and use a local NuGet feed when your private feed is unavailable or unreliable.

This is useful when your packages are hosted on a private feed (for example, Azure DevOps), but your build machine cannot always connect to it.

## Goal

Use a local folder as a fallback NuGet source so restore and build can continue even if the private feed is temporarily unreachable.

## Prerequisites

1. Access to your private NuGet feed.
2. The required `.nupkg` package files.
3. A local folder, for example `C:\dev\local-nuget-feed`.

## Steps

1. Open your private NuGet feed (Azure DevOps in this example).
2. Download the packages your solution needs.
3. Copy the downloaded `.nupkg` files to your local folder, for example `C:\dev\local-nuget-feed`.
4. Update your `nuget.config` file to include the local source.

Use this configuration:

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
	<packageSources>
		<!-- remove any machine-wide sources with <clear/> -->
		<clear />
		<!-- also get packages from the NuGet Gallery -->
		<add key="nuget.org" value="https://www.nuget.org/api/v2/" />
		<add key="local" value="C:\dev\local-nuget-feed" allowInsecureConnections="True" />
	</packageSources>
	<activePackageSource>
		<add key="All" value="(Aggregate source)" />
	</activePackageSource>
</configuration>
```

## Validate

Run restore on the machine with connection issues:

```bash
dotnet restore
```

If restore succeeds, your local feed is configured correctly.

## Use This Pattern In A Docker Image Build

You can use the same approach in Docker by copying your local `.nupkg` files into the image and pointing `nuget.config` to that folder.

1. Create a folder in your repository, for example `local-nuget-feed`, and place the required `.nupkg` files there.
2. Keep a `nuget.config` file that includes both `nuget.org` and the local folder source.
3. In your Dockerfile, copy both the local feed folder and `nuget.config` before running `dotnet restore`.

Example Dockerfile snippet:

```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /src

# Copy local packages and NuGet configuration first
COPY local-nuget-feed/ /opt/local-nuget-feed/
COPY nuget.config ./nuget.config

# Copy project files and restore using the local feed path in nuget.config
COPY . .
RUN dotnet restore --configfile ./nuget.config

RUN dotnet publish -c Release -o /app/out
```

In this scenario, set the local source in `nuget.config` to `/opt/local-nuget-feed`.

### Notes

1. If you do not want to store `.nupkg` files in the repository, generate or copy them into `local-nuget-feed` as part of your CI pipeline before `docker build`.
2. This pattern improves reliability for container builds in environments with unstable access to private feeds.

## Multi-Stage Docker Example (Smaller Runtime Image)

This version keeps SDK tools and local package files in build stages only, so the final runtime image is smaller.

```dockerfile
# Restore stage
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS restore
WORKDIR /src

COPY local-nuget-feed/ /opt/local-nuget-feed/
COPY nuget.config ./nuget.config
COPY . .
RUN dotnet restore --configfile ./nuget.config

# Publish stage
FROM restore AS publish
RUN dotnet publish -c Release -o /app/out --no-restore

# Runtime stage
FROM mcr.microsoft.com/dotnet/aspnet:8.0 AS runtime
WORKDIR /app
COPY --from=publish /app/out .
ENTRYPOINT ["dotnet", "YourApp.dll"]
```

Replace `YourApp.dll` with your real application assembly name.

### Why This Helps

1. Better reliability: restore still works from the local NuGet source.
2. Smaller image: the final stage does not include the SDK or local `.nupkg` files.
3. Faster deployments: smaller runtime layers are typically quicker to push and pull.
