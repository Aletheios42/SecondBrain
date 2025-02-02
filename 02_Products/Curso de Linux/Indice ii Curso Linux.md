
# 3. System Administration
3.1. Boot Process

BIOS/UEFI, GRUB, init, systemd

Configuration files:

/etc/default/grub (GRUB configuration)

/etc/fstab (file system table)

/etc/systemd/system (systemd services)

3.2. Service Management

systemd: systemctl, journalctl

Legacy init systems: /etc/init.d/, /etc/inittab

3.3. Package Management

RPM-based: rpm, yum, dnf

Configuration: /etc/yum.conf, /etc/yum.repos.d/

DEB-based: dpkg, apt, apt-get

Configuration: /etc/apt/sources.list, /etc/apt/apt.conf

3.4. Kernel Management

Kernel modules: lsmod, insmod, rmmod, modprobe

Configuration: /etc/modprobe.d/, /boot/

3.5. File System Management

File system types: ext4, XFS, Btrfs

Tools: mkfs, fsck, tune2fs, xfs_admin

Mounting: mount, umount, /etc/fstab

3.6. Storage Management

LVM: pvcreate, vgcreate, lvcreate

RAID: mdadm

Network Storage: NFS, Samba, iSCSI

3.7. Backup and Recovery

Tools: tar, rsync, dd, dump/restore

Configuration: /etc/rsyncd.conf, cron jobs for backups

3.8. Logging and Monitoring

Logging: syslog, rsyslog, journalctl

Configuration: /etc/rsyslog.conf, /etc/logrotate.conf

Monitoring: top, htop, nmon, sar

3.9. Processes and Jobs

Process management: ps, top, kill, pkill, pgrep

Background/foreground jobs: bg, fg, jobs

Process scheduling: nice, renice

1. Security
4.1. User and Group Management

Configuration Files:

/etc/passwd, /etc/shadow, /etc/group, /etc/sudoers

getent: Retrieve entries from system databases (getent passwd, getent group)

4.2. Permissions and Ownership

chmod, chown, chgrp

Special permissions (SUID, SGID, Sticky Bit)

ACLs (Access Control Lists)

4.3. File System Security

Tools: chattr, lsattr, setfacl, getfacl

Encryption: LUKS (cryptsetup), GPG

4.4. Network Security

SSH hardening: /etc/ssh/sshd_config

Firewalls: iptables, firewalld

Intrusion detection: fail2ban (/etc/fail2ban/)

4.5. Security Auditing

Tools: auditd (/etc/audit/auditd.conf), lynis, rkhunter

4.6. Encryption Tools

Compression and encryption: xz, gzip, bzip2, zip, openssl

1. Networking
#### 📡 Redes y conectividad
ip  → Herramienta compleja para redes
	-a, -r
ping → Prueba conectividad con una dirección
	-c
traceroute → Rastrea la ruta hasta un host
netstat -tulnp → Lista conexiones de red
ss -tulnp → Alternativa moderna a netstat
curl → Descarga archivos o datos desde la web
wget → Descarga archivos desde la web
scp → Copia archivos vía SSH
rsync → Sincroniza archivos de forma eficiente
nmap → Escanea puertos abiertos
whois → Muestra información de dominios
dig → Consulta registros DNS
nslookup → Consulta registros DNS

5.1. Network Configuration

Tools: ifconfig, ip, nmcli, nmtui

Configuration files:

/etc/network/interfaces (Debian-based)

/etc/sysconfig/network-scripts/ifcfg-* (RHEL-based)

5.2. Network Services

DNS: BIND (named.conf, /etc/resolv.conf)

DHCP: isc-dhcp-server (/etc/dhcp/dhcpd.conf)

NTP: chrony (/etc/chrony.conf), ntpd (/etc/ntp.conf)

5.3. Remote Access

SSH: sshd (/etc/ssh/sshd_config)

FTP: vsftpd (/etc/vsftpd.conf)

VPN: OpenVPN (/etc/openvpn/), WireGuard (/etc/wireguard/)

5.4. Firewall and Security

iptables: /etc/sysconfig/iptables

firewalld: /etc/firewalld/

SELinux: /etc/selinux/config

5.5. Troubleshooting

Tools: ping, traceroute, netstat, ss, tcpdump

Configuration: /etc/hosts, /etc/nsswitch.conf

2. Advanced Topics
6.1. Virtualization

KVM, QEMU, libvirt (/etc/libvirt/)

Containers: Docker (/etc/docker/), Podman

6.2. Cloud Integration

AWS, Azure, Google Cloud

Infrastructure as Code: Terraform, Ansible (/etc/ansible/)

6.3. Automation and Configuration Management

Ansible, Puppet (/etc/puppet/), Chef, SaltStack

6.4. High Availability and Load Balancing

HAProxy (/etc/haproxy/), Keepalived (/etc/keepalived/)

Clustering: Pacemaker, Corosync

3. Resources and References
7.1. Books

"Linux Command Line and Shell Scripting Bible"

"Linux Administration Handbook"