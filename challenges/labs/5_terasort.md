```
[raffles@ip-172-31-7-226 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar terasort tgen512m tsort512m
17/02/17 15:52:12 INFO terasort.TeraSort: starting
17/02/17 15:52:13 INFO hdfs.DFSClient: Created token for raffles: HDFS_DELEGATION_TOKEN owner=raffles@LAWANKORN.SG, renewer=yarn, realUser=, issueDate=1487317933734, maxDate=1487922733734, sequenceNumber=1, masterKeyId=2 on 172.31.7.226:8020
17/02/17 15:52:13 INFO security.TokenCache: Got dt for hdfs://ip-172-31-7-226.ap-southeast-1.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.7.226:8020, Ident: (token for raffles: HDFS_DELEGATION_TOKEN owner=raffles@LAWANKORN.SG, renewer=yarn, realUser=, issueDate=1487317933734, maxDate=1487922733734, sequenceNumber=1, masterKeyId=2)
17/02/17 15:52:13 INFO input.FileInputFormat: Total input paths to process : 6
Spent 288ms computing base-splits.
Spent 4ms computing TeraScheduler splits.
Computing input splits took 292ms
Sampling 10 splits of 156
Making 3 from 100000 sampled records
Computing parititions took 1380ms
Spent 1674ms computing partitions.
17/02/17 15:52:15 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-4-71.ap-southeast-1.compute.internal/172.31.4.71:8032
17/02/17 15:52:15 INFO mapreduce.JobSubmitter: number of splits:156
17/02/17 15:52:15 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1487317802284_0001
17/02/17 15:52:15 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.7.226:8020, Ident: (token for raffles: HDFS_DELEGATION_TOKEN owner=raffles@LAWANKORN.SG, renewer=yarn, realUser=, issueDate=1487317933734, maxDate=1487922733734, sequenceNumber=1, masterKeyId=2)
17/02/17 15:52:16 INFO impl.YarnClientImpl: Submitted application application_1487317802284_0001
17/02/17 15:52:16 INFO mapreduce.Job: The url to track the job: http://ip-172-31-4-71.ap-southeast-1.compute.internal:8088/proxy/application_1487317802284_0001/
17/02/17 15:52:16 INFO mapreduce.Job: Running job: job_1487317802284_0001
17/02/17 15:52:25 INFO mapreduce.Job: Job job_1487317802284_0001 running in uber mode : false
17/02/17 15:52:25 INFO mapreduce.Job:  map 0% reduce 0%
17/02/17 15:52:34 INFO mapreduce.Job:  map 1% reduce 0%
17/02/17 15:52:40 INFO mapreduce.Job:  map 2% reduce 0%
17/02/17 15:52:41 INFO mapreduce.Job:  map 3% reduce 0%
17/02/17 15:52:47 INFO mapreduce.Job:  map 4% reduce 0%
17/02/17 15:52:53 INFO mapreduce.Job:  map 5% reduce 0%
17/02/17 15:52:57 INFO mapreduce.Job:  map 6% reduce 0%
17/02/17 15:53:03 INFO mapreduce.Job:  map 7% reduce 0%
17/02/17 15:53:05 INFO mapreduce.Job:  map 8% reduce 0%
17/02/17 15:53:11 INFO mapreduce.Job:  map 9% reduce 0%
17/02/17 15:53:15 INFO mapreduce.Job:  map 10% reduce 0%
17/02/17 15:53:20 INFO mapreduce.Job:  map 11% reduce 0%
17/02/17 15:53:23 INFO mapreduce.Job:  map 12% reduce 0%
17/02/17 15:53:29 INFO mapreduce.Job:  map 13% reduce 0%
17/02/17 15:53:35 INFO mapreduce.Job:  map 14% reduce 0%
17/02/17 15:53:37 INFO mapreduce.Job:  map 15% reduce 0%
17/02/17 15:53:43 INFO mapreduce.Job:  map 16% reduce 0%
17/02/17 15:53:47 INFO mapreduce.Job:  map 17% reduce 0%
17/02/17 15:53:53 INFO mapreduce.Job:  map 18% reduce 0%
17/02/17 15:53:54 INFO mapreduce.Job:  map 19% reduce 0%
17/02/17 15:53:59 INFO mapreduce.Job:  map 20% reduce 0%
17/02/17 15:54:04 INFO mapreduce.Job:  map 21% reduce 0%
17/02/17 15:54:10 INFO mapreduce.Job:  map 22% reduce 0%
17/02/17 15:54:16 INFO mapreduce.Job:  map 23% reduce 0%
17/02/17 15:54:17 INFO mapreduce.Job:  map 24% reduce 0%
17/02/17 15:54:24 INFO mapreduce.Job:  map 25% reduce 0%
17/02/17 15:54:29 INFO mapreduce.Job:  map 26% reduce 0%
17/02/17 15:54:34 INFO mapreduce.Job:  map 27% reduce 0%
17/02/17 15:54:36 INFO mapreduce.Job:  map 28% reduce 0%
17/02/17 15:54:42 INFO mapreduce.Job:  map 29% reduce 0%
17/02/17 15:54:48 INFO mapreduce.Job:  map 30% reduce 0%
17/02/17 15:54:52 INFO mapreduce.Job:  map 31% reduce 0%
17/02/17 15:54:58 INFO mapreduce.Job:  map 32% reduce 0%
17/02/17 15:55:00 INFO mapreduce.Job:  map 33% reduce 0%
17/02/17 15:55:06 INFO mapreduce.Job:  map 34% reduce 0%
17/02/17 15:55:09 INFO mapreduce.Job:  map 35% reduce 0%
17/02/17 15:55:15 INFO mapreduce.Job:  map 36% reduce 0%
17/02/17 15:55:18 INFO mapreduce.Job:  map 37% reduce 0%
17/02/17 15:55:24 INFO mapreduce.Job:  map 38% reduce 0%
17/02/17 15:55:30 INFO mapreduce.Job:  map 39% reduce 0%
17/02/17 15:55:33 INFO mapreduce.Job:  map 40% reduce 0%
17/02/17 15:55:39 INFO mapreduce.Job:  map 41% reduce 0%
17/02/17 15:55:42 INFO mapreduce.Job:  map 42% reduce 0%
17/02/17 15:55:48 INFO mapreduce.Job:  map 43% reduce 0%
17/02/17 15:55:51 INFO mapreduce.Job:  map 44% reduce 0%
17/02/17 15:55:56 INFO mapreduce.Job:  map 45% reduce 0%
17/02/17 15:56:00 INFO mapreduce.Job:  map 46% reduce 0%
17/02/17 15:56:06 INFO mapreduce.Job:  map 47% reduce 0%
17/02/17 15:56:12 INFO mapreduce.Job:  map 48% reduce 0%
17/02/17 15:56:14 INFO mapreduce.Job:  map 49% reduce 0%
17/02/17 15:56:20 INFO mapreduce.Job:  map 50% reduce 0%
17/02/17 15:56:24 INFO mapreduce.Job:  map 51% reduce 0%
17/02/17 15:56:30 INFO mapreduce.Job:  map 52% reduce 0%
17/02/17 15:56:31 INFO mapreduce.Job:  map 53% reduce 0%
17/02/17 15:56:37 INFO mapreduce.Job:  map 54% reduce 0%
17/02/17 15:56:43 INFO mapreduce.Job:  map 55% reduce 0%
17/02/17 15:56:48 INFO mapreduce.Job:  map 56% reduce 0%
17/02/17 15:56:54 INFO mapreduce.Job:  map 58% reduce 0%
17/02/17 15:57:00 INFO mapreduce.Job:  map 59% reduce 0%
17/02/17 15:57:05 INFO mapreduce.Job:  map 60% reduce 0%
17/02/17 15:57:10 INFO mapreduce.Job:  map 61% reduce 0%
17/02/17 15:57:12 INFO mapreduce.Job:  map 62% reduce 0%
17/02/17 15:57:19 INFO mapreduce.Job:  map 63% reduce 0%
17/02/17 15:57:25 INFO mapreduce.Job:  map 64% reduce 0%
17/02/17 15:57:27 INFO mapreduce.Job:  map 65% reduce 0%
17/02/17 15:57:33 INFO mapreduce.Job:  map 66% reduce 0%
17/02/17 15:57:37 INFO mapreduce.Job:  map 67% reduce 0%
17/02/17 15:57:43 INFO mapreduce.Job:  map 68% reduce 0%
17/02/17 15:57:45 INFO mapreduce.Job:  map 69% reduce 0%
17/02/17 15:57:51 INFO mapreduce.Job:  map 70% reduce 0%
17/02/17 15:57:55 INFO mapreduce.Job:  map 71% reduce 0%
17/02/17 15:58:01 INFO mapreduce.Job:  map 72% reduce 0%
17/02/17 15:58:07 INFO mapreduce.Job:  map 73% reduce 0%
17/02/17 15:58:09 INFO mapreduce.Job:  map 74% reduce 0%
17/02/17 15:58:15 INFO mapreduce.Job:  map 75% reduce 0%
17/02/17 15:58:19 INFO mapreduce.Job:  map 76% reduce 0%
17/02/17 15:58:25 INFO mapreduce.Job:  map 77% reduce 0%
17/02/17 15:58:26 INFO mapreduce.Job:  map 78% reduce 0%
17/02/17 15:58:32 INFO mapreduce.Job:  map 79% reduce 0%
17/02/17 15:58:38 INFO mapreduce.Job:  map 80% reduce 0%
17/02/17 15:58:43 INFO mapreduce.Job:  map 81% reduce 0%
17/02/17 15:58:50 INFO mapreduce.Job:  map 82% reduce 0%
17/02/17 15:58:56 INFO mapreduce.Job:  map 83% reduce 0%
17/02/17 15:59:00 INFO mapreduce.Job:  map 83% reduce 9%
17/02/17 15:59:08 INFO mapreduce.Job:  map 84% reduce 9%
17/02/17 15:59:14 INFO mapreduce.Job:  map 85% reduce 9%
17/02/17 15:59:26 INFO mapreduce.Job:  map 86% reduce 9%
17/02/17 15:59:30 INFO mapreduce.Job:  map 86% reduce 10%
17/02/17 15:59:32 INFO mapreduce.Job:  map 87% reduce 10%
17/02/17 15:59:44 INFO mapreduce.Job:  map 88% reduce 10%
17/02/17 15:59:56 INFO mapreduce.Job:  map 89% reduce 10%
17/02/17 16:00:02 INFO mapreduce.Job:  map 90% reduce 10%
17/02/17 16:00:14 INFO mapreduce.Job:  map 91% reduce 10%
17/02/17 16:00:20 INFO mapreduce.Job:  map 92% reduce 10%
17/02/17 16:00:33 INFO mapreduce.Job:  map 93% reduce 10%
17/02/17 16:00:39 INFO mapreduce.Job:  map 94% reduce 10%
17/02/17 16:00:51 INFO mapreduce.Job:  map 95% reduce 10%
17/02/17 16:00:55 INFO mapreduce.Job:  map 95% reduce 11%
17/02/17 16:00:56 INFO mapreduce.Job:  map 96% reduce 11%
17/02/17 16:01:06 INFO mapreduce.Job:  map 97% reduce 11%
17/02/17 16:01:16 INFO mapreduce.Job:  map 98% reduce 11%
17/02/17 16:01:21 INFO mapreduce.Job:  map 99% reduce 11%
17/02/17 16:01:33 INFO mapreduce.Job:  map 100% reduce 11%
17/02/17 16:01:36 INFO mapreduce.Job:  map 100% reduce 22%
17/02/17 16:01:42 INFO mapreduce.Job:  map 100% reduce 26%
17/02/17 16:01:48 INFO mapreduce.Job:  map 100% reduce 30%
17/02/17 16:01:49 INFO mapreduce.Job:  map 100% reduce 41%
17/02/17 16:01:53 INFO mapreduce.Job:  map 100% reduce 44%
17/02/17 16:01:55 INFO mapreduce.Job:  map 100% reduce 56%
17/02/17 16:02:01 INFO mapreduce.Job:  map 100% reduce 60%
17/02/17 16:02:07 INFO mapreduce.Job:  map 100% reduce 64%
17/02/17 16:02:09 INFO mapreduce.Job:  map 100% reduce 74%
17/02/17 16:02:10 INFO mapreduce.Job:  map 100% reduce 77%
17/02/17 16:02:15 INFO mapreduce.Job:  map 100% reduce 89%
17/02/17 16:02:21 INFO mapreduce.Job:  map 100% reduce 94%
17/02/17 16:02:27 INFO mapreduce.Job:  map 100% reduce 98%
17/02/17 16:02:29 INFO mapreduce.Job:  map 100% reduce 100%
17/02/17 16:02:29 INFO mapreduce.Job: Job job_1487317802284_0001 completed successfully
17/02/17 16:02:29 INFO mapreduce.Job: Counters: 50
        File System Counters
                FILE: Number of bytes read=2277643165
                FILE: Number of bytes written=4521339989
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=5120024804
                HDFS: Number of bytes written=5120000000
                HDFS: Number of read operations=477
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=6
        Job Counters 
                Launched map tasks=156
                Launched reduce tasks=3
                Data-local map tasks=154
                Rack-local map tasks=2
                Total time spent by all maps in occupied slots (ms)=736192
                Total time spent by all reduces in occupied slots (ms)=258821
                Total time spent by all map tasks (ms)=736192
                Total time spent by all reduce tasks (ms)=258821
                Total vcore-seconds taken by all map tasks=736192
                Total vcore-seconds taken by all reduce tasks=258821
                Total megabyte-seconds taken by all map tasks=753860608
                Total megabyte-seconds taken by all reduce tasks=265032704
        Map-Reduce Framework
                Map input records=51200000
                Map output records=51200000
                Map output bytes=5222400000
                Map output materialized bytes=2223499425
                Input split bytes=24804
                Combine input records=0
                Combine output records=0
                Reduce input groups=51200000
                Reduce shuffle bytes=2223499425
                Reduce input records=51200000
                Reduce output records=51200000
                Spilled Records=102400000
                Shuffled Maps =468
                Failed Shuffles=0
                Merged Map outputs=468
                GC time elapsed (ms)=8955
                CPU time spent (ms)=501630
                Physical memory (bytes) snapshot=76540588032
                Virtual memory (bytes) snapshot=250397323264
                Total committed heap usage (bytes)=78390493184
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters 
                Bytes Read=5120000000
        File Output Format Counters 
                Bytes Written=5120000000
17/02/17 16:02:29 INFO terasort.TeraSort: done

real    10m18.325s
user    0m7.805s
sys     0m0.499s
[raffles@ip-172-31-7-226 ~]$ 
```