Create a 10 GB file using teragen
```
[lawankorn@ip-172-31-15-226 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen \
> -Ddfs.block.size=33554432 \
> -Dmapred.map.tasks=4 \
> 107374183 \
> terageninput
17/02/14 03:28:11 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-3-223.ap-southeast-1.compute.internal/172.31.3.223:8032
17/02/14 03:28:11 INFO terasort.TeraSort: Generating 107374183 using 4
17/02/14 03:28:11 INFO mapreduce.JobSubmitter: number of splits:4
17/02/14 03:28:11 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/02/14 03:28:11 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/02/14 03:28:12 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1487044813809_0003
17/02/14 03:28:12 INFO impl.YarnClientImpl: Submitted application application_1487044813809_0003
17/02/14 03:28:12 INFO mapreduce.Job: The url to track the job: http://ip-172-31-3-223.ap-southeast-1.compute.internal:8088/proxy/application_1487044813809_0003/
17/02/14 03:28:12 INFO mapreduce.Job: Running job: job_1487044813809_0003
17/02/14 03:28:18 INFO mapreduce.Job: Job job_1487044813809_0003 running in uber mode : false
17/02/14 03:28:18 INFO mapreduce.Job:  map 0% reduce 0%
17/02/14 03:28:28 INFO mapreduce.Job:  map 2% reduce 0%
17/02/14 03:28:29 INFO mapreduce.Job:  map 6% reduce 0%
17/02/14 03:28:31 INFO mapreduce.Job:  map 7% reduce 0%
17/02/14 03:28:32 INFO mapreduce.Job:  map 9% reduce 0%
17/02/14 03:28:34 INFO mapreduce.Job:  map 11% reduce 0%
17/02/14 03:28:35 INFO mapreduce.Job:  map 13% reduce 0%
17/02/14 03:28:37 INFO mapreduce.Job:  map 15% reduce 0%
17/02/14 03:28:38 INFO mapreduce.Job:  map 17% reduce 0%
17/02/14 03:28:40 INFO mapreduce.Job:  map 18% reduce 0%
17/02/14 03:28:41 INFO mapreduce.Job:  map 20% reduce 0%
17/02/14 03:28:43 INFO mapreduce.Job:  map 22% reduce 0%
17/02/14 03:28:44 INFO mapreduce.Job:  map 24% reduce 0%
17/02/14 03:28:46 INFO mapreduce.Job:  map 25% reduce 0%
17/02/14 03:28:47 INFO mapreduce.Job:  map 28% reduce 0%
17/02/14 03:28:49 INFO mapreduce.Job:  map 29% reduce 0%
17/02/14 03:28:50 INFO mapreduce.Job:  map 32% reduce 0%
17/02/14 03:28:52 INFO mapreduce.Job:  map 34% reduce 0%
17/02/14 03:28:53 INFO mapreduce.Job:  map 35% reduce 0%
17/02/14 03:28:55 INFO mapreduce.Job:  map 37% reduce 0%
17/02/14 03:28:56 INFO mapreduce.Job:  map 39% reduce 0%
17/02/14 03:28:58 INFO mapreduce.Job:  map 41% reduce 0%
17/02/14 03:28:59 INFO mapreduce.Job:  map 43% reduce 0%
17/02/14 03:29:01 INFO mapreduce.Job:  map 45% reduce 0%
17/02/14 03:29:02 INFO mapreduce.Job:  map 46% reduce 0%
17/02/14 03:29:04 INFO mapreduce.Job:  map 49% reduce 0%
17/02/14 03:29:05 INFO mapreduce.Job:  map 50% reduce 0%
17/02/14 03:29:07 INFO mapreduce.Job:  map 52% reduce 0%
17/02/14 03:29:08 INFO mapreduce.Job:  map 53% reduce 0%
17/02/14 03:29:10 INFO mapreduce.Job:  map 55% reduce 0%
17/02/14 03:29:11 INFO mapreduce.Job:  map 56% reduce 0%
17/02/14 03:29:13 INFO mapreduce.Job:  map 59% reduce 0%
17/02/14 03:29:14 INFO mapreduce.Job:  map 60% reduce 0%
17/02/14 03:29:17 INFO mapreduce.Job:  map 62% reduce 0%
17/02/14 03:29:18 INFO mapreduce.Job:  map 64% reduce 0%
17/02/14 03:29:20 INFO mapreduce.Job:  map 66% reduce 0%
17/02/14 03:29:21 INFO mapreduce.Job:  map 67% reduce 0%
17/02/14 03:29:23 INFO mapreduce.Job:  map 70% reduce 0%
17/02/14 03:29:24 INFO mapreduce.Job:  map 71% reduce 0%
17/02/14 03:29:26 INFO mapreduce.Job:  map 74% reduce 0%
17/02/14 03:29:27 INFO mapreduce.Job:  map 75% reduce 0%
17/02/14 03:29:36 INFO mapreduce.Job:  map 80% reduce 0%
17/02/14 03:29:39 INFO mapreduce.Job:  map 83% reduce 0%
17/02/14 03:29:42 INFO mapreduce.Job:  map 86% reduce 0%
17/02/14 03:29:45 INFO mapreduce.Job:  map 89% reduce 0%
17/02/14 03:29:48 INFO mapreduce.Job:  map 92% reduce 0%
17/02/14 03:29:51 INFO mapreduce.Job:  map 95% reduce 0%
17/02/14 03:29:54 INFO mapreduce.Job:  map 98% reduce 0%
17/02/14 03:29:56 INFO mapreduce.Job:  map 100% reduce 0%
17/02/14 03:29:56 INFO mapreduce.Job: Job job_1487044813809_0003 completed successfully
17/02/14 03:29:56 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=488820
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=344
                HDFS: Number of bytes written=10737418300
                HDFS: Number of read operations=16
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=8
        Job Counters
                Launched map tasks=4
                Other local map tasks=4
                Total time spent by all maps in occupied slots (ms)=228030
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=228030
                Total vcore-seconds taken by all map tasks=228030
                Total megabyte-seconds taken by all map tasks=233502720
        Map-Reduce Framework
                Map input records=107374183
                Map output records=107374183
                Input split bytes=344
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=1323
                CPU time spent (ms)=132120
                Physical memory (bytes) snapshot=924499968
                Virtual memory (bytes) snapshot=6265413632
                Total committed heap usage (bytes)=605028352
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=230593860607047066
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=10737418300

real    1m47.471s
user    0m4.882s
sys     0m0.284s
[lawankorn@ip-172-31-15-226 ~]$

** Check Output file
[lawankorn@ip-172-31-15-226 ~]$ hadoop fs -ls terageninput
Found 5 items
-rw-r--r--   3 lawankorn supergroup          0 2017-02-14 03:29 terageninput/_SUCCESS
-rw-r--r--   3 lawankorn supergroup 2684354600 2017-02-14 03:29 terageninput/part-m-00000
-rw-r--r--   3 lawankorn supergroup 2684354600 2017-02-14 03:29 terageninput/part-m-00001
-rw-r--r--   3 lawankorn supergroup 2684354600 2017-02-14 03:29 terageninput/part-m-00002
-rw-r--r--   3 lawankorn supergroup 2684354500 2017-02-14 03:29 terageninput/part-m-00003
[lawankorn@ip-172-31-15-226 ~]$

** Check Block size
[lawankorn@ip-172-31-15-226 ~]$ hdfs fsck /user/lawankorn/terageninput/part-m-00001 -files -blocks                                    Connecting to namenode via http://ip-172-31-15-226.ap-southeast-1.compute.internal:50070
FSCK started by lawankorn (auth:SIMPLE) from /172.31.15.226 for path /user/lawankorn/terageninput/part-m-00001 at Tue Feb 14 03:33:57 EST 2017
/user/lawankorn/terageninput/part-m-00001 2684354600 bytes, 81 block(s):  OK
0. BP-687752312-172.31.15.226-1487040358228:blk_1073743346_2522 len=33554432 Live_repl=3
1. BP-687752312-172.31.15.226-1487040358228:blk_1073743349_2525 len=33554432 Live_repl=3
2. BP-687752312-172.31.15.226-1487040358228:blk_1073743352_2528 len=33554432 Live_repl=3
3. BP-687752312-172.31.15.226-1487040358228:blk_1073743357_2533 len=33554432 Live_repl=3
4. BP-687752312-172.31.15.226-1487040358228:blk_1073743358_2534 len=33554432 Live_repl=3
5. BP-687752312-172.31.15.226-1487040358228:blk_1073743359_2535 len=33554432 Live_repl=3
6. BP-687752312-172.31.15.226-1487040358228:blk_1073743362_2538 len=33554432 Live_repl=3
7. BP-687752312-172.31.15.226-1487040358228:blk_1073743366_2542 len=33554432 Live_repl=3
8. BP-687752312-172.31.15.226-1487040358228:blk_1073743370_2546 len=33554432 Live_repl=3
9. BP-687752312-172.31.15.226-1487040358228:blk_1073743373_2549 len=33554432 Live_repl=3
10. BP-687752312-172.31.15.226-1487040358228:blk_1073743376_2552 len=33554432 Live_repl=3
11. BP-687752312-172.31.15.226-1487040358228:blk_1073743379_2555 len=33554432 Live_repl=3
12. BP-687752312-172.31.15.226-1487040358228:blk_1073743382_2558 len=33554432 Live_repl=3
13. BP-687752312-172.31.15.226-1487040358228:blk_1073743385_2561 len=33554432 Live_repl=3
14. BP-687752312-172.31.15.226-1487040358228:blk_1073743388_2564 len=33554432 Live_repl=3
15. BP-687752312-172.31.15.226-1487040358228:blk_1073743391_2567 len=33554432 Live_repl=3
16. BP-687752312-172.31.15.226-1487040358228:blk_1073743394_2570 len=33554432 Live_repl=3
17. BP-687752312-172.31.15.226-1487040358228:blk_1073743397_2573 len=33554432 Live_repl=3
18. BP-687752312-172.31.15.226-1487040358228:blk_1073743400_2576 len=33554432 Live_repl=3
19. BP-687752312-172.31.15.226-1487040358228:blk_1073743403_2579 len=33554432 Live_repl=3
20. BP-687752312-172.31.15.226-1487040358228:blk_1073743406_2582 len=33554432 Live_repl=3
21. BP-687752312-172.31.15.226-1487040358228:blk_1073743409_2585 len=33554432 Live_repl=3
22. BP-687752312-172.31.15.226-1487040358228:blk_1073743412_2588 len=33554432 Live_repl=3
23. BP-687752312-172.31.15.226-1487040358228:blk_1073743415_2591 len=33554432 Live_repl=3
24. BP-687752312-172.31.15.226-1487040358228:blk_1073743418_2594 len=33554432 Live_repl=3
25. BP-687752312-172.31.15.226-1487040358228:blk_1073743421_2597 len=33554432 Live_repl=3
26. BP-687752312-172.31.15.226-1487040358228:blk_1073743424_2600 len=33554432 Live_repl=3
27. BP-687752312-172.31.15.226-1487040358228:blk_1073743428_2604 len=33554432 Live_repl=3
28. BP-687752312-172.31.15.226-1487040358228:blk_1073743431_2607 len=33554432 Live_repl=3
29. BP-687752312-172.31.15.226-1487040358228:blk_1073743434_2610 len=33554432 Live_repl=3
30. BP-687752312-172.31.15.226-1487040358228:blk_1073743437_2613 len=33554432 Live_repl=3
31. BP-687752312-172.31.15.226-1487040358228:blk_1073743440_2616 len=33554432 Live_repl=3
32. BP-687752312-172.31.15.226-1487040358228:blk_1073743443_2619 len=33554432 Live_repl=3
33. BP-687752312-172.31.15.226-1487040358228:blk_1073743446_2622 len=33554432 Live_repl=3
34. BP-687752312-172.31.15.226-1487040358228:blk_1073743449_2625 len=33554432 Live_repl=3
35. BP-687752312-172.31.15.226-1487040358228:blk_1073743452_2628 len=33554432 Live_repl=3
36. BP-687752312-172.31.15.226-1487040358228:blk_1073743454_2630 len=33554432 Live_repl=3
37. BP-687752312-172.31.15.226-1487040358228:blk_1073743458_2634 len=33554432 Live_repl=3
38. BP-687752312-172.31.15.226-1487040358228:blk_1073743461_2637 len=33554432 Live_repl=3
39. BP-687752312-172.31.15.226-1487040358228:blk_1073743463_2639 len=33554432 Live_repl=3
40. BP-687752312-172.31.15.226-1487040358228:blk_1073743467_2643 len=33554432 Live_repl=3
41. BP-687752312-172.31.15.226-1487040358228:blk_1073743471_2647 len=33554432 Live_repl=3
42. BP-687752312-172.31.15.226-1487040358228:blk_1073743474_2650 len=33554432 Live_repl=3
43. BP-687752312-172.31.15.226-1487040358228:blk_1073743476_2652 len=33554432 Live_repl=3
44. BP-687752312-172.31.15.226-1487040358228:blk_1073743479_2655 len=33554432 Live_repl=3
45. BP-687752312-172.31.15.226-1487040358228:blk_1073743482_2658 len=33554432 Live_repl=3
46. BP-687752312-172.31.15.226-1487040358228:blk_1073743486_2662 len=33554432 Live_repl=3
47. BP-687752312-172.31.15.226-1487040358228:blk_1073743489_2665 len=33554432 Live_repl=3
48. BP-687752312-172.31.15.226-1487040358228:blk_1073743493_2669 len=33554432 Live_repl=3
49. BP-687752312-172.31.15.226-1487040358228:blk_1073743495_2671 len=33554432 Live_repl=3
50. BP-687752312-172.31.15.226-1487040358228:blk_1073743498_2674 len=33554432 Live_repl=3
51. BP-687752312-172.31.15.226-1487040358228:blk_1073743501_2677 len=33554432 Live_repl=3
52. BP-687752312-172.31.15.226-1487040358228:blk_1073743503_2679 len=33554432 Live_repl=3
53. BP-687752312-172.31.15.226-1487040358228:blk_1073743506_2682 len=33554432 Live_repl=3
54. BP-687752312-172.31.15.226-1487040358228:blk_1073743507_2683 len=33554432 Live_repl=3
55. BP-687752312-172.31.15.226-1487040358228:blk_1073743510_2686 len=33554432 Live_repl=3
56. BP-687752312-172.31.15.226-1487040358228:blk_1073743514_2690 len=33554432 Live_repl=3
57. BP-687752312-172.31.15.226-1487040358228:blk_1073743518_2694 len=33554432 Live_repl=3
58. BP-687752312-172.31.15.226-1487040358228:blk_1073743522_2698 len=33554432 Live_repl=3
59. BP-687752312-172.31.15.226-1487040358228:blk_1073743523_2699 len=33554432 Live_repl=3
60. BP-687752312-172.31.15.226-1487040358228:blk_1073743526_2702 len=33554432 Live_repl=3
61. BP-687752312-172.31.15.226-1487040358228:blk_1073743529_2705 len=33554432 Live_repl=3
62. BP-687752312-172.31.15.226-1487040358228:blk_1073743532_2708 len=33554432 Live_repl=3
63. BP-687752312-172.31.15.226-1487040358228:blk_1073743536_2712 len=33554432 Live_repl=3
64. BP-687752312-172.31.15.226-1487040358228:blk_1073743539_2715 len=33554432 Live_repl=3
65. BP-687752312-172.31.15.226-1487040358228:blk_1073743542_2718 len=33554432 Live_repl=3
66. BP-687752312-172.31.15.226-1487040358228:blk_1073743545_2721 len=33554432 Live_repl=3
67. BP-687752312-172.31.15.226-1487040358228:blk_1073743548_2724 len=33554432 Live_repl=3
68. BP-687752312-172.31.15.226-1487040358228:blk_1073743551_2727 len=33554432 Live_repl=3
69. BP-687752312-172.31.15.226-1487040358228:blk_1073743554_2730 len=33554432 Live_repl=3
70. BP-687752312-172.31.15.226-1487040358228:blk_1073743557_2733 len=33554432 Live_repl=3
71. BP-687752312-172.31.15.226-1487040358228:blk_1073743560_2736 len=33554432 Live_repl=3
72. BP-687752312-172.31.15.226-1487040358228:blk_1073743564_2740 len=33554432 Live_repl=3
73. BP-687752312-172.31.15.226-1487040358228:blk_1073743567_2743 len=33554432 Live_repl=3
74. BP-687752312-172.31.15.226-1487040358228:blk_1073743570_2746 len=33554432 Live_repl=3
75. BP-687752312-172.31.15.226-1487040358228:blk_1073743573_2749 len=33554432 Live_repl=3
76. BP-687752312-172.31.15.226-1487040358228:blk_1073743576_2752 len=33554432 Live_repl=3
77. BP-687752312-172.31.15.226-1487040358228:blk_1073743579_2755 len=33554432 Live_repl=3
78. BP-687752312-172.31.15.226-1487040358228:blk_1073743582_2758 len=33554432 Live_repl=3
79. BP-687752312-172.31.15.226-1487040358228:blk_1073743585_2761 len=33554432 Live_repl=3
80. BP-687752312-172.31.15.226-1487040358228:blk_1073743588_2764 len=40 Live_repl=3

Status: HEALTHY
 Total size:    2684354600 B
 Total dirs:    0
 Total files:   1
 Total symlinks:                0
 Total blocks (validated):      81 (avg. block size 33140180 B)
 Minimally replicated blocks:   81 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Tue Feb 14 03:33:57 EST 2017 in 2 milliseconds


The filesystem under path '/user/lawankorn/terageninput/part-m-00001' is HEALTHY
[lawankorn@ip-172-31-15-226 ~]$
```
Run Terasort
```
[lawankorn@ip-172-31-15-226 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar terasort terageninput terasortoutput
17/02/14 03:38:01 INFO terasort.TeraSort: starting
17/02/14 03:38:03 INFO input.FileInputFormat: Total input paths to process : 4
Spent 228ms computing base-splits.
Spent 6ms computing TeraScheduler splits.
Computing input splits took 235ms
Sampling 10 splits of 320
Making 3 from 100000 sampled records
Computing parititions took 1038ms
Spent 1275ms computing partitions.
17/02/14 03:38:04 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-3-223.ap-southeast-1.compute.internal/172.31.3.223:8032
17/02/14 03:38:04 INFO mapreduce.JobSubmitter: number of splits:320
17/02/14 03:38:04 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1487044813809_0004
17/02/14 03:38:05 INFO impl.YarnClientImpl: Submitted application application_1487044813809_0004
17/02/14 03:38:05 INFO mapreduce.Job: The url to track the job: http://ip-172-31-3-223.ap-southeast-1.compute.internal:8088/proxy/application_1487044813809_0004/
17/02/14 03:38:05 INFO mapreduce.Job: Running job: job_1487044813809_0004
17/02/14 03:38:10 INFO mapreduce.Job: Job job_1487044813809_0004 running in uber mode : false
17/02/14 03:38:10 INFO mapreduce.Job:  map 0% reduce 0%
17/02/14 03:38:17 INFO mapreduce.Job:  map 1% reduce 0%
17/02/14 03:38:23 INFO mapreduce.Job:  map 2% reduce 0%
17/02/14 03:38:29 INFO mapreduce.Job:  map 3% reduce 0%
17/02/14 03:38:35 INFO mapreduce.Job:  map 4% reduce 0%
17/02/14 03:38:41 INFO mapreduce.Job:  map 5% reduce 0%
17/02/14 03:38:47 INFO mapreduce.Job:  map 6% reduce 0%
17/02/14 03:38:53 INFO mapreduce.Job:  map 7% reduce 0%
17/02/14 03:39:00 INFO mapreduce.Job:  map 8% reduce 0%
17/02/14 03:39:08 INFO mapreduce.Job:  map 9% reduce 0%
17/02/14 03:39:14 INFO mapreduce.Job:  map 10% reduce 0%
17/02/14 03:39:19 INFO mapreduce.Job:  map 11% reduce 0%
17/02/14 03:39:25 INFO mapreduce.Job:  map 12% reduce 0%
17/02/14 03:39:31 INFO mapreduce.Job:  map 13% reduce 0%
17/02/14 03:39:41 INFO mapreduce.Job:  map 14% reduce 0%
17/02/14 03:39:46 INFO mapreduce.Job:  map 15% reduce 0%
17/02/14 03:39:52 INFO mapreduce.Job:  map 16% reduce 0%
17/02/14 03:39:59 INFO mapreduce.Job:  map 17% reduce 0%
17/02/14 03:40:06 INFO mapreduce.Job:  map 18% reduce 0%
17/02/14 03:40:13 INFO mapreduce.Job:  map 19% reduce 0%
17/02/14 03:40:18 INFO mapreduce.Job:  map 20% reduce 0%
17/02/14 03:40:24 INFO mapreduce.Job:  map 21% reduce 0%
17/02/14 03:40:30 INFO mapreduce.Job:  map 22% reduce 0%
17/02/14 03:40:37 INFO mapreduce.Job:  map 23% reduce 0%
17/02/14 03:40:43 INFO mapreduce.Job:  map 24% reduce 0%
17/02/14 03:40:50 INFO mapreduce.Job:  map 25% reduce 0%
17/02/14 03:40:56 INFO mapreduce.Job:  map 26% reduce 0%
17/02/14 03:41:02 INFO mapreduce.Job:  map 27% reduce 0%
17/02/14 03:41:08 INFO mapreduce.Job:  map 28% reduce 0%
17/02/14 03:41:15 INFO mapreduce.Job:  map 29% reduce 0%
17/02/14 03:41:21 INFO mapreduce.Job:  map 30% reduce 0%
17/02/14 03:41:27 INFO mapreduce.Job:  map 31% reduce 0%
17/02/14 03:41:33 INFO mapreduce.Job:  map 32% reduce 0%
17/02/14 03:41:43 INFO mapreduce.Job:  map 33% reduce 0%
17/02/14 03:41:49 INFO mapreduce.Job:  map 34% reduce 0%
17/02/14 03:41:55 INFO mapreduce.Job:  map 35% reduce 0%
17/02/14 03:42:01 INFO mapreduce.Job:  map 36% reduce 0%
17/02/14 03:42:07 INFO mapreduce.Job:  map 37% reduce 0%
17/02/14 03:42:13 INFO mapreduce.Job:  map 38% reduce 0%
17/02/14 03:42:19 INFO mapreduce.Job:  map 39% reduce 0%
17/02/14 03:42:25 INFO mapreduce.Job:  map 40% reduce 0%
17/02/14 03:42:32 INFO mapreduce.Job:  map 41% reduce 0%
17/02/14 03:42:38 INFO mapreduce.Job:  map 42% reduce 0%
17/02/14 03:42:44 INFO mapreduce.Job:  map 43% reduce 0%
17/02/14 03:42:52 INFO mapreduce.Job:  map 44% reduce 0%
17/02/14 03:42:58 INFO mapreduce.Job:  map 45% reduce 0%
17/02/14 03:43:04 INFO mapreduce.Job:  map 46% reduce 0%
17/02/14 03:43:10 INFO mapreduce.Job:  map 47% reduce 0%
17/02/14 03:43:18 INFO mapreduce.Job:  map 48% reduce 0%
17/02/14 03:43:25 INFO mapreduce.Job:  map 49% reduce 0%
17/02/14 03:43:30 INFO mapreduce.Job:  map 50% reduce 0%
17/02/14 03:43:36 INFO mapreduce.Job:  map 51% reduce 0%
17/02/14 03:43:43 INFO mapreduce.Job:  map 52% reduce 0%
17/02/14 03:43:51 INFO mapreduce.Job:  map 53% reduce 0%
17/02/14 03:43:57 INFO mapreduce.Job:  map 54% reduce 0%
17/02/14 03:44:03 INFO mapreduce.Job:  map 55% reduce 0%
17/02/14 03:44:09 INFO mapreduce.Job:  map 56% reduce 0%
17/02/14 03:44:15 INFO mapreduce.Job:  map 57% reduce 0%
17/02/14 03:44:23 INFO mapreduce.Job:  map 58% reduce 0%
17/02/14 03:44:29 INFO mapreduce.Job:  map 59% reduce 0%
17/02/14 03:44:35 INFO mapreduce.Job:  map 60% reduce 0%
17/02/14 03:44:41 INFO mapreduce.Job:  map 61% reduce 0%
17/02/14 03:44:47 INFO mapreduce.Job:  map 62% reduce 0%
17/02/14 03:44:54 INFO mapreduce.Job:  map 63% reduce 0%
17/02/14 03:45:00 INFO mapreduce.Job:  map 64% reduce 0%
17/02/14 03:45:06 INFO mapreduce.Job:  map 65% reduce 0%
17/02/14 03:45:12 INFO mapreduce.Job:  map 66% reduce 0%
17/02/14 03:45:18 INFO mapreduce.Job:  map 67% reduce 0%
17/02/14 03:45:24 INFO mapreduce.Job:  map 68% reduce 0%
17/02/14 03:45:33 INFO mapreduce.Job:  map 69% reduce 0%
17/02/14 03:45:39 INFO mapreduce.Job:  map 70% reduce 0%
17/02/14 03:45:45 INFO mapreduce.Job:  map 71% reduce 0%
17/02/14 03:45:51 INFO mapreduce.Job:  map 72% reduce 0%
17/02/14 03:45:57 INFO mapreduce.Job:  map 73% reduce 0%
17/02/14 03:46:04 INFO mapreduce.Job:  map 74% reduce 0%
17/02/14 03:46:10 INFO mapreduce.Job:  map 75% reduce 0%
17/02/14 03:46:17 INFO mapreduce.Job:  map 76% reduce 0%
17/02/14 03:46:23 INFO mapreduce.Job:  map 77% reduce 0%
17/02/14 03:46:31 INFO mapreduce.Job:  map 78% reduce 0%
17/02/14 03:46:37 INFO mapreduce.Job:  map 79% reduce 0%
17/02/14 03:46:43 INFO mapreduce.Job:  map 80% reduce 0%
17/02/14 03:46:49 INFO mapreduce.Job:  map 81% reduce 0%
17/02/14 03:46:57 INFO mapreduce.Job:  map 81% reduce 3%
17/02/14 03:46:58 INFO mapreduce.Job:  map 82% reduce 3%
17/02/14 03:47:00 INFO mapreduce.Job:  map 82% reduce 4%
17/02/14 03:47:03 INFO mapreduce.Job:  map 82% reduce 5%
17/02/14 03:47:06 INFO mapreduce.Job:  map 82% reduce 6%
17/02/14 03:47:09 INFO mapreduce.Job:  map 82% reduce 7%
17/02/14 03:47:10 INFO mapreduce.Job:  map 83% reduce 7%
17/02/14 03:47:12 INFO mapreduce.Job:  map 83% reduce 8%
17/02/14 03:47:15 INFO mapreduce.Job:  map 83% reduce 9%
17/02/14 03:47:19 INFO mapreduce.Job:  map 84% reduce 9%
17/02/14 03:47:29 INFO mapreduce.Job:  map 85% reduce 9%
17/02/14 03:47:38 INFO mapreduce.Job:  map 86% reduce 9%
17/02/14 03:47:40 INFO mapreduce.Job:  map 86% reduce 10%
17/02/14 03:47:47 INFO mapreduce.Job:  map 87% reduce 10%
17/02/14 03:47:56 INFO mapreduce.Job:  map 88% reduce 10%
17/02/14 03:48:08 INFO mapreduce.Job:  map 89% reduce 10%
17/02/14 03:48:18 INFO mapreduce.Job:  map 90% reduce 10%
17/02/14 03:48:26 INFO mapreduce.Job:  map 91% reduce 10%
17/02/14 03:48:37 INFO mapreduce.Job:  map 92% reduce 10%
17/02/14 03:48:45 INFO mapreduce.Job:  map 93% reduce 10%
17/02/14 03:48:57 INFO mapreduce.Job:  map 94% reduce 10%
17/02/14 03:49:08 INFO mapreduce.Job:  map 95% reduce 10%
17/02/14 03:49:10 INFO mapreduce.Job:  map 95% reduce 11%
17/02/14 03:49:15 INFO mapreduce.Job:  map 96% reduce 11%
17/02/14 03:49:26 INFO mapreduce.Job:  map 97% reduce 11%
17/02/14 03:49:33 INFO mapreduce.Job:  map 98% reduce 11%
17/02/14 03:49:45 INFO mapreduce.Job:  map 99% reduce 11%
17/02/14 03:49:56 INFO mapreduce.Job:  map 100% reduce 11%
17/02/14 03:49:58 INFO mapreduce.Job:  map 100% reduce 20%
17/02/14 03:50:01 INFO mapreduce.Job:  map 100% reduce 23%
17/02/14 03:50:04 INFO mapreduce.Job:  map 100% reduce 24%
17/02/14 03:50:06 INFO mapreduce.Job:  map 100% reduce 27%
17/02/14 03:50:07 INFO mapreduce.Job:  map 100% reduce 30%
17/02/14 03:50:09 INFO mapreduce.Job:  map 100% reduce 31%
17/02/14 03:50:11 INFO mapreduce.Job:  map 100% reduce 33%
17/02/14 03:50:13 INFO mapreduce.Job:  map 100% reduce 34%
17/02/14 03:50:14 INFO mapreduce.Job:  map 100% reduce 36%
17/02/14 03:50:16 INFO mapreduce.Job:  map 100% reduce 37%
17/02/14 03:50:17 INFO mapreduce.Job:  map 100% reduce 39%
17/02/14 03:50:19 INFO mapreduce.Job:  map 100% reduce 40%
17/02/14 03:50:20 INFO mapreduce.Job:  map 100% reduce 42%
17/02/14 03:50:22 INFO mapreduce.Job:  map 100% reduce 43%
17/02/14 03:50:23 INFO mapreduce.Job:  map 100% reduce 44%
17/02/14 03:50:25 INFO mapreduce.Job:  map 100% reduce 45%
17/02/14 03:50:26 INFO mapreduce.Job:  map 100% reduce 47%
17/02/14 03:50:28 INFO mapreduce.Job:  map 100% reduce 48%
17/02/14 03:50:29 INFO mapreduce.Job:  map 100% reduce 50%
17/02/14 03:50:31 INFO mapreduce.Job:  map 100% reduce 51%
17/02/14 03:50:32 INFO mapreduce.Job:  map 100% reduce 53%
17/02/14 03:50:34 INFO mapreduce.Job:  map 100% reduce 54%
17/02/14 03:50:35 INFO mapreduce.Job:  map 100% reduce 55%
17/02/14 03:50:37 INFO mapreduce.Job:  map 100% reduce 58%
17/02/14 03:50:38 INFO mapreduce.Job:  map 100% reduce 69%
17/02/14 03:50:40 INFO mapreduce.Job:  map 100% reduce 78%
17/02/14 03:50:41 INFO mapreduce.Job:  map 100% reduce 79%
17/02/14 03:50:43 INFO mapreduce.Job:  map 100% reduce 80%
17/02/14 03:50:44 INFO mapreduce.Job:  map 100% reduce 81%
17/02/14 03:50:46 INFO mapreduce.Job:  map 100% reduce 82%
17/02/14 03:50:47 INFO mapreduce.Job:  map 100% reduce 83%
17/02/14 03:50:49 INFO mapreduce.Job:  map 100% reduce 84%
17/02/14 03:50:50 INFO mapreduce.Job:  map 100% reduce 85%
17/02/14 03:50:52 INFO mapreduce.Job:  map 100% reduce 86%
17/02/14 03:50:53 INFO mapreduce.Job:  map 100% reduce 87%
17/02/14 03:50:55 INFO mapreduce.Job:  map 100% reduce 88%
17/02/14 03:50:56 INFO mapreduce.Job:  map 100% reduce 89%
17/02/14 03:50:58 INFO mapreduce.Job:  map 100% reduce 90%
17/02/14 03:50:59 INFO mapreduce.Job:  map 100% reduce 91%
17/02/14 03:51:01 INFO mapreduce.Job:  map 100% reduce 92%
17/02/14 03:51:02 INFO mapreduce.Job:  map 100% reduce 93%
17/02/14 03:51:04 INFO mapreduce.Job:  map 100% reduce 94%
17/02/14 03:51:05 INFO mapreduce.Job:  map 100% reduce 95%
17/02/14 03:51:07 INFO mapreduce.Job:  map 100% reduce 96%
17/02/14 03:51:08 INFO mapreduce.Job:  map 100% reduce 97%
17/02/14 03:51:10 INFO mapreduce.Job:  map 100% reduce 98%
17/02/14 03:51:11 INFO mapreduce.Job:  map 100% reduce 99%
17/02/14 03:51:13 INFO mapreduce.Job:  map 100% reduce 100%
17/02/14 03:51:13 INFO mapreduce.Job: Job job_1487044813809_0004 completed successfully
17/02/14 03:51:13 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=4798449967
                FILE: Number of bytes written=9501132025
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=10737471420
                HDFS: Number of bytes written=10737418300
                HDFS: Number of read operations=969
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=6
        Job Counters
                Launched map tasks=320
                Launched reduce tasks=3
                Data-local map tasks=320
                Total time spent by all maps in occupied slots (ms)=1472514
                Total time spent by all reduces in occupied slots (ms)=374052
                Total time spent by all map tasks (ms)=1472514
                Total time spent by all reduce tasks (ms)=374052
                Total vcore-seconds taken by all map tasks=1472514
                Total vcore-seconds taken by all reduce tasks=374052
                Total megabyte-seconds taken by all map tasks=1507854336
                Total megabyte-seconds taken by all reduce tasks=383029248
        Map-Reduce Framework
                Map input records=107374183
                Map output records=107374183
                Map output bytes=10952166666
                Map output materialized bytes=4662738945
                Input split bytes=53120
                Combine input records=0
                Combine output records=0
                Reduce input groups=107374183
                Reduce shuffle bytes=4662738945
                Reduce input records=107374183
                Reduce output records=107374183
                Spilled Records=214748366
                Shuffled Maps =960
                Failed Shuffles=0
                Merged Map outputs=960
                GC time elapsed (ms)=20280
                CPU time spent (ms)=1031030
                Physical memory (bytes) snapshot=154628907008
                Virtual memory (bytes) snapshot=509479198720
                Total committed heap usage (bytes)=157858398208
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=10737418300
        File Output Format Counters
                Bytes Written=10737418300
17/02/14 03:51:13 INFO terasort.TeraSort: done

real    13m12.692s
user    0m8.245s
sys     0m0.503s
[lawankorn@ip-172-31-15-226 ~]$

[lawankorn@ip-172-31-15-226 ~]$ hadoop fs -ls terasortoutput
Found 5 items
-rw-r--r--   1 lawankorn supergroup          0 2017-02-14 03:51 terasortoutput/_SUCCESS
-rw-r--r--  10 lawankorn supergroup         22 2017-02-14 03:38 terasortoutput/_partition.lst
-rw-r--r--   1 lawankorn supergroup 3561320900 2017-02-14 03:50 terasortoutput/part-r-00000
-rw-r--r--   1 lawankorn supergroup 3620956700 2017-02-14 03:51 terasortoutput/part-r-00001
-rw-r--r--   1 lawankorn supergroup 3555140700 2017-02-14 03:51 terasortoutput/part-r-00002
[lawankorn@ip-172-31-15-226 ~]$
```
