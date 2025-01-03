**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Guided Exercises
##### 1. Using the IP 172.16.30.230 and netmask 255.255.255.224, identify: The CIDR notation for the netmask Network address Broadcast address Number of IPs that can be used for hosts in this subnet
- R: The CIDR notation for the netmask:27
Network address: 172.16.30.224
Broadcast address: 172.16.30.255
Number of IPs that can be used for hosts in this subnet: 30
##### 2. Which setting is required on a host to allow an IP communication with a host in a different logical network?
- R: Default route
# Explorational Exercises
##### 1. Why are the IP ranges starting with 127 and the range after 224 not included in the IP address classes A, B or C?
- R: The range that starts with 127 is reserved for loopback addresses, used for tests and internal communication between processes, such as the address 127.0.0.1. In addition, addresses above 224 are also not used as host addresses, but for multicast and other purposes.
##### 2. One of the fields belonging to an IP packet that is very important is TTL (Time To Live). What is the function of this field and how does it work?
- R: TTL defines the lifetime of a packet. This is implemented through a counter in which the initial value defined at the source is decremented in each gateway/router through which the packet passes, which is also called a “hop”. If this counter reaches 0 the packet is discarded.
##### 3. Explain the function of NAT and when it is used.
- R: The NAT (Network Address Translation) feature allows hosts on an internal network, which uses private IPs, to have access to the Internet as if they were directly connected to it, with the Public IP used on the gateway.

- - - 
## ***Sources:***