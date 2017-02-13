
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
