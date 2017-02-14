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
```
