## 值传递
在Java中，当基本类型作为参数传入方法时，无论该参数在方法内怎样被改变，外部的变量原型总是不变的，因为方法内部有外部变量的一份拷贝，对这个拷贝的更改不会改变外部变量的值。代码示例：
```
private static void changeNum(int num) {
        num++;
}

public static void main(String[] args) {
        int num = 0;
        changeNum(num);
        System.out.println(num);
}
```
运行结果：0  
  
这就叫做“值传递”，即方法操作的是参数变量（也就是原型变量的一个值的拷贝）改变的也只是原型变量的一个拷贝而已，而非变量本身。所以变量原型并不会随之改变。
