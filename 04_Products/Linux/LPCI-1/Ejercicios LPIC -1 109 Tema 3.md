**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Lesson1 
# Guided Exercises
##### 1. Which commands can be used to list network interfaces?
- R: ip link, ifconfig -a, or ls /sys/class/net
##### 2. How would you temporarily disable an interface? How would you re-enable it?
- R:  Using ifconfig:
$ ifconfig wlan1 down
$ ifconfig wlan1 up
Using ip link:
$ ip link set wlan1 down
$ ip link set wlan1 up
##### 3. Which of the following is a reasonable subnet mask for IPv4? 0.0.0.255, 255.0.255.0, 255.252.0.0, /24
- R: ◦ 255.252.0.0,  /24
##### 4. Which commands can you use to verify your default route?
- R: route, netstat -r, or ip route
##### 5. How would add a second IP address to an interface?
- R:   ip addr add 172.16.15.16/16 dev enp0s9 label enp0s9:sub1
# Explorational Exercises
##### 1. Which subcommand of ip can be used to configure vlan tagging?
- R:  ip link add link enp0s9 name enp0s9.20 type vlan id 20
##### 2. How would you configure a default route?
- R: route add default gw 192.168.1.1 or ip route add default via 192.168.1.1
##### 3. How would you get detailed information about the ip neighbour command? What happens if you run it by itself?
- R:   ip neighbour
##### 4. How would you backup your routing table? How would you restore from it?
- R:  ip route save > /root/routes/route_backup; ip route restore < /root/routes/route_backup
##### 5. Which ip subcommand can be used to configure spanning tree options?
- R:  ip link add link enp0s9 name enp0s9.50 type bridge priority 50

# Lesson2
# Guided Exercises
##### 1. What command(s) would you use to send an ICMP echo to learning.lpi.org?
- R: ping learning.lpi.org
##### 2. How could you determine the route to 8.8.8.8?
- R:  traceroute 8.8.8.8
##### 3. What command would show you if any processes are listening on TCP port 80?
- R:   ss -ln | grep ":80" or  lsof -Pi:80
##### 4. How could you find which process is listening on a port?
- R: ss -lnp | grep ":22"
##### 5. How could you determine the max MTU of a network path?
- R:   tracepath somehost.example.com
# Explorational Exercises
##### 1. How could you use netcat to send an HTTP request to a web server?
- R:  nc learning.lpi.org 80
##### 2. What are a few reasons pinging a host can fail?
- R:  
 The remote host is down.
 A router ACL is blocking your ping.
 The remote host’s firewall is blocking your ping.
 You may be using an incorrect host name or address.
 Your name resolution is returning an incorrect address.
 Your machine’s network configuration is incorrect.
 Your machine’s firewall is blocking it.
 The remote host’s network configuration is incorrect.
 Your machine’s interface(s) are disconnected.
 The remote machine’s interface(s) are disconnected.
 A network component such as a switch, cable, or router between your machine and the
remote’s is no longer functioning.
##### 3. Name a tool you could use to see network packets reaching or leaving a Linux host?
- R:  tcpdump and wireshark 
##### 4. How can you force traceroute to use a different interface?
- R:  traceroute -i eth2 learning.lpi.org
##### 5. Is it possible for traceroute to report MTUs?
- R:  traceroute -I --mtu learning.lpi.org
- - - 
## ***Sources:***