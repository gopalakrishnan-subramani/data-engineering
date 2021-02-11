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
