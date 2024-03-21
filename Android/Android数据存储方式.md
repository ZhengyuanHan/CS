### SharedPreferences
**特点**：保存的数据格式较为简单：字符串型、基本类型的值。  
保存原理：基于XML文件存储的key-value键值对数据。  
使用场景：用于存储一些简单的配置信息。比如，我的用户是否第一次登陆，保存用户积分等。  
优势与局限：SharedPreferences对象与SQLite数据库相比，免去了创建数据库，创建表，写SQL语句等诸多操作，相对而言更加方便，简洁。但是SharedPreferences也有其自身缺陷，比如其职能存储boolean，int，float，long和String五种简单的数据类型，比如其无法进行条件查询等。所以不论SharedPreferences的数据存储操作是如何简单，它也只能是存储方式的一种补充，而无法完全替代如SQLite数据库这样的其他数据存储方式。

### 文件存储数据
