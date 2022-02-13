Docker Get Started
===

Install Docker based on the Host OS.

Try this link in order to install Docker on Windows 10
[Docker](https://docs.microsoft.com/en-us/virtualization/windowscontainers/quick-start/quick-start-windows-10)


## How to set proxy
1. Set environmental variable HTTP_PROXY
2. Restart the server

``` PS
Restart-Service docker
```

## How run login
``` PS
docker login
```

## How to switch container type
Following command allows toggling between Windows and Linux

``` PS
& $Env:ProgramFiles\Docker\Docker\DockerCli.exe -SwitchDaemon
```

## How check images list available locally
``` PS
docker images
```

## How show runninng container
Flag --all show even not running

``` PS
docker container ls --all
```

## How delete container and images

Following commands do:
5. Restart container
6. Remove image
7. Stop container
8. Remove every not running container


``` bash
# Stop running containers
docker stop $(docker ps -a -q)

# Delete all the containers
docker rm $(docker ps -a -q)

# Delete all the images
docker rmi $(docker images -q)

# Delete all the images (force delete) very usefull when an image has multiple references
docker container prune

# Remove image
docker rmi 6c367cf4cb98

# Remove every not running container
docker rmi $(docker images -q) -f

# Restart container
docker container restart 42dd3725810b

# Stop container
docker stop f93f9e2d7ba8
```
 
# Docker compose

``` bash
docker-compose --help
docker-compose version
docker-compose up
```


## Docker network

Official documentation:
[Docker network](https://docs.docker.com/engine/userguide/networking/work-with-networks/)

If you are running your containers in a user-defined network, then Docker maintains a DNS server that will map container names to addresses.
That is, if I first create a network: [user-defined network]((https://docs.docker.com/engine/userguide/networking/)


Useful network commands 

``` bash
# Get the available docker network
docker network ls

# Crete a network
docker network create myapp_net

# Remove unused networks
docker network prune

```

# Docker Volumes
Docker allows to manage volumes as external data folder. These volumes can be either folder managed by host or logical volumes managed by Virtual Machine.
Use following link to a complete list of commands 
[Docker Volumes](https://docs.docker.com/engine/reference/commandline/volume_ls/#usage)

``` PS
docker volume ls
docker volume create my_data-vol
docker volume prune
docker volume rm

```

-v "$PWD/neo4j":/usr/share/elasticsearch/data
--volume=$HOME/neo4j:/usr/share/elasticsearch/data
-v my-vol:/usr/share/elasticsearch/data


## How run shell inside  container
``` PS
docker exec -it redis bash
```


## How get an image from repository (default: leatest version)
``` PS
docker pull microsoft/aspnet
docker pull microsoft/nanoserver
```


## Procedura per installare l'immagine di ASP.NET (Leatest Version)

``` PS
docker inspect 1b4e1cd7ddb6
docker run debian echo "Welcome to Docker"
docker run -it debian /bin/bash
```

## Esempio completo

Il seguente esempio è stato copiato dal link:

[stormpath.com](https://stormpath.com/blog/tutorial-deploy-asp-net-core-on-linux-with-docker)

Setting up Docker
It’s easy to get started with Docker.
First, you have to install the Docker Engine on your machine (or your server).
Follow the official instructions for Windows 10, Mac, or Linux.

For my own testing, I installed Docker for Windows on my Windows 10 development environment, and also on my Mac.
To make sure the service is installed correctly, run this from the terminal:


``` PS
docker --version
```

Docker version 1.12.0-rc4, build e4a0dbc, experimental
If you see a version number, everything is working!

# Creating an ASP.NET Core project
If you don’t already have the latest .NET Core tooling installed, grab that at the official .NET Core site. Once it’s installed on your machine, you can create a new directory and scaffold a new ASP.NET Core project easily:

``` PS
mkdir AspNetCoreHelloWorld
cd AspNetCoreHelloWorld
dotnet new web --framework netcoreapp1.1
```

To make sure everything is working, try running the project locally first:

``` PS
dotnet restore
dotnet run
```

The project should start listening on http://localhost:5000. Try it out in your browser!

Building a Dockerfile for ASP.NET Core
Docker needs a Dockerfile that contains the “recipe” for creating an image based on the project. 
Create a new file called Dockerfile in the project directory:

``` BASH
touch Dockerfile
```

On Windows, you can run notepad Dockerfile instead, or use your favorite text editor. 
Make sure that this file isn’t saved with an extension like .txt – it’s supposed to have no extension.

The Dockerfile contents are straightforward:

``` js
FROM microsoft/dotnet:2.0.0-sdk

ENV http_proxy 192.168.2.7:3128
ENV https_proxy 192.168.2.7:3128

COPY . /app
WORKDIR /app

RUN ["dotnet", "restore"]
RUN ["dotnet", "build"]

EXPOSE 5000/tcp
ENV ASPNETCORE_URLS http://*:5000

ENTRYPOINT ["dotnet", "run"]
```

Here’s what each of these instructions does:

FROM tells Docker that you want to base your image on the existing image called microsoft/dotnet:1.1.2-sdk. This image already contains all the dependencies for running .NET Core on Linux, so you don’t have to worry about setting those up.
COPY and WORKDIR copy the current directory’s contents into a new directory inside the container called /app, and set that to the the working directory for the subsequent instructions.
RUN executes dotnet restore and dotnet build, which restores the packages needed to run the ASP.NET Core application and compiles the project.
EXPOSE tells Docker to expose port 5000 (the default port for ASP.NET) on the container.
ENV sets the environment variable ASPNETCORE_URLS in the container. This will ensure that ASP.NET Core binds to the correct port and address.
ENTRYPOINT specifies the command to execute when the container starts up. In this case, it’s dotnet run.
Creating the Docker image
Once you’ve created the Dockerfile, you’re ready to build an image:

``` PS
docker build -t genocs:aspnetcorehelloworld .
```

See that trailing period? That tells docker to look in the current directory for a Dockerfile. The -t flag tags the image with tag genocs:aspnetcorehelloworld.

When the image finishes building, you can spin it up:

``` PS
docker run -d -p 8083:5000 -t genocs:aspnetcorehelloworld
```

`docker run -it --rm the_image_you_built ls -l /usr/local/bin`


The -d flag tells Docker to run the container in detached mode (in the background).
The -p flag will map port 8080 on the host machine to port 5000 inside the container.
Finally, the -t flag is used to specify which image to run.

That’s it! 

You should see your container running when you check docker ps.
Open up a web browser and navigate to http://localhost:8080.
You should see the welcome page


## How install RabbitMQ container 
L'immagine ufficiale di RabbitMQ gira su una macchina linux. Quindi assicurarsi che il server giri in modalità Linux

RabbitMQ container
[RabbitMQ](https://hub.docker.com/_/rabbitmq/)


``` PS
docker build -t my_test .

docker run -d --hostname hpn-rabbit-host --name hpn-rabbit rabbitmq:3
docker run -d --hostname hpn-rabbit-host --name hpn-rabbit rabbitmq:3-management 
docker run -d --hostname hpn-rabbit-host --name hpn-rabbit -p 15672:15672 -p 5672:5672 rabbitmq:3-management
docker run -d --hostname hpn-rabbit-host --name hpn-rabbit -p 15672:15672 -p 5672:5672 rabbitmq:3-management
docker logs  hpn-rabbit
```

``` PS
docker build -t utu_rabbit .
docker run -d --hostname utu_rabbit-host --name utu-points -p 15672:15672 -p 5672:5672 utu_rabbit:latest
docker logs utu-points
```


I seguenti comandi eseguono il container utilizzando la rete locale e facendo il forward delle porte.
Nota: La rete locale deve essere stata creata

``` PS
docker run -d --hostname hpn_rabbit_host --name hpn_rabbit -p 15672:15672 -p 5672:5672 rabbitmq:3-management --network utu_server_back
docker logs some-rabbit
```



# Clear
``` bash
#!/bin/bash
docker rm -f $(docker ps -a -q)
docker volume rm $(docker volume ls)
docker rmi -f $(docker images -q)
```


# Very useful rabbit example
https://github.com/Gsantomaggio/rabbitmqexample


# Clear All
docker stop $(docker ps -a -q)
docker rm $(docker ps -a -q)
docker rmi $(docker images -q)
docker rmi $(docker images -q) -f

docker container prune
docker network prune
docker volume prune

docker container ls
docker network ls
docker volume ls



Build steps


``` bash
# Build the Docker image
docker build -t genocs.qrcode .

# Create the image tag
docker tag genocs.qrcode genocs/identity
```


### Run the container
Before start check if the network exist otherwise remove it or create the network

``` ps
docker run -d --name qrcode_1 -p 5000:5001 genocs.qrcode --network genocs-network
docker run -d --name qrcode_2 -p 5000:5002 genocs.qrcode --network genocs-network

```



### Push the images to the Docker image repository (Docker Hub)

``` ps
docker push genocs/identity
```


docker pull genocscontainerregistry.azurecr.io/solomonbesearch:60
docker run  genocscontainerregistry.azurecr.io/solomonbesearch:60 -p 80:5001



wsl --shutdown
notepad "$env:USERPROFILE/.wslconfig"
