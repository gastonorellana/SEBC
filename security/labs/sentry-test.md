```
#Verify user privileges

[root@ip-172-31-13-83 282-hdfs-DATANODE]# groupadd -r bootcamp
[root@ip-172-31-13-83 282-hdfs-DATANODE]# gpasswd -a gastonorellana bootcamp
Adding user gastonorellana to group bootcamp
[root@ip-172-31-13-83 282-hdfs-DATANODE]# ^C
[root@ip-172-31-13-83 282-hdfs-DATANODE]# ^C
[root@ip-172-31-13-83 282-hdfs-DATANODE]# beeline
Beeline version 1.1.0-cdh5.11.2 by Apache Hive
beeline>  !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-13-83.us-west-2.compute.internal@AGNOSTIC.COM
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-13-83.us-west-2.compute.internal@AGNOSTIC.COM
Connected to: Apache Hive (version 1.1.0-cdh5.11.2)
Driver: Hive JDBC (version 1.1.0-cdh5.11.2)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171004162222_d4f6caa8-b1f1-41fa-a034-3c5e092df5d6): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171004162222_d4f6caa8-b1f1-41fa-a034-3c5e092df5d6); Time taken: 0.081 seconds
INFO  : Executing command(queryId=hive_20171004162222_d4f6caa8-b1f1-41fa-a034-3c5e092df5d6): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171004162222_d4f6caa8-b1f1-41fa-a034-3c5e092df5d6); Time taken: 0.172 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (0.363 seconds)


#kinit as george and ferdinand

[root@ip-172-31-13-83 ~]# kinit george
Password for george@AGNOSTIC.COM:
[root@ip-172-31-13-83 ~]# beeline
Beeline version 1.1.0-cdh5.11.2 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-13-83.us-west-2.compute.internal@AGNOSTIC.COM
scan complete in 1ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-13-83.us-west-2.compute.internal@AGNOSTIC.COM
Connected to: Apache Hive (version 1.1.0-cdh5.11.2)
Driver: Hive JDBC (version 1.1.0-cdh5.11.2)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171004163535_70d7c367-6932-4326-865d-6d9495c8a6b8): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171004163535_70d7c367-6932-4326-865d-6d9495c8a6b8); Time taken: 0.076 seconds
INFO  : Executing command(queryId=hive_20171004163535_70d7c367-6932-4326-865d-6d9495c8a6b8): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171004163535_70d7c367-6932-4326-865d-6d9495c8a6b8); Time taken: 0.164 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.36 seconds)
0: jdbc:hive2://localhost:10000/default>


[root@ip-172-31-13-83 ~]# kinit ferdinand
Password for ferdinand@AGNOSTIC.COM:
[root@ip-172-31-13-83 ~]# beeline
Beeline version 1.1.0-cdh5.11.2 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-13-83.us-west-2.compute.internal@AGNOSTIC.COM
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-13-83.us-west-2.compute.internal@AGNOSTIC.COM
Connected to: Apache Hive (version 1.1.0-cdh5.11.2)
Driver: Hive JDBC (version 1.1.0-cdh5.11.2)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171004163737_59cc0233-eb8e-4d36-8aa0-534228a1abd1): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171004163737_59cc0233-eb8e-4d36-8aa0-534228a1abd1); Time taken: 0.072 seconds
INFO  : Executing command(queryId=hive_20171004163737_59cc0233-eb8e-4d36-8aa0-534228a1abd1): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171004163737_59cc0233-eb8e-4d36-8aa0-534228a1abd1); Time taken: 0.148 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.346 seconds)
0: jdbc:hive2://localhost:10000/default>

```
