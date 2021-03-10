```
sudo pip3 install 'pyhive[presto]'
sudo pip3 install thrift

```

```
python
```

```
from pyhive import presto
cursor = presto.connect(host='localhost', port=8889).cursor()

cursor.execute('SELECT 1 + 1')
print cursor.fetchone()
print cursor.fetchall()

```
