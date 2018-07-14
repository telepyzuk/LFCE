
# Intro

*Important:* For this item, you should ssh to the node `exam-1` and complete all tasks on this node. Ensure that you return to the base node (hostname: `node-1` ) when you have completed this item.

# Question

Your organization is in the process of launching a new brand. Part of the work required for this launch involves the configuration of a master DNS server for the new domain name which has been registered. To provide access to a new webserver both internally and externally, you will make use of BIND views to provide clients with access to two different zonefiles for the example.info domain. Perform the following tasks to install and configure the master DNS server on node `exam-1` :

Install BIND on the server, and ensure it is started and configured to start automatically on boot. 

BIND should be listening on at least the loopback interface

Create the `/etc/bind/zones` directory

Create an `RFC 1035` compliant zonefile for the example.info domain, to be served to internal clients. The zone file should be placed at `/etc/bind/zones/example.info-internal.db` . Ensure that an A record exists for the new webserver with a host label of `webdev.example.info` . and record data of `192.168.23.85` . The TTL is not important

Create an `RFC 1035` complaint zonefile for the `example.info` domain, to be served to external clients. The zone file should be placed at `/etc/bind/zones/example.info-external.db` . Ensure that an A record exists for the new webserver with a host label of `webdev.example.info` . and record data of `192.0.2.243` . The TTL is not important

Configure BIND using the view mechanism so that the internal copy of the zone is served to clients whose requests originate from the subnet `10.250.0.0/24` ONLY, and the external copy of the zone is served to all other clients

Ensure that BIND is reloaded appropriately so that your changes are made live

To assist you with these tasks, an incomplete sample zonefile has been provided in the directory `/opt/CESC01001/zonefiles` on node `exam-1` .

# Question Weight

3%

# did it??

Couldn't do it...

