![Euromonitor International](http://www.euromonitor.com/Content/images/emi-logo.png)

# Install Redis Cluster on Linux Server

Author: Barend Erasmus

Date: 22 February 2017

In this document we'll cover:

* How to install a Redis Cluster on a Linux Server
* How to install a Redis Cluster across two or more servers

## How to install a Redis Cluster on a Linux Server

*The following steps will result in a Redis Cluster with 8 instances of Redis where 4 will be masters and 4 slaves.*

Connect to your Linux Server using a SSH Client such as Putty.

*For more details on Putty click [here](https://github.com/developersworkspace/OpenDocs/tree/master/The-Basics-Of-Linux#ssh-client-putty).*

Run the following command, which will install 8 instances and configure them as a service.

`bash <(curl -s https://raw.githubusercontent.com/developersworkspace/Production-Apps/master/Redis-Cluster/install.sh)`

Change to the Redis source directory by running

`cd /tmp/redis-stable/src`

**Note**

In this example we will use '172.24.40.21' as the IP Address of our Linux Server. You'll need to replace it with the IP Address of your Linux Server.

Run the following command to cluster the 8 instances in a 4 master, 4 slave configuration.

Usage: 

`./redis-trib.rb create --replicas <numberOfReplicas> <ipAddress>:<port> <ipAddress>:<port>`

*--replicas* The number of replicas each master will have.

Example: 

`./redis-trib.rb create --replicas 1 172.24.40.21:7001 172.24.40.21:7002 172.24.40.21:7003 172.24.40.21:7004 172.24.40.21:7005 172.24.40.21:7006 172.24.40.21:7007 172.24.40.21:7008`



## How to install a Redis Cluster across two or more servers

To install a Redis Cluster across multiple servers you'll need to run the following command on each of the servers.

`bash <(curl -s https://raw.githubusercontent.com/developersworkspace/Production-Apps/master/Redis-Cluster/install.sh)`

Then on one of the servers you need to execute the clustering commands.

`cd /tmp/redis-stable/src`

followed by

`./redis-trib.rb create --replicas <numberOfReplicas> <ipAddress>:<port> <ipAddress>:<port>`

For example, if you have two servers with the IP Addresses of 172.1.1.1 and 172.2.2.2, your command will be.

`./redis-trib.rb create --replicas 1 172.1.1.1:7001 172.1.1.1:7002 172.1.1.1:7003 172.1.1.1:7004 172.1.1.1:7005 172.1.1.1:7006 172.1.1.1:7007 172.1.1.1:7008 172.2.2.2:7001 172.2.2.2:7002 172.2.2.2:7003 172.2.2.2:7004 172.2.2.2:7005 172.2.2.2:7006 172.2.2.2:7007 172.2.2.2:7008`

## Sources

* [Redis cluster tutorial](https://redis.io/topics/cluster-tutorial)