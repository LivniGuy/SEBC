### Creating livniguy user:

[ec2-user@ip-172-31-19-244 ~]$ sudo useradd livniguy
[ec2-user@ip-172-31-19-244 ~]$ sudo passwd livniguy
Changing password for user livniguy.
New password: 
BAD PASSWORD: The password is shorter than 8 characters
Retype new password: 
passwd: all authentication tokens updated successfully.

[ec2-user@ip-172-31-19-244 ~]$ sudo -u hdfs hdfs dfs -mkdir /user/livniguy
[ec2-user@ip-172-31-19-244 ~]$ sudo -u hdfs hdfs dfs -chown livniguy:livniguy /user/livniguy


### Create a 10 GB file using teragen:

[livniguy@ip-172-31-19-244 ~]$ time yarn jar ${EXAMPLES_PATH}/hadoop-mapreduce-examples.jar teragen -Dmapreduce.job.maps=4 -Ddfs.blocksize=33554432 100000000 /user/livniguy/teragen10gb
18/10/16 11:52:10 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-30-16.eu-west-1.compute.internal/172.31.30.16:8032
18/10/16 11:52:11 INFO terasort.TeraGen: Generating 100000000 using 4
18/10/16 11:52:11 INFO mapreduce.JobSubmitter: number of splits:4
18/10/16 11:52:11 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1539684804586_0011
18/10/16 11:52:11 INFO impl.YarnClientImpl: Submitted application application_1539684804586_0011
18/10/16 11:52:11 INFO mapreduce.Job: The url to track the job: http://ip-172-31-30-16.eu-west-1.compute.internal:8088/proxy/application_1539684804586_0011/
18/10/16 11:52:11 INFO mapreduce.Job: Running job: job_1539684804586_0011
18/10/16 11:52:18 INFO mapreduce.Job: Job job_1539684804586_0011 running in uber mode : false
18/10/16 11:52:18 INFO mapreduce.Job:  map 0% reduce 0%
18/10/16 11:52:35 INFO mapreduce.Job:  map 8% reduce 0%
18/10/16 11:52:36 INFO mapreduce.Job:  map 13% reduce 0%
18/10/16 11:52:37 INFO mapreduce.Job:  map 16% reduce 0%
18/10/16 11:52:41 INFO mapreduce.Job:  map 17% reduce 0%
18/10/16 11:52:42 INFO mapreduce.Job:  map 18% reduce 0%
18/10/16 11:52:43 INFO mapreduce.Job:  map 19% reduce 0%
18/10/16 11:52:47 INFO mapreduce.Job:  map 24% reduce 0%
18/10/16 11:52:48 INFO mapreduce.Job:  map 27% reduce 0%
18/10/16 11:52:49 INFO mapreduce.Job:  map 29% reduce 0%
18/10/16 11:52:54 INFO mapreduce.Job:  map 34% reduce 0%
18/10/16 11:52:55 INFO mapreduce.Job:  map 36% reduce 0%
18/10/16 11:52:56 INFO mapreduce.Job:  map 37% reduce 0%
18/10/16 11:53:00 INFO mapreduce.Job:  map 42% reduce 0%
18/10/16 11:53:01 INFO mapreduce.Job:  map 44% reduce 0%
18/10/16 11:53:02 INFO mapreduce.Job:  map 47% reduce 0%
18/10/16 11:53:06 INFO mapreduce.Job:  map 52% reduce 0%
18/10/16 11:53:07 INFO mapreduce.Job:  map 53% reduce 0%
18/10/16 11:53:08 INFO mapreduce.Job:  map 55% reduce 0%
18/10/16 11:53:12 INFO mapreduce.Job:  map 59% reduce 0%
18/10/16 11:53:13 INFO mapreduce.Job:  map 61% reduce 0%
18/10/16 11:53:14 INFO mapreduce.Job:  map 63% reduce 0%
18/10/16 11:53:18 INFO mapreduce.Job:  map 67% reduce 0%
18/10/16 11:53:19 INFO mapreduce.Job:  map 69% reduce 0%
18/10/16 11:53:20 INFO mapreduce.Job:  map 71% reduce 0%
18/10/16 11:53:24 INFO mapreduce.Job:  map 73% reduce 0%
18/10/16 11:53:25 INFO mapreduce.Job:  map 74% reduce 0%
18/10/16 11:53:26 INFO mapreduce.Job:  map 75% reduce 0%
18/10/16 11:53:30 INFO mapreduce.Job:  map 77% reduce 0%
18/10/16 11:53:31 INFO mapreduce.Job:  map 79% reduce 0%
18/10/16 11:53:32 INFO mapreduce.Job:  map 81% reduce 0%
18/10/16 11:53:36 INFO mapreduce.Job:  map 86% reduce 0%
18/10/16 11:53:37 INFO mapreduce.Job:  map 89% reduce 0%
18/10/16 11:53:38 INFO mapreduce.Job:  map 91% reduce 0%
18/10/16 11:53:42 INFO mapreduce.Job:  map 93% reduce 0%
18/10/16 11:53:43 INFO mapreduce.Job:  map 96% reduce 0%
18/10/16 11:53:45 INFO mapreduce.Job:  map 97% reduce 0%
18/10/16 11:53:48 INFO mapreduce.Job:  map 100% reduce 0%
18/10/16 11:53:48 INFO mapreduce.Job: Job job_1539684804586_0011 completed successfully
18/10/16 11:53:48 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=592648
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=344
		HDFS: Number of bytes written=10000000000
		HDFS: Number of read operations=16
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=8
	Job Counters 
		Launched map tasks=4
		Other local map tasks=4
		Total time spent by all maps in occupied slots (ms)=334957
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=334957
		Total vcore-milliseconds taken by all map tasks=334957
		Total megabyte-milliseconds taken by all map tasks=342995968
	Map-Reduce Framework
		Map input records=100000000
		Map output records=100000000
		Input split bytes=344
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=1327
		CPU time spent (ms)=170440
		Physical memory (bytes) snapshot=726396928
		Virtual memory (bytes) snapshot=6331023360
		Total committed heap usage (bytes)=871890944
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=214760662691937609
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=10000000000

real	1m41.067s
user	0m6.477s
sys	0m0.502s


### Run the terasort command on this file:

[livniguy@ip-172-31-19-244 ~]$ time yarn jar ${EXAMPLES_PATH}/hadoop-mapreduce-examples.jar terasort -Dmapreduce.job.maps=4 /user/livniguy/teragen10gb /user/livniguy/terasort10gb
18/10/16 12:06:27 INFO terasort.TeraSort: starting
18/10/16 12:06:29 INFO input.FileInputFormat: Total input paths to process : 4
Spent 268ms computing base-splits.
Spent 6ms computing TeraScheduler splits.
Computing input splits took 275ms
Sampling 10 splits of 300
Making 8 from 100000 sampled records
Computing parititions took 763ms
Spent 1040ms computing partitions.
18/10/16 12:06:30 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-30-16.eu-west-1.compute.internal/172.31.30.16:8032
18/10/16 12:06:30 INFO mapreduce.JobSubmitter: number of splits:300
18/10/16 12:06:31 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1539684804586_0013
18/10/16 12:06:31 INFO impl.YarnClientImpl: Submitted application application_1539684804586_0013
18/10/16 12:06:31 INFO mapreduce.Job: The url to track the job: http://ip-172-31-30-16.eu-west-1.compute.internal:8088/proxy/application_1539684804586_0013/
18/10/16 12:06:31 INFO mapreduce.Job: Running job: job_1539684804586_0013
18/10/16 12:06:38 INFO mapreduce.Job: Job job_1539684804586_0013 running in uber mode : false
18/10/16 12:06:38 INFO mapreduce.Job:  map 0% reduce 0%
18/10/16 12:06:48 INFO mapreduce.Job:  map 1% reduce 0%
18/10/16 12:06:52 INFO mapreduce.Job:  map 2% reduce 0%
18/10/16 12:06:54 INFO mapreduce.Job:  map 3% reduce 0%
18/10/16 12:06:55 INFO mapreduce.Job:  map 4% reduce 0%
18/10/16 12:06:59 INFO mapreduce.Job:  map 5% reduce 0%
18/10/16 12:07:03 INFO mapreduce.Job:  map 6% reduce 0%
18/10/16 12:07:05 INFO mapreduce.Job:  map 7% reduce 0%
18/10/16 12:07:08 INFO mapreduce.Job:  map 8% reduce 0%
18/10/16 12:07:12 INFO mapreduce.Job:  map 9% reduce 0%
18/10/16 12:07:13 INFO mapreduce.Job:  map 10% reduce 0%
18/10/16 12:07:21 INFO mapreduce.Job:  map 11% reduce 0%
18/10/16 12:07:22 INFO mapreduce.Job:  map 12% reduce 0%
18/10/16 12:07:24 INFO mapreduce.Job:  map 13% reduce 0%
18/10/16 12:07:26 INFO mapreduce.Job:  map 14% reduce 0%
18/10/16 12:07:31 INFO mapreduce.Job:  map 15% reduce 0%
18/10/16 12:07:35 INFO mapreduce.Job:  map 16% reduce 0%
18/10/16 12:07:36 INFO mapreduce.Job:  map 17% reduce 0%
18/10/16 12:07:37 INFO mapreduce.Job:  map 18% reduce 0%
18/10/16 12:07:46 INFO mapreduce.Job:  map 19% reduce 0%
18/10/16 12:07:47 INFO mapreduce.Job:  map 20% reduce 0%
18/10/16 12:07:50 INFO mapreduce.Job:  map 21% reduce 0%
18/10/16 12:07:51 INFO mapreduce.Job:  map 22% reduce 0%
18/10/16 12:07:56 INFO mapreduce.Job:  map 23% reduce 0%
18/10/16 12:07:57 INFO mapreduce.Job:  map 24% reduce 0%
18/10/16 12:08:02 INFO mapreduce.Job:  map 25% reduce 0%
18/10/16 12:08:04 INFO mapreduce.Job:  map 26% reduce 0%
18/10/16 12:08:08 INFO mapreduce.Job:  map 27% reduce 0%
18/10/16 12:08:10 INFO mapreduce.Job:  map 28% reduce 0%
18/10/16 12:08:18 INFO mapreduce.Job:  map 29% reduce 0%
18/10/16 12:08:19 INFO mapreduce.Job:  map 31% reduce 0%
18/10/16 12:08:20 INFO mapreduce.Job:  map 32% reduce 0%
18/10/16 12:08:27 INFO mapreduce.Job:  map 33% reduce 0%
18/10/16 12:08:30 INFO mapreduce.Job:  map 34% reduce 0%
18/10/16 12:08:34 INFO mapreduce.Job:  map 36% reduce 0%
18/10/16 12:08:42 INFO mapreduce.Job:  map 38% reduce 0%
18/10/16 12:08:46 INFO mapreduce.Job:  map 39% reduce 0%
18/10/16 12:08:48 INFO mapreduce.Job:  map 40% reduce 0%
18/10/16 12:08:52 INFO mapreduce.Job:  map 41% reduce 0%
18/10/16 12:08:53 INFO mapreduce.Job:  map 42% reduce 0%
18/10/16 12:08:58 INFO mapreduce.Job:  map 43% reduce 0%
18/10/16 12:09:01 INFO mapreduce.Job:  map 44% reduce 0%
18/10/16 12:09:04 INFO mapreduce.Job:  map 45% reduce 0%
18/10/16 12:09:06 INFO mapreduce.Job:  map 46% reduce 0%
18/10/16 12:09:11 INFO mapreduce.Job:  map 47% reduce 0%
18/10/16 12:09:14 INFO mapreduce.Job:  map 48% reduce 0%
18/10/16 12:09:15 INFO mapreduce.Job:  map 49% reduce 0%
18/10/16 12:09:17 INFO mapreduce.Job:  map 50% reduce 0%
18/10/16 12:09:23 INFO mapreduce.Job:  map 51% reduce 0%
18/10/16 12:09:25 INFO mapreduce.Job:  map 52% reduce 0%
18/10/16 12:09:28 INFO mapreduce.Job:  map 53% reduce 0%
18/10/16 12:09:30 INFO mapreduce.Job:  map 54% reduce 0%
18/10/16 12:09:37 INFO mapreduce.Job:  map 55% reduce 0%
18/10/16 12:09:38 INFO mapreduce.Job:  map 56% reduce 0%
18/10/16 12:09:40 INFO mapreduce.Job:  map 57% reduce 0%
18/10/16 12:09:42 INFO mapreduce.Job:  map 58% reduce 0%
18/10/16 12:09:48 INFO mapreduce.Job:  map 60% reduce 0%
18/10/16 12:09:54 INFO mapreduce.Job:  map 62% reduce 0%
18/10/16 12:10:00 INFO mapreduce.Job:  map 63% reduce 0%
18/10/16 12:10:02 INFO mapreduce.Job:  map 64% reduce 0%
18/10/16 12:10:05 INFO mapreduce.Job:  map 65% reduce 0%
18/10/16 12:10:09 INFO mapreduce.Job:  map 66% reduce 0%
18/10/16 12:10:10 INFO mapreduce.Job:  map 67% reduce 0%
18/10/16 12:10:12 INFO mapreduce.Job:  map 68% reduce 0%
18/10/16 12:10:18 INFO mapreduce.Job:  map 69% reduce 0%
18/10/16 12:10:20 INFO mapreduce.Job:  map 70% reduce 0%
18/10/16 12:10:21 INFO mapreduce.Job:  map 71% reduce 0%
18/10/16 12:10:27 INFO mapreduce.Job:  map 72% reduce 0%
18/10/16 12:10:31 INFO mapreduce.Job:  map 73% reduce 0%
18/10/16 12:10:33 INFO mapreduce.Job:  map 74% reduce 0%
18/10/16 12:10:35 INFO mapreduce.Job:  map 75% reduce 0%
18/10/16 12:10:36 INFO mapreduce.Job:  map 76% reduce 0%
18/10/16 12:10:43 INFO mapreduce.Job:  map 77% reduce 0%
18/10/16 12:10:44 INFO mapreduce.Job:  map 78% reduce 0%
18/10/16 12:10:48 INFO mapreduce.Job:  map 79% reduce 0%
18/10/16 12:10:50 INFO mapreduce.Job:  map 80% reduce 0%
18/10/16 12:10:55 INFO mapreduce.Job:  map 81% reduce 0%
18/10/16 12:10:57 INFO mapreduce.Job:  map 82% reduce 0%
18/10/16 12:11:00 INFO mapreduce.Job:  map 83% reduce 0%
18/10/16 12:11:04 INFO mapreduce.Job:  map 84% reduce 0%
18/10/16 12:11:11 INFO mapreduce.Job:  map 85% reduce 0%
18/10/16 12:11:14 INFO mapreduce.Job:  map 85% reduce 6%
18/10/16 12:11:17 INFO mapreduce.Job:  map 85% reduce 10%
18/10/16 12:11:18 INFO mapreduce.Job:  map 85% reduce 13%
18/10/16 12:11:19 INFO mapreduce.Job:  map 85% reduce 16%
18/10/16 12:11:20 INFO mapreduce.Job:  map 86% reduce 16%
18/10/16 12:11:21 INFO mapreduce.Job:  map 86% reduce 17%
18/10/16 12:11:23 INFO mapreduce.Job:  map 86% reduce 20%
18/10/16 12:11:25 INFO mapreduce.Job:  map 87% reduce 21%
18/10/16 12:11:29 INFO mapreduce.Job:  map 87% reduce 22%
18/10/16 12:11:32 INFO mapreduce.Job:  map 88% reduce 22%
18/10/16 12:11:38 INFO mapreduce.Job:  map 89% reduce 22%
18/10/16 12:11:43 INFO mapreduce.Job:  map 90% reduce 22%
18/10/16 12:11:49 INFO mapreduce.Job:  map 91% reduce 23%
18/10/16 12:11:55 INFO mapreduce.Job:  map 92% reduce 23%
18/10/16 12:11:58 INFO mapreduce.Job:  map 93% reduce 23%
18/10/16 12:12:05 INFO mapreduce.Job:  map 94% reduce 23%
18/10/16 12:12:09 INFO mapreduce.Job:  map 95% reduce 23%
18/10/16 12:12:11 INFO mapreduce.Job:  map 95% reduce 24%
18/10/16 12:12:15 INFO mapreduce.Job:  map 96% reduce 24%
18/10/16 12:12:21 INFO mapreduce.Job:  map 97% reduce 24%
18/10/16 12:12:25 INFO mapreduce.Job:  map 98% reduce 24%
18/10/16 12:12:30 INFO mapreduce.Job:  map 99% reduce 24%
18/10/16 12:12:32 INFO mapreduce.Job:  map 99% reduce 25%
18/10/16 12:12:37 INFO mapreduce.Job:  map 100% reduce 25%
18/10/16 12:12:39 INFO mapreduce.Job:  map 100% reduce 27%
18/10/16 12:12:41 INFO mapreduce.Job:  map 100% reduce 32%
18/10/16 12:12:42 INFO mapreduce.Job:  map 100% reduce 40%
18/10/16 12:12:44 INFO mapreduce.Job:  map 100% reduce 45%
18/10/16 12:12:45 INFO mapreduce.Job:  map 100% reduce 52%
18/10/16 12:12:47 INFO mapreduce.Job:  map 100% reduce 53%
18/10/16 12:12:48 INFO mapreduce.Job:  map 100% reduce 56%
18/10/16 12:12:49 INFO mapreduce.Job:  map 100% reduce 60%
18/10/16 12:12:50 INFO mapreduce.Job:  map 100% reduce 67%
18/10/16 12:12:51 INFO mapreduce.Job:  map 100% reduce 69%
18/10/16 12:12:53 INFO mapreduce.Job:  map 100% reduce 70%
18/10/16 12:12:54 INFO mapreduce.Job:  map 100% reduce 73%
18/10/16 12:12:55 INFO mapreduce.Job:  map 100% reduce 74%
18/10/16 12:12:56 INFO mapreduce.Job:  map 100% reduce 80%
18/10/16 12:12:57 INFO mapreduce.Job:  map 100% reduce 82%
18/10/16 12:12:59 INFO mapreduce.Job:  map 100% reduce 85%
18/10/16 12:13:00 INFO mapreduce.Job:  map 100% reduce 86%
18/10/16 12:13:01 INFO mapreduce.Job:  map 100% reduce 91%
18/10/16 12:13:02 INFO mapreduce.Job:  map 100% reduce 92%
18/10/16 12:13:03 INFO mapreduce.Job:  map 100% reduce 93%
18/10/16 12:13:05 INFO mapreduce.Job:  map 100% reduce 94%
18/10/16 12:13:07 INFO mapreduce.Job:  map 100% reduce 96%
18/10/16 12:13:08 INFO mapreduce.Job:  map 100% reduce 97%
18/10/16 12:13:13 INFO mapreduce.Job:  map 100% reduce 98%
18/10/16 12:13:18 INFO mapreduce.Job:  map 100% reduce 100%
18/10/16 12:13:18 INFO mapreduce.Job: Job job_1539684804586_0013 completed successfully
18/10/16 12:13:19 INFO mapreduce.Job: Counters: 49
	File System Counters
		FILE: Number of bytes read=4443647165
		FILE: Number of bytes written=8832639532
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=10000047400
		HDFS: Number of bytes written=10000000000
		HDFS: Number of read operations=924
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=16
	Job Counters 
		Launched map tasks=300
		Launched reduce tasks=8
		Data-local map tasks=300
		Total time spent by all maps in occupied slots (ms)=2615336
		Total time spent by all reduces in occupied slots (ms)=832561
		Total time spent by all map tasks (ms)=2615336
		Total time spent by all reduce tasks (ms)=832561
		Total vcore-milliseconds taken by all map tasks=2615336
		Total vcore-milliseconds taken by all reduce tasks=832561
		Total megabyte-milliseconds taken by all map tasks=2678104064
		Total megabyte-milliseconds taken by all reduce tasks=852542464
	Map-Reduce Framework
		Map input records=100000000
		Map output records=100000000
		Map output bytes=10200000000
		Map output materialized bytes=4342841401
		Input split bytes=47400
		Combine input records=0
		Combine output records=0
		Reduce input groups=100000000
		Reduce shuffle bytes=4342841401
		Reduce input records=100000000
		Reduce output records=100000000
		Spilled Records=200000000
		Shuffled Maps =2400
		Failed Shuffles=0
		Merged Map outputs=2400
		GC time elapsed (ms)=41141
		CPU time spent (ms)=1515400
		Physical memory (bytes) snapshot=156473016320
		Virtual memory (bytes) snapshot=487563448320
		Total committed heap usage (bytes)=179538755584
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=10000000000
	File Output Format Counters 
		Bytes Written=10000000000
18/10/16 12:13:19 INFO terasort.TeraSort: done

real	6m52.440s
user	0m9.906s
sys	0m0.781s

