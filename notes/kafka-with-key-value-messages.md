
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

example 

```
>IN:msg1
>USA:msg2
>CA:msg3
>UA:msg4
>DE:msg5
>FR:msg5
>USA:msg6
>AU:msg7
>SL:msg8
>CH:msg9
>TH:msg10
>SL:msg11
>TH:msg12
>
```

## Part 1

1 Consumer and 4 Partitions

C1: [P0, P1, P2, P3] 

```
kafka-console-consumer --bootstrap-server localhost:9092 --topic greetings --group greetings-consumer-group --property print.key=true
```


## Part 1

open new terminal, run the consumer again, this add 2 consumer instance to the group greetings-consumer-group

Kafka revoke all the partitiosn from C1 and 
rebalance partitions to C1 and C2

2 Consumer and 4 Partitions

C1:  []
C2:  []

```
kafka-console-consumer --bootstrap-server localhost:9092 --topic greetings --group greetings-consumer-group --property print.key=true
```




// Debug
to know the partition where the messages are stored
```
kafka-console-consumer --bootstrap-server localhost:9092 --topic greetings --partition 0  --from-beginning --property print.key=true
kafka-console-consumer --bootstrap-server localhost:9092 --topic greetings --partition 1  --from-beginning --property print.key=true
kafka-console-consumer --bootstrap-server localhost:9092 --topic greetings --partition 2  --from-beginning --property print.key=true
kafka-console-consumer --bootstrap-server localhost:9092 --topic greetings --partition 3  --from-beginning --property print.key=true

```

