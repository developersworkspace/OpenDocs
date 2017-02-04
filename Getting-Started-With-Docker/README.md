# Getting Started with Docker

"Docker containers wrap a piece of software in a complete filesystem that contains everything needed to run: code, runtime, system tools, system libraries – anything that can be installed on a server. This guarantees that the software will always run the same, regardless of its environment." ~ Docker

## Prerequisites

* Window or Linux virtual machine/physical machine
* Remote Desktop Connection Manager (for Windows) or SSH CLient (for linux)

## Installing Docker

### Linux

Connect to your linux machine using a SSH Client such as Putty.

!["Putty SSH Client"](https://github.com/developersworkspace/OpenDocs/blob/master/Getting-Started-With-Docker/screenshots/putty.PNG?raw=true)

First we need to update all packages.

`sudo apt-get update`

Next you'll need to add the GPG (GNU Privacy Guard) key for the Docker repository.

`sudo apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D`

We are now authorized to access the Docker repository and it's sources. We can add these source to our APT sources.

`sudo apt-add-repository 'deb https://apt.dockerproject.org/repo ubuntu-xenial main`

To make sure that we use the docker-engine package that we just added, we need to update all packages and clear the original docker-engine package from the APT sources

`sudo apt-get update & apt-cache policy docker-engine`

Installing Docker

`sudo apt-get install -y docker-engine`

To check if you have successfully install docker you can run this command

`sudo systemctl status docker`


### Windows





