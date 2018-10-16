### Create a precious directory in HDFS; copy the ZIP course file into it:

[livniguy@ip-172-31-19-244 ~]$ hdfs dfs -mkdir precious
[livniguy@ip-172-31-19-244 ~]$ hdfs dfs -ls
Found 4 items
drwx------   - livniguy livniguy          0 2018-10-16 12:13 .staging
drwxr-xr-x   - livniguy livniguy          0 2018-10-16 12:18 precious
drwxr-xr-x   - livniguy livniguy          0 2018-10-16 11:53 teragen10gb
drwxr-xr-x   - livniguy livniguy          0 2018-10-16 12:13 terasort10gb

### Uploading the zip file to ec2, then to HDFS:

glivni-mbp:Downloads gl$ scp -i sebc-madrid.pem SEBC-master.zip ec2-user@34.250.35.168:/tmp

[livniguy@ip-172-31-19-244 ~]$ hdfs dfs -put /tmp/SEBC-master.zip precious
[livniguy@ip-172-31-19-244 ~]$ hdfs dfs -ls precious
Found 1 items
-rw-r--r--   3 livniguy livniguy    1720611 2018-10-16 12:27 precious/SEBC-master.zip


### Enabling snapshot via Cloudera Manager - HDFS File Browser

### Trying to delete the folder fails:
[livniguy@ip-172-31-19-244 ~]$ hdfs dfs -rm -r precious
rm: Failed to move to trash: hdfs://ip-172-31-30-16.eu-west-1.compute.internal:8020/user/livniguy/precious: The directory /user/livniguy/precious cannot be deleted since /user/livniguy/precious is snapshottable and already has snapshots

#Deleting the ZIP file:
[livniguy@ip-172-31-19-244 ~]$ hdfs dfs -rm precious/SEBC-master.zip
18/10/16 12:33:40 INFO fs.TrashPolicyDefault: Moved: 'hdfs://ip-172-31-30-16.eu-west-1.compute.internal:8020/user/livniguy/precious/SEBC-master.zip' to trash at: hdfs://ip-172-31-30-16.eu-west-1.compute.internal:8020/user/livniguy/.Trash/Current/user/livniguy/precious/SEBC-master.zip

[livniguy@ip-172-31-19-244 ~]$ hdfs dfs -ls precious

### Restore the deleted file via Cloudera Manager - HDFS File Browser

[livniguy@ip-172-31-19-244 ~]$ hdfs dfs -ls precious
Found 1 items
-rw-r--r--   3 hdfs livniguy    1720611 2018-10-16 12:35 precious/SEBC-master.zip





