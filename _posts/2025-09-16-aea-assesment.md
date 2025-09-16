---
title: ".NET Solution Repository layout"
date: 2025-09-16 10:00:00 -0700
categories: architectures
---


# Repository structure for .NET Solution

root-project/
├── .cursor/
│   ├── rules/
│   │   ├── ...
├── .git/
│   ├── ...
├── .github/
│   ├── workflows/
│   │   ├── ...
├── devops/
│   ├── azure
│   │   ├── ...
├── infrastructure/
│   ├── bicep/
│   │   ├── ...
│   ├── terraform/
│   │   ├── ...
│   ├── ...
├── scripts/
│   ├── ...
├── src/
│   ├── ...
├── .gitignore
├── .editconfig
├── Directory.Build.props
├── Directory.Build.targets
├── dotnet.ruleset
├── global.json
├── stylecop.json
├── nuget.config
├── project.sln
├── README.md


## Build pipeline
The build pipeline shall not take more the 10 min to be completed. 1 min is the default value

## Unit test
The unit test shall not take more the 5 min to be completed. 2 min is the default value

## Deployment pipeline
The deployment pipeline shall be separated by the build pipeline.

## Database migration shall be disabled and only manual migration shall be possible.

## Commit and PR
PR approvation is not compulsory, developer will decide when code review is need.


| Repo                            | Artifact                   | Note                            |
| ------------------------------- | -------------------------- | ------------------------------- |
| AEA.Appointments                | WebAPI                     |                                 |
| AEA.BusinessLayer               | WebAPI/FunctionApp         | Split to multiple microservices |
| AEA.BusinessLayer.LogicApps     | LogicApps                  | Convert to WebApp               |
| AEA.CommunicationLayer          |                            |                                 |
| AEA.DocumentLayer               | WebAPI/FunctionApp         |                                 |
| AEA.Frontend                    | Web                        | Move to docker                  |
| AEA.Infrastructure              | N/A                        |                                 |
| AEA.Meteorage                   | WebAPI                     |                                 |
| AEA.OrdersLayer                 | WebAPI/FunctionApp         |                                 |
| AEA.ProcessLayer                | FunctionApp                |                                 |
| AEA.Profiles                    | WebAPI                     |                                 |
| AEA.Proxy                       | WebAPI                     |                                 |
| AEA.ReverseProxyYarp            | WebAPI                     |                                 |
| AEA.Scheduler                   |                            | Check if still required         |
| AEA.SharedLibs                  | Nuget                      | Build removing prerelease       |

## Todo

Demo with hc swap