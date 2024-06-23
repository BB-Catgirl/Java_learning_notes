---
title: Mastering Java for Data Science
updated: 2022-12-16 02:57:27Z
created: 2022-12-14 01:13:00Z
latitude: 9.92806940
longitude: -84.09072460
altitude: 0.0000
---

# [Mastering Java for Data Science](https://read.amazon.com/?asin=B01JLBMHMM&ref_=kwl_kr_iv_aqd_des_8&language=en-US)

# Data Science Using Java

* Response to CRISP-DM.
* Introduction
* Data science libraries
	* Chapter 2, Data Processing Toolbox: Google Guava, Apache Common Collections, Apache Commons IO, AOL Cyclps-React, Java Database Connectivity
	* Data frame libraries: Joinery, Tablesaw, Saddle (Scala?), Apache Spark DataFrames.
	* Chapter 9, Scaling Data Science: Apache Hadoop, Apache Spark, Apache Flink
* Math and stats libraries: Apache Commons Math, Apache Mahout, JBLAS
* Machine learning and data mining libraries: Weka, JavaML, Smile, JSAT, H2O, Apache Mahout, Encog, DeepLearning4j.
* Text processing: Apache Lucene, Stanford CoreNLP, Apache OpenNLP, LingPipe, GATE, MALLET, Smile

# Data Processing Toolbox

## Collections

The **list** are made this way. There are other implemetations (**LinkedList**, **CopyOnWriteArrayList**)

```java
List<String> list = new ArrayList<>();
list.add("alpha");
list.add("beta");
list.add("beta");
list.add("gamma");
System.out.println(list);
```

A **set** in Java is like a mathematical set. Both of the previous collections are **Iterable** so a for-each loop is possible.
**Map**, **LinkedHashMap** and **ConcurrentHashMap** are like dictionaries, the differences between them is preserve order of the elements or can be used on multiple threads. **Collections** are collections with methods to sort, extracting maximum and minimum.

## Input / Output

### Reading input data

A text file need no be read line by line with the `Reader` class, especifically `BufferedReader`. Every action have a way to handle the exception, and need to defines character set, before the whiole loop reading lines. There is a shorter version but still is *really* long, The shortest version that uses **Java NIO API** is this one.

```java
Path path = Paths.get("data/text.txt"); // Wow! a Path class!
List<String> lines = Files.readAllLines(path, StandardCharsets.UTF_8);
System.out.println(lines);
```

### Writing output data



# [Maven in 5 minutes](https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html)

Requires Java, is a command line utility: can be invoked by `mvn --version` to check the version. 
It creates the folder structure of the project, almost all depends on the file pom.xml