# Spark / PySpark / Databricks ADF Interview Questions

This README provides answers to frequently asked questions related to Spark, PySpark, Databricks, and Azure Data Factory (ADF).

## Spark / PySpark / Databricks

1. **Describe the PySpark architecture.**

    - **Answer:** The PySpark architecture consists of various components such as SparkContext, SparkSession, DataFrame, RDD, Catalyst optimizer, and Execution Engine. It provides a distributed data processing framework for large-scale data processing.

2. **What are RDDs in PySpark?**

    - **Answer:** RDDs (Resilient Distributed Datasets) are the fundamental data structure in PySpark, representing a distributed collection of objects across the Spark cluster. They are immutable and fault-tolerant.

3. **Explain the concept of lazy evaluation in PySpark.**

    - **Answer:** Lazy evaluation means that transformations on RDDs or DataFrames in PySpark are not executed immediately. Instead, transformations are stored as a directed acyclic graph (DAG), and actions trigger the execution of the DAG.

4. **How does PySpark differ from Apache Hadoop?**

    - **Answer:** PySpark is a Python API for Apache Spark, while Apache Hadoop is a distributed storage and processing framework. PySpark provides a more user-friendly interface and supports various programming languages like Python, Scala, and Java.

5. **What are DataFrames in PySpark?**

    - **Answer:** DataFrames in PySpark are distributed collections of data organized into named columns, similar to tables in relational databases. They provide a higher-level API than RDDs and support various relational and functional operations.

6. **How do you initialize a SparkSession?**

    - **Answer:** You can initialize a SparkSession in PySpark using the `SparkSession.builder` method. Example:

       ```python
       from pyspark.sql import SparkSession
       spark = SparkSession.builder.appName("MyApp").getOrCreate()
       ```

7. **What is the significance of the SparkContext?**

    - **Answer:** SparkContext is the entry point for interacting with Spark functionality. It coordinates the execution of Spark jobs in a cluster and provides access to various Spark features like RDDs.

8. **Describe the types of transformations in PySpark.**

    - **Answer:** Transformations in PySpark are operations that transform an RDD or DataFrame into another RDD or DataFrame. Common transformations include `map()`, `filter()`, `join()`, `groupBy()`, `agg()`, etc.

9. **What is Azure Databricks.**

    - **Answer:** Azure Databricks is an Apache Spark-based analytics platform optimized for Azure. It provides a collaborative environment for data scientists, data engineers, and analysts to work together on big data and AI projects.

10. **Explain the role of Apache Spark in Azure Databricks.**

    - **Answer:** Apache Spark is the underlying distributed computing engine used in Azure Databricks for processing large-scale data analytics and machine learning workloads.

11. **How do you configure a Spark cluster in Azure Databricks?**

    - **Answer:** In Azure Databricks, you can configure a Spark cluster through the Databricks UI or using the Databricks CLI. You can specify the cluster configuration, including instance types, number of nodes, and auto-scaling options.

12. **What are the advantages of using PySpark in Azure Databricks for data processing?**

    - **Answer:** Some advantages of using PySpark in Azure Databricks include seamless integration with other Azure services, scalability, performance optimization, collaborative environment, and support for big data processing and machine learning.

13. **Describe the concept of notebooks in Azure Databricks.**

    - **Answer:** Notebooks in Azure Databricks are interactive documents that combine live code, visualizations, narrative text, and other rich media. They provide a collaborative environment for data exploration, analysis, and sharing.

14. **How do Azure Databricks workspaces enhance collaboration?**

    - **Answer:** Azure Databricks workspaces provide a centralized environment for teams to collaborate on data analytics projects. They offer features like version control, shared notebooks, role-based access control (RBAC), and integration with Git repositories.

15. **What is the Databricks File System (DBFS), and how is it used?**

    - **Answer:** DBFS is a distributed file system provided by Azure Databricks for storing data and files. It provides a unified interface to access data across various storage solutions like Azure Blob Storage, Azure Data Lake Storage, and local file systems.

16. **How do you schedule jobs in Azure Databricks?**

    - **Answer:** Jobs in Azure Databricks can be scheduled using the Databricks UI or API. You can specify the notebook or jar file, cluster configuration, schedule frequency, and other parameters.

17. **Explain the significance of Delta Lake in Azure Databricks.**

    - **Answer:** Delta Lake is an open-source storage layer that brings ACID transactions, schema enforcement, and time travel capabilities to data lakes. It ensures data reliability, consistency, and performance for big data analytics and machine learning workloads.

18. **How do you read a CSV file into a PySpark DataFrame?**

    - **Answer:** You can read a CSV file into a PySpark DataFrame using the `spark.read.csv()` method. Example:

       ```python
       df = spark.read.csv("path/to/your/file.csv", header=True, inferSchema=True)
       ```

19. **What are actions in PySpark, and how do they differ from transformations?**

    - **Answer:** Actions in PySpark are operations that trigger the execution of a Spark job and return a result to the driver program. They differ from transformations, which are lazy evaluated operations on RDDs or DataFrames that produce new RDDs or DataFrames.

20. **How can you filter rows in a DataFrame?**

    - **Answer:** You can filter rows in a DataFrame using the `filter()` method or boolean conditions within `df.select()`. Example:

       ```python
       filtered_df = df.filter(df["column"] > 5)
       ```

21. **Explain how to perform joins in PySpark.**

    - **Answer:** Joins in PySpark can be performed using the `join()` method by specifying the join condition and type of join (inner, outer, left, right). Example:

       ```python
       joined_df = df1.join(df2, on="common_column", how="inner")
       ```

22. **How do you aggregate data in PySpark?**

    - **Answer:** Data aggregation in PySpark can be done using methods like `groupBy()` followed by aggregate functions like `agg()`. Example:

       ```python
       aggregated_df = df.groupBy("group_column").agg({"value_column": "sum"})
       ```

23. **What are UDFs (User Defined Functions), and how are they used?**

    - **Answer:** UDFs in PySpark allow you to define custom functions in Python and apply them to DataFrame columns. Example:

       ```python
       from pyspark.sql.functions import udf
       from pyspark.sql.types import IntegerType

       def square(x):
           return x ** 2

       square_udf = udf(square, IntegerType())

       df = df.withColumn("squared_column", square_udf(df["column"]))
       ```

24. **How can you handle missing or null values in PySpark?**

    - **Answer:** Missing or null values in PySpark can be handled using methods like `fillna()` or `dropna()`. Example:

       ```python
       filled_df = df.fillna(0)
       ```

25. **How do you repartition a DataFrame, and why?**

    - **Answer:** You can repartition a DataFrame using the `repartition()` method to redistribute data across partitions. This is useful for improving parallelism and optimizing performance. Example:

       ```python
       repartitioned_df = df.repartition(10)
       ```

26. **Describe how to cache a DataFrame. Why is it useful?**

    - **Answer:** Caching a DataFrame in PySpark can be done using the `cache()` method. It is useful for storing intermediate results in memory to avoid recomputation and improve performance.

27. **How do you save a DataFrame to a file?**

    - **Answer:** You can save a DataFrame to a file using the `write` method with appropriate format and options. Example:

       ```python
       df.write.csv("path/to/save/file.csv", header=True)
       ```

28. **What is the Catalyst Optimizer?**

    - **Answer:** The Catalyst Optimizer is a query optimizer in Spark that optimizes the execution plan of DataFrame operations for better performance.

29. **Explain the concept of partitioning in PySpark.**

    - **Answer:** Partitioning in PySpark involves splitting a DataFrame into smaller parts based on certain criteria. It helps in parallelizing data processing and optimizing performance.

30. **How can broadcast variables improve performance?**

    - **Answer:** Broadcast variables in PySpark allow you to efficiently distribute read-only variables to all the nodes in a Spark cluster. They improve performance by reducing data transfer and memory usage during computation.

31. **What are accumulators, and how are they used?**

    - **Answer:** Accumulators in PySpark are variables that are shared across tasks and updated through associative and commutative operations. They are used for aggregating information or collecting statistics across tasks.

32. **Describe strategies for optimizing PySpark jobs.**

    - **Answer:** Strategies for optimizing PySpark jobs include partitioning, caching, using broadcast variables, tuning parallelism, and optimizing data shuffling.

33. **What is the significance of the Tungsten execution engine?**

    - **Answer:** The Tungsten execution engine in Spark improves memory management and processing speed by using binary memory representation and optimized execution algorithms.

34. **How does PySpark handle data skewness?**

    - **Answer:** PySpark handles data skewness by using techniques like salting, custom partitioning, and skew join optimization to distribute data evenly across partitions.

35. **What are the best practices for managing memory in PySpark?**

    - **Answer:** Best practices for managing memory in PySpark include optimizing data serialization, tuning memory configurations, caching intermediate results, and monitoring memory usage.

36. **How can you monitor the performance of a PySpark application?**

    - **Answer:** You can monitor the performance of a PySpark application using Spark UI, monitoring tools like Ganglia or Prometheus, and logging application metrics.

37. **Explain how checkpointing works in PySpark.**

    - **Answer:** Checkpointing in PySpark involves saving the state of RDDs to disk to prevent recomputation in case of failures. It helps in improving fault tolerance and optimizing lineage computation.

38. **What is delta lake?**

    - **Answer:** Delta Lake is an open-source storage layer that brings ACID transactions, schema enforcement, and time travel capabilities to data lakes. It ensures data reliability, consistency, and performance for big data analytics and machine learning workloads.

39. **What is data lakehouse architecture?**

    - **Answer:** Data lakehouse architecture combines the best aspects of data lakes and data warehouses by integrating scalable storage (data lake) with transactional capabilities (data warehouse) in a unified architecture.

### ADF Interview Questions

1. **Integration runtime**

    - **Answer:** Integration runtime in Azure Data Factory (ADF) is the compute infrastructure used by ADF to provide data integration capabilities across different network environments.

2. **Self hosted IR**

    - **Answer:** Self-hosted integration runtime in Azure Data Factory (ADF) allows you to run data integration tasks on your on-premises infrastructure or virtual machines.

3. **On-prem to Cloud Migration**

    - **Answer:** On-prem to cloud migration in Azure Data Factory (ADF) involves moving data and workloads from on-premises systems to cloud-based storage and compute services.

4. **Schedule Triggers**

    - **Answer:** Schedule triggers in Azure Data Factory (ADF) allow you to schedule and automate the execution of data integration pipelines at specified times or intervals.

