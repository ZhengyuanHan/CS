## delete
detele 可用于删除表的部分或所有数据

## truncate
truncate 执行效果和 delete 类似，也是用来删除表中的所有行数据的，和 delete 最大的区别是，delete 可以使用条件表达式删除部分数据，而 truncate 不能加条件表达式，所以它只能删除所有的行数据。其本质上是新建了一个表结构，再把原先的表删除掉，所以它属于 DDL（Data Definition Language 数据定义语言，它是用来维护存储数据的结构指令）语言，而非 DML（Data Manipulation Language 数据操纵语言，用来对数据进行操作的）语言。

## drop
drop 和前两个命令只删除表的行数据不同，drop 会把整张表的行数据和表结构一起删除掉。

## 总结
1. delete 和 truncate 仅仅删除表数据，drop 连表数据和表结构一起删除，打个比方，delete 是单杀，truncate 是团灭，drop 是把电脑摔了。
2. delete 是 DML 语句，操作完以后如果没有不想提交事务还可以回滚，truncate 和 drop 是 DDL 语句，操作完马上生效，不能回滚。
3. 执行的速度上，drop > truncate > delete。

