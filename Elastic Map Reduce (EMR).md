Master node controls and directs the cluster. When the master node terminates, it ends the  
EMR cluster. Since the data is critical, we cannot use a spot instance for the master node. Core  
nodes process data and store using HDFS. When you terminate a core instance, there is a risk  
of data loss. We cannot use a spot instance for a core node as the question mentions that data  
is critical. Task nodes process data but do not hold persistent data in HDFS. If a task node  
terminates, there is no risk of data loss. Adding additional spot capacity to task nodes is a great  
way to speed up data processing.