**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Lesson 1
# Guided Exercises
##### 1. What commands can be used to list the network adapters present in the system?
- R: ip link show, nmcli device
##### 2. What is the type of network adapter whose interface name is wlo1?
- R: wireless LAN adapter
##### 3. What role does the file /etc/network/interfaces play during boot time?
- R: It has the configurations used by command ifup to activate the corresponding interfaces during boot time.
##### 4. What entry in /etc/network/interfaces configures interface eno1 to obtain its IP settings with DHCP?
- R:  iface eno1 inet dhcp.
# Explorational Exercises
##### 1. How could the hostnamectl command be used to change only the static hostname of the local machine to firewall?
- R:  hostnamectl --static set-hostname firewall
##### 2. What details other than hostnames can be modified by command hostnamectl?
- R: hostnamectl can also set the default icon for the local machine, its chassis type, the location and the deployment environment.
##### 3. What entry in /etc/hosts associates both names firewall and router with IP 10.8.0.1?
- R: 10.8.0.1 firewall router.
##### 4. How could the /etc/resolv.conf file be modified in order to send all DNS requests to 1.1.1.1?
- R:  nameserver 1.1.1.1 

# Lesson 2

# Guided Exercises
##### 1. What is the meaning of the word Portal in the CONNECTIVITY column in the output of command nmcli general status?
- R: extra authetifications steps
##### 2. In a console terminal, how can an ordinary user use the command nmcli to connect to the MyWifi wireless network protected by the password MyPassword?
- R:  nmcli device wifi connect MyWifi password MyPassword
##### 3. What command can turn the wireless adapter on if it was previously disabled by the operating system?
- R: nmcli radio wifi on
##### 4. Custom configuration files should be placed in what directory when systemd-networkd is managing the network interfaces?
- R:  /etc/systemd/network.
# Explorational Exercises
##### 1. How can a user run the command nmcli to delete an unused connection named Hotel Internet?
- R:   nmcli connection delete "Hotel Internet"
##### 2. NetworkManager scans wi-fi networks periodically and command nmcli device wifi list only lists the access points found in the last scan. How should the nmcli command be used to ask NetworkManager to immediately re-scan all available access points?
- R:   nmcli device wifi rescan 
##### 3. What name entry should be used in the \[Match] section of a systemd-networkd configuration file to match all ethernet interfaces?
- R:  name=en*
##### 4. How should the wpa_passphrase command be executed to use the passphrase given as an argument and not from the standard input?
- R:   wpa_passphrase MyWifi MyPassword.
- - - 
## ***Sources:***