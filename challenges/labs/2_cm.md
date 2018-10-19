### ls /etc/yum.repos.d

```
[ec2-user@ip-172-31-24-148 yum.repos.d]$ ls /etc/yum.repos.d
cloudera-manager.repo  redhat-rhui-client-config.repo  redhat-rhui.repo  rhui-load-balancers.conf
```

### scm_prepare_database.sh command
```
sudo /usr/share/cmf/schema/scm_prepare_database.sh -h 172.31.26.77 mysql scm scm cloudera
```
