```
[root@ip-172-31-26-225 ec2-user]# curl -X POST -u LivniGuy:cloudera 'http://localhost:7180/api/v1/clusters/LivniGuy/services/hive/commands/stop'
{
  "id" : 790,
  "name" : "Stop",
  "startTime" : "2018-10-17T11:14:55.964Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}

[root@ip-172-31-26-225 ec2-user]# curl -X POST -u LivniGuy:cloudera 'http://localhost:7180/api/v1/clusters/LivniGuy/services/hive/commands/start'
{
  "id" : 794,
  "name" : "Start",
  "startTime" : "2018-10-17T11:15:37.150Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}

[root@ip-172-31-26-225 ec2-user]# curl -X GET -u LivniGuy:cloudera 'http://localhost:7180/api/v1/clusters/LivniGuy/services/hive'
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-31-26-225.eu-west-1.compute.internal:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD"
  } ],
  "configStale" : false
}
```
