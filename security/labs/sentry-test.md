```
[root@ip-172-31-30-16 jks]# kinit livniguy
Password for livniguy@LIVNIGUY.COM:
[root@ip-172-31-30-16 jks]#
[root@ip-172-31-30-16 jks]#
[root@ip-172-31-30-16 jks]# beeline
Beeline version 1.1.0-cdh5.13.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-30-16.eu-west-1.compute.internal@LIVNIGUY.COM
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-30-16.eu-west-1.compute.internal@LIVNIGUY.COM
Connected to: Apache Hive (version 1.1.0-cdh5.13.3)
Driver: Hive JDBC (version 1.1.0-cdh5.13.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20181017164343_ddf37109-6e4a-4327-ba81-254f91d7c228): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20181017164343_ddf37109-6e4a-4327-ba81-254f91d7c228); Time taken: 0.083 seconds
INFO  : Executing command(queryId=hive_20181017164343_ddf37109-6e4a-4327-ba81-254f91d7c228): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017164343_ddf37109-6e4a-4327-ba81-254f91d7c228); Time taken: 0.148 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (0.337 seconds)
0: jdbc:hive2://localhost:10000/default>




0: jdbc:hive2://localhost:10000/default> CREATE ROLE reads;
INFO  : Compiling command(queryId=hive_20181017164949_ed923481-be54-47f7-8a16-8e4f06a955c0): CREATE ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017164949_ed923481-be54-47f7-8a16-8e4f06a955c0); Time taken: 0.077 seconds
INFO  : Executing command(queryId=hive_20181017164949_ed923481-be54-47f7-8a16-8e4f06a955c0): CREATE ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017164949_ed923481-be54-47f7-8a16-8e4f06a955c0); Time taken: 0.018 seconds
INFO  : OK
No rows affected (0.114 seconds)
0: jdbc:hive2://localhost:10000/default> CREATE ROLE writes;
INFO  : Compiling command(queryId=hive_20181017164949_1d28085d-c0ff-428c-8548-ee292f717c85): CREATE ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017164949_1d28085d-c0ff-428c-8548-ee292f717c85); Time taken: 0.065 seconds
INFO  : Executing command(queryId=hive_20181017164949_1d28085d-c0ff-428c-8548-ee292f717c85): CREATE ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017164949_1d28085d-c0ff-428c-8548-ee292f717c85); Time taken: 0.015 seconds
INFO  : OK
No rows affected (0.096 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT SELECT ON DATABASE default TO ROLE reads;
INFO  : Compiling command(queryId=hive_20181017164949_2fb323e8-c556-4dfa-a393-fa487fefae0d): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017164949_2fb323e8-c556-4dfa-a393-fa487fefae0d); Time taken: 0.079 seconds
INFO  : Executing command(queryId=hive_20181017164949_2fb323e8-c556-4dfa-a393-fa487fefae0d): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017164949_2fb323e8-c556-4dfa-a393-fa487fefae0d); Time taken: 0.022 seconds
INFO  : OK
No rows affected (0.118 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE reads TO GROUP selector;
INFO  : Compiling command(queryId=hive_20181017165050_8b88d769-005b-4ab9-8012-45e4635a44a3): GRANT ROLE reads TO GROUP selector
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017165050_8b88d769-005b-4ab9-8012-45e4635a44a3); Time taken: 0.08 seconds
INFO  : Executing command(queryId=hive_20181017165050_8b88d769-005b-4ab9-8012-45e4635a44a3): GRANT ROLE reads TO GROUP selector
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017165050_8b88d769-005b-4ab9-8012-45e4635a44a3); Time taken: 0.019 seconds
INFO  : OK
No rows affected (0.117 seconds)
0: jdbc:hive2://localhost:10000/default> REVOKE ALL ON DATABASE default FROM ROLE writes;
INFO  : Compiling command(queryId=hive_20181017165050_8a22c4fa-e5ee-4890-b329-78a2c14c28dc): REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017165050_8a22c4fa-e5ee-4890-b329-78a2c14c28dc); Time taken: 0.068 seconds
INFO  : Executing command(queryId=hive_20181017165050_8a22c4fa-e5ee-4890-b329-78a2c14c28dc): REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017165050_8a22c4fa-e5ee-4890-b329-78a2c14c28dc); Time taken: 0.063 seconds
INFO  : OK
No rows affected (0.145 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT SELECT ON default.sample_07 TO ROLE writes;
INFO  : Compiling command(queryId=hive_20181017165050_4a9f422d-02a8-4317-9e29-764092b3990e): GRANT SELECT ON default.sample_07 TO ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017165050_4a9f422d-02a8-4317-9e29-764092b3990e); Time taken: 0.07 seconds
INFO  : Executing command(queryId=hive_20181017165050_4a9f422d-02a8-4317-9e29-764092b3990e): GRANT SELECT ON default.sample_07 TO ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017165050_4a9f422d-02a8-4317-9e29-764092b3990e); Time taken: 0.021 seconds
INFO  : OK
No rows affected (0.105 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE writes TO GROUP inserters;
INFO  : Compiling command(queryId=hive_20181017165050_f0549ba3-a6ef-48b5-8281-016df60d3de4): GRANT ROLE writes TO GROUP inserters
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017165050_f0549ba3-a6ef-48b5-8281-016df60d3de4); Time taken: 0.065 seconds
INFO  : Executing command(queryId=hive_20181017165050_f0549ba3-a6ef-48b5-8281-016df60d3de4): GRANT ROLE writes TO GROUP inserters
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017165050_f0549ba3-a6ef-48b5-8281-016df60d3de4); Time taken: 0.021 seconds
INFO  : OK
No rows affected (0.104 seconds)
0: jdbc:hive2://localhost:10000/default>



[root@ip-172-31-30-16 ~]#
[root@ip-172-31-30-16 ~]# kinit george
Password for george@LIVNIGUY.COM:
[root@ip-172-31-30-16 ~]# beeline
Beeline version 1.1.0-cdh5.13.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-30-16.eu-west-1.compute.internal@LIVNIGUY.COM
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-30-16.eu-west-1.compute.internal@LIVNIGUY.COM
Connected to: Apache Hive (version 1.1.0-cdh5.13.3)
Driver: Hive JDBC (version 1.1.0-cdh5.13.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20181017174343_1c44bb6e-5b16-4ebb-9732-80047bb7f9dc): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20181017174343_1c44bb6e-5b16-4ebb-9732-80047bb7f9dc); Time taken: 0.717 seconds
INFO  : Executing command(queryId=hive_20181017174343_1c44bb6e-5b16-4ebb-9732-80047bb7f9dc): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017174343_1c44bb6e-5b16-4ebb-9732-80047bb7f9dc); Time taken: 0.41 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (2.551 seconds)
0: jdbc:hive2://localhost:10000/default> Closing: 0: jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-30-16.eu-west-1.compute.internal@LIVNIGUY.COM
[root@ip-172-31-30-16 ~]#
[root@ip-172-31-30-16 ~]#
[root@ip-172-31-30-16 ~]# kinit ferdinand
Password for ferdinand@LIVNIGUY.COM:
[root@ip-172-31-30-16 ~]# beeline
Beeline version 1.1.0-cdh5.13.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-30-16.eu-west-1.compute.internal@LIVNIGUY.COM
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-30-16.eu-west-1.compute.internal@LIVNIGUY.COM
Connected to: Apache Hive (version 1.1.0-cdh5.13.3)
Driver: Hive JDBC (version 1.1.0-cdh5.13.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> SHOW TABLE
TABLE        TABLE_NAME   
0: jdbc:hive2://localhost:10000/default> SHOW TABLE
TABLE        TABLE_NAME   
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20181017174444_6a304996-a472-43d0-bc02-02cbe97fc71c): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20181017174444_6a304996-a472-43d0-bc02-02cbe97fc71c); Time taken: 0.082 seconds
INFO  : Executing command(queryId=hive_20181017174444_6a304996-a472-43d0-bc02-02cbe97fc71c): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017174444_6a304996-a472-43d0-bc02-02cbe97fc71c); Time taken: 0.143 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.337 seconds)
0: jdbc:hive2://localhost:10000/default>


```
