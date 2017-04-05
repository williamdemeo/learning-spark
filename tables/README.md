<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Spark Book Notes](#spark-book-notes)
  - [Chapter 1. Introduction to Data Analysis](#chapter-1-introduction-to-data-analysis)
    - [What Is Apache Spark?](#what-is-apache-spark)
    - [A Unified Stack](#a-unified-stack)
      - [Spark Core](#spark-core)
      - [Spark SQL](#spark-sql)
      - [Spark Streaming](#spark-streaming)
      - [MLlib](#mllib)
      - [GraphX](#graphx)
      - [Cluster Managers](#cluster-managers)
    - [Who Uses Spark, and for What?](#who-uses-spark-and-for-what)
      - [Data Science Tasks](#data-science-tasks)
      - [Data Processing Applications](#data-processing-applications)
    - [A Brief History of Spark](#a-brief-history-of-spark)
    - [Spark Versions and Releases](#spark-versions-and-releases)
    - [Storage Layers for Spark](#storage-layers-for-spark)
  - [Chapter 2. Downloading Spark and Getting Started](#chapter-2-downloading-spark-and-getting-started)
    - [Downloading Spark](#downloading-spark)
    - [Introduction to Spark's Python and Scala Shells](#introduction-to-sparks-python-and-scala-shells)
    - [Introduction to Core Spark Concepts](#introduction-to-core-spark-concepts)
    - [Standalone Applications](#standalone-applications)
      - [Initializing a SparkContext](#initializing-a-sparkcontext)
      - [Building Standalone Applications](#building-standalone-applications)
    - [Conclusion](#conclusion)
  - [Chapter 3. Programming with RDDs](#chapter-3-programming-with-rdds)
    - [RDD Basics](#rdd-basics)
    - [Creating RDDs](#creating-rdds)
    - [RDD Operations](#rdd-operations)
      - [Transformations](#transformations)
      - [Actions](#actions)
      - [Lazy Evaluation](#lazy-evaluation)
    - [Passing Functions to Spark](#passing-functions-to-spark)
    - [Common Transformations and Actions](#common-transformations-and-actions)
      - [Basic RDDs](#basic-rdds)
      - [Converting Between RDD Types](#converting-between-rdd-types)
    - [Persistence (Caching)](#persistence-caching)
    - [Conclusion](#conclusion-1)
  - [Chapter 4. Working with Key/Value Pairs](#chapter-4-working-with-keyvalue-pairs)
    - [Motivation](#motivation)
    - [Creating Pair RDDs](#creating-pair-rdds)
    - [Transformations on Pair RDDs](#transformations-on-pair-rdds)
      - [Aggregations](#aggregations)
      - [Grouping Data](#grouping-data)
      - [Joins](#joins)
      - [Sorting Data](#sorting-data)
    - [Actions Available on Pair RDDs](#actions-available-on-pair-rdds)
    - [Data Partitioning (Advanced)](#data-partitioning-advanced)
      - [Determining an RDD's Partitioner](#determining-an-rdds-partitioner)
      - [Operations That Benefit from Partitioning](#operations-that-benefit-from-partitioning)
      - [Operations That Affect Partitioning](#operations-that-affect-partitioning)
      - [Example: PageRank](#example-pagerank)
      - [Custom Partitioners](#custom-partitioners)
    - [Conclusion](#conclusion-2)
  - [Chapter 5. Loading and Saving Your Data](#chapter-5-loading-and-saving-your-data)
    - [Motivation](#motivation-1)
    - [File Formats](#file-formats)
      - [Text Files](#text-files)
      - [JSON](#json)
      - [Comma-Separated Values and Tab-Separated Values](#comma-separated-values-and-tab-separated-values)
      - [SequenceFiles](#sequencefiles)
      - [Object Files](#object-files)
      - [Hadoop Input and Output Formats](#hadoop-input-and-output-formats)
      - [File Compression](#file-compression)
    - [Filesystems](#filesystems)
      - [Local/“Regular” FS](#localregular-fs)
      - [Amazon S3](#amazon-s3)
      - [HDFS](#hdfs)
    - [Structured Data with Spark SQL](#structured-data-with-spark-sql)
      - [Apache Hive](#apache-hive)
      - [JSON](#json-1)
    - [Databases](#databases)
      - [Java Database Connectivity](#java-database-connectivity)
      - [Cassandra](#cassandra)
      - [HBase](#hbase)
      - [Elasticsearch](#elasticsearch)
    - [Conclusion](#conclusion-3)
  - [Chapter 6. Advanced Spark Programming](#chapter-6-advanced-spark-programming)
    - [Introduction](#introduction)
    - [Accumulators](#accumulators)
      - [Accumulators and Fault Tolerance](#accumulators-and-fault-tolerance)
      - [Custom Accumulators](#custom-accumulators)
    - [Broadcast Variables](#broadcast-variables)
      - [Optimizing Broadcasts](#optimizing-broadcasts)
    - [Working on a Per-Partition Basis](#working-on-a-per-partition-basis)
    - [Piping to External Programs](#piping-to-external-programs)
    - [Numeric RDD Operations](#numeric-rdd-operations)
    - [Conclusion](#conclusion-4)
  - [Chapter 7. Running on a Cluster](#chapter-7-running-on-a-cluster)
    - [Introduction](#introduction-1)
    - [Spark Runtime Architecture](#spark-runtime-architecture)
      - [The Driver](#the-driver)
      - [Executors](#executors)
      - [Cluster Manager](#cluster-manager)
      - [Launching a Program](#launching-a-program)
      - [Summary](#summary)
    - [Deploying Applications with spark-submit](#deploying-applications-with-spark-submit)
    - [Packaging Your Code and Dependencies](#packaging-your-code-and-dependencies)
      - [A Java Spark Application Built with Maven](#a-java-spark-application-built-with-maven)
      - [A Scala Spark Application Built with sbt](#a-scala-spark-application-built-with-sbt)
      - [Dependency Conflicts](#dependency-conflicts)
    - [Scheduling Within and Between Spark Applications](#scheduling-within-and-between-spark-applications)
    - [Cluster Managers](#cluster-managers-1)
      - [Standalone Cluster Manager](#standalone-cluster-manager)
      - [Hadoop YARN](#hadoop-yarn)
      - [Apache Mesos](#apache-mesos)
      - [Amazon EC2](#amazon-ec2)
    - [Which Cluster Manager to Use?](#which-cluster-manager-to-use)
    - [Conclusion](#conclusion-5)
  - [Chapter 8. Tuning and Debugging Spark](#chapter-8-tuning-and-debugging-spark)
    - [Configuring Spark with SparkConf](#configuring-spark-with-sparkconf)
    - [Components of Execution: Jobs, Tasks, and Stages](#components-of-execution-jobs-tasks-and-stages)
    - [Finding Information](#finding-information)
      - [Spark Web UI](#spark-web-ui)
      - [Driver and Executor Logs](#driver-and-executor-logs)
    - [Key Performance Considerations](#key-performance-considerations)
      - [Level of Parallelism](#level-of-parallelism)
      - [Serialization Format](#serialization-format)
      - [Memory Management](#memory-management)
      - [Hardware Provisioning](#hardware-provisioning)
    - [Conclusion](#conclusion-6)
  - [Chapter 9. Spark SQL](#chapter-9-spark-sql)
    - [Linking with Spark SQL](#linking-with-spark-sql)
    - [Using Spark SQL in Applications](#using-spark-sql-in-applications)
      - [Initializing Spark SQL](#initializing-spark-sql)
      - [Basic Query Example](#basic-query-example)
      - [SchemaRDDs](#schemardds)
      - [Caching](#caching)
    - [Loading and Saving Data](#loading-and-saving-data)
      - [Apache Hive](#apache-hive-1)
      - [Parquet](#parquet)
      - [JSON](#json-2)
      - [From RDDs](#from-rdds)
    - [JDBC/ODBC Server](#jdbcodbc-server)
      - [Working with Beeline](#working-with-beeline)
      - [Long-Lived Tables and Queries](#long-lived-tables-and-queries)
    - [User-Defined Functions](#user-defined-functions)
      - [Spark SQL UDFs](#spark-sql-udfs)
      - [Hive UDFs](#hive-udfs)
    - [Spark SQL Performance](#spark-sql-performance)
      - [Performance Tuning Options](#performance-tuning-options)
    - [Conclusion](#conclusion-7)
  - [Chapter 10. Spark Streaming](#chapter-10-spark-streaming)
    - [A Simple Example](#a-simple-example)
    - [Architecture and Abstraction](#architecture-and-abstraction)
    - [Transformations](#transformations-1)
      - [Stateless Transformations](#stateless-transformations)
      - [Stateful Transformations](#stateful-transformations)
    - [Output Operations](#output-operations)
    - [Input Sources](#input-sources)
      - [Core Sources](#core-sources)
      - [Additional Sources](#additional-sources)
      - [Multiple Sources and Cluster Sizing](#multiple-sources-and-cluster-sizing)
    - [24/7 Operation](#247-operation)
      - [Checkpointing](#checkpointing)
      - [Driver Fault Tolerance](#driver-fault-tolerance)
      - [Worker Fault Tolerance](#worker-fault-tolerance)
      - [Receiver Fault Tolerance](#receiver-fault-tolerance)
      - [Processing Guarantees](#processing-guarantees)
    - [Streaming UI](#streaming-ui)
    - [Performance Considerations](#performance-considerations)
      - [Batch and Window Sizes](#batch-and-window-sizes)
      - [Level of Parallelism](#level-of-parallelism-1)
      - [Garbage Collection and Memory Usage](#garbage-collection-and-memory-usage)
    - [Conclusion](#conclusion-8)
  - [Chapter 11. Machine Learning with MLlib](#chapter-11-machine-learning-with-mllib)
    - [Overview](#overview)
    - [System Requirements](#system-requirements)
    - [Machine Learning Basics](#machine-learning-basics)
      - [Example: Spam Classification](#example-spam-classification)
    - [Data Types](#data-types)
      - [Working with Vectors](#working-with-vectors)
    - [Algorithms](#algorithms)
      - [Feature Extraction](#feature-extraction)
      - [Statistics](#statistics)
      - [Classification and Regression](#classification-and-regression)
      - [Clustering](#clustering)
      - [Collaborative Filtering and Recommendation](#collaborative-filtering-and-recommendation)
      - [Dimensionality Reduction](#dimensionality-reduction)
      - [Model Evaluation](#model-evaluation)
    - [Tips and Performance Considerations](#tips-and-performance-considerations)
      - [Preparing Features](#preparing-features)
      - [Configuring Algorithms](#configuring-algorithms)
      - [Caching RDDs to Reuse](#caching-rdds-to-reuse)
      - [Recognizing Sparsity](#recognizing-sparsity)
      - [Level of Parallelism](#level-of-parallelism-2)
    - [Pipeline API](#pipeline-api)
    - [Conclusion](#conclusion-9)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Spark Book Notes

**Title**: Learning Spark
**Authors**: Holden Karau, Andy Konwinski, Patrick Wendell, Matei Zaharia
**Date**: 2015
**Publisher**: O'Reilly

------------------------------------------------
## Chapter 1. Introduction to Data Analysis

### What Is Apache Spark?
### A Unified Stack
#### Spark Core
#### Spark SQL
#### Spark Streaming
#### MLlib
#### GraphX
#### Cluster Managers

### Who Uses Spark, and for What?
#### Data Science Tasks
#### Data Processing Applications

### A Brief History of Spark
### Spark Versions and Releases
### Storage Layers for Spark

-------------------------------------------------
## Chapter 2. Downloading Spark and Getting Started

### Downloading Spark
### Introduction to Spark's Python and Scala Shells
### Introduction to Core Spark Concepts
### Standalone Applications

The process of linking to Spark varies by language. In Java and Scala, you give your
application a Maven dependency on the spark-core artifact. As of the time of writ‐
ing, the latest Spark version is 1.2.0, and the Maven coordinates for that are:

```scala
	groupId = org.apache.spark
	artifactId = spark-core_2.10
	version = 1.2.0
```

Maven is a popular package management tool for Java-based languages that lets you
link to libraries in public repositories. You can use Maven itself to build your project,
or use other tools that can talk to the Maven repositories, including Scala's sbt tool or
Gradle. Popular integrated development environments like Eclipse also allow you to
directly add a Maven dependency to a project.

#### Initializing a SparkContext

Once you have linked an application to Spark, you need to import the Spark packages
in your program and create a SparkContext. You do so by first creating a SparkConf
object to configure your application, and then building a SparkContext for it.

**Example 2-8.** Initializing Spark in Scala
      
```scala
	import org.apache.spark.SparkConf
	import org.apache.spark.SparkContext
	import org.apache.spark.SparkContext._
	val conf = new SparkConf().setMaster("local").setAppName("My App")
	val sc = new SparkContext(conf)
```

This shows the minimal way to initialize a SparkContext, where you pass 2 parameters:
1. *A cluster URL*, namely local in these examples, which tells Spark how to connect
   to a cluster. `local` is a special value that runs Spark on one thread on the local
   machine, without connecting to a cluster.

2. *An application name*, namely `My App`, which will identify your
   application on the cluster manager's UI if you connect to a cluster.

Additional parameters exist for configuring how your application executes or adding
code to be shipped to the cluster; we'll cover these later.


#### Building Standalone Applications

This wouldn't be a complete introductory chapter of a Big Data book if we didn't
have a word count example. On a single machine, implementing word count is sim‐
ple, but in distributed frameworks it is a common example because it involves read‐
ing and combining data from many worker nodes.
      
**Example 2-11.** Word count Scala application--don't worry about the details yet
(See also: `learning-spark-examples/mini-complete-example` in the github repo)

```scala
	import org.apache.spark.SparkConf
	import org.apache.spark.SparkContext
	import org.apache.spark.SparkContext._

	// Create a Scala Spark Context.
	val conf = new SparkConf().setAppName("wordCount")
	val sc = new SparkContext(conf)

	// Load our input data.
	val input = sc.textFile(inputFile)

	// Split it up into words.
	val words = input.flatMap(line => line.split(" "))

	// Transform into pairs and count.
	val counts = words.map(word => (word, 1)).reduceByKey{case (x, y) => x + y}

	// Save the word count back out to a text file, causing evaluation.
	counts.saveAsTextFile(outputFile)
```

We can build this app with a very simple build files for sbt.
We've marked the Spark Core dependency as provided so that, later on, 
when we use an assembly JAR we don't include the spark-core JAR, which 
is already on the classpath of the workers.

**Example 2-12.** sbt build file (remember, blank lines are important here; 
note the `spark-core` package is marked "provided" in case we package
our application into an assembly JAR; see Ch. 7)

```scala
	name := "learning-spark-mini-example"

	version := "0.0.1"

	scalaVersion := "2.10.4"

	// additional libraries
	libraryDependencies ++= Seq(
	"org.apache.spark" %% "spark-core" % "1.2.0" % "provided"
	)
```

Once we have our build defined, we can easily package and run our application using
the bin/spark-submit script. The `spark-submit` script sets up a number of environment
variables used by Spark. 
      
**Example 2-14.** Scala build and run (start from the `mini-complete-example` directory)

```scala
	sbt clean package
	$SPARK_HOME/bin/spark-submit \
	--class com.oreilly.learningsparkexamples.mini.scala.WordCount \
	./target/learning-spark-mini-example-0.0.1.jar \
	./README.md ./wordcounts
```

### Conclusion

------------------------------

## Chapter 3. Programming with RDDs

### RDD Basics
### Creating RDDs
### RDD Operations
#### Transformations
#### Actions
#### Lazy Evaluation

### Passing Functions to Spark
### Common Transformations and Actions
#### Basic RDDs
#### Converting Between RDD Types

### Persistence (Caching)
### Conclusion

---------------------------------------
## Chapter 4. Working with Key/Value Pairs
### Motivation
### Creating Pair RDDs
### Transformations on Pair RDDs
Pair RDDs are allowed to use all the transformations available to standard RDDs. The
same rules apply from "Passing Functions to Spark" on page 30. Since pair RDDs
contain tuples, we need to pass functions that operate on tuples rather than on 
individual elements. Tables 4-1 and 4-2 summarize transformations on pair RDDs.

**Table 4-1.** Transformations on one pair RDD 

**Example:** `{(1, 2), (3, 4), (3, 6)}`

| Function name   | Purpose | Example | Result     |
| --------------- | --------| ------- | ---------- |
|`reduceByKey(func)` | Combine values with the same key| `rdd.reduceByKey((x, y) => x + y)`  | `{(1,2),(3,10)}`   |
| `groupByKey()`     | Group values with the same key.   | `rdd.groupByKey()` |  `{(1,[2]),(3, [4,6])}`|
| `combineByKey ( createCombiner, mergeValue, mergeCombiners, partitioner )`  | Combine values with the same key using a different result type. | See Ex 4-12--4-14 |       |
| `mapValues(func)` |  Apply a function to each value of a pair RDD without changing the key |  `rdd.mapValues(x => x+1)` | `{(1,3), (3,5), (3,7)}` |
| `flatMapValues(func)` | Apply a function that returns an iterator to each value of a pair RDD, and for each element returned, produce a key/value entry with the old key. Often used for tokenization | `rdd.flatMapValues(x => (x to 5))` | `{(1,2), (1,3),(1,4), (1, 5),(3, 4),(3, 5)}` |
| `keys()` | Return an RDD of just the keys  | `rdd.keys()` | `{1, 3, 3}` |
| `values()`| Return an RDD of just the values | `rdd.values()` | `{2, 4, 6}`|
| `sortByKey()` |  Return an RDD sorted by the key| `rdd.sortByKey()`| `{(1, 2), (3, 4), (3, 6)}` |


**Table 4-2.** Transformations on two pair RDDs 

**Example:** `rdd = {(1, 2), (3, 4), (3, 6)}; other = {(3, 9)}){(1, 2), (3, 4), (3, 6)}`

|------------------|------------------------------|----------------------------|------------|
|**Function name** | **Purpose**                  | **Example**                | **Result** |
|------------------|------------------------------|----------------------------|------------|
| `subtractByKey`  | Remove elements with a key   | `rdd.subtractByKey(other)` | `{(1, 2)}` |
|                  | key present in the other RDD |                            |            |
|------------------|------------------------------|----------------------------|------------|
| `join`           | Perform an inner join        | `rdd.join(other)` | `{(3, (4, 9)), (3, (6, 9))}`|
|                  | between two RDDs             |                   |                             | 
|------------------|------------------------------|-------------------|---------------------------------|
| `rightOuterJoin` | Perform a join between two   | `rdd.rightOuterJoin(other)` | `{(3,(Some(4),9)),`   |
|                  | RDDs where the key must      |                             |   ` (3,(Some(6),9))}` |
|                  | be present in the first RDD  |                             |                       |
|------------------|------------------------------|-----------------------------|-----------------------|
| `leftOuterJoin`  | Perform a join between two   | `rdd.leftOuterJoin(other)`  | `{(1,(2,None)),`      |
|                  | RDDs where the key must      |                             |   ` (3,(4,Some(9))),` | 
|                  | be present in the other RDD  |                             |   `(3,(6,Some(9)))}`  | 
|------------------|------------------------------|-----------------------------|-----------------------|
| `cogroup`        | Group data from both RDDs    | `rdd.cogroup(other)`        | `{(1,([2],[])),`      |
|                  | sharing the same key         |                             |  `(3,([4, 6],[9]))}`  |
|------------------|------------------------------|-----------------------------|-----------------------|

#### Aggregations
#### Grouping Data
#### Joins
#### Sorting Data
### Actions Available on Pair RDDs
### Data Partitioning (Advanced)
#### Determining an RDD's Partitioner
#### Operations That Benefit from Partitioning
#### Operations That Affect Partitioning
#### Example: PageRank
#### Custom Partitioners
### Conclusion

------------------------------------------

## Chapter 5. Loading and Saving Your Data
### Motivation
### File Formats
#### Text Files
#### JSON
#### Comma-Separated Values and Tab-Separated Values
#### SequenceFiles
#### Object Files
#### Hadoop Input and Output Formats
#### File Compression
### Filesystems
#### Local/“Regular” FS
#### Amazon S3
#### HDFS
### Structured Data with Spark SQL
#### Apache Hive
#### JSON
### Databases
#### Java Database Connectivity
#### Cassandra
#### HBase
#### Elasticsearch
### Conclusion

-------------------------------------

## Chapter 6. Advanced Spark Programming
### Introduction
### Accumulators
#### Accumulators and Fault Tolerance
#### Custom Accumulators
### Broadcast Variables
#### Optimizing Broadcasts
### Working on a Per-Partition Basis
### Piping to External Programs
### Numeric RDD Operations
### Conclusion

------------------------------------------

## Chapter 7. Running on a Cluster
### Introduction
### Spark Runtime Architecture
#### The Driver
#### Executors
#### Cluster Manager
#### Launching a Program
#### Summary
### Deploying Applications with spark-submit
### Packaging Your Code and Dependencies
#### A Java Spark Application Built with Maven
#### A Scala Spark Application Built with sbt
#### Dependency Conflicts
### Scheduling Within and Between Spark Applications
### Cluster Managers
#### Standalone Cluster Manager
#### Hadoop YARN
#### Apache Mesos
#### Amazon EC2
### Which Cluster Manager to Use?
### Conclusion

-------------------------------------------

## Chapter 8. Tuning and Debugging Spark
### Configuring Spark with SparkConf
### Components of Execution: Jobs, Tasks, and Stages
### Finding Information
#### Spark Web UI
#### Driver and Executor Logs
### Key Performance Considerations
#### Level of Parallelism
#### Serialization Format
#### Memory Management
#### Hardware Provisioning
### Conclusion

------------------------------------------

## Chapter 9. Spark SQL
### Linking with Spark SQL
### Using Spark SQL in Applications
#### Initializing Spark SQL
#### Basic Query Example
#### SchemaRDDs
#### Caching
### Loading and Saving Data
#### Apache Hive
#### Parquet
#### JSON
#### From RDDs
### JDBC/ODBC Server
#### Working with Beeline
#### Long-Lived Tables and Queries
### User-Defined Functions
#### Spark SQL UDFs
#### Hive UDFs
### Spark SQL Performance
#### Performance Tuning Options
### Conclusion

------------------------------------------

## Chapter 10. Spark Streaming
### A Simple Example
### Architecture and Abstraction
### Transformations
#### Stateless Transformations
#### Stateful Transformations
### Output Operations
### Input Sources
#### Core Sources
#### Additional Sources
#### Multiple Sources and Cluster Sizing
### 24/7 Operation
#### Checkpointing
#### Driver Fault Tolerance
#### Worker Fault Tolerance
#### Receiver Fault Tolerance
#### Processing Guarantees
### Streaming UI
### Performance Considerations
#### Batch and Window Sizes
#### Level of Parallelism
#### Garbage Collection and Memory Usage
### Conclusion

------------------------------------------

## Chapter 11. Machine Learning with MLlib
### Overview
### System Requirements
### Machine Learning Basics
#### Example: Spam Classification
### Data Types
#### Working with Vectors
### Algorithms
#### Feature Extraction
#### Statistics
#### Classification and Regression
#### Clustering
#### Collaborative Filtering and Recommendation
#### Dimensionality Reduction
#### Model Evaluation
### Tips and Performance Considerations
#### Preparing Features
#### Configuring Algorithms
#### Caching RDDs to Reuse
#### Recognizing Sparsity
#### Level of Parallelism
### Pipeline API
### Conclusion
