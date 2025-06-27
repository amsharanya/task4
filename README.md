 select min(price) as SmallestPrice from products;
+---------------+
| SmallestPrice |
+---------------+
|          5.00 |
+---------------+
1 row in set (0.006 sec)

mysql> select max(price) as HighestPrice from products;
+--------------+
| HighestPrice |
+--------------+
|        45.00 |
+--------------+
1 row in set (0.007 sec)

mysql> select sum(price) as TotalPrice from products;
+------------+
| TotalPrice |
+------------+
|     152.00 |
+------------+
1 row in set (0.007 sec)

mysql> select avg(price) as AveragePrice from products;
+--------------+
| AveragePrice |
+--------------+
|    30.400000 |
+--------------+
1 row in set (0.013 sec)

mysql> select count(*) from products;
+----------+
| count(*) |
+----------+
|        5 |
+----------+
1 row in set (0.006 sec)
 select count(price) from products;
+--------------+
| count(price) |
+--------------+
|            5 |
+--------------+
1 row in set (0.046 sec)

mysql> select count(distinct price) from products;
+-----------------------+
| count(distinct price) |
+-----------------------+
|                     5 |
+-----------------------+
1 row in set (0.013 sec)

mysql> select count(product_id) from products where price>20;
+-------------------+
| count(product_id) |
+-------------------+
|                 3 |
+-------------------+
1 row in set (0.007 sec)

mysql> select count(*) as NumberofRecords, name from products group by name;
+-----------------+---------------+
| NumberofRecords | name          |
+-----------------+---------------+
|               1 | basumati rice |
|               1 | sugar         |
|               1 | egg           |
|               1 | wheat atta    |
|               1 | colgate       |
+-----------------+---------------+
5 rows in set (0.009 sec)

mysql> select count(product_id), name from products group by name having max(price)>20;
+-------------------+---------------+
| count(product_id) | name          |
+-------------------+---------------+
|                 1 | basumati rice |
|                 1 | sugar         |
|                 1 | wheat atta    |
+-------------------+---------------+
3 rows in set (0.011 sec)
 select count(customer_id), name from customers group by name having count(customer_id)<2;
+--------------------+---------+
| count(customer_id) | name    |
+--------------------+---------+
|                  1 | smitha  |
|                  1 | shreeja |
+--------------------+---------+
2 rows in set (0.019 sec)
