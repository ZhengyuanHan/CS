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

## 引用传递
但当方法传入的参数为非基本类型时（也就是说是一个对象类型的变量）， 方法里面改变参数变量的同时原型变量也会随之改变，代码示例：
```
private static void changeStringBuilder(StringBuilder sb) {
        sb.append(" is changed!");
}

public static void main(String[] args) {
        StringBuilder sb = new StringBuilder("Original");
        changeStringBuilder(sb);
        System.out.println(sb);
}
```
运行结果：Original is changed!  

这种特性就叫做“引用传递”，也叫做传址，即***方法操作参数变量时是拷贝了变量的引用，注意下传递给方法的参数为变量的引用，其实也就是指针***，而后***通过这个引用找到变量（在这里是对象）的真正地址***，并对其进行操作。当 该方法结束后，方法内部的那个参数变量随之消失。但是要知道这个变量只是对象的一个引用而已，它只是指向了对象所在的真实地址，而非对象本身，所以它的消 失并不会带来什么负面影响。  
回头来看原型变量，***原型变量本质上也是那个对象的一个引用***（和参数变量是一样一样的），当初对参数变量所指对象的改变就根本就 是对原型变量所指对象的改变。所以原型变量所代表的对象就这样被改变了，而且这种改变被保存了下来。
