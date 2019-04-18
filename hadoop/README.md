# building
1. sudo apt install[yum -y] install g++ autoconf automake libtool cmake zlib1g-dev pkg-config libssl-dev
2. https://github.com/protocolbuffers/protobuf/releases/download/v2.5.0/protobuf-2.5.0.tar.gz
3. cd /opt/cpp/protobuf > ./configure --prefix=/opt/cpp/protobuf > make > make install
4. mvn clean package -Pdist,native -DskipTests -Dtar

# centos 6 settings
## selinux
/etc/selinux/config  
SELINUX=disabled
## firewall
chkconfig iptables off  
chkconfig ip6tables off
## ip
ONBOOT=yes  
BOOTPROTO=static  
IPADDR=192.168.0.106  
NETMASK=255.255.255.0  
GATEWAY=192.168.0.1  
DNS1=8.8.8.8  
NETWORKING_IPV6=no  
# clone virtual machine
edit /etc/udev/rules.d/70-persistent-net.rules  
1. delete line 1  
2. 'eth1' -> 'eth0'
3. update /etc/sysconfig/network-scripts/ifcfg-eth0 [HWADDR]

# Pseudo-Distributed Operation
$ ssh-keygen -t rsa -P '' -f ~/.ssh/id_rsa  
$ cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys  
$ chmod 0600 ~/.ssh/authorized_keys

# 运维命令
>直接删除，不入回收站  
>hadoop fs -rm -r -skipTrash