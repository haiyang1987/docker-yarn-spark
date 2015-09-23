# Quick Start
#### Pull the image from Docker Repository
```sh
docker pull kairen/yarn-spark:1.5
```

#### Running the image
```sh
docker run -d -p 8088:8088 -p 50070:50070 -h sandbox  \
-v  <your_dir>:/root/  \
--name yarn-spark kairen/yarn-spark:1.5 -d
```

#### Enter container 
```sh
docker exec -ti <conatiner id> bash
```

### Running examples 
#### Creating a test data 
```sh
$ touch test.txt
$ vi test.txt

# add the following
Absence of evidence
is not evidence 
of absence

Absence of evidence
is not evidence 
of absence

Absence of evidence
is not evidence 
of absence
```

##### Upload test data to HDFS
```sh
hadoop fs -mkdir /test
hadoop fs -put test.txt /test
```

##### Running spark job
```sh
cd /root/python
spark-submit --master yarn-cluster wordcount.py hdfs://sandbox:9000/test/test.txt
```

