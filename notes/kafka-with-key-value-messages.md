
```
kafka-topics --create --zookeeper localhost:2181 --replication-factor 1 --partitions 4 --topic greetings

```

```
kafka-topics --describe --zookeeper localhost:2181 --topic greetings
```


```	
kafka-console-producer --broker-list localhost:9092 --topic greetings --property "parse.key=true" --property "key.separator=:"
```

>key:value
>NY:Happy New Year (Key is NY, seperator :), value part

## Part 1

1 Consumer and 4 Partitions

C1: [P0, P1, P2, P3] 

```
kafka-console-consumer --bootstrap-server localhost:9092 --topic greetings --group greetings-consumer-group --property print.key=true
```


// Debug
to know the partition where the messages are stored
```
kafka-console-consumer --bootstrap-server localhost:9092 --topic greetings --partition 0  --from-beginning
kafka-console-consumer --bootstrap-server localhost:9092 --topic greetings --partition 1  --from-beginning
kafka-console-consumer --bootstrap-server localhost:9092 --topic greetings --partition 2  --from-beginning
kafka-console-consumer --bootstrap-server localhost:9092 --topic greetings --partition 3  --from-beginning

```

