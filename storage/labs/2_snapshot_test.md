Load Zip file into HDFS
```
[root@ip-172-31-15-226 ~]# sudo -u hdfs hadoop fs -put /tmp/SEBC.zip /precious/
[root@ip-172-31-15-226 ~]# sudo -u hdfs hadoop fs -ls /precious/
Found 1 items
-rw-r--r--   3 hdfs supergroup     414615 2017-02-14 03:51 /precious/SEBC.zip
[root@ip-172-31-15-226 ~]#
```
Enable snapshots
```
[root@ip-172-31-15-226 ~]# sudo -u hdfs hdfs dfsadmin -allowSnapshot /precious
Allowing snaphot on /precious succeeded
[root@ip-172-31-15-226 ~]#
```
Create a snapshot called sebc-hdfs-test
```
[root@ip-172-31-15-226 ~]# sudo -u hdfs hdfs dfs -createSnapshot /precious sebc-hdfs-test
Created snapshot /precious/.snapshot/sebc-hdfs-test
[root@ip-172-31-15-226 ~]#
[root@ip-172-31-15-226 ~]# sudo -u hdfs hdfs dfs -ls /precious/.snapshot/sebc-hdfs-test
Found 1 items
-rw-r--r--   3 hdfs supergroup     414615 2017-02-14 03:51 /precious/.snapshot/sebc-hdfs-test/SEBC.zip
[root@ip-172-31-15-226 ~]#
```
Delete the directory
```
[root@ip-172-31-15-226 ~]# sudo -u hdfs hdfs dfs -rm -r /precious
rm: Failed to move to trash: hdfs://ip-172-31-15-226.ap-southeast-1.compute.internal:8020/precious: The directory /precious cannot be deleted since /precious is snapshottable and already has snapshots
[root@ip-172-31-15-226 ~]#
```
Delete the ZIP file
```
[root@ip-172-31-15-226 ~]# sudo -u hdfs hdfs dfs -rm -f /precious/SEBC.zip
17/02/14 04:00:58 INFO fs.TrashPolicyDefault: Moved: 'hdfs://ip-172-31-15-226.ap-southeast-1.compute.internal:8020/precious/SEBC.zip' to trash at: hdfs://ip-172-31-15-226.ap-southeast-1.compute.internal:8020/user/hdfs/.Trash/Current/precious/SEBC.zip
[root@ip-172-31-15-226 ~]#
[root@ip-172-31-15-226 ~]# sudo -u hdfs hdfs dfs -ls /precious
[root@ip-172-31-15-226 ~]#
```
Restore the deleted file
```
[root@ip-172-31-15-226 ~]# sudo -u hdfs hdfs dfs -cp /precious/.snapshot/sebc-hdfs-test/SEBC.zip /precious
[root@ip-172-31-15-226 ~]#
[root@ip-172-31-15-226 ~]# sudo -u hdfs hdfs dfs -ls /precious
Found 1 items
-rw-r--r--   3 hdfs supergroup     414615 2017-02-14 04:02 /precious/SEBC.zip
[root@ip-172-31-15-226 ~]#
```
