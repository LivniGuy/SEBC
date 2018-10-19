```
[ec2-user@ip-172-31-24-148 yum.repos.d]$ hdfs dfs -ls /user
Found 6 items
drwxr-xr-x   - hdfs   supergroup          0 2018-10-19 09:15 /user/fullerton
drwxrwxrwx   - mapred hadoop              0 2018-10-19 09:11 /user/history
drwxrwxr-t   - hive   hive                0 2018-10-19 09:11 /user/hive
drwxrwxr-x   - hue    hue                 0 2018-10-19 09:12 /user/hue
drwxrwxr-x   - oozie  oozie               0 2018-10-19 09:12 /user/oozie
drwxr-xr-x   - hdfs   supergroup          0 2018-10-19 09:15 /user/raffles
[ec2-user@ip-172-31-24-148 yum.repos.d]$





[ec2-user@ip-172-31-24-148 yum.repos.d]$ curl -X GET -u admin:admin 'http://localhost:7180/api/v14/hosts'
{
  "items" : [ {
    "hostId" : "a90367ba-0d52-4650-8cf2-28f91eed5e3e",
    "ipAddress" : "172.31.24.148",
    "hostname" : "ip-172-31-24-148.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-24-148.eu-west-1.compute.internal:7180/cmf/hostRedirect/a90367ba-0d52-4650-8cf2-28f91eed5e3e",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15599267840
  }, {
    "hostId" : "dc77abd0-09c1-4a2d-844e-2fe076594d78",
    "ipAddress" : "172.31.24.159",
    "hostname" : "ip-172-31-24-159.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-24-148.eu-west-1.compute.internal:7180/cmf/hostRedirect/dc77abd0-09c1-4a2d-844e-2fe076594d78",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15599280128
  }, {
    "hostId" : "31be47bd-605a-4456-a7cf-748c0e504dd2",
    "ipAddress" : "172.31.25.209",
    "hostname" : "ip-172-31-25-209.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-24-148.eu-west-1.compute.internal:7180/cmf/hostRedirect/31be47bd-605a-4456-a7cf-748c0e504dd2",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15599280128
  }, {
    "hostId" : "3418f6a4-377b-4132-b602-1f85bd9f3d9c",
    "ipAddress" : "172.31.26.77",
    "hostname" : "ip-172-31-26-77.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-24-148.eu-west-1.compute.internal:7180/cmf/hostRedirect/3418f6a4-377b-4132-b602-1f85bd9f3d9c",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15599280128
  }, {
    "hostId" : "174e65d4-f84c-41fa-b006-033dd5f101c4",
    "ipAddress" : "172.31.31.40",
    "hostname" : "ip-172-31-31-40.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-24-148.eu-west-1.compute.internal:7180/cmf/hostRedirect/174e65d4-f84c-41fa-b006-033dd5f101c4",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15599280128
  } ]
}
```
