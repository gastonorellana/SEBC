1. Check swappiness 

[ec2-user@ip-172-31-13-246 ~]$ sysctl vm.swappiness
vm.swappiness = 30
[ec2-user@ip-172-31-13-246 ~]$ sudo sysctl -w vm.swappiness="1"
vm.swappiness = 1
[ec2-user@ip-172-31-13-246 ~]$ sysctl vm.swappiness
vm.swappiness = 1

Para evitar el cambio al reiniciar. 
Add vm.swappiness=1
[root@ip-172-31-13-246 ec2-user]# vi /etc/sysctl.conf

[root@ip-172-31-13-246 ec2-user]# tail -2 /etc/sysctl.conf
# For more information, see sysctl.conf(5) and sysctl.d(5).
vm.swappiness=1


2. Show the mount attributes

df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2      120G  931M  120G   1% /
devtmpfs         15G     0   15G   0% /dev
tmpfs            15G     0   15G   0% /dev/shm
tmpfs            15G   17M   15G   1% /run
tmpfs            15G     0   15G   0% /sys/fs/cgroup
/dev/xvdb       118G   61M  112G   1% /disk01
/dev/xvdc       118G   61M  112G   1% /disk02
tmpfs           3.0G     0  3.0G   0% /run/user/1000

3. List the reserve space
[root@ip-172-31-13-246 ec2-user]# cat /etc/fstab

#
# /etc/fstab
# Created by anaconda on Mon Nov  9 20:20:10 2015
#
# Accessible filesystems, by reference, are maintained under '/dev/disk'
# See man pages fstab(5), findfs(8), mount(8) and/or blkid(8) for more info
#
UUID=379de64d-ea11-4f5b-ae6a-0aa50ff7b24d /                       xfs     defaults        0 0
UUID=a2c40d87-381b-4543-a47a-2b314d0c96d7 /disk01 ext4 defaults 0 0
UUID=b45b636c-c30a-4888-a38d-543af46338fe /disk02 ext4 defaults 0 0


4. Disable THP
[root@ip-172-31-13-246 ec2-user]# echo never > /sys/kernel/mm/transparent_hugepage/enabled
[root@ip-172-31-13-246 ec2-user]# cat /sys/kernel/mm/transparent_hugepage/enabled
always madvise [never]

[root@ip-172-31-13-246 ec2-user]# cat /sys/kernel/mm/transparent_hugepage/defrag
[always] madvise never
[root@ip-172-31-13-246 ec2-user]# echo never > /sys/kernel/mm/transparent_hugepage/defrag
[root@ip-172-31-13-246 ec2-user]# cat /sys/kernel/mm/transparent_hugepage/defrag
always madvise [never]
[root@ip-172-31-13-246 ec2-user]#

THP Permanente
[root@ip-172-31-13-246 ec2-user]# tail -2 /etc/rc.local
echo never > /sys/kernel/mm/transparent_hugepage/enabled
echo never > /sys/kernel/mm/transparent_hugepage/defrag


5. List your network interface configuration

[root@ip-172-31-13-246 ec2-user]# ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.31.13.246  netmask 255.255.240.0  broadcast 172.31.15.255
        inet6 fe80::860:9cff:fe31:a474  prefixlen 64  scopeid 0x20<link>
        ether 0a:60:9c:31:a4:74  txqueuelen 1000  (Ethernet)
        RX packets 2776  bytes 263276 (257.1 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 2544  bytes 449813 (439.2 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 0  (Local Loopback)
        RX packets 4  bytes 340 (340.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 4  bytes 340 (340.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
 
 
6. forward and reverse host lookups

 [root@ip-172-31-13-246 ec2-user]# getent hosts 172.31.13.83
172.31.13.83    ip-172-31-13-83.us-west-2.compute.internal N2

6. nscd service

[root@ip-172-31-13-246 ec2-user]# sudo yum install nscd
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
Resolving Dependencies
--> Running transaction check
---> Package nscd.x86_64 0:2.17-196.el7 will be installed
--> Processing Dependency: glibc = 2.17-196.el7 for package: nscd-2.17-196.el7.x86_64
--> Running transaction check
---> Package glibc.x86_64 0:2.17-105.el7 will be updated
--> Processing Dependency: glibc = 2.17-105.el7 for package: glibc-common-2.17-105.el7.x86_64
---> Package glibc.x86_64 0:2.17-196.el7 will be an update
--> Running transaction check
---> Package glibc-common.x86_64 0:2.17-105.el7 will be updated
---> Package glibc-common.x86_64 0:2.17-196.el7 will be an update
--> Finished Dependency Resolution

Dependencies Resolved

=========================================================================================================================================
 Package                      Arch                   Version                      Repository                                        Size
=========================================================================================================================================
Installing:
 nscd                         x86_64                 2.17-196.el7                 rhui-REGION-rhel-server-releases                 273 k
Updating for dependencies:
 glibc                        x86_64                 2.17-196.el7                 rhui-REGION-rhel-server-releases                 3.6 M
 glibc-common                 x86_64                 2.17-196.el7                 rhui-REGION-rhel-server-releases                  11 M

Transaction Summary
=========================================================================================================================================
Install  1 Package
Upgrade             ( 2 Dependent packages)

Total download size: 15 M
Is this ok [y/d/N]: y
Downloading packages:
Delta RPMs disabled because /usr/bin/applydeltarpm not installed.
(1/3): glibc-2.17-196.el7.x86_64.rpm                                                                              | 3.6 MB  00:00:00
(2/3): nscd-2.17-196.el7.x86_64.rpm                                                                               | 273 kB  00:00:00
(3/3): glibc-common-2.17-196.el7.x86_64.rpm                                                                       |  11 MB  00:00:00
-----------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                     25 MB/s |  15 MB  00:00:00
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Updating   : glibc-2.17-196.el7.x86_64                                                                                             1/5
warning: /etc/nsswitch.conf created as /etc/nsswitch.conf.rpmnew
  Updating   : glibc-common-2.17-196.el7.x86_64                                                                                      2/5
  Installing : nscd-2.17-196.el7.x86_64                                                                                              3/5
  Cleanup    : glibc-2.17-105.el7.x86_64                                                                                             4/5
  Cleanup    : glibc-common-2.17-105.el7.x86_64                                                                                      5/5
  Verifying  : glibc-common-2.17-196.el7.x86_64                                                                                      1/5
  Verifying  : nscd-2.17-196.el7.x86_64                                                                                              2/5
  Verifying  : glibc-2.17-196.el7.x86_64                                                                                             3/5
  Verifying  : glibc-2.17-105.el7.x86_64                                                                                             4/5
  Verifying  : glibc-common-2.17-105.el7.x86_64                                                                                      5/5

Installed:
  nscd.x86_64 0:2.17-196.el7

Dependency Updated:
  glibc.x86_64 0:2.17-196.el7                                     glibc-common.x86_64 0:2.17-196.el7

Complete!

[root@ip-172-31-13-246 ec2-user]# ^C
[root@ip-172-31-13-246 ec2-user]# service nscd status
Redirecting to /bin/systemctl status  nscd.service
? nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; disabled; vendor preset: disabled)
   Active: inactive (dead)
[root@ip-172-31-13-246 ec2-user]# service nscd start
Redirecting to /bin/systemctl start  nscd.service
[root@ip-172-31-13-246 ec2-user]# service nscd status
Redirecting to /bin/systemctl status  nscd.service
? nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; disabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-10-02 13:36:43 EDT; 13s ago
  Process: 9707 ExecStart=/usr/sbin/nscd $NSCD_OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 9708 (nscd)
   CGroup: /system.slice/nscd.service
           +-9708 /usr/sbin/nscd

Oct 02 13:36:43 ip-172-31-13-246.us-west-2.compute.internal nscd[9708]: 9708 monitoring directory `/etc` (2)
Oct 02 13:36:43 ip-172-31-13-246.us-west-2.compute.internal nscd[9708]: 9708 monitoring file `/etc/hosts` (4)
Oct 02 13:36:43 ip-172-31-13-246.us-west-2.compute.internal nscd[9708]: 9708 monitoring directory `/etc` (2)
Oct 02 13:36:43 ip-172-31-13-246.us-west-2.compute.internal nscd[9708]: 9708 monitoring file `/etc/resolv.conf` (5)
Oct 02 13:36:43 ip-172-31-13-246.us-west-2.compute.internal nscd[9708]: 9708 monitoring directory `/etc` (2)
Oct 02 13:36:43 ip-172-31-13-246.us-west-2.compute.internal nscd[9708]: 9708 monitoring file `/etc/services` (6)
Oct 02 13:36:43 ip-172-31-13-246.us-west-2.compute.internal nscd[9708]: 9708 monitoring directory `/etc` (2)
Oct 02 13:36:43 ip-172-31-13-246.us-west-2.compute.internal nscd[9708]: 9708 disabled inotify-based monitoring for file `/etc/netg...tory
Oct 02 13:36:43 ip-172-31-13-246.us-west-2.compute.internal nscd[9708]: 9708 stat failed for file `/etc/netgroup'; will try again ...tory
Oct 02 13:36:43 ip-172-31-13-246.us-west-2.compute.internal systemd[1]: Started Name Service Cache Daemon.
Hint: Some lines were ellipsized, use -l to show in full.

****NTP SERVICES

[root@ip-172-31-13-246 ec2-user]# service ntpd status
Redirecting to /bin/systemctl status  ntpd.service
? ntpd.service
   Loaded: not-found (Reason: No such file or directory)
   Active: inactive (dead)
[root@ip-172-31-13-246 ec2-user]# yum install ntp
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
Resolving Dependencies
--> Running transaction check
---> Package ntp.x86_64 0:4.2.6p5-25.el7_3.2 will be installed
--> Processing Dependency: ntpdate = 4.2.6p5-25.el7_3.2 for package: ntp-4.2.6p5-25.el7_3.2.x86_64
--> Processing Dependency: libopts.so.25()(64bit) for package: ntp-4.2.6p5-25.el7_3.2.x86_64
--> Running transaction check
---> Package autogen-libopts.x86_64 0:5.18-5.el7 will be installed
---> Package ntpdate.x86_64 0:4.2.6p5-25.el7_3.2 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

=========================================================================================================================================
 Package                      Arch                Version                            Repository                                     Size
=========================================================================================================================================
Installing:
 ntp                          x86_64              4.2.6p5-25.el7_3.2                 rhui-REGION-rhel-server-releases              547 k
Installing for dependencies:
 autogen-libopts              x86_64              5.18-5.el7                         rhui-REGION-rhel-server-releases               66 k
 ntpdate                      x86_64              4.2.6p5-25.el7_3.2                 rhui-REGION-rhel-server-releases               86 k

Transaction Summary
=========================================================================================================================================
Install  1 Package (+2 Dependent packages)

Total download size: 699 k
Installed size: 1.6 M
Is this ok [y/d/N]: y
Downloading packages:
(1/3): ntp-4.2.6p5-25.el7_3.2.x86_64.rpm                                                                          | 547 kB  00:00:00
(2/3): autogen-libopts-5.18-5.el7.x86_64.rpm                                                                      |  66 kB  00:00:00
(3/3): ntpdate-4.2.6p5-25.el7_3.2.x86_64.rpm                                                                      |  86 kB  00:00:00
-----------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                    1.3 MB/s | 699 kB  00:00:00
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Installing : ntpdate-4.2.6p5-25.el7_3.2.x86_64                                                                                     1/3
  Installing : autogen-libopts-5.18-5.el7.x86_64                                                                                     2/3
  Installing : ntp-4.2.6p5-25.el7_3.2.x86_64                                                                                         3/3
  Verifying  : autogen-libopts-5.18-5.el7.x86_64                                                                                     1/3
  Verifying  : ntp-4.2.6p5-25.el7_3.2.x86_64                                                                                         2/3
  Verifying  : ntpdate-4.2.6p5-25.el7_3.2.x86_64                                                                                     3/3

Installed:
  ntp.x86_64 0:4.2.6p5-25.el7_3.2

Dependency Installed:
  autogen-libopts.x86_64 0:5.18-5.el7                                 ntpdate.x86_64 0:4.2.6p5-25.el7_3.2

Complete!
[root@ip-172-31-13-246 ec2-user]# service ntpd status
Redirecting to /bin/systemctl status  ntpd.service
? ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; disabled; vendor preset: disabled)
   Active: inactive (dead)
[root@ip-172-31-13-246 ec2-user]# service ntpd start
Redirecting to /bin/systemctl start  ntpd.service
[root@ip-172-31-13-246 ec2-user]# service ntpd status
Redirecting to /bin/systemctl status  ntpd.service
? ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; disabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-10-02 13:40:25 EDT; 9s ago
  Process: 9815 ExecStart=/usr/sbin/ntpd -u ntp:ntp $OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 9816 (ntpd)
   CGroup: /system.slice/ntpd.service
           +-9816 /usr/sbin/ntpd -u ntp:ntp -g

Oct 02 13:40:25 ip-172-31-13-246.us-west-2.compute.internal ntpd[9816]: Listen normally on 2 lo 127.0.0.1 UDP 123
Oct 02 13:40:25 ip-172-31-13-246.us-west-2.compute.internal ntpd[9816]: Listen normally on 3 eth0 172.31.13.246 UDP 123
Oct 02 13:40:25 ip-172-31-13-246.us-west-2.compute.internal ntpd[9816]: Listen normally on 4 lo ::1 UDP 123
Oct 02 13:40:25 ip-172-31-13-246.us-west-2.compute.internal ntpd[9816]: Listen normally on 5 eth0 fe80::860:9cff:fe31:a474 UDP 123
Oct 02 13:40:25 ip-172-31-13-246.us-west-2.compute.internal ntpd[9816]: Listening on routing socket on fd #22 for interface updates
Oct 02 13:40:25 ip-172-31-13-246.us-west-2.compute.internal systemd[1]: Started Network Time Service.
Oct 02 13:40:25 ip-172-31-13-246.us-west-2.compute.internal ntpd[9816]: 0.0.0.0 c016 06 restart
Oct 02 13:40:25 ip-172-31-13-246.us-west-2.compute.internal ntpd[9816]: 0.0.0.0 c012 02 freq_set kernel 0.000 PPM
Oct 02 13:40:25 ip-172-31-13-246.us-west-2.compute.internal ntpd[9816]: 0.0.0.0 c011 01 freq_not_set
Oct 02 13:40:32 ip-172-31-13-246.us-west-2.compute.internal ntpd[9816]: 0.0.0.0 c614 04 freq_mode
