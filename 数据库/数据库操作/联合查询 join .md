![表A](https://github.com/ZhengyuanHan/CS/blob/main/img/%E8%A1%A8A.png)  
![表B](https://github.com/ZhengyuanHan/CS/blob/main/img/%E8%A1%A8B.png)

## 【INNER JOIN】内连接（一般直接写JOIN）
![内连接](https://github.com/ZhengyuanHan/CS/blob/main/img/%E5%86%85%E8%BF%9E%E6%8E%A5.png)
```
SELECT A.学号, A.姓名, A.籍贯, A.年龄, B.专业, B.班级
FROM student A
JOIN major B  
ON  A.学号=B.学号
```
![内连接结果](https://github.com/ZhengyuanHan/CS/blob/main/img/%E5%86%85%E8%BF%9E%E6%8E%A5%E7%BB%93%E6%9E%9C.png)

## 【LEFT JOIN】左连接
获取左表中的所有记录，即使在右表没有对应匹配的记录。  
![左连接](https://github.com/ZhengyuanHan/CS/blob/main/img/%E5%B7%A6%E8%BF%9E%E6%8E%A5.png)
```
SELECT A.学号, A.姓名, A.籍贯, A.年龄, B.专业, B.班级
FROM student A LEFT JOIN major B  
ON  A.学号=B.学号
```
