[root@ip-172-31-26-225 ec2-user]# curl -X GET -u LivniGuy:cloudera 'http://localhost:7180/api/version'
v19

[root@ip-172-31-26-225 ec2-user]# curl -X GET -u LivniGuy:cloudera 'http://localhost:7180/api/v19/cm/version'
{
  "version" : "5.15.1",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20180731-0834",
  "gitHash" : "6e046fd999fd99e7e12299386ba69b23afa43c60",
  "snapshot" : false
}

[root@ip-172-31-26-225 ec2-user]# curl -X GET -u LivniGuy:cloudera 'http://localhost:7180/api/v19/users'
{
  "items" : [ {
    "name" : "LivniGuy",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  } ]
}

[root@ip-172-31-26-225 ec2-user]# curl -X GET -u LivniGuy:cloudera 'http://localhost:7180/api/v19/cm/scmDbInfo'
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}
