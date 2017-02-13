
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
List forward and reverse host lookups using getent or nslookup
```
[root@ip-172-31-4-207 ~]# getent hosts 172.31.4.207
172.31.4.207    ip-172-31-4-207.ap-southeast-1.compute.internal
[root@ip-172-31-4-207 ~]#
```
Show nscd service is running
```
** Check RHEL Repo and YUM service available
[root@ip-172-31-4-207 ~]# head /etc/yum.repos.d/redhat-rhui.repo
# The amazon ec2 region is now dynamically set via yum.  REGION can be replaced by the amazon ec2 region for debugging
[rhui-REGION-rhel-server-releases]
name=Red Hat Enterprise Linux Server 7 (RPMs)
mirrorlist=https://rhui2-cds01.REGION.aws.ce.redhat.com/pulp/mirror/content/dist/rhel/rhui/server/7/$releasever/$basearch/os
enabled=1
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-redhat-release
sslverify=1
sslclientkey=/etc/pki/rhui/content-rhel7.key
sslclientcert=/etc/pki/rhui/product/content-rhel7.crt
[root@ip-172-31-4-207 ~]#

[root@ip-172-31-4-207 ~]# yum list nscd
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
Available Packages
nscd.x86_64                                    2.17-157.el7_3.1                                    rhui-REGION-rhel-server-releases
[root@ip-172-31-4-207 ~]#
```
```
** Install nscd package
[root@ip-172-31-4-207 ~]# yum install nscd
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
Resolving Dependencies
--> Running transaction check
---> Package nscd.x86_64 0:2.17-157.el7_3.1 will be installed
--> Processing Dependency: glibc = 2.17-157.el7_3.1 for package: nscd-2.17-157.el7_3.1.x86_64
--> Running transaction check
---> Package glibc.x86_64 0:2.17-157.el7 will be updated
--> Processing Dependency: glibc = 2.17-157.el7 for package: glibc-common-2.17-157.el7.x86_64
---> Package glibc.x86_64 0:2.17-157.el7_3.1 will be an update
--> Running transaction check
---> Package glibc-common.x86_64 0:2.17-157.el7 will be updated
---> Package glibc-common.x86_64 0:2.17-157.el7_3.1 will be an update
--> Finished Dependency Resolution

Dependencies Resolved

===================================================================================================================================
 Package                   Arch                Version                         Repository                                     Size
===================================================================================================================================
Installing:
 nscd                      x86_64              2.17-157.el7_3.1                rhui-REGION-rhel-server-releases              267 k
Updating for dependencies:
 glibc                     x86_64              2.17-157.el7_3.1                rhui-REGION-rhel-server-releases              3.6 M
 glibc-common              x86_64              2.17-157.el7_3.1                rhui-REGION-rhel-server-releases               11 M

Transaction Summary
===================================================================================================================================
Install  1 Package
Upgrade             ( 2 Dependent packages)

Total download size: 15 M
Is this ok [y/d/N]: y
Downloading packages:
Delta RPMs disabled because /usr/bin/applydeltarpm not installed.
(1/3): glibc-2.17-157.el7_3.1.x86_64.rpm                                                                    | 3.6 MB  00:00:00
(2/3): nscd-2.17-157.el7_3.1.x86_64.rpm                                                                     | 267 kB  00:00:00
(3/3): glibc-common-2.17-157.el7_3.1.x86_64.rpm                                                             |  11 MB  00:00:00
-----------------------------------------------------------------------------------------------------------------------------------
Total                                                                                               15 MB/s |  15 MB  00:00:01
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Updating   : glibc-common-2.17-157.el7_3.1.x86_64                                                                            1/5
  Updating   : glibc-2.17-157.el7_3.1.x86_64                                                                                   2/5
warning: /etc/nsswitch.conf created as /etc/nsswitch.conf.rpmnew
  Installing : nscd-2.17-157.el7_3.1.x86_64                                                                                    3/5
  Cleanup    : glibc-common-2.17-157.el7.x86_64                                                                                4/5
  Cleanup    : glibc-2.17-157.el7.x86_64                                                                                       5/5
  Verifying  : glibc-2.17-157.el7_3.1.x86_64                                                                                   1/5
  Verifying  : nscd-2.17-157.el7_3.1.x86_64                                                                                    2/5
  Verifying  : glibc-common-2.17-157.el7_3.1.x86_64                                                                            3/5
  Verifying  : glibc-common-2.17-157.el7.x86_64                                                                                4/5
  Verifying  : glibc-2.17-157.el7.x86_64                                                                                       5/5

Installed:
  nscd.x86_64 0:2.17-157.el7_3.1

Dependency Updated:
  glibc.x86_64 0:2.17-157.el7_3.1                              glibc-common.x86_64 0:2.17-157.el7_3.1

Complete!
[root@ip-172-31-4-207 ~]#
[root@ip-172-31-4-207 ~]# service nscd status
Redirecting to /bin/systemctl status  nscd.service
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; disabled; vendor preset: disabled)
   Active: inactive (dead)
[root@ip-172-31-4-207 ~]#
```
```
** Start nscd service
[root@ip-172-31-4-207 ~]# service nscd start
Redirecting to /bin/systemctl start  nscd.service
[root@ip-172-31-4-207 ~]#
[root@ip-172-31-4-207 ~]# service nscd status
Redirecting to /bin/systemctl status  nscd.service
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; disabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-02-13 04:01:49 EST; 9s ago
  Process: 3259 ExecStart=/usr/sbin/nscd $NSCD_OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 3260 (nscd)
   CGroup: /system.slice/nscd.service
           └─3260 /usr/sbin/nscd

Feb 13 04:01:49 ip-172-31-4-207.ap-southeast-1.compute.internal nscd[3260]: 3260 monitoring file `/etc/hosts` (4)
Feb 13 04:01:49 ip-172-31-4-207.ap-southeast-1.compute.internal nscd[3260]: 3260 monitoring directory `/etc` (2)
Feb 13 04:01:49 ip-172-31-4-207.ap-southeast-1.compute.internal nscd[3260]: 3260 monitoring file `/etc/resolv.conf` (5)
Feb 13 04:01:49 ip-172-31-4-207.ap-southeast-1.compute.internal nscd[3260]: 3260 monitoring directory `/etc` (2)
Feb 13 04:01:49 ip-172-31-4-207.ap-southeast-1.compute.internal nscd[3260]: 3260 monitoring file `/etc/services` (6)
Feb 13 04:01:49 ip-172-31-4-207.ap-southeast-1.compute.internal nscd[3260]: 3260 monitoring directory `/etc` (2)
Feb 13 04:01:49 ip-172-31-4-207.ap-southeast-1.compute.internal nscd[3260]: 3260 disabled inotify-based monitoring for file `...ory
Feb 13 04:01:49 ip-172-31-4-207.ap-southeast-1.compute.internal nscd[3260]: 3260 stat failed for file `/etc/netgroup'; will t...ory
Feb 13 04:01:49 ip-172-31-4-207.ap-southeast-1.compute.internal nscd[3260]: 3260 Access Vector Cache (AVC) started
Feb 13 04:01:49 ip-172-31-4-207.ap-southeast-1.compute.internal systemd[1]: Started Name Service Cache Daemon.
Hint: Some lines were ellipsized, use -l to show in full.
[root@ip-172-31-4-207 ~]#
```
Show the ntpd service is running
```
** Install ntpd package
[root@ip-172-31-4-207 ~]# yum list ntp
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
Available Packages
ntp.x86_64                                   4.2.6p5-25.el7_3.1                                    rhui-REGION-rhel-server-releases
[root@ip-172-31-4-207 ~]#

[root@ip-172-31-4-207 ~]# yum install ntp
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
Resolving Dependencies
--> Running transaction check
---> Package ntp.x86_64 0:4.2.6p5-25.el7_3.1 will be installed
--> Processing Dependency: ntpdate = 4.2.6p5-25.el7_3.1 for package: ntp-4.2.6p5-25.el7_3.1.x86_64
--> Processing Dependency: libopts.so.25()(64bit) for package: ntp-4.2.6p5-25.el7_3.1.x86_64
--> Running transaction check
---> Package autogen-libopts.x86_64 0:5.18-5.el7 will be installed
---> Package ntpdate.x86_64 0:4.2.6p5-25.el7_3.1 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

===================================================================================================================================
 Package                     Arch               Version                         Repository                                    Size
===================================================================================================================================
Installing:
 ntp                         x86_64             4.2.6p5-25.el7_3.1              rhui-REGION-rhel-server-releases             547 k
Installing for dependencies:
 autogen-libopts             x86_64             5.18-5.el7                      rhui-REGION-rhel-server-releases              66 k
 ntpdate                     x86_64             4.2.6p5-25.el7_3.1              rhui-REGION-rhel-server-releases              85 k

Transaction Summary
===================================================================================================================================
Install  1 Package (+2 Dependent packages)

Total download size: 699 k
Installed size: 1.6 M
Is this ok [y/d/N]: y
Downloading packages:
(1/3): autogen-libopts-5.18-5.el7.x86_64.rpm                                                                |  66 kB  00:00:00
(2/3): ntp-4.2.6p5-25.el7_3.1.x86_64.rpm                                                                    | 547 kB  00:00:00
(3/3): ntpdate-4.2.6p5-25.el7_3.1.x86_64.rpm                                                                |  85 kB  00:00:00
-----------------------------------------------------------------------------------------------------------------------------------
Total                                                                                              793 kB/s | 699 kB  00:00:00
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Installing : autogen-libopts-5.18-5.el7.x86_64                                                                               1/3
  Installing : ntpdate-4.2.6p5-25.el7_3.1.x86_64                                                                               2/3
  Installing : ntp-4.2.6p5-25.el7_3.1.x86_64                                                                                   3/3
  Verifying  : ntpdate-4.2.6p5-25.el7_3.1.x86_64                                                                               1/3
  Verifying  : ntp-4.2.6p5-25.el7_3.1.x86_64                                                                                   2/3
  Verifying  : autogen-libopts-5.18-5.el7.x86_64                                                                               3/3

Installed:
  ntp.x86_64 0:4.2.6p5-25.el7_3.1

Dependency Installed:
  autogen-libopts.x86_64 0:5.18-5.el7                              ntpdate.x86_64 0:4.2.6p5-25.el7_3.1

Complete!
[root@ip-172-31-4-207 ~]#
[root@ip-172-31-4-207 ~]# service ntpd status
Redirecting to /bin/systemctl status  ntpd.service
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; disabled; vendor preset: disabled)
   Active: inactive (dead)
[root@ip-172-31-4-207 ~]#
```
```
** Start ntpd service
[root@ip-172-31-4-207 ~]# service ntpd start
Redirecting to /bin/systemctl start  ntpd.service
[root@ip-172-31-4-207 ~]#
[root@ip-172-31-4-207 ~]# service ntpd status
Redirecting to /bin/systemctl status  ntpd.service
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; disabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-02-13 04:08:40 EST; 2s ago
  Process: 3409 ExecStart=/usr/sbin/ntpd -u ntp:ntp $OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 3410 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─3410 /usr/sbin/ntpd -u ntp:ntp -g

Feb 13 04:08:40 ip-172-31-4-207.ap-southeast-1.compute.internal ntpd[3410]: Listen and drop on 1 v6wildcard :: UDP 123
Feb 13 04:08:40 ip-172-31-4-207.ap-southeast-1.compute.internal ntpd[3410]: Listen normally on 2 lo 127.0.0.1 UDP 123
Feb 13 04:08:40 ip-172-31-4-207.ap-southeast-1.compute.internal ntpd[3410]: Listen normally on 3 eth0 172.31.4.207 UDP 123
Feb 13 04:08:40 ip-172-31-4-207.ap-southeast-1.compute.internal ntpd[3410]: Listen normally on 4 eth0 fe80::12:d4ff:fecb:401b...123
Feb 13 04:08:40 ip-172-31-4-207.ap-southeast-1.compute.internal ntpd[3410]: Listen normally on 5 lo ::1 UDP 123
Feb 13 04:08:40 ip-172-31-4-207.ap-southeast-1.compute.internal ntpd[3410]: Listening on routing socket on fd #22 for interfa...tes
Feb 13 04:08:40 ip-172-31-4-207.ap-southeast-1.compute.internal systemd[1]: Started Network Time Service.
Feb 13 04:08:41 ip-172-31-4-207.ap-southeast-1.compute.internal ntpd[3410]: 0.0.0.0 c016 06 restart
Feb 13 04:08:41 ip-172-31-4-207.ap-southeast-1.compute.internal ntpd[3410]: 0.0.0.0 c012 02 freq_set kernel 0.000 PPM
Feb 13 04:08:41 ip-172-31-4-207.ap-southeast-1.compute.internal ntpd[3410]: 0.0.0.0 c011 01 freq_not_set
Hint: Some lines were ellipsized, use -l to show in full.
[root@ip-172-31-4-207 ~]#
```
