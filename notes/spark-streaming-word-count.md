Open terminal to run word count server

```
nc -lk 9999
```

to test it working right, run telnet on second terminal

```
telnet localhost 9999
```

now type lines and enter key 

check in second terminal, it should appear.


follow python/scala sample given in official link

https://spark.apache.org/docs/2.4.0/structured-streaming-programming-guide.html



```
pyspark
```


```python
lines = spark \
    .readStream \
    .format("socket") \
    .option("host", "localhost") \
    .option("port", 9999) \
    .load()
```

```python
echoLinesQuery = lines \
    .writeStream \
    .outputMode("append") \
    .format("console") \
    .start()
```

```
echoLinesQuery.awaitTermination()
```

