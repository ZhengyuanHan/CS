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
