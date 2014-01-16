docker-osx
==========

# WILL BE DEPRECATED

boot2docker provide an init script with most of docker-osx features and more support:
https://github.com/steeve/boot2docker


# WARNING

This an unofficial docker helper made to simplify docker usage on OSX.

# What is docker-osx

Docker on OS X in three steps:

1. Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads) and [Vagrant](http://www.vagrantup.com/downloads.html).

2. Put the `docker-osx` script somewhere on your path:

        curl https://raw.github.com/noplay/docker-osx/master/docker-osx > /usr/local/bin/docker-osx
        chmod +x /usr/local/bin/docker-osx

3. Run:

        docker-osx shell
        docker version

This script acts as both an installer and as Virtual machine manager. On first run, it installs an OS X binary of the Docker client and starts a virtual machine with the Docker daemon running. It then setup the shell environnement for docker in order to access to the virtual machine.

The virtual machine that Docker runs on is given the hostname `localdocker`. For example, if you run `docker run -p 8000:8000 ...`, then that will be available at `localdocker:8000` from OS X.

## Additional commands

`docker-osx` provide additional commands as shortcuts for controlling the Vagrant VM:

### docker-osx start

Start the local Virtual Machine

### docker-osx destroy

Destroy the local Virtual Machine

### docker-osx shell

Start the virtual machine and open a shell with DOCKER_HOST environnement variable configured.

### docker-osx halt

Stop the Vagrant VM. You'll probably want to do this after you've finished working with Docker project to save RAM.

### docker-osx ssh

Open a console on the Vagrant virtual machine.

## Contributors

* [Julien Duponchelle](https://github.com/noplay/) – Original author
* [Ben Firshman](https://github.com/bfirsh) – Faster and simpler installation with Vagrant image and pre-built binary

## Licence

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


