
Time: 10 mins

1. Create a topic called orders with partitions 4 paritions, 1 replica
2. console-producer with key and value delimited by :, format orderId:json  example,  1234:10 where is 1234 is order id, 10 is the value
3. console-consumer, with group id called order-terminal-consumer-group
4. Run 4 instances of console-consumer mentioned on step 3

-----


Time: 15 Mins

Scala Code

1. Write a Scala producer for order topic
2. Write a scala consumer for order topic
