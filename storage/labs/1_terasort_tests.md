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


``` 