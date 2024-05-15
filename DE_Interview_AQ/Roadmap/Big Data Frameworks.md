# Big Data Frameworks:

#### Apache Hadoop:
**Architecture**: Apache Hadoop is designed to handle and process large datasets distributed across clusters of commodity hardware. Its core components are:
- **HDFS (Hadoop Distributed File System)**: This is the storage layer of Hadoop. It divides files into large blocks (typically 128MB or 256MB) and distributes them across the cluster. It provides high-throughput access to application data and is fault-tolerant.
- **MapReduce**: This is a programming model for processing and generating large datasets. It consists of two parts: the Map function, which processes key-value pairs to generate intermediate key-value pairs, and the Reduce function, which processes these intermediate pairs to produce the final output. MapReduce operates on data stored in HDFS.
- **YARN (Yet Another Resource Negotiator)**: YARN is the resource management layer of Hadoop. It manages and allocates resources (CPU, memory) across applications running on the cluster.

#### Apache Hive:
- **Loading data from various file formats**: Apache Hive is a data warehouse infrastructure built on top of Hadoop. It provides tools to enable easy data summarization, ad-hoc querying, and analysis of large datasets. Hive supports various file formats such as text, CSV, Parquet, ORC, Avro, etc.
- **Internal vs external tables**: Internal tables manage data within the Hive warehouse directory. External tables, on the other hand, reference data located outside of the Hive warehouse directory. Dropping an internal table also deletes its data, whereas dropping an external table only removes the table metadata.
- **Partitioning**: Partitioning allows Hive to organize data in a table into multiple directories based on the values of one or more columns. It helps improve query performance by reducing the amount of data that needs to be scanned.
- **Bucketing**: Bucketing is another way to organize data in Hive tables. It divides data into a fixed number of buckets based on the hash value of a column. Bucketing can improve query performance, especially when used in conjunction with partitioning.
- **Map-side join**: Map-side join is a type of join operation in Hive where the join is performed during the map phase of MapReduce. It is more efficient than traditional reduce-side joins as it reduces the amount of data shuffled between nodes.
- **Sorted-merge join**: Sorted-merge join is another type of join operation in Hive where the data is sorted before the join operation. It merges sorted datasets efficiently to perform the join.
- **UDF (User-defined functions)**: Hive allows users to define custom functions to extend its functionality. These functions can be written in Java, Python, or other languages supported by Hive.
- **SerDe (Serializer/Deserializer)**: SerDe is a mechanism in Hive for serializing and deserializing data between the internal representation used by Hive and the external representation used by storage systems or file formats.

#### Apache Spark:
- **RDDs (Resilient Distributed Datasets)**: RDDs are the fundamental data structure in Spark. They represent a collection of immutable, partitioned records that can be processed in parallel across a cluster.
- **Transformations and Actions**: Transformations are operations that transform one RDD into another, while actions are operations that trigger computation and return results to the driver program.
- **Spark Context**: Spark Context is the main entry point for Spark functionality. It represents the connection to a Spark cluster and is used to create RDDs, broadcast variables, and accumulators.
- **Shared Variables**: Shared variables are variables that can be shared across tasks running on a Spark cluster. Examples include broadcast variables and accumulators.
- **Caching**: Caching allows you to persist RDDs in memory across multiple operations. It improves performance by avoiding recomputation of RDDs.
- **DataFrame and Dataset API**: DataFrame and Dataset APIs provide higher-level abstractions for working with structured data in Spark. They offer optimizations and a more user-friendly interface compared to RDDs.
- **Spark SQL Functions**: Spark SQL provides a rich set of built-in functions for querying and manipulating data.
- **Joins and Aggregations**: Spark supports various types of joins (e.g., inner join, outer join) and aggregation operations (e.g., sum, count).
- **Window Functions**: Window functions allow you to perform calculations across a set of rows related to the current row.
- **Partitioning and Shuffling**: Partitioning controls the distribution of data across partitions, while shuffling is the process of redistributing data across partitions.
- **Broadcast Variables and Accumulators**: Broadcast variables allow you to efficiently distribute large read-only variables to all nodes in a Spark cluster, while accumulators are variables that can be used for aggregating values across tasks.
- **Understanding Spark Cluster & Cluster Modes**: Spark can run in various cluster modes such as standalone mode, YARN mode, and Mesos mode. Each mode has its own resource manager for managing cluster resources.
- **How Spark Executes Program on the Cluster**: Spark programs are executed in a distributed manner across the nodes in a cluster. Tasks are scheduled and executed by the Spark driver program.
- **Stages in Spark**: Spark programs are divided into stages based on the transformations and actions applied to RDDs. Each stage consists of tasks that can be executed in parallel.
- **Repartition Vs Coalesce**: Repartition and coalesce are operations used to control the partitioning of data in RDDs. Repartition reshuffles data across partitions, while coalesce reduces the number of partitions without shuffling.
- **Lazy Evaluation**: Spark uses lazy evaluation, which means that transformations on RDDs are not executed immediately. Instead, they are queued up and executed when an action is called.
- **Narrow Vs Wide Transformations**: Narrow transformations are transformations where each input partition contributes to only one output partition, while wide transformations are transformations where each input partition can contribute to multiple output partitions.
- **Spark Storage Levels**: Spark provides different storage levels for persisting RDDs in memory or disk. Examples include MEMORY_ONLY, MEMORY_AND_DISK, etc.
- **Cache Vs Persist**: Cache and persist are operations used to persist RDDs in memory or disk for reuse in subsequent operations.
- **Spark Optimization Techniques**: Spark provides various optimization techniques such as predicate pushdown, broadcast join, and partition pruning to improve performance.
- **File Formats — Parquet | ORC | Avro**: Spark supports various file formats for reading and writing data, including Parquet, ORC, and Avro. These formats are optimized for performance and storage efficiency.
- **Compression Techniques**: Spark supports various compression techniques such as Snappy, Gzip, and LZO for compressing data to reduce storage space and improve read and write performance.
- **Understanding Cluster Configurations**: Understanding the configuration of the Spark cluster is essential for optimizing performance and resource utilization.
- **How to Submit Spark Job Scheduling and Running Spark Jobs**: Spark jobs can be submitted using the spark-submit command-line tool or through Spark APIs. It is essential to schedule and manage Spark jobs effectively to utilize cluster resources efficiently.
- **Sort Vs Hash Aggregate**: Sort and hash aggregate are different strategies used for aggregating data in Spark. Sort aggregation involves sorting data before performing aggregation, while hash aggregation involves hashing data to perform aggregation.
- **Spark Catalyst Optimizer**: Spark Catalyst optimizer is a query optimizer that optimizes Spark SQL queries by transforming logical plans into more efficient physical plans.
