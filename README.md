# Large_Computing_Cluster_Job_Scheduling
## Data Question 2: The Advanced Computing Center for Research and Education

In this data question, you will be analyzing data on jobs run on ACCRE's hardware. You will need to do some data cleaning and preparation and then explore and analyze to answer the following questions.

### Data cleaning / formatting

  * We really only want to look at the "production" partition so rows with other partitions should be removed

  * Job time is in a format of either d-hh:mm:ss or hh:mm:ss, it needs to be converted to total seconds

  * Only successful jobs with "0:0" exit codes should be considered for memory use analysis

  * Memory is reported in terms of Megabytes per node (Mc) or Megabytes per core (Mc), this needs to be uniformly converted to Megabytes per core by dividing by the number of cores per node in a job.


### Project questions

  * While we have systematic checks in place to ensure the general system health of each compute node, we would like to use long-term data to see if there are any clusters of job failures on specific nodes. Do any of the production partition nodes show an unusual number of failed jobs relative to the others? Ignore the debug partition for this question.

  * The CMS collaboration has an automated job submission system that runs jobs as "cmslocal" and "cmspilot". For these two users, jobs have internal system tests that will terminate their jobs early after approximately 30 minutes. Do any of their jobs that ended in under an hour also cluster on specific compute nodes, suggesting possbily unreliable systems? Check both “production” and “nogpfs” partitions. Look for commonly failing nodes and compare with other failed jobs.

  * What groups are best optimizing their memory usage in terms of percent of actual memory used of the memory requested for a job? What is the average percent for each group?

  * Optimizing memory is more important for longer running jobs then shorter running jobs as the resources are tied up for longer. If jobs are weighted by runtime, what is the average percent of memory used of the requested memory for each group?
