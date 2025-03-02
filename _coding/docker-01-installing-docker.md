---
layout: post
title: "Installing Docker"
excerpt: ""
modified: 2017-11-22T14:17:25-04:00
categories: Docker
subcategory: "01 - using container"
tags: [Docker, using-container]
comments: true
share: true
---

Docker consists of three programs: Docker Daemon, API and CLI
Installing Docker gives us the access to its command line interface (CLI) and we will interact to Docker through its CLI.

## Docker on MacOS

To install Docker on Mac follow the steps [Installing docker on Mac](https://docs.docker.com/desktop/setup/install/mac-install/) and jump to step **8**.

## Installing Docker on Linux

#### 1. Uninstalling previous versions

To guarantee we start the installation from scratch:

`sudo apt-get remove docker* containerd runc`

or:

`sudo apt-get remove docker\* containerd runc`

`sudo apt-get remove 'docker*' containerd runc`

However, Docker preserves information about images, containers, volumes and network in the `/var/lib/docker` folder. The commands above do not deleted these files.

#### 2. Installing initial dependencies

To enable getting repositories via HTTPS through apt-get, install the following packages:

```sh
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```

#### 3. Add the public key

To add the official GPG key of the Docker repository:

```sh
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

If this is correct, you do not get any return.

#### 4. Add remote repository to the `apt` list

To add the official Docker repository to `apt`:

```sh
echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" \
  | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

#### 5. Installing Docker on Linux

First, let's update the `apt` package lists:

```sh
sudo apt-get update
```

Install the latest stable version of Docker Engine - Community, which is a version maintained by the community itself:

```sh
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

#### 6. Add your user to the group of Docker users

To avoid typing `sudo` for every Docker command, let's give the user permission:




