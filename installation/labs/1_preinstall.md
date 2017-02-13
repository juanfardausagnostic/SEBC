
Check vm.swappiness on all your nodes
```
[root@ip-172-31-4-207 ~]# cat /proc/sys/vm/swappiness
30
[root@ip-172-31-4-207 ~]#
[root@ip-172-31-4-207 ~]# sysctl vm.swappiness=1
vm.swappiness = 1
[root@ip-172-31-4-207 ~]#
[root@ip-172-31-4-207 ~]# cat /proc/sys/vm/swappiness
1
[root@ip-172-31-4-207 ~]#

** Setup permanent when machine startup
[root@ip-172-31-4-207 ~]# tail -2 /etc/sysctl.conf
####################
vm.swappiness=1
[root@ip-172-31-4-207 ~]#
```

Show mount attributed of all volumes
```
[root@ip-172-31-4-207 ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2      100G  984M  100G   1% /
devtmpfs        3.9G     0  3.9G   0% /dev
tmpfs           3.7G     0  3.7G   0% /dev/shm
tmpfs           3.7G   17M  3.7G   1% /run
tmpfs           3.7G     0  3.7G   0% /sys/fs/cgroup
tmpfs           757M     0  757M   0% /run/user/1000
tmpfs           757M     0  757M   0% /run/user/0
[root@ip-172-31-4-207 ~]#
```
Show the reserve space of any non-root, ext-based volumes
```
[root@ip-172-31-4-207 ~]# egrep "^/dev/*" /proc/mounts
/dev/xvda2 / xfs rw,seclabel,relatime,attr2,inode64,noquota 0 0
[root@ip-172-31-4-207 ~]#

** I'm configure only 1 volum to shared with all (root and non-root)
```
Disable transparent hugepages
```
[root@ip-172-31-4-207 ~]# cat /sys/kernel/mm/transparent_hugepage/enabled
[always] madvise never
[root@ip-172-31-4-207 ~]# cat /sys/kernel/mm/transparent_hugepage/defrag
[always] madvise never
[root@ip-172-31-4-207 ~]#
[root@ip-172-31-4-207 ~]# echo never > /sys/kernel/mm/transparent_hugepage/enabled
[root@ip-172-31-4-207 ~]# echo never > /sys/kernel/mm/transparent_hugepage/defrag
[root@ip-172-31-4-207 ~]#
[root@ip-172-31-4-207 ~]# cat /sys/kernel/mm/transparent_hugepage/enabled
always madvise [never]
[root@ip-172-31-4-207 ~]# cat /sys/kernel/mm/transparent_hugepage/defrag
always madvise [never]
[root@ip-172-31-4-207 ~]#

** Setup permanent when machine startup
[root@ip-172-31-4-207 ~]# tail -2 /etc/rc.local
echo never > /sys/kernel/mm/transparent_hugepage/enabled
echo never > /sys/kernel/mm/transparent_hugepage/defrag
[root@ip-172-31-4-207 ~]#
```
List the network interface configuration
```
[root@ip-172-31-4-207 ~]# ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.31.4.207  netmask 255.255.240.0  broadcast 172.31.15.255
        inet6 fe80::12:d4ff:fecb:401b  prefixlen 64  scopeid 0x20<link>
        ether 02:12:d4:cb:40:1b  txqueuelen 1000  (Ethernet)
        RX packets 3648  bytes 320205 (312.7 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 3403  bytes 534153 (521.6 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1  (Local Loopback)
        RX packets 68  bytes 6420 (6.2 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 68  bytes 6420 (6.2 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

[root@ip-172-31-4-207 ~]#
[root@ip-172-31-4-207 ~]#
[root@ip-172-31-4-207 ~]# cat /etc/sysconfig/network-scripts/ifcfg-eth* | egrep "^DEVICE|BOOTPROTO|ONBOOT|NETMASK|NETWORK|IPADDR|PEERDNS"
DEVICE="eth0"
BOOTPROTO="dhcp"
ONBOOT="yes"
PEERDNS="yes"
[root@ip-172-31-4-207 ~]#
```
