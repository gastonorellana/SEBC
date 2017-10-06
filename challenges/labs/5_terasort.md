```
#Run the terasort program as user saturn with the output target /user/saturn/tsort

[root@ip-172-31-20-250 ec2-user]# kinit saturn
Password for saturn@GASTONORELLANA.HQ:


[root@ip-172-31-20-250 ec2-user]# time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar terasort tgen tsort
17/10/06 12:10:29 INFO terasort.TeraSort: starting
17/10/06 12:10:30 INFO hdfs.DFSClient: Created token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@GASTONORELLANA.HQ, renewer=yarn, realUser=, issueDate=1507306230602, maxDate=1507911030602, sequenceNumber=4, masterKeyId=4 on 172.31.18.5:8020
17/10/06 12:10:30 INFO security.TokenCache: Got dt for hdfs://ip-172-31-18-5.us-west-2.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.18.5:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@GASTONORELLANA.HQ, renewer=yarn, realUser=, issueDate=1507306230602, maxDate=1507911030602, sequenceNumber=4, masterKeyId=4)
17/10/06 12:10:30 INFO input.FileInputFormat: Total input paths to process : 12
Spent 328ms computing base-splits.
Spent 4ms computing TeraScheduler splits.
Computing input splits took 333ms
Sampling 10 splits of 204
Making 12 from 100000 sampled records
Computing parititions took 501ms
Spent 836ms computing partitions.

######El proceso falla ######


```