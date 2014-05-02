docker-osx
==========


# WARNING

This an unofficial docker helper made to simplify docker usage on OSX.

You can also read the official OSX documentation on Docker website: http://docs.docker.io/installation/mac/

# What is docker-osx

Docker on OS X in three steps:

1. Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads) and [Vagrant](http://www.vagrantup.com/downloads.html).

2. Put the `docker-osx` script somewhere on your path:

        curl https://raw.githubusercontent.com/noplay/docker-osx/0.10.0/docker-osx > /usr/local/bin/docker-osx
        chmod +x /usr/local/bin/docker-osx

3. Run:

        docker-osx shell
        docker version


This script acts as both an installer and as Virtual machine manager. On first run, it installs an OS X binary of the Docker client and starts a virtual machine with the Docker daemon running. It then sets up the shell environment so the Docker client knows to talk to the Docker daemon on the virtual machine.

The virtual machine that Docker runs on is given the hostname `localdocker`. For example, if you run `docker run -p 8000:8000 ...`, then that will be available at `localdocker:8000` from OS X.

## Additional commands

`docker-osx` provide additional commands as shortcuts for controlling the Vagrant VM:

### docker-osx start

Start the local Virtual Machine

### docker-osx ssh

Open a console on the Vagrant virtual machine.

### docker-osx destroy

Destroy the local Virtual Machine

### docker-osx halt

Stop the Vagrant VM. You'll probably want to do this after you've finished working with Docker project to save RAM.

### docker-osx shell

Start the virtual machine and open a shell with DOCKER_HOST environment variable configured.


## Override defaults

The docker-osx script has several options that can be overridden by adding a
new file `$HOME/.docker-osx/defaults`. When docker-osx starts the VM, it will
source this file.

When modifying the defaults for docker-osx, currently, it is best to destroy
any already-created VM and configure a new one with the changes.

An example `defaults` file follows:

```bash
# $HOME/.docker-osx/defaults
DOCKER_IP=192.168.228.10
```

### DOCKER_BIN

The installed location of the docker client.

Default: `/usr/local/bin/docker`

### DOCKER_IP

The IP that the docker host will be mapped to on your machine.

Default: `172.16.42.43`

### DOCKER_DOMAIN

The domain name added to `/etc/hosts`, pointing at the `DOCKER_IP`.

Default: `localdocker`

### DOCKER_PORT

The port that docker will be listening on.

Default: `4243`

### DOCKER_VERSION

The version of docker that will be installed when provisioning the vagrant vm.

Default: `0.7.6`

### DOCKER_CLIENT_URL

The URL used to download the docker client.

Default: <http://get.docker.io/builds/Darwin/x86_64/docker-0.7.6.tgz>

### VAGRANT_BOX_URL

The URL used to download the vagrant box.

Default: <http://static.orchardup.com/binaries/vagrant/vagrant-docker-0.7.2-virtualbox.box>

## Contributors

* [Julien Duponchelle](https://github.com/noplay/) – Original author
* [Ben Firshman](https://github.com/bfirsh) – Faster and simpler installation with Vagrant image and pre-built binary


## Alternatives

boot2docker provide an init script with most of docker-osx features and a dynamic team: https://github.com/steeve/boot2docker

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


