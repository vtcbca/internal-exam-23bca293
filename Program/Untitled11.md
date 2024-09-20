## 10.Create table cricketer(cid, cname, match, run) and insert 8 players records. Print player records with average. and write this data into player.csv file. Do all this task from python. 11


```python
import sqlite3 as sq
```


```python
con=sq.connect("D:/23bca293/sqlite3/csv/cricketer1.db")
```


```python
c=con.cursor()
```


```python
c.execute("create table if not exists cricketer1(cid,cname,match,run)")
```




    <sqlite3.Cursor at 0x1dc7666aa40>



## create the cricketer table


```python
c.execute("insert into cricketer1 values(1,'rohit sharma',150,12000),(2,'virat kohli',160,18000),(3,'kl rahul',80,8000),(4,'yashsvi jaiswal',35,2000),(5,'sachin',215,20390),(6,'iyer',37,5000),(7,'ishan',28,2500),(8,'jadeja',86,7000)")
```




    <sqlite3.Cursor at 0x1dc7666aa40>




```python
c.execute("select * ,run/match as average from cricketer1")
rows=c.fetchall()
for row in rows:
    print(row)
```

    (1, 'rohit sharma', 150, 12000, 80)
    (2, 'virat kohli', 160, 18000, 112)
    (3, 'kl rahul', 80, 8000, 100)
    (4, 'yashsvi jaiswal', 35, 2000, 57)
    (5, 'sachin', 215, 20390, 94)
    (6, 'iyer', 37, 5000, 135)
    (7, 'ishan', 28, 2500, 89)
    (8, 'jadeja', 86, 7000, 81)
    


```python
with open("D:/23bca293/sqlite3/csv/player.csv","w") as csv_file:
    writer=csv.writer(csv_file)
    writer.writerow(['cid','cname','match','run','average'])
    for row in rows:
        w.writerow(row)

```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Input In [36], in <cell line: 1>()
          1 with open("D:/23bca293/sqlite3/csv/player.csv","w") as csv_file:
    ----> 2     writer=csv.writer(csv_file)
          3     writer.writerow(['cid','cname','match','run','average'])
          4     for row in rows:
    

    NameError: name 'csv' is not defined



```python

```
