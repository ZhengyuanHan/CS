SQL语言具有两种使用方式，分别称为交互式SQL和嵌入式SQL  
交互式SQL：只是SQL  
嵌入式SQL：与其他语言连用

athletes 表包含运动员姓名，年纪和代表国家。下面哪个查询可以找出代表每个国家最年轻的运动员情况？
A. SELECT name, country, age FROM athletes WHERE (country, age) IN (SELECT country, min(age) FROM athletes GROUP BY country)  
B. SELECT name, country, age FROM athletes WHERE (country, age) IN (SELECT min(age), country FROM athletes GROUP BY country)  
C. SELECT name, country, age FROM athletes WHERE (country, age) IN (SELECT country, min(age) FROM athletes) GROUP BY country  
D. SELECT name, country, age FROM athletes WHERE age IN (SELECT country, min(age) FROM athletes GROUP BY country)
```
A：正确
B：嵌套子序列要与查询的时候的顺序一致
C：语法错误
D：嵌套查询的子查询是有两个返回值,而In之前只有一个age所以数据只会返回age不会返回国家与题目不符。
```
