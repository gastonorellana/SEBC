```



#A command and output that shows the hostname of your database server

[root@ip-172-31-18-5 ec2-user]# hostname
ip-172-31-18-5.us-west-2.compute.internal


#A command and output that reports the database server version


[root@ip-172-31-18-5 ec2-user]# mysql --version
mysql  Ver 14.14 Distrib 5.6.37, for Linux (x86_64) using  EditLine wrapper




#A command and output that lists all the databases in the server

[root@ip-172-31-18-5 ec2-user]# mysql -uroot -p
Enter password:
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 4
Server version: 5.6.37 MySQL Community Server (GPL)

Copyright (c) 2000, 2017, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| amon               |
| hive               |
| hue                |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
+--------------------+
9 rows in set (0.00 sec)


```