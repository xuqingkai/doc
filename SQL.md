### 联表更新
```
UPDATE table1 AS a
LEFT JOIN table2 AS b ON a.bid=b.id
SET a.author_name=b.nick_name
WHERE a.id<100;
```
