``` 

Create Directory and Load Zip to HDFS

[gastonorellana@ip-172-31-13-83 ec2-user]$ hdfs dfs -mkdir -p precious

[gastonorellana@ip-172-31-13-83 ec2-user]$ ls /tmp | grep SEBC*
SEBC-master-students.zip

[gastonorellana@ip-172-31-13-83 ec2-user]$ ^C
[gastonorellana@ip-172-31-13-83 ec2-user]$ hdfs dfs -put /tmp/SEBC-master-students.zip /precious
put: Permission denied: user=gastonorellana, access=WRITE, inode="/":hdfs:supergroup:drwxr-xr-x
[gastonorellana@ip-172-31-13-83 ec2-user]$ exit
exit
[root@ip-172-31-13-83 ec2-user]# chmod 777 /tmp/SEBC-master-students.zip
[root@ip-172-31-13-83 ec2-user]# su gastonorellana
[gastonorellana@ip-172-31-13-83 ec2-user]$ hdfs dfs -put /tmp/SEBC-master-students.zip /precious
put: Permission denied: user=gastonorellana, access=WRITE, inode="/":hdfs:supergroup:drwxr-xr-x
[gastonorellana@ip-172-31-13-83 ec2-user]$ hdfs dfs -put /tmp/SEBC-master-students.zip precious

[gastonorellana@ip-172-31-13-83 ec2-user]$ hdfs dfs -ls /user/gastonorellana/precious
Found 1 items
-rw-r--r--   3 gastonorellana supergroup     474831 2017-10-03 10:22 /user/gastonorellana/precious/SEBC-master-students.zip


Enable SnapShot


[root@ip-172-31-13-83 ec2-user]#  sudo -u hdfs hdfs dfsadmin -allowSnapshot /user/gastonorellana/precious
Allowing snaphot on /user/gastonorellana/precious succeeded

Create Snapshot

[root@ip-172-31-13-83 ec2-user]#  sudo -u hdfs hdfs dfs -CreateSnapshot /user/gastonorellana/precious sebc-hdfs-test
-CreateSnapshot: Unknown command
[root@ip-172-31-13-83 ec2-user]#  sudo -u hdfs hdfs dfs -createSnapshot /user/gastonorellana/precious sebc-hdfs-test
Created snapshot /user/gastonorellana/precious/.snapshot/sebc-hdfs-test


[root@ip-172-31-13-83 ec2-user]#  sudo -u hdfs hdfs dfs -ls /user/gastonorellana/precious/.snapshot/sebc-hdfs-test
Found 1 items
-rw-r--r--   3 gastonorellana supergroup     474831 2017-10-03 10:22 /user/gastonorellana/precious/.snapshot/sebc-hdfs-test/SEBC-master-students.zip

Delete Directory

[root@ip-172-31-13-83 ec2-user]#  sudo -u hdfs hdfs dfs -rm -r /user/gastonorellana/precious
rm: Failed to move to trash: hdfs://ip-172-31-13-83.us-west-2.compute.internal:8020/user/gastonorellana/precious: The directory /user/gastonorellana/precious cannot be deleted since /user/gastonorellana/precious is snapshottable and already has snapshots


Delete Zip

[root@ip-172-31-13-83 ec2-user]#  sudo -u hdfs hdfs dfs -rm -r /user/gastonorellana/precious/SEBC-master-students.zip
17/10/03 10:43:02 INFO fs.TrashPolicyDefault: Moved: 'hdfs://ip-172-31-13-83.us-west-2.compute.internal:8020/user/gastonorellana/precious/SEBC-master-students.zip' to trash at: hdfs://ip-172-31-13-83.us-west-2.compute.internal:8020/user/hdfs/.Trash/Current/user/gastonorellana/precious/SEBC-master-students.zip

[root@ip-172-31-13-83 ec2-user]#  sudo -u hdfs hdfs dfs -ls /user/gastonorellana/precious
[root@ip-172-31-13-83 ec2-user]#

Restore Zip

[root@ip-172-31-13-83 ec2-user]#  sudo -u hdfs hdfs dfs -cp /user/gastonorellana/precious/.snapshot/sebc-hdfs-test/SEBC-master-students.zip /user/gastonorellana/precious/
[root@ip-172-31-13-83 ec2-user]# sudo -u hdfs hdfs dfs -ls /user/gastonorellana/precious
Found 1 items
-rw-r--r--   3 hdfs supergroup     474831 2017-10-03 10:49 /user/gastonorellana/precious/SEBC-master-students.zip


``` 