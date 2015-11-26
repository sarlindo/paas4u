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

1. Clone the project to a directory of your choice
 
   git clone https://github.com/sarlindo/paas4u


2. change into the mesos directory

   cd paasy

3. bring up the mesos cluster

   vagrant up

 
## Usage


All logs will go into /var/log/mesos
