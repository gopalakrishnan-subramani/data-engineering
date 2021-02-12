
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

```
kafka-console-consumer --bootstrap-server localhost:9092 --topic greetings --group greetings-consumer-group --property print.key=true
```
