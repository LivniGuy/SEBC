[root@ip-172-31-26-225 ec2-user]# curl -X GET -u "LivniGuy:cloudera" -i localhost:7180/api/v2/cm/deployment
HTTP/1.1 200 OK
Expires: Thu, 01-Jan-1970 00:00:00 GMT
Set-Cookie: CLOUDERA_MANAGER_SESSIONID=1l1er3uc45x6911438zghwabby;Path=/;HttpOnly
Content-Type: application/json
Date: Wed, 17 Oct 2018 10:39:36 GMT
Transfer-Encoding: chunked
Server: Jetty(6.1.26.cloudera.4)

{
  "timestamp" : "2018-10-17T10:39:36.073Z",
  "clusters" : [ {
    "name" : "LivniGuy",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "796917760"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "796917760"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "912680550"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "153"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-26-225.eu-west-1.compute.internal"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "123456"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-21a34b12feb52431f525ae862264a5f4",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "7147880d-170a-497e-a752-3740d83d21c6"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-3bc4f38b76a80a9f950eb869d87f4615",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "f4ea023f-a2a0-4d41-be84-90688610f4d8"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-7332336232d0be26e00b036b6a2f129b",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "5a5aa8c4-a0f4-4732-ad18-9e9218b8a290"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-844b258b9cf74554209628700c498013",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "806124bf-e49b-4d56-ae4c-2bb7955eeff8"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-b541d4a280beab774b3c99cea27d87ad",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "26b90466-f93b-4790-bbc5-567dd68a34d9"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-3bc4f38b76a80a9f950eb869d87f4615",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "f4ea023f-a2a0-4d41-be84-90688610f4d8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5zm5v69x7hqm625177w9dvgd8"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-3bc4f38b76a80a9f950eb869d87f4615",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "f4ea023f-a2a0-4d41-be84-90688610f4d8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5r1hhpbuawfhrrw6nqasbjf68"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "SERVER",
          "items" : [ {
            "name" : "zookeeper_server_java_heapsize",
            "value" : "796917760"
          } ]
        } ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-21a34b12feb52431f525ae862264a5f4",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "7147880d-170a-497e-a752-3740d83d21c6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "baieq424pjbtv0nk1w5zg75n7"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-3bc4f38b76a80a9f950eb869d87f4615",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "f4ea023f-a2a0-4d41-be84-90688610f4d8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bebvumq9qkmf58hez6ui49ekl"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-7332336232d0be26e00b036b6a2f129b",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "5a5aa8c4-a0f4-4732-ad18-9e9218b8a290"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "eif9zyezbo8eu6hvtwczf9kqh"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-172-31-26-225.eu-west-1.compute.internal"
        }, {
          "name" : "database_password",
          "value" : "123456"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-b541d4a280beab774b3c99cea27d87ad"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_LOAD_BALANCER-b541d4a280beab774b3c99cea27d87ad",
        "type" : "HUE_LOAD_BALANCER",
        "hostRef" : {
          "hostId" : "26b90466-f93b-4790-bbc5-567dd68a34d9"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2wiv4oqeltt0rf247vw5v5098"
          } ]
        }
      }, {
        "name" : "hue-HUE_SERVER-b541d4a280beab774b3c99cea27d87ad",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "26b90466-f93b-4790-bbc5-567dd68a34d9"
        },
        "config" : {
          "items" : [ {
            "name" : "navmetadataserver_cmdb_password",
            "value" : "cb6783e5-6c2d-4770-9e8d-d41a7fa23bc0"
          }, {
            "name" : "role_jceks_password",
            "value" : "e6nwzjefzwyfrm0yonpsz2tnt"
          }, {
            "name" : "secret_key",
            "value" : "Fhs6gOi7LPN5Pm0UAHS88JbDJZy5q7"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "ip-172-31-26-225.eu-west-1.compute.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "123456"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "989855744"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-b541d4a280beab774b3c99cea27d87ad",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "26b90466-f93b-4790-bbc5-567dd68a34d9"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ftyrxk405hyhkuz2lc24jctx"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "8"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "3"
          } ]
        }, {
          "roleType" : "JOBHISTORY",
          "items" : [ {
            "name" : "mr2_jobhistory_java_heapsize",
            "value" : "796917760"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "rm_cpu_shares",
            "value" : "1800"
          }, {
            "name" : "rm_io_weight",
            "value" : "900"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "3"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "3489"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "resource_manager_java_heapsize",
            "value" : "796917760"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "4477"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "3"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "90"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "hsYWmtHQgq6vZsb9rDwMQEGBI12v5q"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-GATEWAY-b541d4a280beab774b3c99cea27d87ad",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "26b90466-f93b-4790-bbc5-567dd68a34d9"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "yarn-JOBHISTORY-3bc4f38b76a80a9f950eb869d87f4615",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "f4ea023f-a2a0-4d41-be84-90688610f4d8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bscikgh9ccv2e5cbdnf9jvluv"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-21a34b12feb52431f525ae862264a5f4",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "7147880d-170a-497e-a752-3740d83d21c6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2to0cl458u4ofrx7rr9w33i8d"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-3bc4f38b76a80a9f950eb869d87f4615",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "f4ea023f-a2a0-4d41-be84-90688610f4d8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7rdlnqx3mhanktn1u8nn3d5xb"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-7332336232d0be26e00b036b6a2f129b",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "5a5aa8c4-a0f4-4732-ad18-9e9218b8a290"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4p1s1ilbfzqh17bcs8uvulay2"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-844b258b9cf74554209628700c498013",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "806124bf-e49b-4d56-ae4c-2bb7955eeff8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9sstgnfd1t0oq3clvby8wgo79"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-3bc4f38b76a80a9f950eb869d87f4615",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "f4ea023f-a2a0-4d41-be84-90688610f4d8"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "183"
          }, {
            "name" : "role_jceks_password",
            "value" : "bkv0o3rfd152dvhlkg8mwndsb"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "BALANCER",
          "items" : [ {
            "name" : "balancer_java_heapsize",
            "value" : "796917760"
          } ]
        }, {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "3219965132"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "200"
          }, {
            "name" : "rm_io_weight",
            "value" : "100"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "JOURNALNODE",
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/dfs/jn/edits"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          }, {
            "name" : "namenode_java_heapsize",
            "value" : "796917760"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "796917760"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "b9gk8YuASA3aBtGa627ZUMBqW8vgHN"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "baFoLVGPLv9KbciexFfHCjO9YwUGqF"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "QuYnJ61jWJH3mo1hatiRaRVI3fLMhq"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "10"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-3bc4f38b76a80a9f950eb869d87f4615",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "f4ea023f-a2a0-4d41-be84-90688610f4d8"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-21a34b12feb52431f525ae862264a5f4",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "7147880d-170a-497e-a752-3740d83d21c6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dauxdevs23iytfcjhuzmw1u6z"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-3bc4f38b76a80a9f950eb869d87f4615",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "f4ea023f-a2a0-4d41-be84-90688610f4d8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4updi7zoo5287imlntbnp689b"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-7332336232d0be26e00b036b6a2f129b",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "5a5aa8c4-a0f4-4732-ad18-9e9218b8a290"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "97e8v7aahjaidagunnmtrpthu"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-844b258b9cf74554209628700c498013",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "806124bf-e49b-4d56-ae4c-2bb7955eeff8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5vu3zh616a912r47v9chli4hm"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-3bc4f38b76a80a9f950eb869d87f4615",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "f4ea023f-a2a0-4d41-be84-90688610f4d8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1id46ig4kq1il2q437zz6nl4"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-b541d4a280beab774b3c99cea27d87ad",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "26b90466-f93b-4790-bbc5-567dd68a34d9"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9yyf6k957o4rnffwoevdxdi0z"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-b541d4a280beab774b3c99cea27d87ad",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "26b90466-f93b-4790-bbc5-567dd68a34d9"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "c38r5r8xj95jk9xabfy3ra13u"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-21a34b12feb52431f525ae862264a5f4",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "7147880d-170a-497e-a752-3740d83d21c6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dsupvy3hg9zcdw8njp3g8hm42"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-7332336232d0be26e00b036b6a2f129b",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "5a5aa8c4-a0f4-4732-ad18-9e9218b8a290"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4zi9vqicab5rtjz3g6yf1bjpo"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-844b258b9cf74554209628700c498013",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "806124bf-e49b-4d56-ae4c-2bb7955eeff8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "88kkarl7g9lkziv81osr53m8f"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-3bc4f38b76a80a9f950eb869d87f4615",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "f4ea023f-a2a0-4d41-be84-90688610f4d8"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "185"
          }, {
            "name" : "role_jceks_password",
            "value" : "312uyxfmjb6yp6kr62gte0ax4"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-b541d4a280beab774b3c99cea27d87ad",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "26b90466-f93b-4790-bbc5-567dd68a34d9"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "191"
          }, {
            "name" : "role_jceks_password",
            "value" : "i8kmtzhqf10gm3jf48fl2ymf"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "806124bf-e49b-4d56-ae4c-2bb7955eeff8",
    "ipAddress" : "172.31.19.244",
    "hostname" : "ip-172-31-19-244.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "7147880d-170a-497e-a752-3740d83d21c6",
    "ipAddress" : "172.31.25.211",
    "hostname" : "ip-172-31-25-211.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "26b90466-f93b-4790-bbc5-567dd68a34d9",
    "ipAddress" : "172.31.26.225",
    "hostname" : "ip-172-31-26-225.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "5a5aa8c4-a0f4-4732-ad18-9e9218b8a290",
    "ipAddress" : "172.31.27.218",
    "hostname" : "ip-172-31-27-218.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "f4ea023f-a2a0-4d41-be84-90688610f4d8",
    "ipAddress" : "172.31.30.16",
    "hostname" : "ip-172-31-30-16.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "LivniGuy",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "54c521fb99525a46619287f458deb010047e481fc23ade04d14a9701e22487c7",
    "pwSalt" : 2705723481079243875,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__hue-HUE_SERVER-b541d4a280beab774b3c99cea27d87ad",
    "roles" : [ "ROLE_NAVIGATOR_ADMIN" ],
    "pwHash" : "333f2e55fb1708040203e00bd6ae91ea4c54593ee3f0d0e756193e87878a08f7",
    "pwSalt" : 34679096127192432,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-ACTIVITYMONITOR-b541d4a280beab774b3c99cea27d87ad",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "c5493d3ff77d7159fdbd0f3762351512f6b873d440ba6c5e753e86b0da314203",
    "pwSalt" : 2609961056112655684,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-b541d4a280beab774b3c99cea27d87ad",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "9b05906aa2742890dfe0c06ee7f067040c8e8679900eef43588d72b9bd9ed6bf",
    "pwSalt" : -8267585222491126026,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-b541d4a280beab774b3c99cea27d87ad",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "a88be12c967fc7f656da1703322cfcd2f799480125aef95ca0269eec95d12aa5",
    "pwSalt" : -420707983616245886,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-b541d4a280beab774b3c99cea27d87ad",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "c48dfb70be0600a373b3eca06aa99043800ea578f54adbfcc22d223436c44e88",
    "pwSalt" : -3615997715772823151,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-b541d4a280beab774b3c99cea27d87ad",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "0b6126f3a4023fa5b7a1a26058d3bfda5843aee4a13be7587db9f931bdcc51a1",
    "pwSalt" : -2063463170698824408,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "3e53cb5742fad74f664022abee80010e46780e4a26bf9497d475bc1c87a9e297",
    "pwSalt" : -4626280879091368196,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "db9a9b3070a5197a7a78abcf73e55e891a9c7d9e22e2a84aaac4258c7e164975",
    "pwSalt" : 4164453618018720394,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.15.1",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20180731-0834",
    "gitHash" : "6e046fd999fd99e7e12299386ba69b23afa43c60",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "ACTIVITYMONITOR",
        "items" : [ {
          "name" : "firehose_database_host",
          "value" : "ip-172-31-26-225.eu-west-1.compute.internal"
        }, {
          "name" : "firehose_database_name",
          "value" : "amon"
        }, {
          "name" : "firehose_database_password",
          "value" : "123456"
        }, {
          "name" : "firehose_database_user",
          "value" : "amon"
        }, {
          "name" : "firehose_heapsize",
          "value" : "989855744"
        } ]
      }, {
        "roleType" : "EVENTSERVER",
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "989855744"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "989855744"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1287651328"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-172-31-26-225.eu-west-1.compute.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "123456"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "989855744"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "989855744"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1287651328"
        } ]
      }, {
        "roleType" : "TELEMETRYPUBLISHER",
        "items" : [ {
          "name" : "telemetry_publisher_heapsize",
          "value" : "989855744"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ACTIVITYMONITOR-b541d4a280beab774b3c99cea27d87ad",
      "type" : "ACTIVITYMONITOR",
      "hostRef" : {
        "hostId" : "26b90466-f93b-4790-bbc5-567dd68a34d9"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "3zv7jlypbj0ci0aqupyr68h58"
        } ]
      }
    }, {
      "name" : "mgmt-ALERTPUBLISHER-b541d4a280beab774b3c99cea27d87ad",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "26b90466-f93b-4790-bbc5-567dd68a34d9"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "dere5waqkhk6ydfm5oeg6hv6a"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-b541d4a280beab774b3c99cea27d87ad",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "26b90466-f93b-4790-bbc5-567dd68a34d9"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "cfmhyvs2umzbm58ahcpe0wyad"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-b541d4a280beab774b3c99cea27d87ad",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "26b90466-f93b-4790-bbc5-567dd68a34d9"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "6ymq7iyxjig0uw8qxnvgyadid"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-b541d4a280beab774b3c99cea27d87ad",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "26b90466-f93b-4790-bbc5-567dd68a34d9"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "r5n9mu8ctertcghsvjy6pw6"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-b541d4a280beab774b3c99cea27d87ad",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "26b90466-f93b-4790-bbc5-567dd68a34d9"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "eic4qlfppsunwg55dabl985sh"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/21/2012 13:40"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,http://172.31.26.225/cdh5.15.0.21/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/cdh5/parcels/5.13.3.2/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,http://archive.cloudera.com/kudu/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    }, {
      "name" : "TELEMETRY_MASTER",
      "value" : "true"
    }, {
      "name" : "TELEMETRY_WA",
      "value" : "true"
    } ]
  }
}
