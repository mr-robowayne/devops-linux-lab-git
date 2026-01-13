# Getting Started – DevOps Linux Lab (Docker)

This guide explains how to run the Linux lab environment locally using Docker.

## Prerequisites
- Docker installed
- Git installed

## Verify Docker
```bash
    docker --version
```

## Clone this Repo
```bash
    git clone https://github.com/mr-robowayne/devops-linux-lab-git.git
    cd devops-linux-lab-git
```

## Build Docker Image
```bash
    docker build -t devops-linux-lab docker
```

## Check if running
```bash
    docker ps

```
## Run Container with a Bind Mount on the Host

## Create Working Directory on the Host

```bash
    mkdir -p workspace
```

This directory will be used to keep files persistent outside the container.

## Set Path inside Variable

```bash
    HOST_WORKSPACE="$(pwd)/workspace"
```

## Start Container with a Bind Mount

```bash
    docker run -dit --name devops-linux-lab \
    -v "$HOST_WORKSPACE:/home/labuser/workspace" \
    devops-linux-lab

```

This command starts the container and logs in as `labuser`.

This allows working inside the container like on a virtual machine while keeping all files on the host system.

## Check if container is running 
```bash
    docker ps
```
## Reenter Container

```bash
    docker exec -it devops-linux-lab bash
```

# Exit Container

```bash
    exit
```

## Stop and Remove Container

```bash
    docker stop devops-linux-lab
    docker rm devops-linux-lab
```
This stops and removes the container when the lab is no longer needed.
