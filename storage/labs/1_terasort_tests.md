Create a 10 GB file using teragen
```
[lawankorn@ip-172-31-15-226 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen \
> -Ddfs.block.size=33554432 \
> -Dmapred.map.tasks=4 \
> 107374183 \
> teragen_source
17/02/14 02:29:40 INFO Configuration.deprecation: session.id is deprecated. Instead, use dfs.metrics.session-id
17/02/14 02:29:40 INFO jvm.JvmMetrics: Initializing JVM Metrics with processName=JobTracker, sessionId=
17/02/14 02:29:40 INFO terasort.TeraSort: Generating 107374183 using 1
17/02/14 02:29:40 INFO mapreduce.JobSubmitter: number of splits:1
17/02/14 02:29:40 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/02/14 02:29:40 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/02/14 02:29:40 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_local1465216135_0001
17/02/14 02:29:40 INFO mapreduce.Job: The url to track the job: http://localhost:8080/
17/02/14 02:29:40 INFO mapreduce.Job: Running job: job_local1465216135_0001
17/02/14 02:29:40 INFO mapred.LocalJobRunner: OutputCommitter set in config null
17/02/14 02:29:40 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/02/14 02:29:40 INFO mapred.LocalJobRunner: OutputCommitter is org.apache.hadoop.mapreduce.lib.output.FileOutputCommitter
17/02/14 02:29:40 INFO mapred.LocalJobRunner: Waiting for map tasks
17/02/14 02:29:40 INFO mapred.LocalJobRunner: Starting task: attempt_local1465216135_0001_m_000000_0
17/02/14 02:29:40 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/02/14 02:29:40 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/02/14 02:29:40 INFO mapred.MapTask: Processing split: org.apache.hadoop.examples.terasort.TeraGen$RangeInputFormat$RangeInputSplit@27f80b13
17/02/14 02:29:41 INFO mapreduce.Job: Job job_local1465216135_0001 running in uber mode : false
17/02/14 02:29:41 INFO mapreduce.Job:  map 0% reduce 0%
17/02/14 02:29:46 INFO mapred.LocalJobRunner: map > map
17/02/14 02:29:47 INFO mapreduce.Job:  map 5% reduce 0%
17/02/14 02:29:49 INFO mapred.LocalJobRunner: map > map
17/02/14 02:29:50 INFO mapreduce.Job:  map 8% reduce 0%
17/02/14 02:29:52 INFO mapred.LocalJobRunner: map > map
17/02/14 02:29:53 INFO mapreduce.Job:  map 11% reduce 0%
17/02/14 02:29:55 INFO mapred.LocalJobRunner: map > map
17/02/14 02:29:56 INFO mapreduce.Job:  map 14% reduce 0%
17/02/14 02:29:58 INFO mapred.LocalJobRunner: map > map
17/02/14 02:29:59 INFO mapreduce.Job:  map 17% reduce 0%
17/02/14 02:30:01 INFO mapred.LocalJobRunner: map > map
17/02/14 02:30:02 INFO mapreduce.Job:  map 20% reduce 0%
17/02/14 02:30:04 INFO mapred.LocalJobRunner: map > map
17/02/14 02:30:05 INFO mapreduce.Job:  map 23% reduce 0%
17/02/14 02:30:07 INFO mapred.LocalJobRunner: map > map
17/02/14 02:30:08 INFO mapreduce.Job:  map 26% reduce 0%
17/02/14 02:30:10 INFO mapred.LocalJobRunner: map > map
17/02/14 02:30:11 INFO mapreduce.Job:  map 29% reduce 0%
17/02/14 02:30:13 INFO mapred.LocalJobRunner: map > map
17/02/14 02:30:14 INFO mapreduce.Job:  map 32% reduce 0%
17/02/14 02:30:16 INFO mapred.LocalJobRunner: map > map
17/02/14 02:30:17 INFO mapreduce.Job:  map 35% reduce 0%
17/02/14 02:30:19 INFO mapred.LocalJobRunner: map > map
17/02/14 02:30:20 INFO mapreduce.Job:  map 38% reduce 0%
17/02/14 02:30:22 INFO mapred.LocalJobRunner: map > map
17/02/14 02:30:23 INFO mapreduce.Job:  map 41% reduce 0%
17/02/14 02:30:25 INFO mapred.LocalJobRunner: map > map
17/02/14 02:30:26 INFO mapreduce.Job:  map 44% reduce 0%
17/02/14 02:30:28 INFO mapred.LocalJobRunner: map > map
17/02/14 02:30:29 INFO mapreduce.Job:  map 47% reduce 0%
17/02/14 02:30:31 INFO mapred.LocalJobRunner: map > map
17/02/14 02:30:32 INFO mapreduce.Job:  map 50% reduce 0%
17/02/14 02:30:34 INFO mapred.LocalJobRunner: map > map
17/02/14 02:30:35 INFO mapreduce.Job:  map 53% reduce 0%
17/02/14 02:30:37 INFO mapred.LocalJobRunner: map > map
17/02/14 02:30:38 INFO mapreduce.Job:  map 55% reduce 0%
17/02/14 02:30:40 INFO mapred.LocalJobRunner: map > map
17/02/14 02:30:41 INFO mapreduce.Job:  map 58% reduce 0%
17/02/14 02:30:43 INFO mapred.LocalJobRunner: map > map
17/02/14 02:30:44 INFO mapreduce.Job:  map 61% reduce 0%
17/02/14 02:30:46 INFO mapred.LocalJobRunner: map > map
17/02/14 02:30:47 INFO mapreduce.Job:  map 64% reduce 0%
17/02/14 02:30:49 INFO mapred.LocalJobRunner: map > map
17/02/14 02:30:50 INFO mapreduce.Job:  map 67% reduce 0%
17/02/14 02:30:52 INFO mapred.LocalJobRunner: map > map
17/02/14 02:30:53 INFO mapreduce.Job:  map 70% reduce 0%
17/02/14 02:30:55 INFO mapred.LocalJobRunner: map > map
17/02/14 02:30:56 INFO mapreduce.Job:  map 73% reduce 0%
17/02/14 02:30:58 INFO mapred.LocalJobRunner: map > map
17/02/14 02:30:59 INFO mapreduce.Job:  map 76% reduce 0%
17/02/14 02:31:01 INFO mapred.LocalJobRunner: map > map
17/02/14 02:31:02 INFO mapreduce.Job:  map 79% reduce 0%
17/02/14 02:31:04 INFO mapred.LocalJobRunner: map > map
17/02/14 02:31:05 INFO mapreduce.Job:  map 82% reduce 0%
17/02/14 02:31:07 INFO mapred.LocalJobRunner: map > map
17/02/14 02:31:08 INFO mapreduce.Job:  map 85% reduce 0%
17/02/14 02:31:10 INFO mapred.LocalJobRunner: map > map
17/02/14 02:31:11 INFO mapreduce.Job:  map 88% reduce 0%
17/02/14 02:31:13 INFO mapred.LocalJobRunner: map > map
17/02/14 02:31:14 INFO mapreduce.Job:  map 91% reduce 0%
17/02/14 02:31:16 INFO mapred.LocalJobRunner: map > map
17/02/14 02:31:17 INFO mapreduce.Job:  map 94% reduce 0%
17/02/14 02:31:19 INFO mapred.LocalJobRunner: map > map
17/02/14 02:31:20 INFO mapreduce.Job:  map 97% reduce 0%
17/02/14 02:31:22 INFO mapred.LocalJobRunner: map > map
17/02/14 02:31:22 INFO mapred.LocalJobRunner: map > map
17/02/14 02:31:23 INFO mapred.Task: Task:attempt_local1465216135_0001_m_000000_0 is done. And is in the process of committing
17/02/14 02:31:23 INFO mapred.LocalJobRunner: map > map
17/02/14 02:31:23 INFO mapred.Task: Task attempt_local1465216135_0001_m_000000_0 is allowed to commit now
17/02/14 02:31:23 INFO output.FileOutputCommitter: Saved output of task 'attempt_local1465216135_0001_m_000000_0' to hdfs://ip-172-31-15-226.ap-southeast-1.compute.internal:8020/user/lawankorn/teragen_source/_temporary/0/task_local1465216135_0001_m_000000
17/02/14 02:31:23 INFO mapred.LocalJobRunner: map
17/02/14 02:31:23 INFO mapred.Task: Task 'attempt_local1465216135_0001_m_000000_0' done.
17/02/14 02:31:23 INFO mapred.LocalJobRunner: Finishing task: attempt_local1465216135_0001_m_000000_0
17/02/14 02:31:23 INFO mapred.LocalJobRunner: map task executor complete.
17/02/14 02:31:23 INFO mapreduce.Job:  map 100% reduce 0%
17/02/14 02:31:23 INFO mapreduce.Job: Job job_local1465216135_0001 completed successfully
17/02/14 02:31:23 INFO mapreduce.Job: Counters: 21
        File System Counters
                FILE: Number of bytes read=276331
                FILE: Number of bytes written=568980
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=0
                HDFS: Number of bytes written=10737418300
                HDFS: Number of read operations=4
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=3
        Map-Reduce Framework
                Map input records=107374183
                Map output records=107374183
                Input split bytes=83
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=996
                Total committed heap usage (bytes)=164102144
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=230593860607047066
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=10737418300

real    1m45.956s
user    1m49.685s
sys     0m7.073s
[lawankorn@ip-172-31-15-226 ~]$
```
