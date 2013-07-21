docker-osx
==========

This script allow you to install and use docker on MacOS X.
The target is to allow users to forgot they are running docker
inside a Virtual Machine.

The results is you can run command like:
```
docker pull ubuntu:12.10
docker images
```
Directly from the MacOS terminal without ssh on the docker Vagrant box.


In details the script:
* setup the docker Virtual Machine
* enable access to docker network from the MacOS host
* compile docker for MacOS
* launch the docker VM if docker is not running when you use the docker command in your MacOS terminal

# Installation

You need to install Vagrant and VirtualBox before. 

```
curl https://raw.github.com/noplay/docker-osx/master/docker > /usr/local/bin/docker
chmod 700 /usr/local/bin/docker

docker version
```

# Additional commands

## ssh

Open an ssh console on docker virtual machine

## halt

Stop docker daemon (by stopping the docker virtual machine)

## upgrade

Upgrade the docker version


# Licence
Copyright 2013 Julien Duponchelle

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.


