```
confluent local start

confluent local status
```

```
kafka-topics --list --zookeeper localhost:2181

kafka-topics --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test

kafka-topics --list --zookeeper localhost:2181

kafka-topics --describe --zookeeper localhost:2181 --topic test

```


Open a new terminal

```
kafka-console-producer --broker-list localhost:9092 --topic test
```


open new terminal 

listen for the messages published/latest

```
kafka-console-consumer --bootstrap-server localhost:9092 --topic test
```

Ctrl + C to stop it

Produce messages when consumer down...

start consumer  with --from-beginging

```
kafka-console-consumer --bootstrap-server localhost:9092 --topic test --from-beginning
```

### Excercise [5 mins]

create a topic called messsages with partition 1 and replication factor 1

run the producer in terminal and produce messsage to messsages topic

run the consumer and susbcribe from messages topics

and check when consumer offline, you could produce message

and try reading using from-begining


```

kafka-topics --create --zookeeper localhost:2181 --replication-factor 1 --partitions 4 --topic greetings

kafka-topics --create --zookeeper localhost:2181 --replication-factor 1 --partitions  3 --topic logs
```





