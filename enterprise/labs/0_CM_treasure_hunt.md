### What is ubertask optimization?
Ubertask optimization runs "sufficiently small" jobs sequentially within a single JVM.

### Where in CM is the Kerberos Security Realm value displayed?
CM -> Administration -> Settings -> Filter by Kerberos -> Look for "Kerberos Security Realm"

### Which CDH service(s) host a property for enabling Kerberos authentication?
YARN, HDFS, oozie, Hive, HUE, ZooKeeper

### How do you upgrade the CM agents?
http://<cmhost>:7180/cmf/upgrade has a wizard to upgrade the agents

### Give the tsquery statement used to chart Hue's CPU utilization?
SELECT cpu_system_rate + cpu_user_rate WHERE entityName = "hue-HUE_SERVER-b541d4a280beab774b3c99cea27d87ad" AND category = ROLE

### Name all the roles that make up the Hive service
HiveServer2, Hive Metastore server, hive gateway, webhcat server

### What steps must be completed before integrating Cloudera Manager with Kerberos?
* Make sure you have a KDC (either set one up or use your organization's existing one)
* Configure KDC to allow renewable tickets with non-zero ticket lifetimes
* If you are using Active Directory, make sure LDAP over TLS/SSL (LDAPS) is enabled for the Domain Controllers.
* Install the OS-specific packages for your cluster
* Create an account for Cloudera Manager that has the permissions to create other accounts in the KDC
