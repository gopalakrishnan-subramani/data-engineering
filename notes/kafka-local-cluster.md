 - ZooKeeper - 1 instance [not in cluster]
 - Kafka Broker -  PORT 9092, directory where the data is stored, directory to the files

 4 instances of kafka
  They run different machines on port 9092. Since we have 1 VM, we will 4 Brokers in 1 VM in cluster
  
  WE will use different ports for cluster purpose, different directory for cluster purpose.
  
  Each broker, needs unique id, numeric type, integer, 0, 1, 2...............64 bit number
  Port number: 9092, 9093, 9094, 9095
  Directories, use /tmp directory to store the content of the kafka data
  
  We will not use confluent local command.....
  
  
  
  
 ```
 confluent local stop
 ```
 
 ```
 cd $KAFKA_HOME
 
 ```
 
 
 ## Setting up Zoo Keeper in Cluster
  ZooKeeper runs on port 2181
  
  Open new terminal, paste below command to start zooKeeper
  
```  
  $KAFKA_HOME/bin/zookeeper-server-start $KAFKA_HOME/etc/kafka/zookeeper.properties
```
 
 ## Setting up Brokers in Cluster
 
 server.properties - broker setting file

few propertis to be overridden

```
broker.id=0
listeners=PLAINTEXT://:9092
log.dirs=/tmp/kafka-logs
```  
  
  
Starting Broker 0 on Port 9092, which store content on /tmp/kafka-logs-0
 
Open new terminal 

Broker 0 setting

```
$KAFKA_HOME/bin/kafka-server-start $KAFKA_HOME/etc/kafka/server.properties --override broker.id=0  --override listeners=PLAINTEXT://:9092 --override log.dirs=/tmp/kafka-logs-0 --override confluent.metadata.server.listeners=http://0.0.0.0:8090 --override confluent.metadata.server.advertised.listeners=http://127.0.0.1:8090
```

Open new terminal 

Broker 1 setting

```
$KAFKA_HOME/bin/kafka-server-start $KAFKA_HOME/etc/kafka/server.properties --override broker.id=1  --override listeners=PLAINTEXT://:9093 --override log.dirs=/tmp/kafka-logs-1 --override confluent.metadata.server.listeners=http://0.0.0.0:8091 --override confluent.metadata.server.advertised.listeners=http://127.0.0.1:8091
```

 
Open new terminal 

Broker 2 setting

```
$KAFKA_HOME/bin/kafka-server-start $KAFKA_HOME/etc/kafka/server.properties --override broker.id=2  --override listeners=PLAINTEXT://:9094 --override log.dirs=/tmp/kafka-logs-2 --override confluent.metadata.server.listeners=http://0.0.0.0:8092 --override confluent.metadata.server.advertised.listeners=http://127.0.0.1:8092
```


Open new terminal 

Broker 3 setting

```
$KAFKA_HOME/bin/kafka-server-start $KAFKA_HOME/etc/kafka/server.properties --override broker.id=3  --override listeners=PLAINTEXT://:9095 --override log.dirs=/tmp/kafka-logs-3 --override confluent.metadata.server.listeners=http://0.0.0.0:8093 --override confluent.metadata.server.advertised.listeners=http://127.0.0.1:8093
```



open new terminal

zookeeper-shell, cli for zookeeper for debugging purpose..

```
zookeeper-shell localhost:2181
```

once it is connected, you can below commands

```

ls /

ls /brokers

ls /brokers/ids

ls /brokers/topics



```
