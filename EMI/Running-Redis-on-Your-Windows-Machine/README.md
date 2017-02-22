![Euromonitor International](http://www.euromonitor.com/Content/images/emi-logo.png)

# Running Redis on Your Windows Machine

Author: Barend Erasmus

Date: 17 February 2017

In this document we'll cover:

* How to install Docker on Windows
* How to run a single instance of Redis in a Docker Container
* How to configure Passport to run using the Docker Container


## How to install Docker on Windows

Go to the [docker site](https://docs.docker.com/docker-for-windows) to download the installer.

Once you have downloaded the installer, run the .msi file.

Follow the installation guide.

After installation you'll have to restart your machine.

To test your docker installation, open command prompt as Administrator and run the following command:

`docker -v`

You should get an output of `Docker version 1.13.0, build 49bf474` or something similar.


## How to run a single instance of Redis in a Docker Container

Once you have Docker installed, you'll be able to run this command, `docker run --name my-redis -p 6379:6379 -d redis`, in a command prompt (Administrator) window.

This will create a Docker Container with Redis running on port 6379. 

To stop the Docker Container, run `docker stop my-redis`
and to start the Docker Container, run `docker start my-redis`

**NOTE:**

The Docker Containers do not start automatically and will need to be started each time your machine is rebooted.

### How to configure Passport to run using the Docker Container

Once we our Docker Container of Redis running we can configure Passport to use the instance on localhost:6379.

In Passport we have a Redis configuration section which looks like this:

```xml
<redis Ports="7001|7002|7003|7004|7005|7006|7007|7008|7009">
    <redisServers>
        <add Hostname="RedisServer1"></add>
        <add Hostname="RedisServer2"></add>
        <add Hostname="RedisServer3"></add>
    </redisServers>
</redis>
```

* **Ports:** A pipe separated list of Redis ports.
* **Hostname:** IP Address or Hostname of Redis instance

The above configuration should be used when running Passport with a Redis Cluster.

We can remove all the ports and replace it with 6379 as we only have one instance of Redis running.

We'll also have to remove the two additional hostnames and replace the first one with 'localhost'.

The configuration section should now look like this:

```xml
<redis Ports="6379">
    <redisServers>
        <add Hostname="localhost"></add>
    </redisServers>
</redis>
```

## Sources

* [Docker for Windows Installation](https://docs.docker.com/docker-for-windows/install/)