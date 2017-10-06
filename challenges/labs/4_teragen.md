```

#The full teragen command and output:

[root@ip-172-31-18-5 ec2-user]# su saturn
[saturn@ip-172-31-18-5 ec2-user]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen \
>  -Ddfs.block.size=33554432 \
>  -Dmapred.map.tasks=12 \
>  -Dmapreduce.map.memory.mb=512 \
>  65536000 \
>  tgen
17/10/06 10:18:54 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-18-5.us-west-2.compute.internal/172.31.18.5:8032
17/10/06 10:18:54 INFO terasort.TeraSort: Generating 65536000 using 12
17/10/06 10:18:54 INFO mapreduce.JobSubmitter: number of splits:12
17/10/06 10:18:54 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/10/06 10:18:54 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/10/06 10:18:54 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1507297665951_0001
17/10/06 10:18:55 INFO impl.YarnClientImpl: Submitted application application_1507297665951_0001
17/10/06 10:18:55 INFO mapreduce.Job: The url to track the job: http://ip-172-31-18-5.us-west-2.compute.internal:8088/proxy/application_1507297665951_0001/
17/10/06 10:18:55 INFO mapreduce.Job: Running job: job_1507297665951_0001
17/10/06 10:19:01 INFO mapreduce.Job: Job job_1507297665951_0001 running in uber mode : false
17/10/06 10:19:01 INFO mapreduce.Job:  map 0% reduce 0%
17/10/06 10:19:14 INFO mapreduce.Job:  map 11% reduce 0%
17/10/06 10:19:15 INFO mapreduce.Job:  map 17% reduce 0%
17/10/06 10:19:17 INFO mapreduce.Job:  map 21% reduce 0%
17/10/06 10:19:18 INFO mapreduce.Job:  map 24% reduce 0%
17/10/06 10:19:20 INFO mapreduce.Job:  map 29% reduce 0%
17/10/06 10:19:21 INFO mapreduce.Job:  map 32% reduce 0%
17/10/06 10:19:23 INFO mapreduce.Job:  map 37% reduce 0%
17/10/06 10:19:24 INFO mapreduce.Job:  map 40% reduce 0%
17/10/06 10:19:25 INFO mapreduce.Job:  map 41% reduce 0%
17/10/06 10:19:26 INFO mapreduce.Job:  map 44% reduce 0%
17/10/06 10:19:27 INFO mapreduce.Job:  map 45% reduce 0%
17/10/06 10:19:29 INFO mapreduce.Job:  map 47% reduce 0%
17/10/06 10:19:30 INFO mapreduce.Job:  map 48% reduce 0%
17/10/06 10:19:32 INFO mapreduce.Job:  map 51% reduce 0%
17/10/06 10:19:33 INFO mapreduce.Job:  map 52% reduce 0%
17/10/06 10:19:35 INFO mapreduce.Job:  map 53% reduce 0%
17/10/06 10:19:36 INFO mapreduce.Job:  map 54% reduce 0%
17/10/06 10:19:37 INFO mapreduce.Job:  map 56% reduce 0%
17/10/06 10:19:39 INFO mapreduce.Job:  map 58% reduce 0%
17/10/06 10:19:40 INFO mapreduce.Job:  map 60% reduce 0%
17/10/06 10:19:42 INFO mapreduce.Job:  map 62% reduce 0%
17/10/06 10:19:44 INFO mapreduce.Job:  map 63% reduce 0%
17/10/06 10:19:45 INFO mapreduce.Job:  map 64% reduce 0%
17/10/06 10:19:46 INFO mapreduce.Job:  map 65% reduce 0%
17/10/06 10:19:48 INFO mapreduce.Job:  map 66% reduce 0%
17/10/06 10:19:55 INFO mapreduce.Job:  map 68% reduce 0%
17/10/06 10:19:57 INFO mapreduce.Job:  map 70% reduce 0%
17/10/06 10:20:00 INFO mapreduce.Job:  map 71% reduce 0%
17/10/06 10:20:01 INFO mapreduce.Job:  map 73% reduce 0%
17/10/06 10:20:03 INFO mapreduce.Job:  map 74% reduce 0%
17/10/06 10:20:05 INFO mapreduce.Job:  map 75% reduce 0%
17/10/06 10:20:06 INFO mapreduce.Job:  map 76% reduce 0%
17/10/06 10:20:07 INFO mapreduce.Job:  map 77% reduce 0%
17/10/06 10:20:09 INFO mapreduce.Job:  map 78% reduce 0%
17/10/06 10:20:10 INFO mapreduce.Job:  map 80% reduce 0%
17/10/06 10:20:13 INFO mapreduce.Job:  map 81% reduce 0%
17/10/06 10:20:14 INFO mapreduce.Job:  map 82% reduce 0%
17/10/06 10:20:15 INFO mapreduce.Job:  map 83% reduce 0%
17/10/06 10:20:16 INFO mapreduce.Job:  map 85% reduce 0%
17/10/06 10:20:17 INFO mapreduce.Job:  map 86% reduce 0%
17/10/06 10:20:18 INFO mapreduce.Job:  map 87% reduce 0%
17/10/06 10:20:19 INFO mapreduce.Job:  map 90% reduce 0%
17/10/06 10:20:20 INFO mapreduce.Job:  map 92% reduce 0%
17/10/06 10:20:21 INFO mapreduce.Job:  map 94% reduce 0%
17/10/06 10:20:22 INFO mapreduce.Job:  map 98% reduce 0%
17/10/06 10:20:24 INFO mapreduce.Job:  map 100% reduce 0%
17/10/06 10:20:24 INFO mapreduce.Job: Job job_1507297665951_0001 completed successfully
17/10/06 10:20:24 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=1484150
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=1025
                HDFS: Number of bytes written=6553600000
                HDFS: Number of read operations=48
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=24
        Job Counters
                Launched map tasks=12
                Other local map tasks=12
                Total time spent by all maps in occupied slots (ms)=935906
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=935906
                Total vcore-seconds taken by all map tasks=935906
                Total megabyte-seconds taken by all map tasks=958367744
        Map-Reduce Framework
                Map input records=65536000
                Map output records=65536000
                Input split bytes=1025
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=2178
                CPU time spent (ms)=147290
                Physical memory (bytes) snapshot=2332233728
                Virtual memory (bytes) snapshot=13812547584
                Total committed heap usage (bytes)=4391436288
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=140750829423462787
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=6553600000
				
#The result of the time command:

real    1m32.794s
user    0m4.965s
sys     0m0.291s

#The command and output of hdfs dfs -ls /user/saturn/tgen:

[saturn@ip-172-31-18-5 ec2-user]$ hdfs dfs -ls /user/saturn/tgen
Found 13 items
-rw-r--r--   3 saturn supergroup          0 2017-10-06 10:20 /user/saturn/tgen/_SUCCESS
-rw-r--r--   3 saturn supergroup  546133400 2017-10-06 10:20 /user/saturn/tgen/part-m-00000
-rw-r--r--   3 saturn supergroup  546133300 2017-10-06 10:20 /user/saturn/tgen/part-m-00001
-rw-r--r--   3 saturn supergroup  546133300 2017-10-06 10:20 /user/saturn/tgen/part-m-00002
-rw-r--r--   3 saturn supergroup  546133400 2017-10-06 10:20 /user/saturn/tgen/part-m-00003
-rw-r--r--   3 saturn supergroup  546133300 2017-10-06 10:20 /user/saturn/tgen/part-m-00004
-rw-r--r--   3 saturn supergroup  546133300 2017-10-06 10:20 /user/saturn/tgen/part-m-00005
-rw-r--r--   3 saturn supergroup  546133400 2017-10-06 10:20 /user/saturn/tgen/part-m-00006
-rw-r--r--   3 saturn supergroup  546133300 2017-10-06 10:20 /user/saturn/tgen/part-m-00007
-rw-r--r--   3 saturn supergroup  546133300 2017-10-06 10:20 /user/saturn/tgen/part-m-00008
-rw-r--r--   3 saturn supergroup  546133400 2017-10-06 10:20 /user/saturn/tgen/part-m-00009
-rw-r--r--   3 saturn supergroup  546133300 2017-10-06 10:20 /user/saturn/tgen/part-m-00010
-rw-r--r--   3 saturn supergroup  546133300 2017-10-06 10:20 /user/saturn/tgen/part-m-00011


#The command and output of hadoop fsck -blocks /user/saturn:

[saturn@ip-172-31-18-5 ec2-user]$ hadoop fsck -blocks /user/saturn
DEPRECATED: Use of this script to execute hdfs command is deprecated.
Instead use the hdfs command for it.

Connecting to namenode via http://ip-172-31-18-5.us-west-2.compute.internal:50070
FSCK started by saturn (auth:SIMPLE) from /172.31.18.5 for path /user/saturn at Fri Oct 06 10:23:05 EDT 2017
.............Status: HEALTHY
 Total size:    6553600000 B
 Total dirs:    3
 Total files:   13
 Total symlinks:                0
 Total blocks (validated):      204 (avg. block size 32125490 B)
 Minimally replicated blocks:   204 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Fri Oct 06 10:23:05 EDT 2017 in 12 milliseconds


The filesystem under path '/user/saturn' is HEALTHY



```