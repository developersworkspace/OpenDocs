# Getting Started with Docker

"Docker containers wrap a piece of software in a complete filesystem that contains everything needed to run: code, runtime, system tools, system libraries – anything that can be installed on a server. This guarantees that the software will always run the same, regardless of its environment." ~ Docker

## Prerequisites

* Windows or Linux virtual machine/physical machine
* Remote Desktop Connection Manager (for Windows) or SSH CLient (for linux)

## Installing Docker

### Linux

Connect to your linux machine using a SSH Client such as Putty.

!["Putty SSH Client"](https://github.com/developersworkspace/OpenDocs/blob/master/Getting-Started-With-Docker/screenshots/putty.PNG?raw=true)

We need to start by updating the local server's apt package indexes

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

Go to the [docker site](https://docs.docker.com/docker-for-windows) to download the installer.

Once you have downloaded the installer, run the .msi file.

Follow the installation guide.

After installation you'll have to restart your machine.

To test your docker installation, open command prompt and run the following command:

`docker -v`

You should get an output of `Docker version 1.13.0, build 49bf474` or something similar.

## Related

* [Back to OpenDocs](https://github.com/developersworkspace/OpenDocs)

The MIT License (MIT)
=====================

Copyright © `2017` `Barend Erasmus`

Permission is hereby granted, free of charge, to any person
obtaining a copy of this software and associated documentation
files (the “Software”), to deal in the Software without
restriction, including without limitation the rights to use,
copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the
Software is furnished to do so, subject to the following
conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES
OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT
HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY,
WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.



