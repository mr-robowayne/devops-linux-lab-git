# Docker Linux Lab

## Purpose
Provide a reproducible Linux environment for DevOps practice using Docker.

## Base Image
- Ubuntu 22.04 LTS

## Installed Tools
- git
- curl
- vim
- networking utilities (ping, net-tools)

## User
- labuser (passwordless sudo)

## Persistent Workspace
A bind mount is used to persist work outside the container.

- Host path: ./workspace
- Container path: /home/labuser/workspace

This allows working like on a virtual machine while keeping data persistent.
