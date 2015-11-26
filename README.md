# PAASY - Simple Ubuntu two node cluster

[https://cloud.githubusercontent.com/assets/6406166/11431151/d94688d6-945f-11e5-9af6-8451d2b3ea85.png]

This project automates a simple Ubuntu 14.04 two node cluster using vagrant and ansible as the provisioner.

This will build one master node and one slave node.

This build will pull whatever latest builds that are available in the mesosphere repos for mesos, marathon, chronos and zookeeper and also the latest docker versions that are used to run containers on the mesos slaves.

However, for mesos-dns, this will pull the binary release 0.4.0 and will automatically deploy mesos-dns as an application using marathon.

## Installation

Pre-req:

1. Ensure you have vagrant installed
2. Ensure you have virtualbox installed
3. Ensure you have ansible installed

Note: This may not work on windows dev machines because I believe the ansible provisioners won't run on windows, but not 100% sure. This should work fine on a mac or linux machine. 

Run it:

1. Clone the project to a directory of your choice
 
   git clone https://github.com/sarlindo/mesos


2. change into the mesos directory

   cd mesos

3. bring up the mesos cluster

   vagrant up

 
## Usage

URL for mesos will be - http://192.168.33.10:5050

URL for marathon will be - http://192.168.33.10:8080

URL for chronos will be - http://192.168.33.10:4400

All logs will go into /var/log/mesos
