SQL语言具有两种使用方式，分别称为交互式SQL和嵌入式SQL  
交互式SQL：只是SQL  
嵌入式SQL：与其他语言连用

athletes 表包含运动员姓名，年纪和代表国家。下面哪个查询可以找出代表每个国家最年轻的运动员情况？
A. SELECT name, country, age FROM athletes WHERE (country, age) IN (SELECT country, min(age) FROM athletes GROUP BY country)
B. 
