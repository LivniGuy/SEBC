### Creating HDFS directories:

[ec2-user@ip-172-31-19-244 ~]$ sudo -u hdfs hdfs dfs -mkdir /user/LivniGuy
[ec2-user@ip-172-31-19-244 ~]$ sudo -u hdfs hdfs dfs -mkdir /user/VasilyMelnik
[ec2-user@ip-172-31-19-244 ~]$ hdfs dfs -ls /user/
Found 6 items
drwxr-xr-x   - hdfs   supergroup          0 2018-10-16 08:09 /user/LivniGuy
drwxr-xr-x   - hdfs   supergroup          0 2018-10-16 08:10 /user/VasilyMelnik
drwxrwxrwx   - mapred hadoop              0 2018-10-15 17:37 /user/history
drwxrwxr-t   - hive   hive                0 2018-10-15 17:38 /user/hive
drwxrwxr-x   - hue    hue                 0 2018-10-15 17:38 /user/hue
drwxrwxr-x   - oozie  oozie               0 2018-10-15 17:38 /user/oozie

### Running teragen:
[ec2-user@ip-172-31-19-244 ~]$ EXAMPLES_PATH=/opt/cloudera/parcels/CDH/lib/hadoop-mapreduce
[ec2-user@ip-172-31-19-244 ~]$ sudo -u hdfs yarn jar ${EXAMPLES_PATH}/hadoop-mapreduce-examples.jar teragen -Ddfs.replication=1 -Dmapreduce.job.maps=30 5000000 /tmp/teragen500mb

18/10/16 08:21:19 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-30-16.eu-west-1.compute.internal/172.31.30.16:8032
18/10/16 08:21:21 INFO terasort.TeraGen: Generating 5000000 using 30
18/10/16 08:21:21 INFO mapreduce.JobSubmitter: number of splits:30
18/10/16 08:21:21 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1539625689480_0001
18/10/16 08:21:21 INFO impl.YarnClientImpl: Submitted application application_1539625689480_0001
18/10/16 08:21:21 INFO mapreduce.Job: The url to track the job: http://ip-172-31-30-16.eu-west-1.compute.internal:8088/proxy/application_1539625689480_0001/
18/10/16 08:21:21 INFO mapreduce.Job: Running job: job_1539625689480_0001
18/10/16 08:21:30 INFO mapreduce.Job: Job job_1539625689480_0001 running in uber mode : false
18/10/16 08:21:30 INFO mapreduce.Job:  map 0% reduce 0%
18/10/16 08:21:41 INFO mapreduce.Job:  map 3% reduce 0%
18/10/16 08:21:42 INFO mapreduce.Job:  map 20% reduce 0%
18/10/16 08:21:44 INFO mapreduce.Job:  map 33% reduce 0%
18/10/16 08:21:50 INFO mapreduce.Job:  map 53% reduce 0%


18/10/16 08:21:55 INFO mapreduce.Job:  map 67% reduce 0%
18/10/16 08:21:58 INFO mapreduce.Job:  map 70% reduce 0%
18/10/16 08:21:59 INFO mapreduce.Job:  map 87% reduce 0%
18/10/16 08:22:06 INFO mapreduce.Job:  map 90% reduce 0%
18/10/16 08:22:07 INFO mapreduce.Job:  map 100% reduce 0%
18/10/16 08:22:08 INFO mapreduce.Job: Job job_1539625689480_0001 completed successfully
18/10/16 08:22:08 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=4443890
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=2547
		HDFS: Number of bytes written=500000000
		HDFS: Number of read operations=120
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=60
	Job Counters 
		Launched map tasks=30
		Other local map tasks=30
		Total time spent by all maps in occupied slots (ms)=270689
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=270689
		Total vcore-milliseconds taken by all map tasks=270689
		Total megabyte-milliseconds taken by all map tasks=277185536
	Map-Reduce Framework
		Map input records=5000000
		Map output records=5000000
		Input split bytes=2547
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=3357
		CPU time spent (ms)=56170
		Physical memory (bytes) snapshot=6498574336
		Virtual memory (bytes) snapshot=47342338048
		Total committed heap usage (bytes)=8855224320
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=10735710707299981
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=500000000
[ec2-user@ip-172-31-19-244 ~]$ 

[ec2-user@ip-172-31-19-244 ~]$ hdfs dfs -du -s -h /tmp/teragen500mb/
476.8 M  476.8 M  /tmp/teragen500mb


### Copying to my cluster with distcp:

[ec2-user@ip-172-31-19-244 ~]$ sudo -u hdfs hadoop distcp /tmp/teragen500mb/ hdfs://172.31.30.16:8020/user/LivniGuy
18/10/16 11:03:32 INFO tools.OptionsParser: parseChunkSize: blocksperchunk false
18/10/16 11:03:37 INFO tools.DistCp: Input Options: DistCpOptions{atomicCommit=false, syncFolder=false, deleteMissing=false, ignoreFailures=false, overwrite=false, append=false, useDiff=false, useRdiff=false, fromSnapshot=null, toSnapshot=null, skipCRC=false, blocking=true, numListstatusThreads=0, maxMaps=20, mapBandwidth=100, sslConfigurationFile='null', copyStrategy='uniformsize', preserveStatus=[], preserveRawXattrs=false, atomicWorkPath=null, logPath=null, sourceFileListing=null, sourcePaths=[/tmp/teragen500mb], targetPath=hdfs://172.31.30.16:8020/user/LivniGuy, targetPathExists=true, filtersFile='null', blocksPerChunk=0, copyBufferSize=8192}
18/10/16 11:03:37 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-30-16.eu-west-1.compute.internal/172.31.30.16:8032
18/10/16 11:03:39 INFO tools.SimpleCopyListing: Paths (files+dirs) cnt = 32; dirCnt = 1
18/10/16 11:03:39 INFO tools.SimpleCopyListing: Build file listing completed.
18/10/16 11:03:39 INFO Configuration.deprecation: io.sort.mb is deprecated. Instead, use mapreduce.task.io.sort.mb
18/10/16 11:03:39 INFO Configuration.deprecation: io.sort.factor is deprecated. Instead, use mapreduce.task.io.sort.factor
18/10/16 11:03:40 INFO tools.DistCp: Number of paths in the copy list: 32
18/10/16 11:03:40 INFO tools.DistCp: Number of paths in the copy list: 32
18/10/16 11:03:40 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-30-16.eu-west-1.compute.internal/172.31.30.16:8032
18/10/16 11:03:44 INFO mapreduce.JobSubmitter: number of splits:30
18/10/16 11:03:44 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1539684804586_0007
18/10/16 11:03:45 INFO impl.YarnClientImpl: Submitted application application_1539684804586_0007
18/10/16 11:03:45 INFO mapreduce.Job: The url to track the job: http://ip-172-31-30-16.eu-west-1.compute.internal:8088/proxy/application_1539684804586_0007/
18/10/16 11:03:45 INFO tools.DistCp: DistCp job-id: job_1539684804586_0007
18/10/16 11:03:45 INFO mapreduce.Job: Running job: job_1539684804586_0007
18/10/16 11:04:10 INFO mapreduce.Job: Job job_1539684804586_0007 running in uber mode : false
18/10/16 11:04:10 INFO mapreduce.Job:  map 0% reduce 0%
18/10/16 11:04:28 INFO mapreduce.Job:  map 3% reduce 0%
18/10/16 11:04:30 INFO mapreduce.Job:  map 7% reduce 0%
18/10/16 11:04:33 INFO mapreduce.Job:  map 17% reduce 0%
18/10/16 11:04:35 INFO mapreduce.Job:  map 27% reduce 0%
18/10/16 11:04:38 INFO mapreduce.Job:  map 33% reduce 0%
18/10/16 11:04:41 INFO mapreduce.Job:  map 37% reduce 0%
18/10/16 11:04:49 INFO mapreduce.Job:  map 40% reduce 0%
18/10/16 11:04:55 INFO mapreduce.Job:  map 47% reduce 0%
18/10/16 11:05:03 INFO mapreduce.Job:  map 57% reduce 0%
18/10/16 11:05:04 INFO mapreduce.Job:  map 67% reduce 0%
18/10/16 11:05:06 INFO mapreduce.Job:  map 70% reduce 0%
18/10/16 11:05:09 INFO mapreduce.Job:  map 73% reduce 0%
18/10/16 11:05:11 INFO mapreduce.Job:  map 77% reduce 0%
18/10/16 11:05:14 INFO mapreduce.Job:  map 80% reduce 0%
18/10/16 11:05:20 INFO mapreduce.Job:  map 87% reduce 0%
18/10/16 11:05:21 INFO mapreduce.Job:  map 90% reduce 0%
18/10/16 11:05:22 INFO mapreduce.Job:  map 97% reduce 0%
18/10/16 11:05:24 INFO mapreduce.Job:  map 100% reduce 0%
18/10/16 11:05:29 INFO mapreduce.Job: Job job_1539684804586_0007 completed successfully
18/10/16 11:05:29 INFO mapreduce.Job: Counters: 33
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=4549100
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=500019904
		HDFS: Number of bytes written=500000000
		HDFS: Number of read operations=519
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=124
	Job Counters 
		Launched map tasks=30
		Other local map tasks=30
		Total time spent by all maps in occupied slots (ms)=600942
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=600942
		Total vcore-milliseconds taken by all map tasks=600942
		Total megabyte-milliseconds taken by all map tasks=615364608
	Map-Reduce Framework
		Map input records=32
		Map output records=0
		Input split bytes=3480
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=5531
		CPU time spent (ms)=54080
		Physical memory (bytes) snapshot=6330572800
		Virtual memory (bytes) snapshot=47318294528
		Total committed heap usage (bytes)=8855224320
	File Input Format Counters 
		Bytes Read=16424
	File Output Format Counters 
		Bytes Written=0
	DistCp Counters
		Bytes Copied=500000000
		Bytes Expected=500000000
		Files Copied=32


Browsing the results:

[ec2-user@ip-172-31-19-244 ~]$ hdfs fsck /user/LivniGuy -files -blocks
Connecting to namenode via http://ip-172-31-30-16.eu-west-1.compute.internal:50070/fsck?ugi=ec2-user&files=1&blocks=1&path=%2Fuser%2FLivniGuy
FSCK started by ec2-user (auth:SIMPLE) from /172.31.19.244 for path /user/LivniGuy at Tue Oct 16 11:18:30 UTC 2018
/user/LivniGuy <dir>
/user/LivniGuy/teragen500mb <dir>
/user/LivniGuy/teragen500mb/_SUCCESS 0 bytes, 0 block(s):  OK

/user/LivniGuy/teragen500mb/part-m-00000 16666700 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744166_3342 len=16666700 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00001 16666700 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744180_3356 len=16666700 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00002 16666600 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744184_3360 len=16666600 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00003 16666700 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744177_3353 len=16666700 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00004 16666700 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744175_3351 len=16666700 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00005 16666600 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744169_3345 len=16666600 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00006 16666700 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744186_3362 len=16666700 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00007 16666700 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744185_3361 len=16666700 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00008 16666600 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744170_3346 len=16666600 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00009 16666700 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744168_3344 len=16666700 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00010 16666700 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744174_3350 len=16666700 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00011 16666600 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744178_3354 len=16666600 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00012 16666700 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744194_3370 len=16666700 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00013 16666700 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744191_3367 len=16666700 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00014 16666600 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744196_3372 len=16666600 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00015 16666700 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744188_3364 len=16666700 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00016 16666700 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744172_3348 len=16666700 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00017 16666600 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744173_3349 len=16666600 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00018 16666700 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744187_3363 len=16666700 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00019 16666700 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744179_3355 len=16666700 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00020 16666600 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744171_3347 len=16666600 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00021 16666700 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744183_3359 len=16666700 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00022 16666700 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744167_3343 len=16666700 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00023 16666600 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744165_3341 len=16666600 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00024 16666700 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744163_3339 len=16666700 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00025 16666700 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744181_3357 len=16666700 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00026 16666600 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744193_3369 len=16666600 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00027 16666700 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744182_3358 len=16666700 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00028 16666700 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744192_3368 len=16666700 Live_repl=3

/user/LivniGuy/teragen500mb/part-m-00029 16666600 bytes, 1 block(s):  OK
0. BP-1887483980-172.31.30.16-1539624990024:blk_1073744195_3371 len=16666600 Live_repl=3

Status: HEALTHY
 Total size:	500000000 B
 Total dirs:	2
 Total files:	31
 Total symlinks:		0
 Total blocks (validated):	30 (avg. block size 16666666 B)
 Minimally replicated blocks:	30 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		4
 Number of racks:		1
FSCK ended at Tue Oct 16 11:18:30 UTC 2018 in 10 milliseconds


The filesystem under path '/user/LivniGuy' is HEALTHY








