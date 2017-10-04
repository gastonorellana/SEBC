```

#The kinit command you use to authenticate your test user

[gastonorellana@ip-172-31-13-83 ec2-user]$ kinit gastonorellana
Password for gastonorellana@AGNOSTIC.COM:
[gastonorellana@ip-172-31-13-83 ec2-user]$ hdfs dfs -ls /
Found 2 items
drwxrwxrwt   - hdfs supergroup          0 2017-10-04 10:02 /tmp
drwxr-xr-x   - hdfs supergroup          0 2017-10-03 10:41 /user


#The output from a klist command listing your credentials and ticket lifetime

[gastonorellana@ip-172-31-13-83 ec2-user]$ klist
Ticket cache: FILE:/tmp/krb5cc_1001
Default principal: gastonorellana@AGNOSTIC.COM

Valid starting       Expires              Service principal
10/04/2017 11:29:38  10/05/2017 11:29:38  krbtgt/AGNOSTIC.COM@AGNOSTIC.COM
        renew until 10/11/2017 11:29:38
		
```