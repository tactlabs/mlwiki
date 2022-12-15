/ [Home](index.md)

# PySpark

<br>

![PySpark](images/PySpark.png "PySpark")

<br>

Apache Spark is written in Scala programming language. PySpark has been released in order to support the collaboration of Apache Spark and Python, it actually is a Python API for Spark. In addition, PySpark, helps you interface with Resilient Distributed Datasets (RDDs) in Apache Spark and Python programming language. 

Advantages of PySpark:
* Simple to write
* Framework handles errors
* Ease of use

Disadvantages of PySpark:
* Difficult to express
* Less Efficient



```
Spark Extraction using READ API:
✅ creating dataframe using spark read api
✅ df = spark.read.api (csv,json,parquet,orc,text....)
✅ df = spark.createDataFrame(data,schema)
✅ df = spark.read.format().load() (format - csv,json,xml,excel,....)

Spark Transform using Metadata and Data Transformations:
✅ df = df.withColumn() - for adding new column or chaging data type
✅ df = df.withColumnRenamed() - for renaming a column
✅ df = df.drop() - removing a column or columns
✅ df = df.toDF() - renaming multiple columns
✅ df = df.dropDuplicates() - for removing duplicates
✅ df = df.dropna(how='all') - for removing null rows
✅ df = df.fillna({col:val,col2:val}) - for converting null values into actual values
✅ df = df.filter() - for filtering rows based on condition
✅ df = df.select() - for selecting required columns
✅ df = df.selectExpr() - for selecting columns with expressions
✅ df = df.groupBy().agg() - for grouping and aggregations
✅ df = df.orderBy() - for global sorting
✅ df = df.sort() - for local sorting

Spark Load using Write API:
✅ Loading data into table or File using write API
✅ df.write.format("csv").mode("append").saveAsTable(table) -- table
✅ df.write.format("csv").mode("append").save(path) -- file
✅ df.write.format("csv").mode("overwrite").saveAsTable(table)
✅ df.write.format("csv").mode("overwrite").save(path) -- file
```