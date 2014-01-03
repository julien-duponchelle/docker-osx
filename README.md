docker-osx
==========

# WARNING

This an unofficial docker wrapper made to simplify docker usage on OSX. In a near futur docker (version 0.7.3) will provide official binary for client part.

# What is docker-osx

Docker on OS X in three steps:

1. Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads) and [Vagrant](http://www.vagrantup.com/downloads.html).

2. Put the `docker` script somewhere on your path:

        curl https://raw.github.com/noplay/docker-osx/master/docker > /usr/local/bin/docker
        chmod +x /usr/local/bin/docker

3. Run:

        docker version

This script acts as both an installer and a Docker binary. On first run, it installs an OS X binary of the Docker client and starts a virtual machine with the Docker daemon running. It then passes through all invocations of `docker` to the client which controls the daemon running on the virtual machine.

The virtual machine that Docker runs on is given the hostname `localdocker`. For example, if you run `docker run -p 8000:8000 ...`, then that will be available at `localdocker:8000` from OS X.

## Additional commands

Two extra commands have been added to `docker` as shortcuts for controlling the Vagrant VM:

### docker halt

Stop the Vagrant VM. You'll probably want to do this after you've finished working with Docker project to save RAM.

### docker ssh

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


