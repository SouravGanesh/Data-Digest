# ETL Flow Documentation

## 1) Setting up ETL Flow

To set up the ETL flow for processing files placed in an S3 bucket and loading them into Redshift, we follow these steps:

- **Triggering ETL:** We utilize AWS Lambda to trigger an AWS Glue ETL job whenever new files are placed in the S3 bucket. This is achieved by configuring an S3 event notification to invoke the Lambda function upon object creation.

- **ETL Process:** The AWS Glue ETL job reads the data from S3, performs necessary transformations using PySpark (or Python), and then loads the processed data into the target Redshift database.

## 2) Full Load and Incremental Load

Yes, I have worked on both full load and incremental load strategies as part of ETL processes. Full load involves loading all data from the source into the target, while incremental load involves loading only the changed or new data since the last ETL run.

## 3) Loading Modes on Target Side

The different loading modes used on the target side include:
- **Full Load:** Loading all data from the source into the target.
- **Incremental Load:** Loading only the changed or new data since the last load.
- **Append Load:** Appending new data to the existing data in the target.
- **Overwrite Load:** Overwriting existing data in the target with new data.

## 4) Configuring ETL Glue Job from Scratch

Yes, I have experience in configuring AWS Glue ETL jobs from scratch to perform various data transformation and loading tasks.

## 5) Difference between List and Tuple

A list is a mutable data type in Python, meaning its elements can be modified after creation. On the other hand, a tuple is immutable, meaning its elements cannot be changed after creation.

## 6) DataFrame

DataFrame is a two-dimensional labeled data structure in pandas, which is widely used for data manipulation and analysis in Python.

## 7) Pandas Library

Yes, I am familiar with the pandas library and have used it extensively for data manipulation tasks in Python.

## 8) Working with File System or Databases through Python or PySpark

I have experience working with both file systems and databases using Python's built-in libraries such as `os` for file system operations and libraries like `psycopg2` for database connectivity. Additionally, I have used PySpark for working with distributed file systems and processing large-scale data.

## 9) Converting CSV to Parquet

Below is a Python program to convert a CSV file stored in an S3 bucket to a Parquet file:

```python
# Python code to convert CSV to Parquet
import pandas as pd

# Read CSV from S3
df = pd.read_csv('s3://bucket_name/file.csv')

# Write Parquet to S3
df.to_parquet('s3://bucket_name/file.parquet')
```
