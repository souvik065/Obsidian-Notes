

- Hadoop is an open source framework that allows us to store & process large data sets in a **parallel** & **distributed manner**.+
- Hadoop stores data in a distributed manner into multiple clusters.

-  Doug Cutting and Mike Cafarella.
- 2008 it became a open source
- It's an framework to how we can store Large Number Data in todays world.

- Two main component **HDFS(Hadoop Distributed File System)** & **MapReduce**.
-  It has been written in java
- Master Data



## **HDFS(Hadoop Distributed File System)**
- It's one partition it self is 128MB
-  We can access data through **Master Node(meta data)**.
- It also replicate multiple copy of Data nodes
- Purpose of HDFS is to store the data into multiple data node into a cluster form.


## **MapReduce**
- **MapReduce** performs the processing of large data sets in a distributed and parallel manner.
- **MapReduce** consists of two distinct task - **Map** and **Reduce**. 
- **MapReduce** is a processing element in the concept of key value pair.
 
- We need a processing unit which can parallelly process the data.
- Their are two class inside this MapReduce 
	1. Map
	2. Reduce
	- It work's in **divide** and **concur** approach (divide and conure rule means, it split's or breaks the problem into small problems.)
- Two essential daemons of MapReduce: **Job-Tracker** and **Task-Tracker**.
- Job-Tracker works as **Master Tracker**, Monitoring
- Task-Tracker work as Slave/Employee


## Hadoop Deployment Modes

1. Local (Standalone) - Default
2. Pseudo distributed
3. Fully Distributed 

### Standalone Mode
- None of the daemons will run (name node, Data name, Job-Tracker, Map-Reduce)
- Hadoop works very much fastest in this mode among all of this three mode
- we only use this mode for the purpose of learning, testing and debugging.

### Pseudo - Distributed mode (single node cluster)
- Master(**Job-Tracker**) and Slave(**Task-Tracker**.) process are handled by single system.
- All the process inside cluster will run independent 
- All daemon will run separately on various JVM
- used for - Development and debugging purposes and manages the I/O process

### Fully Distributed Mode (Multiple Node Cluster)
- (Most Imp mode) it is the actual Hadoop cluster.
- Has multiple nodes few of them run Master daemon rest are slaves
- Data that is distributed across different nodes


### **YARN(Yet Another Resource Negotiator) in Hadoop**

- YARN is core component of Hadoop
- YARN is the next generation Hadoop computing of platforms
- Available in Hadoop 2.0
- it's separates the resource management layer and the processing component layer.
- Resource Management: Monitor nodes, allocate resources and schedule jobs.
- Node Manager: to oversee the containers running on the cluster nodes.
- Application Master: which negotiates with  the resource manager for resources and runs the application-specific process 



**Use Case:** Storing and processing large amounts of backup data in the cloud using Hadoop ensures data is always available and recoverable.

**Use Case:** Hadoop can serve as a data warehouse for storing massive volumes of data and running complex queries across it.
