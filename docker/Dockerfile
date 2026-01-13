FROM ubuntu:22.04

# Disable interactive prompts during build
ENV DEBIAN_FRONTEND=noninteractive

# Install essential Linux and DevOps tools
RUN apt-get update && apt-get install -y \
    sudo \
    curl \
    vim \
    git \
    net-tools \
    iputils-ping \
    ca-certificates \
    && rm -rf /var/lib/apt/lists/*

# Create a non-root user for lab work
RUN useradd -m labuser && echo "labuser ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

USER labuser
WORKDIR /home/labuser
