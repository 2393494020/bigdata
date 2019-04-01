# centos 6 settings
## selinux
/etc/selinux/config  
SELINUX=disabled
## firewall
chkconfig iptables off  
chkconfig ip6tables off
## ip

# clone virtual machine
edit /etc/udev/rules.d/70-persistent-net.rules  
1. delete line 1  
2. 'eth1' -> 'eth0'

# Pseudo-Distributed Operation
$ ssh-keygen -t rsa -P '' -f ~/.ssh/id_rsa  
$ cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys  
$ chmod 0600 ~/.ssh/authorized_keys
