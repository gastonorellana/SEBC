``` 


[root@ip-172-31-13-83 ec2-user]# su gastonorellana
[gastonorellana@ip-172-31-13-83 ec2-user]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen -Ddfs.block.size=33554432 -Dmapred.map.tasks=4 10000000 terageninput
17/10/03 09:39:50 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-11-232.us-west-2.compute.internal/172.31.11.232:8032
17/10/03 09:39:51 INFO terasort.TeraGen: Generating 10000000 using 4
17/10/03 09:39:51 INFO mapreduce.JobSubmitter: number of splits:4
17/10/03 09:39:51 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/10/03 09:39:51 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/10/03 09:39:51 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1506977436863_0001
17/10/03 09:39:52 INFO impl.YarnClientImpl: Submitted application application_1506977436863_0001
17/10/03 09:39:52 INFO mapreduce.Job: The url to track the job: http://ip-172-31-11-232.us-west-2.compute.internal:8088/proxy/application_1506977436863_0001/
17/10/03 09:39:52 INFO mapreduce.Job: Running job: job_1506977436863_0001
17/10/03 09:39:59 INFO mapreduce.Job: Job job_1506977436863_0001 running in uber mode : false
17/10/03 09:39:59 INFO mapreduce.Job:  map 0% reduce 0%
17/10/03 09:40:14 INFO mapreduce.Job:  map 75% reduce 0%
17/10/03 09:40:15 INFO mapreduce.Job:  map 100% reduce 0%
17/10/03 09:40:15 INFO mapreduce.Job: Job job_1506977436863_0001 completed successfully
17/10/03 09:40:15 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=512760
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=337
                HDFS: Number of bytes written=1000000000
                HDFS: Number of read operations=16
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=8
        Job Counters
                Launched map tasks=4
                Other local map tasks=4
                Total time spent by all maps in occupied slots (ms)=53247
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=53247
                Total vcore-milliseconds taken by all map tasks=53247
                Total megabyte-milliseconds taken by all map tasks=54524928
        Map-Reduce Framework
                Map input records=10000000
                Map output records=10000000
                Input split bytes=337
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=546
                CPU time spent (ms)=29320
                Physical memory (bytes) snapshot=1493528576
                Virtual memory (bytes) snapshot=6403125248
                Total committed heap usage (bytes)=2296381440
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=21472776955442690
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=1000000000

Time
				
real    0m27.170s
user    0m5.051s
sys     0m0.279s


Terasort

[gastonorellana@ip-172-31-13-83 ec2-user]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar terasort terageninput teresortoutput
17/10/03 09:57:11 INFO terasort.TeraSort: starting
17/10/03 09:57:13 INFO input.FileInputFormat: Total input paths to process : 4
Spent 149ms computing base-splits.
Spent 2ms computing TeraScheduler splits.
Computing input splits took 152ms
Sampling 10 splits of 32
Making 16 from 100000 sampled records
Computing parititions took 533ms
Spent 687ms computing partitions.
17/10/03 09:57:13 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-11-232.us-west-2.compute.internal/172.31.11.232:8032
17/10/03 09:57:14 INFO mapreduce.JobSubmitter: number of splits:32
17/10/03 09:57:14 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1506977436863_0002
17/10/03 09:57:14 INFO impl.YarnClientImpl: Submitted application application_1506977436863_0002
17/10/03 09:57:14 INFO mapreduce.Job: The url to track the job: http://ip-172-31-11-232.us-west-2.compute.internal:8088/proxy/application_1506977436863_0002/
17/10/03 09:57:14 INFO mapreduce.Job: Running job: job_1506977436863_0002
17/10/03 09:57:20 INFO mapreduce.Job: Job job_1506977436863_0002 running in uber mode : false
17/10/03 09:57:20 INFO mapreduce.Job:  map 0% reduce 0%
17/10/03 09:57:28 INFO mapreduce.Job:  map 6% reduce 0%
17/10/03 09:57:29 INFO mapreduce.Job:  map 9% reduce 0%
17/10/03 09:57:33 INFO mapreduce.Job:  map 13% reduce 0%
17/10/03 09:57:34 INFO mapreduce.Job:  map 38% reduce 0%
17/10/03 09:57:35 INFO mapreduce.Job:  map 47% reduce 0%
17/10/03 09:57:36 INFO mapreduce.Job:  map 81% reduce 0%
17/10/03 09:57:37 INFO mapreduce.Job:  map 91% reduce 0%
17/10/03 09:57:41 INFO mapreduce.Job:  map 100% reduce 0%
17/10/03 09:57:45 INFO mapreduce.Job:  map 100% reduce 13%
17/10/03 09:57:46 INFO mapreduce.Job:  map 100% reduce 31%
17/10/03 09:57:47 INFO mapreduce.Job:  map 100% reduce 44%
17/10/03 09:57:48 INFO mapreduce.Job:  map 100% reduce 100%
17/10/03 09:57:48 INFO mapreduce.Job: Job job_1506977436863_0002 completed successfully
17/10/03 09:57:48 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=439895400
                FILE: Number of bytes written=880191484
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=1000005280
                HDFS: Number of bytes written=1000000000
                HDFS: Number of read operations=144
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=32
        Job Counters
                Launched map tasks=32
                Launched reduce tasks=16
                Data-local map tasks=32
                Total time spent by all maps in occupied slots (ms)=331105
                Total time spent by all reduces in occupied slots (ms)=134410
                Total time spent by all map tasks (ms)=331105
                Total time spent by all reduce tasks (ms)=134410
                Total vcore-milliseconds taken by all map tasks=331105
                Total vcore-milliseconds taken by all reduce tasks=134410
                Total megabyte-milliseconds taken by all map tasks=339051520
                Total megabyte-milliseconds taken by all reduce tasks=137635840
        Map-Reduce Framework
                Map input records=10000000
                Map output records=10000000
                Map output bytes=1020000000
                Map output materialized bytes=434068551
                Input split bytes=5280
                Combine input records=0
                Combine output records=0
                Reduce input groups=10000000
                Reduce shuffle bytes=434068551
                Reduce input records=10000000
                Reduce output records=10000000
                Spilled Records=20000000
                Shuffled Maps =512
                Failed Shuffles=0
                Merged Map outputs=512
                GC time elapsed (ms)=5360
                CPU time spent (ms)=205200
                Physical memory (bytes) snapshot=22361956352
                Virtual memory (bytes) snapshot=76987596800
                Total committed heap usage (bytes)=27173847040
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=1000000000
        File Output Format Counters
                Bytes Written=1000000000
17/10/03 09:57:48 INFO terasort.TeraSort: done

Time

real    0m37.694s
user    0m6.871s
sys     0m0.286s


``` 