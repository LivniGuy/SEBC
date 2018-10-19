```
[raffles@ip-172-31-24-148 root]$ time yarn jar ${EXAMPLES_PATH}/hadoop-mapreduce-examples.jar terasort -Dmapreduce.job.maps=4 /user/raffles/tgen512 /user/raffles/tsort512

18/10/19 09:41:16 INFO terasort.TeraSort: starting
18/10/19 09:41:18 INFO hdfs.DFSClient: Created token for raffles: HDFS_DELEGATION_TOKEN owner=raffles@LIVNIGUY.SG, renewer=yarn, realUser=, issueDate=1539942078478, maxDate=1540546878478, sequenceNumber=1, masterKeyId=2 on 172.31.24.159:8020
18/10/19 09:41:18 INFO security.TokenCache: Got dt for hdfs://ip-172-31-24-159.eu-west-1.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.24.159:8020, Ident: (token for raffles: HDFS_DELEGATION_TOKEN owner=raffles@LIVNIGUY.SG, renewer=yarn, realUser=, issueDate=1539942078478, maxDate=1540546878478, sequenceNumber=1, masterKeyId=2)
18/10/19 09:41:18 INFO input.FileInputFormat: Total input paths to process : 4
Spent 428ms computing base-splits.
Spent 5ms computing TeraScheduler splits.
Computing input splits took 434ms
Sampling 10 splits of 156
Making 8 from 100000 sampled records
Computing parititions took 1065ms
Spent 1502ms computing partitions.
18/10/19 09:41:19 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-24-159.eu-west-1.compute.internal/172.31.24.159:8032
18/10/19 09:41:20 INFO mapreduce.JobSubmitter: number of splits:156
18/10/19 09:41:20 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1539941976071_0001
18/10/19 09:41:20 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.24.159:8020, Ident: (token for raffles: HDFS_DELEGATION_TOKEN owner=raffles@LIVNIGUY.SG, renewer=yarn, realUser=, issueDate=1539942078478, maxDate=1540546878478, sequenceNumber=1, masterKeyId=2)
18/10/19 09:41:21 INFO impl.YarnClientImpl: Submitted application application_1539941976071_0001
18/10/19 09:41:21 INFO mapreduce.Job: The url to track the job: http://ip-172-31-24-159.eu-west-1.compute.internal:8088/proxy/application_1539941976071_0001/
18/10/19 09:41:21 INFO mapreduce.Job: Running job: job_1539941976071_0001
18/10/19 09:41:31 INFO mapreduce.Job: Job job_1539941976071_0001 running in uber mode : false
18/10/19 09:41:31 INFO mapreduce.Job:  map 0% reduce 0%
18/10/19 09:41:43 INFO mapreduce.Job:  map 1% reduce 0%
18/10/19 09:41:44 INFO mapreduce.Job:  map 2% reduce 0%
18/10/19 09:41:52 INFO mapreduce.Job:  map 3% reduce 0%
18/10/19 09:41:53 INFO mapreduce.Job:  map 5% reduce 0%
18/10/19 09:41:54 INFO mapreduce.Job:  map 10% reduce 0%
18/10/19 09:41:55 INFO mapreduce.Job:  map 12% reduce 0%
18/10/19 09:42:06 INFO mapreduce.Job:  map 13% reduce 0%
18/10/19 09:42:07 INFO mapreduce.Job:  map 16% reduce 0%
18/10/19 09:42:08 INFO mapreduce.Job:  map 20% reduce 0%
18/10/19 09:42:09 INFO mapreduce.Job:  map 21% reduce 0%
18/10/19 09:42:16 INFO mapreduce.Job:  map 22% reduce 0%
18/10/19 09:42:17 INFO mapreduce.Job:  map 24% reduce 0%
18/10/19 09:42:21 INFO mapreduce.Job:  map 26% reduce 0%
18/10/19 09:42:22 INFO mapreduce.Job:  map 31% reduce 0%
18/10/19 09:42:29 INFO mapreduce.Job:  map 33% reduce 0%
18/10/19 09:42:34 INFO mapreduce.Job:  map 35% reduce 0%
18/10/19 09:42:35 INFO mapreduce.Job:  map 38% reduce 0%
18/10/19 09:42:36 INFO mapreduce.Job:  map 40% reduce 0%
18/10/19 09:42:38 INFO mapreduce.Job:  map 41% reduce 0%
18/10/19 09:42:39 INFO mapreduce.Job:  map 42% reduce 0%
18/10/19 09:42:42 INFO mapreduce.Job:  map 43% reduce 0%
18/10/19 09:42:47 INFO mapreduce.Job:  map 44% reduce 0%
18/10/19 09:42:49 INFO mapreduce.Job:  map 48% reduce 0%
18/10/19 09:42:50 INFO mapreduce.Job:  map 51% reduce 0%
18/10/19 09:42:51 INFO mapreduce.Job:  map 52% reduce 0%
18/10/19 09:42:56 INFO mapreduce.Job:  map 53% reduce 0%
18/10/19 09:43:00 INFO mapreduce.Job:  map 54% reduce 0%
18/10/19 09:43:01 INFO mapreduce.Job:  map 57% reduce 0%
18/10/19 09:43:02 INFO mapreduce.Job:  map 59% reduce 0%
18/10/19 09:43:03 INFO mapreduce.Job:  map 60% reduce 0%
18/10/19 09:43:04 INFO mapreduce.Job:  map 62% reduce 0%
18/10/19 09:43:08 INFO mapreduce.Job:  map 63% reduce 0%
18/10/19 09:43:13 INFO mapreduce.Job:  map 64% reduce 0%
18/10/19 09:43:14 INFO mapreduce.Job:  map 65% reduce 0%
18/10/19 09:43:15 INFO mapreduce.Job:  map 67% reduce 0%
18/10/19 09:43:16 INFO mapreduce.Job:  map 69% reduce 0%
18/10/19 09:43:18 INFO mapreduce.Job:  map 72% reduce 0%
18/10/19 09:43:23 INFO mapreduce.Job:  map 74% reduce 0%
18/10/19 09:43:27 INFO mapreduce.Job:  map 76% reduce 0%
18/10/19 09:43:28 INFO mapreduce.Job:  map 78% reduce 0%
18/10/19 09:43:29 INFO mapreduce.Job:  map 79% reduce 0%
18/10/19 09:43:31 INFO mapreduce.Job:  map 81% reduce 0%
18/10/19 09:43:34 INFO mapreduce.Job:  map 82% reduce 0%
18/10/19 09:43:35 INFO mapreduce.Job:  map 83% reduce 0%
18/10/19 09:43:38 INFO mapreduce.Job:  map 84% reduce 0%
18/10/19 09:43:39 INFO mapreduce.Job:  map 85% reduce 0%
18/10/19 09:43:40 INFO mapreduce.Job:  map 86% reduce 0%
18/10/19 09:43:41 INFO mapreduce.Job:  map 87% reduce 0%
18/10/19 09:43:43 INFO mapreduce.Job:  map 88% reduce 0%
18/10/19 09:43:44 INFO mapreduce.Job:  map 89% reduce 0%
18/10/19 09:43:45 INFO mapreduce.Job:  map 91% reduce 0%
18/10/19 09:43:46 INFO mapreduce.Job:  map 92% reduce 0%
18/10/19 09:43:53 INFO mapreduce.Job:  map 93% reduce 0%
18/10/19 09:43:54 INFO mapreduce.Job:  map 94% reduce 0%
18/10/19 09:43:55 INFO mapreduce.Job:  map 94% reduce 4%
18/10/19 09:43:56 INFO mapreduce.Job:  map 95% reduce 4%
18/10/19 09:43:58 INFO mapreduce.Job:  map 96% reduce 8%
18/10/19 09:43:59 INFO mapreduce.Job:  map 97% reduce 12%
18/10/19 09:44:00 INFO mapreduce.Job:  map 97% reduce 16%
18/10/19 09:44:03 INFO mapreduce.Job:  map 97% reduce 20%
18/10/19 09:44:05 INFO mapreduce.Job:  map 98% reduce 24%
18/10/19 09:44:06 INFO mapreduce.Job:  map 99% reduce 28%
18/10/19 09:44:08 INFO mapreduce.Job:  map 99% reduce 29%
18/10/19 09:44:11 INFO mapreduce.Job:  map 100% reduce 29%
18/10/19 09:44:13 INFO mapreduce.Job:  map 100% reduce 32%
18/10/19 09:44:14 INFO mapreduce.Job:  map 100% reduce 35%
18/10/19 09:44:15 INFO mapreduce.Job:  map 100% reduce 39%
18/10/19 09:44:16 INFO mapreduce.Job:  map 100% reduce 43%
18/10/19 09:44:17 INFO mapreduce.Job:  map 100% reduce 51%
18/10/19 09:44:18 INFO mapreduce.Job:  map 100% reduce 55%
18/10/19 09:44:19 INFO mapreduce.Job:  map 100% reduce 58%
18/10/19 09:44:20 INFO mapreduce.Job:  map 100% reduce 60%
18/10/19 09:44:21 INFO mapreduce.Job:  map 100% reduce 66%
18/10/19 09:44:22 INFO mapreduce.Job:  map 100% reduce 70%
18/10/19 09:44:23 INFO mapreduce.Job:  map 100% reduce 74%
18/10/19 09:44:25 INFO mapreduce.Job:  map 100% reduce 75%
18/10/19 09:44:26 INFO mapreduce.Job:  map 100% reduce 82%
18/10/19 09:44:27 INFO mapreduce.Job:  map 100% reduce 86%
18/10/19 09:44:28 INFO mapreduce.Job:  map 100% reduce 90%
18/10/19 09:44:29 INFO mapreduce.Job:  map 100% reduce 92%
18/10/19 09:44:31 INFO mapreduce.Job:  map 100% reduce 97%
18/10/19 09:44:33 INFO mapreduce.Job:  map 100% reduce 100%
18/10/19 09:44:35 INFO mapreduce.Job: Job job_1539941976071_0001 completed successfully
18/10/19 09:44:35 INFO mapreduce.Job: Counters: 49
	File System Counters
		FILE: Number of bytes read=2268844498
		FILE: Number of bytes written=4517410531
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=5120024024
		HDFS: Number of bytes written=5120000000
		HDFS: Number of read operations=492
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=16
	Job Counters
		Launched map tasks=156
		Launched reduce tasks=8
		Data-local map tasks=156
		Total time spent by all maps in occupied slots (ms)=1888513
		Total time spent by all reduces in occupied slots (ms)=368037
		Total time spent by all map tasks (ms)=1888513
		Total time spent by all reduce tasks (ms)=368037
		Total vcore-milliseconds taken by all map tasks=1888513
		Total vcore-milliseconds taken by all reduce tasks=368037
		Total megabyte-milliseconds taken by all map tasks=1933837312
		Total megabyte-milliseconds taken by all reduce tasks=376869888
	Map-Reduce Framework
		Map input records=51200000
		Map output records=51200000
		Map output bytes=5222400000
		Map output materialized bytes=2223633259
		Input split bytes=24024
		Combine input records=0
		Combine output records=0
		Reduce input groups=51200000
		Reduce shuffle bytes=2223633259
		Reduce input records=51200000
		Reduce output records=51200000
		Spilled Records=102400000
		Shuffled Maps =1248
		Failed Shuffles=0
		Merged Map outputs=1248
		GC time elapsed (ms)=30062
		CPU time spent (ms)=873260
		Physical memory (bytes) snapshot=85005885440
		Virtual memory (bytes) snapshot=258850648064
		Total committed heap usage (bytes)=94389665792
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters
		Bytes Read=5120000000
	File Output Format Counters
		Bytes Written=5120000000
18/10/19 09:44:35 INFO terasort.TeraSort: done

real	3m20.466s
user	0m9.438s
sys	0m0.768s
```
