## The hostname of your MySQL node
```
[root@ip-172-31-7-226 software]# hostname
ip-172-31-7-226.ap-southeast-1.compute.internal
[root@ip-172-31-7-226 software]#
```
## The command and output for mysql --version
```
[root@ip-172-31-7-226 mysql]# mysql --version
mysql  Ver 15.1 Distrib 5.5.54-MariaDB, for Linux (x86_64) using readline 5.1
[root@ip-172-31-7-226 mysql]#
```
## The command and output for listing MySQL databases
```
[root@ip-172-31-7-226 mysql]# mysql -uroot -ppassword -e 'show databases;'
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hive               |
| hue                |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| sentry             |
+--------------------+
[root@ip-172-31-7-226 mysql]# 
```