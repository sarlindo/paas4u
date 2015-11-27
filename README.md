# PAAS4U - Platform as a service for YOU!

![alt text](https://cloud.githubusercontent.com/assets/6406166/11431151/d94688d6-945f-11e5-9af6-8451d2b3ea85.png)

This project automates a small 2 node paas on Ubuntu 14.04 utilizing a few open sources tools. This project uses vagrant, virtualbox and ansible as the provisioner.

This build will pull whatever latest builds that are available in the mesosphere repos for mesos, marathon, chronos and zookeeper and also the latest docker versions that are used to run containers on the mesos slaves.  
However, for mesos-dns, this will pull the binary release 0.4.0 and will automatically deploy mesos-dns as an application using marathon.

## Installation

### Pre-req

1. Ensure you have vagrant installed
2. Ensure you have virtualbox installed
3. Ensure you have ansible installed

Note: This may not work on windows dev machines because I believe the ansible provisioners won't run on windows, but not 100% sure. This should work fine on a mac or linux machine. 

### O.K enough already, how do I RUN IT?

Clone the project to a directory of your choice

``` 
   git clone https://github.com/sarlindo/paas4u
```

change into the pass4u directory

```
   cd paas4u
```

bring up pass4u

```
   vagrant up
```
 
## Usage


#### The following are the URL's for the individual Web UI applications

```
http://marathon.192.168.33.10.xip.io                 (this is the Web UI for marathon, you can use this UI to launch new applications)
http://mesos.192.168.33.10.xip.io                    (this is the Web UI for mesos, you can use this UI to check on your mesos cluster's resources)
http://chronos.192.168.33.10.xip.io                  (this is the Web UI for chronos, you can use this UI to schedule jobs in mesos, like cron)
http://servicediscovery.192.168.33.10.xip.io         (this is the Web UI for consul, you can use this UI to see all services in your registry)


http://python.192.168.33.10.xip.io                   (this is the Web UI for a sample python web server)
http://wildfly.192.168.33.10.xip.io/node-info        (this is the Web UI for a sample jboss/wildfly JEE app)
```

## Troubleshooting


All logs for marathon, mesos-master, mesos-slave and chronos will go into /var/log/mesos in their individual log files.

All logs for docker containers can be inspected with the command 

```
sudo docker logs <containerid>
```
