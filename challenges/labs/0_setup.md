## Cloud Provider
```
My cloud provider is "AWS"
```
## OS version
```
[root@ip-172-31-12-111 ~]# cat /etc/redhat-release
Red Hat Enterprise Linux Server release 7.3 (Maipo)
[root@ip-172-31-12-111 ~]#
```
## Show space available on each node is at least 30 GB
```
[root@ip-172-31-12-111 ~]# ssh node1 df -h |grep "/dev/xvda2"
/dev/xvda2      100G  1.3G   99G   2% /
[root@ip-172-31-12-111 ~]# ssh node2 df -h |grep "/dev/xvda2"
/dev/xvda2      100G  1.3G   99G   2% /
[root@ip-172-31-12-111 ~]# ssh node3 df -h |grep "/dev/xvda2"
/dev/xvda2      100G  1.3G   99G   2% /
[root@ip-172-31-12-111 ~]# ssh node4 df -h |grep "/dev/xvda2"
/dev/xvda2      100G  1.3G   99G   2% /
[root@ip-172-31-12-111 ~]# ssh node5 df -h |grep "/dev/xvda2"
/dev/xvda2      100G  1.3G   99G   2% /
[root@ip-172-31-12-111 ~]# 
```
## List the command and output for yum repolist enabled
```
[root@ip-172-31-12-111 ~]# yum repolist enabled
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
repo id                                                 repo name                                                             status
!rhui-REGION-client-config-server-7/x86_64              Red Hat Update Infrastructure 2.0 Client Configuration Server 7            6
!rhui-REGION-rhel-server-releases/7Server/x86_64        Red Hat Enterprise Linux Server 7 (RPMs)                              13,838
!rhui-REGION-rhel-server-rh-common/7Server/x86_64       Red Hat Enterprise Linux Server 7 RH Common (RPMs)                       209
repolist: 14,053
[root@ip-172-31-12-111 ~]#
```
## List the /etc/passwd entries for raffles and fullerton
```
[root@ip-172-31-12-111 ~]# cat /etc/passwd |grep -E "raffles|fullerton"
raffles:x:2000:1003::/home/raffles:/bin/bash
fullerton:x:3000:1004::/home/fullerton:/bin/bash
[root@ip-172-31-12-111 ~]# 
```
## List the /etc/group entries for hotels and shops
```
[root@ip-172-31-12-111 ~]# cat /etc/group |grep -E "shops|hotels"
shops:x:1003:
hotels:x:1004:
[root@ip-172-31-12-111 ~]# 
```
