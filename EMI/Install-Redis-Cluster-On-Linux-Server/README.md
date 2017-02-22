![Euromonitor International](http://www.euromonitor.com/Content/images/emi-logo.png)

# Install Redis Cluster on Linux Server

Author: Barend Erasmus

Date: 22 February 2017

In this document we'll cover:

* How to install a Redis Cluster across one or more servers

## How to install a Redis Cluster across one or more servers

To install a Redis Cluster across multiple servers you'll need to execute the following command on each of the servers.

`curl -s https://raw.githubusercontent.com/developersworkspace/Production-Apps/master/Redis-Cluster/cluster.sh | bash -s "7001|7002|7003|7004|7005|7006|7007|7008"`

Then on one of the servers you need to execute the clustering commands.

`curl -s https://raw.githubusercontent.com/developersworkspace/Production-Apps/master/Redis-Cluster/cluster.sh | bash -s "<numberOfReplicas>" "<ipAddressOfServer1>|<ipAddressOfServer2>" "<port1>|<port2>"`

For example, if you have two servers with the IP Addresses of '172.24.40.21' and '172.24.40.22', your command will be.

`curl -s https://raw.githubusercontent.com/developersworkspace/Production-Apps/master/Redis-Cluster/cluster.sh | bash -s "1" "172.24.40.21|172.24.40.22" "7001|7002|7003|7004|7005|7006|7007|7008"`

## Sources

* [Redis cluster tutorial](https://redis.io/topics/cluster-tutorial)