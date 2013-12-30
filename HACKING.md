docker-osx Hacking
===================

## Build Vagrant image

The image is built using this Packer script:

https://github.com/mitchellh/packer-ubuntu-12.04-docker

For example:

    $ packer build -only virtualbox,vmware template.json

