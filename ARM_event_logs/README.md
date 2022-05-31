An experiment of using Associative Rule Mining (ARM) to correlate events
and tie frequently occuring events together. This is particularly useful 
when having to sift through several hundreds of thousands of events/logs 
aggregated from network or software components in one place. While modern
log analytics provide means to search data through indexing and knowing
when volumes were high nothing really exists out there to find frequently
occuring patterns.

For instance, imagine we have APM/app logs, k8s logs and logs from network
functions like NFS/EFS - we want to have ability to root-cause slow app
performance by stitching logs/events from app -> etcd -> nfs/efs. And do
this using ARM techniques crunching through large data sets.

Pre-req: In order to make ARM efficient (reducing feature dimensions), 
parse the data using some NLTK libraries and filter to remove stop-words
and other redundant symbols.

Goal: The end goal of something like this to allow SREs/ITOps/DevOps/
SecOps tag the groupings and associate remediaton steps with tags so, 
future occurences are automatically healed.

The idea overall is to replace complex tasks (looking through logs,
identifying patterns, constantly adapt to new logging/events and associate 
it etc.) with machines and yet leave critical decision points to humans,
where human=SRE/ITOps/DevOps/SecOps.  
