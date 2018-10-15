### ssh with:
ssh -i ~/Downloads/sebc-madrid.pem ec2-user@52.31.90.43

### Check vm.swappiness on all your nodes:

[ec2-user@ip-172-31-26-225 ~]$ cat /proc/sys/vm/swappiness
30

[ec2-user@ip-172-31-26-225 ~]$ sudo sysctl -w vm.swappiness=1
vm.swappiness = 1
[ec2-user@ip-172-31-26-225 ~]$ cat /proc/sys/vm/swappiness
1

### Show the mount attributes of all volumes:

[ec2-user@ip-172-31-26-225 ~]$ mount
sysfs on /sys type sysfs (rw,nosuid,nodev,noexec,relatime,seclabel)
proc on /proc type proc (rw,nosuid,nodev,noexec,relatime)
devtmpfs on /dev type devtmpfs (rw,nosuid,seclabel,size=7594628k,nr_inodes=1898657,mode=755)
securityfs on /sys/kernel/security type securityfs (rw,nosuid,nodev,noexec,relatime)
tmpfs on /dev/shm type tmpfs (rw,nosuid,nodev,seclabel)
devpts on /dev/pts type devpts (rw,nosuid,noexec,relatime,seclabel,gid=5,mode=620,ptmxmode=000)
tmpfs on /run type tmpfs (rw,nosuid,nodev,seclabel,mode=755)
tmpfs on /sys/fs/cgroup type tmpfs (ro,nosuid,nodev,noexec,seclabel,mode=755)
cgroup on /sys/fs/cgroup/systemd type cgroup (rw,nosuid,nodev,noexec,relatime,seclabel,xattr,release_agent=/usr/lib/systemd/systemd-cgroups-agent,name=systemd)
pstore on /sys/fs/pstore type pstore (rw,nosuid,nodev,noexec,relatime)
cgroup on /sys/fs/cgroup/devices type cgroup (rw,nosuid,nodev,noexec,relatime,seclabel,devices)
cgroup on /sys/fs/cgroup/cpu,cpuacct type cgroup (rw,nosuid,nodev,noexec,relatime,seclabel,cpuacct,cpu)
cgroup on /sys/fs/cgroup/perf_event type cgroup (rw,nosuid,nodev,noexec,relatime,seclabel,perf_event)
cgroup on /sys/fs/cgroup/net_cls,net_prio type cgroup (rw,nosuid,nodev,noexec,relatime,seclabel,net_prio,net_cls)
cgroup on /sys/fs/cgroup/blkio type cgroup (rw,nosuid,nodev,noexec,relatime,seclabel,blkio)
cgroup on /sys/fs/cgroup/freezer type cgroup (rw,nosuid,nodev,noexec,relatime,seclabel,freezer)
cgroup on /sys/fs/cgroup/memory type cgroup (rw,nosuid,nodev,noexec,relatime,seclabel,memory)
cgroup on /sys/fs/cgroup/pids type cgroup (rw,nosuid,nodev,noexec,relatime,seclabel,pids)
cgroup on /sys/fs/cgroup/cpuset type cgroup (rw,nosuid,nodev,noexec,relatime,seclabel,cpuset)
cgroup on /sys/fs/cgroup/hugetlb type cgroup (rw,nosuid,nodev,noexec,relatime,seclabel,hugetlb)
configfs on /sys/kernel/config type configfs (rw,relatime)
/dev/xvda2 on / type xfs (rw,relatime,seclabel,attr2,inode64,noquota)
selinuxfs on /sys/fs/selinux type selinuxfs (rw,relatime)
mqueue on /dev/mqueue type mqueue (rw,relatime,seclabel)
debugfs on /sys/kernel/debug type debugfs (rw,relatime)
hugetlbfs on /dev/hugepages type hugetlbfs (rw,relatime,seclabel)
systemd-1 on /proc/sys/fs/binfmt_misc type autofs (rw,relatime,fd=26,pgrp=1,timeout=0,minproto=5,maxproto=5,direct,pipe_ino=12957)
tmpfs on /run/user/1000 type tmpfs (rw,nosuid,nodev,relatime,seclabel,size=1523368k,mode=700,uid=1000,gid=1000)

### Show the reserve space of any non-root, ext-based volumes:
[root@ip-172-31-26-225 ~]# df -hT | grep -i ext

[root@ip-172-31-26-225 ~]# df -hT | grep -v xfs
Filesystem     Type      Size  Used Avail Use% Mounted on
devtmpfs       devtmpfs  7.3G     0  7.3G   0% /dev
tmpfs          tmpfs     7.3G     0  7.3G   0% /dev/shm
tmpfs          tmpfs     7.3G   17M  7.3G   1% /run
tmpfs          tmpfs     7.3G     0  7.3G   0% /sys/fs/cgroup
tmpfs          tmpfs     1.5G     0  1.5G   0% /run/user/1000
tmpfs          tmpfs     1.5G     0  1.5G   0% /run/user/0


### Disable transparent hugepage support

[root@ip-172-31-26-225 ~]# cat /etc/rc.d/rc.local 
#!/bin/bash
# THIS FILE IS ADDED FOR COMPATIBILITY PURPOSES
#
# It is highly advisable to create own systemd services or udev rules
# to run scripts during boot instead of using this file.
#
# In contrast to previous versions due to parallel execution during boot
# this script will NOT be run after all other services.
#
# Please note that you must run 'chmod +x /etc/rc.d/rc.local' to ensure
# that this script will be executed during boot.

touch /var/lock/subsys/local
echo never > /sys/kernel/mm/transparent_hugepage/enabled
echo never > /sys/kernel/mm/transparent_hugepage/defrag

[root@ip-172-31-26-225 ~]# cat /sys/kernel/mm/transparent_hugepage/enabled
[always] madvise never
[root@ip-172-31-26-225 ~]# cat /sys/kernel/mm/transparent_hugepage/defrag 
[always] madvise never

[root@ip-172-31-26-225 ~]# echo never > /sys/kernel/mm/transparent_hugepage/enabled
[root@ip-172-31-26-225 ~]# echo never > /sys/kernel/mm/transparent_hugepage/defrag

[root@ip-172-31-26-225 ~]# cat /sys/kernel/mm/transparent_hugepage/defrag 
always madvise [never]
[root@ip-172-31-26-225 ~]# cat /sys/kernel/mm/transparent_hugepage/enabled
always madvise [never]

chmod +x /etc/rc.d/rc.local

Modified line: GRUB_CMDLINE_LINUX="console=ttyS0,115200n8 console=tty0 net.ifnames=0 crashkernel=auto transparent_hugepage=never"


### List your network interface configuration

[root@ip-172-31-26-225 ~]# ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.31.26.225  netmask 255.255.240.0  broadcast 172.31.31.255
        inet6 fe80::437:a0ff:fead:c442  prefixlen 64  scopeid 0x20<link>
        ether 06:37:a0:ad:c4:42  txqueuelen 1000  (Ethernet)
        RX packets 2418  bytes 190094 (185.6 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 1627  bytes 212123 (207.1 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 0  bytes 0 (0.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 0  bytes 0 (0.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0


### List forward and reverse host lookups using getent or nslookup

[root@ip-172-31-26-225 ~]# getent ahosts www.google.com
74.125.193.99   STREAM www.google.com
74.125.193.99   DGRAM  
74.125.193.99   RAW    
74.125.193.103  STREAM 
74.125.193.103  DGRAM  
74.125.193.103  RAW    
74.125.193.104  STREAM 
74.125.193.104  DGRAM  
74.125.193.104  RAW    
74.125.193.105  STREAM 
74.125.193.105  DGRAM  
74.125.193.105  RAW    
74.125.193.106  STREAM 
74.125.193.106  DGRAM  
74.125.193.106  RAW    
74.125.193.147  STREAM 
74.125.193.147  DGRAM  
74.125.193.147  RAW    
2a00:1450:400b:c00::93 STREAM 
2a00:1450:400b:c00::93 DGRAM  
2a00:1450:400b:c00::93 RAW


### Show the nscd service is running
yum install nscd -y
service nscd start
service nscd status

Redirecting to /bin/systemctl status nscd.service
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2018-10-15 13:50:56 UTC; 47s ago
 Main PID: 17522 (nscd)
   CGroup: /system.slice/nscd.service
           └─17522 /usr/sbin/nscd

Oct 15 13:50:56 ip-172-31-26-225.eu-west-1.compute.internal nscd[17522]: 17522 monitoring directory `/etc` (2)
Oct 15 13:50:56 ip-172-31-26-225.eu-west-1.compute.internal nscd[17522]: 17522 monitoring file `/etc/resolv.conf` (5)
Oct 15 13:50:56 ip-172-31-26-225.eu-west-1.compute.internal nscd[17522]: 17522 monitoring directory `/etc` (2)
Oct 15 13:50:56 ip-172-31-26-225.eu-west-1.compute.internal nscd[17522]: 17522 monitoring file `/etc/services` (6)
Oct 15 13:50:56 ip-172-31-26-225.eu-west-1.compute.internal nscd[17522]: 17522 monitoring directory `/etc` (2)
Oct 15 13:50:56 ip-172-31-26-225.eu-west-1.compute.internal nscd[17522]: 17522 disabled inotify-based monitoring for file `/etc/netgroup': No ...ctory
Oct 15 13:50:56 ip-172-31-26-225.eu-west-1.compute.internal nscd[17522]: 17522 stat failed for file `/etc/netgroup'; will try again later: No ...ctory
Oct 15 13:50:56 ip-172-31-26-225.eu-west-1.compute.internal nscd[17522]: 17522 Access Vector Cache (AVC) started
Oct 15 13:50:56 ip-172-31-26-225.eu-west-1.compute.internal systemd[1]: Started Name Service Cache Daemon.
Oct 15 13:51:15 ip-172-31-26-225.eu-west-1.compute.internal nscd[17522]: 17522 checking for monitored file `/etc/netgroup': No such file or directory
Hint: Some lines were ellipsized, use -l to show in full.


### Show the ntpd service is running
yum install ntp -y
chkconfig ntpd on
service ntpd start

[root@ip-172-31-26-225 ~]# service ntpd status
Redirecting to /bin/systemctl status ntpd.service
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2018-10-15 13:56:52 UTC; 2s ago
  Process: 17746 ExecStart=/usr/sbin/ntpd -u ntp:ntp $OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 17747 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─17747 /usr/sbin/ntpd -u ntp:ntp -g

Oct 15 13:56:52 ip-172-31-26-225.eu-west-1.compute.internal ntpd[17747]: Listen and drop on 0 v4wildcard 0.0.0.0 UDP 123
Oct 15 13:56:52 ip-172-31-26-225.eu-west-1.compute.internal ntpd[17747]: Listen and drop on 1 v6wildcard :: UDP 123
Oct 15 13:56:52 ip-172-31-26-225.eu-west-1.compute.internal ntpd[17747]: Listen normally on 2 lo 127.0.0.1 UDP 123
Oct 15 13:56:52 ip-172-31-26-225.eu-west-1.compute.internal ntpd[17747]: Listen normally on 3 eth0 172.31.26.225 UDP 123
Oct 15 13:56:52 ip-172-31-26-225.eu-west-1.compute.internal ntpd[17747]: Listen normally on 4 lo ::1 UDP 123
Oct 15 13:56:52 ip-172-31-26-225.eu-west-1.compute.internal ntpd[17747]: Listen normally on 5 eth0 fe80::437:a0ff:fead:c442 UDP 123
Oct 15 13:56:52 ip-172-31-26-225.eu-west-1.compute.internal ntpd[17747]: Listening on routing socket on fd #22 for interface updates
Oct 15 13:56:52 ip-172-31-26-225.eu-west-1.compute.internal ntpd[17747]: 0.0.0.0 c016 06 restart
Oct 15 13:56:52 ip-172-31-26-225.eu-west-1.compute.internal ntpd[17747]: 0.0.0.0 c012 02 freq_set kernel 0.000 PPM
Oct 15 13:56:52 ip-172-31-26-225.eu-west-1.compute.internal ntpd[17747]: 0.0.0.0 c011 01 freq_not_set


### MySQL/MariaDB Installation Lab:
sudo yum install mariadb-server

[root@ip-172-31-26-225 ~]# ll /var/lib/mysql/
total 0

mariadb root/123456


### Installing MySQL JDBC Driver
sudo yum install wget -y
wget https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.47.tar.gz
tar zxvf mysql-connector-java-5.1.47.tar.gz
sudo mkdir -p /usr/share/java/
cd mysql-connector-java-5.1.47
sudo cp mysql-connector-java-5.1.47-bin.jar /usr/share/java/mysql-connector-java.jar



MariaDB [(none)]> CREATE USER 'replication_user'@'%' IDENTIFIED BY 'bigs3cret';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> GRANT REPLICATION SLAVE ON *.* TO 'replication_user'@'%';
Query OK, 0 rows affected (0.00 sec)

Install slave with id=2

MariaDB [(none)]> FLUSH TABLES WITH READ LOCK;
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> SHOW MASTER STATUS;
+-------------------------+----------+--------------+------------------+
| File                    | Position | Binlog_Do_DB | Binlog_Ignore_DB |
+-------------------------+----------+--------------+------------------+
| mysql_binary_log.000003 |     4073 |              |                  |
+-------------------------+----------+--------------+------------------+
1 row in set (0.00 sec)

CHANGE MASTER TO
  MASTER_HOST='ec2-52-31-90-43.eu-west-1.compute.amazonaws.com',
  MASTER_USER='replication_user',
  MASTER_PASSWORD='123456',
  MASTER_PORT=3306,
  MASTER_LOG_FILE='mysql_binary_log.000003',
  MASTER_LOG_POS=5033,
  MASTER_CONNECT_RETRY=10;



MariaDB [(none)]> START SLAVE;
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> SHOW SLAVE STATUS \G
*************************** 1. row ***************************
               Slave_IO_State: Connecting to master
                  Master_Host: ec2-34-250-35-168.eu-west-1.compute.amazonaws.com
                  Master_User: replication_user
                  Master_Port: 3306
                Connect_Retry: 10
              Master_Log_File: mysql_binary_log.000003
          Read_Master_Log_Pos: 3961
               Relay_Log_File: master1-relay-bin.000001
                Relay_Log_Pos: 4
        Relay_Master_Log_File: mysql_binary_log.000003
             Slave_IO_Running: Connecting
            Slave_SQL_Running: Yes
              Replicate_Do_DB: 
          Replicate_Ignore_DB: 
           Replicate_Do_Table: 
       Replicate_Ignore_Table: 
      Replicate_Wild_Do_Table: 
  Replicate_Wild_Ignore_Table: 
                   Last_Errno: 0
                   Last_Error: 
                 Skip_Counter: 0
          Exec_Master_Log_Pos: 3961
              Relay_Log_Space: 245
              Until_Condition: None
               Until_Log_File: 
                Until_Log_Pos: 0
           Master_SSL_Allowed: No
           Master_SSL_CA_File: 
           Master_SSL_CA_Path: 
              Master_SSL_Cert: 
            Master_SSL_Cipher: 
               Master_SSL_Key: 
        Seconds_Behind_Master: NULL
Master_SSL_Verify_Server_Cert: No
                Last_IO_Errno: 1045
                Last_IO_Error: error connecting to master 'replication_user@ec2-34-250-35-168.eu-west-1.compute.amazonaws.com:3306' - retry-time: 10  retries: 86400  message: Access denied for user 'replication_user'@'ip-172-31-19-244.eu-west-1.compute.internal' (using password: YES)
               Last_SQL_Errno: 0
               Last_SQL_Error: 
  Replicate_Ignore_Server_Ids: 
             Master_Server_Id: 0
1 row in set (0.00 sec)




CREATE DATABASE scm DEFAULT CHARACTER SET utf8 DEFAULT COLLATE utf8_general_ci;
CREATE DATABASE amon DEFAULT CHARACTER SET utf8 DEFAULT COLLATE utf8_general_ci;
CREATE DATABASE rman DEFAULT CHARACTER SET utf8 DEFAULT COLLATE utf8_general_ci;
CREATE DATABASE hue DEFAULT CHARACTER SET utf8 DEFAULT COLLATE utf8_general_ci;
CREATE DATABASE metastore DEFAULT CHARACTER SET utf8 DEFAULT COLLATE utf8_general_ci;
CREATE DATABASE sentry DEFAULT CHARACTER SET utf8 DEFAULT COLLATE utf8_general_ci;
CREATE DATABASE nav DEFAULT CHARACTER SET utf8 DEFAULT COLLATE utf8_general_ci;
CREATE DATABASE navms DEFAULT CHARACTER SET utf8 DEFAULT COLLATE utf8_general_ci;
CREATE DATABASE oozie DEFAULT CHARACTER SET utf8 DEFAULT COLLATE utf8_general_ci;

GRANT ALL ON scm.* TO 'scm'@'%' IDENTIFIED BY '123456';
GRANT ALL ON amon.* TO 'amon'@'%' IDENTIFIED BY '123456';
GRANT ALL ON rman.* TO 'rman'@'%' IDENTIFIED BY '123456';
GRANT ALL ON hue.* TO 'hue'@'%' IDENTIFIED BY '123456';
GRANT ALL ON metastore.* TO 'hive'@'%' IDENTIFIED BY '123456';
GRANT ALL ON sentry.* TO 'sentry'@'%' IDENTIFIED BY '123456';
GRANT ALL ON nav.* TO 'nav'@'%' IDENTIFIED BY '123456';
GRANT ALL ON navms.* TO 'navms'@'%' IDENTIFIED BY '123456';
GRANT ALL ON oozie.* TO 'oozie'@'%' IDENTIFIED BY '123456';


MariaDB [(none)]> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| amon               |
| hue                |
| metastore          |
| mysql              |
| nav                |
| navms              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| sentry             |
+--------------------+
12 rows in set (0.00 sec)

MariaDB [(none)]> SHOW GRANTS FOR 'scm'@'%';
+----------------------------------------------------------------------------------------------------+
| Grants for scm@%                                                                                   |
+----------------------------------------------------------------------------------------------------+
| GRANT USAGE ON *.* TO 'scm'@'%' IDENTIFIED BY PASSWORD '*6BB4837EB74329105EE4568DDA7DC67ED2CA2AD9' |
| GRANT ALL PRIVILEGES ON `scm`.* TO 'scm'@'%'                                                       |
+----------------------------------------------------------------------------------------------------+
2 rows in set (0.00 sec)



### Installing CM:
sudo yum install oracle-j2sdk1.7
sudo yum install cloudera-manager-daemons cloudera-manager-server

/usr/share/cmf/schema/scm_prepare_database.sh mysql scm scm 123456

sudo service cloudera-scm-server start

2018-10-15 16:24:34,132 INFO WebServerImpl:com.cloudera.server.cmf.WebServerImpl: Started Jetty server.





