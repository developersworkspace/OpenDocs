# The Basics of Linux

## Remote Access?

For the windows users that like to use Remote Deskop Protocol, your luck is out :)

Most, if not all, Linux servers has not user-interface. Here are two tools which will make administration of Linux servers somewhat simpler.

### SSH Client (Putty)

SSH client is a program that allows establishing a secure and authenticated SSH connections to SSH servers.

You can download Putty [here](http://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html).

**NOTE**

Ctrl + V won't work. To paste in Putty, right click in the console window. 


!["Putty SSH Client"](https://github.com/developersworkspace/OpenDocs/blob/master/The-Basics-Of-Linux/screenshots/putty.PNG?raw=true)

### FTP Client

An FTP Client is a software designed to transfer files back-and-forth between two computers over the Internet.

You can download FileZilla [here](https://filezilla-project.org/).

!["FileZilla FTP Client"](https://github.com/developersworkspace/OpenDocs/blob/master/The-Basics-Of-Linux/screenshots/filezilla.PNG?raw=true)

## Basic commands

### Display path of current directory

Command: 

`pwd`

Output: 

`/root`


### Change current directory

Command: 

`cd /etc/systemd`

### Change current directory to user home directory

Command: 

`cd ~`

### Change permission of file/folder recursively

Command: 

`chmod -R 777 /var/www`

### Change ownership of file/folder recursively

Command:

`chown -R <username>:<group> /var/www`

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
