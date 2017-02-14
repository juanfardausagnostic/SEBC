```
[root@ip-172-31-15-226 111-hdfs-NAMENODE]# hdfs fsck /lawankorn/SEBC/source -files -blocks
Connecting to namenode via http://ip-172-31-15-226.ap-southeast-1.compute.internal:50070
FSCK started by root (auth:SIMPLE) from /172.31.15.226 for path /lawankorn/SEBC/source at Tue Feb 14 00:51:44 EST 2017
/lawankorn/SEBC/source <dir>
/lawankorn/SEBC/source/_SUCCESS 0 bytes, 0 block(s):  OK

/lawankorn/SEBC/source/part-m-00000 524288000 bytes, 4 block(s):  OK
0. BP-687752312-172.31.15.226-1487040358228:blk_1073742676_1852 len=134217728 Live_repl=3
1. BP-687752312-172.31.15.226-1487040358228:blk_1073742677_1853 len=134217728 Live_repl=3
2. BP-687752312-172.31.15.226-1487040358228:blk_1073742678_1854 len=134217728 Live_repl=3
3. BP-687752312-172.31.15.226-1487040358228:blk_1073742679_1855 len=121634816 Live_repl=3

Status: HEALTHY
 Total size:    524288000 B
 Total dirs:    1
 Total files:   2
 Total symlinks:                0
 Total blocks (validated):      4 (avg. block size 131072000 B)
 Minimally replicated blocks:   4 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Tue Feb 14 00:51:44 EST 2017 in 2 milliseconds


The filesystem under path '/lawankorn/SEBC/source' is HEALTHY
[root@ip-172-31-15-226 111-hdfs-NAMENODE]#
```

```
[root@ip-172-31-15-226 111-hdfs-NAMENODE]# hdfs fsck /Walker/SEBC/target -files -blocks
Connecting to namenode via http://ip-172-31-15-226.ap-southeast-1.compute.internal:50070
FSCK started by root (auth:SIMPLE) from /172.31.15.226 for path /Walker/SEBC/target at Tue Feb 14 00:52:27 EST 2017
/Walker/SEBC/target <dir>
/Walker/SEBC/target/source <dir>
/Walker/SEBC/target/source/_SUCCESS 0 bytes, 0 block(s):  OK

/Walker/SEBC/target/source/part-m-00000 262144000 bytes, 2 block(s):  OK
0. BP-687752312-172.31.15.226-1487040358228:blk_1073742716_1892 len=134217728 Live_repl=3
1. BP-687752312-172.31.15.226-1487040358228:blk_1073742717_1893 len=127926272 Live_repl=3

/Walker/SEBC/target/source/part-m-00001 262144000 bytes, 2 block(s):  OK
0. BP-687752312-172.31.15.226-1487040358228:blk_1073742718_1894 len=134217728 Live_repl=3
1. BP-687752312-172.31.15.226-1487040358228:blk_1073742719_1895 len=127926272 Live_repl=3

Status: HEALTHY
 Total size:    524288000 B
 Total dirs:    2
 Total files:   3
 Total symlinks:                0
 Total blocks (validated):      4 (avg. block size 131072000 B)
 Minimally replicated blocks:   4 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Tue Feb 14 00:52:27 EST 2017 in 1 milliseconds


The filesystem under path '/Walker/SEBC/target' is HEALTHY
[root@ip-172-31-15-226 111-hdfs-NAMENODE]#
```
