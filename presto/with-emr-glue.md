Ensure that you create cluster with Glue catalog

ssh into emr master

```

 presto-cli --catalog hive


```

```
show schemas;

select * from orderdb.invoices;

-- optional 
use  orderdb;

show tables;

select * from invoices;
```
