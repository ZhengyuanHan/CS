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
![左连接结果](https://github.com/ZhengyuanHan/CS/blob/main/img/%E5%B7%A6%E8%BF%9E%E6%8E%A5%E7%BB%93%E6%9E%9C.png)

## 【RIGHT JOIN】右连接
用于获取右表中的所有记录，即使左表没有对应匹配的记录。  
![右连接](https://github.com/ZhengyuanHan/CS/blob/main/img/%E5%8F%B3%E8%BF%9E%E6%8E%A5.png)
```
SELECT A.学号, A.姓名, A.籍贯, A.年龄, B.专业, B.班级
FROM student A RIGHT JOIN major B  
ON  A.学号=B.学号
```
![右连接结果](https://github.com/ZhengyuanHan/CS/blob/main/img/%E5%8F%B3%E8%BF%9E%E6%8E%A5%E7%BB%93%E6%9E%9C.png)

## 【FULL JOIN】 完全连接
返回两个表中的所有行。  
![完全连接](https://github.com/ZhengyuanHan/CS/blob/main/img/%E5%85%A8%E8%BF%9E%E6%8E%A5.png)
```
SELECT A.学号, A.姓名, A.籍贯, A.年龄, B.专业, B.班级
FROM student A FULL JOIN major B  
ON  A.学号=B.学号
```
![完全连接结果](https://github.com/ZhengyuanHan/CS/blob/main/img/%E5%85%A8%E8%BF%9E%E6%8E%A5%E7%BB%93%E6%9E%9C.png)
