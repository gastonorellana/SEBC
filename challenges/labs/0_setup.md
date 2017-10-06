```

#Cloud provider 
is "AWS"

#List your instances by IP address and DNS name

N1 172.31.18.5 ip-172-31-18-5.us-west-2.compute.internal
N2 172.31.21.107 ip-172-31-21-107.us-west-2.compute.internal
N3 172.31-26.49 ip-172-31-26-49.us-west-2.compute.internal
N4 172.31.20.250 ip-172-31-20-250.us-west-2.compute.interna
N5 172.31.20.4 ip-172-31-20-4.us-west-2.compute.internal

#Linux Release

[root@ip-172-31-18-5 ec2-user]# cat /etc/redhat-release
Red Hat Enterprise Linux Server release 7.2 (Maipo)

#File system capacity

[root@ip-172-31-18-5 ec2-user]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2      120G  1.3G  119G   2% /
devtmpfs         15G     0   15G   0% /dev
tmpfs            15G     0   15G   0% /dev/shm
tmpfs            15G   17M   15G   1% /run
tmpfs            15G     0   15G   0% /sys/fs/cgroup
tmpfs           3.0G     0  3.0G   0% /run/user/1000
tmpfs           3.0G     0  3.0G   0% /run/user/0


#Command and output for yum repolist enabled

[root@ip-172-31-18-5 ec2-user]# yum repolist enabled
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
rhui-REGION-client-config-server-7                                                                                | 2.9 kB  00:00:00
rhui-REGION-rhel-server-releases                                                                                  | 3.5 kB  00:00:00
rhui-REGION-rhel-server-rh-common                                                                                 | 3.8 kB  00:00:00
(1/7): rhui-REGION-client-config-server-7/x86_64/primary_db                                                       | 5.4 kB  00:00:00
(2/7): rhui-REGION-rhel-server-releases/7Server/x86_64/group                                                      | 709 kB  00:00:00
(3/7): rhui-REGION-rhel-server-rh-common/7Server/x86_64/group                                                     |  104 B  00:00:00
(4/7): rhui-REGION-rhel-server-releases/7Server/x86_64/updateinfo                                                 | 2.3 MB  00:00:00
(5/7): rhui-REGION-rhel-server-rh-common/7Server/x86_64/primary_db                                                | 119 kB  00:00:00
(6/7): rhui-REGION-rhel-server-rh-common/7Server/x86_64/updateinfo                                                |  32 kB  00:00:00
(7/7): rhui-REGION-rhel-server-releases/7Server/x86_64/primary_db                                                 |  43 MB  00:00:00
repo id                                                   repo name                                                                status
rhui-REGION-client-config-server-7/x86_64                 Red Hat Update Infrastructure 2.0 Client Configuration Server 7               6
rhui-REGION-rhel-server-releases/7Server/x86_64           Red Hat Enterprise Linux Server 7 (RPMs)                                 17,249
rhui-REGION-rhel-server-rh-common/7Server/x86_64          Red Hat Enterprise Linux Server 7 RH Common (RPMs)                          228
repolist: 17,483

#List the /etc/passwd entries for saturn and haley  

cat /etc/passwd |grep -E "saturn|haley"

#List the /etc/group entries for comets and planets

cat /etc/group | grep -E "comets|planets"

```