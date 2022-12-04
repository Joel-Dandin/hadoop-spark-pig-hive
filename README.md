# Apache Hadoop distribution on Ubuntu

The docker image Apache hadoop 3.3.4 distribution on Ubuntu 22.04


Find this on Docker Hub [https://hub.docker.com/r/fedric/hadoop-spark-pig-hive](https://hub.docker.com/r/fedric/hadoop-spark-pig-hive)

# Build the image

```
docker build -t fedric/hadoop-spark-pig-hive .
```
# Pull the image

```
docker pull fedric/hadoop-spark-pig-hive
```

# Start a container

In order to use the Docker image you have just build or pulled use:

```
docker run -it -p 50070:50070 -p 8088:8088 -p 8080:8080 fedric/hadoop-spark-pig-hive bash
```

## Testing

You can run one of the hadoop examples:

```
# run the mapreduce
yarn jar $HADOOP_HOME/share/hadoop/mapreduce/hadoop-mapreduce-examples-2.9.2.jar grep input output 'dfs[a-z.]+'

# check the output
hdfs dfs -cat output/*
```

## Run 

### Hive 

```
hive
```

or 

```
 beeline -u jdbc:hive2://
```

### Pig 

```
pig
```

### Spark 

Scala 

```
spark-shell
```

Python

```
pyspark
```



