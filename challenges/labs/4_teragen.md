## The full teragen command
```
time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen \
 -Ddfs.block.size=33554432 \
 -Dmapred.map.tasks=6 \
 51200000 \
 tgen512m
```
## The output of the time command
```
real    1m11.444s
user    0m4.357s
sys     0m0.313s
```
## The command and output of hdfs dfs -ls /user/raffles/tgen512m
```
[raffles@ip-172-31-7-226 ~]$ hdfs dfs -ls /user/raffles/tgen512m
Found 7 items
-rw-r--r--   3 raffles supergroup          0 2017-02-17 15:28 /user/raffles/tgen512m/_SUCCESS
-rw-r--r--   3 raffles supergroup  853333400 2017-02-17 15:27 /user/raffles/tgen512m/part-m-00000
-rw-r--r--   3 raffles supergroup  853333300 2017-02-17 15:27 /user/raffles/tgen512m/part-m-00001
-rw-r--r--   3 raffles supergroup  853333300 2017-02-17 15:28 /user/raffles/tgen512m/part-m-00002
-rw-r--r--   3 raffles supergroup  853333400 2017-02-17 15:28 /user/raffles/tgen512m/part-m-00003
-rw-r--r--   3 raffles supergroup  853333300 2017-02-17 15:28 /user/raffles/tgen512m/part-m-00004
-rw-r--r--   3 raffles supergroup  853333300 2017-02-17 15:28 /user/raffles/tgen512m/part-m-00005
[raffles@ip-172-31-7-226 ~]$
```