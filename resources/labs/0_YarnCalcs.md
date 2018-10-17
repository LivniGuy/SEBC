# Assuming a cluster with Analytics and MapReduce use cases - I will include Impala daemons as well (without HBase or SOLR)

## Following Cloudera 5.x release notes and Tuning YARN document:
https://www.cloudera.com/documentation/enterprise/release-notes/topics/hardware_requirements_guide.html
http://www.cloudera.com/documentation/enterprise/latest/topics/cdh_ig_yarn_tuning.html

Decreased OS memory from 12.8 GB to 8 GB - Starting with the minimum requirement
Increased Impala memory from 0 GB to 32 GB and 4 vcores to allow running BI/Analytics workloads


### What criteria affects workload factor? What does a value of 1, 2, or 4 signify?

Workload factor should be decided by how busy our cluster will be, will we have a few large batch jobs or many small jobs in parallel.
Workload factor affects how many maps each job will get, the higher it is, the more mappers a job will get.


