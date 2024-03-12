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

&emsp;这种特性就叫做“引用传递”，也叫做传址，即***方法操作参数变量时是拷贝了变量的引用，注意下传递给方法的参数为变量的引用，其实也就是指针***，而后***通过这个引用找到变量（在这里是对象）的真正地址***，并对其进行操作。当 该方法结束后，方法内部的那个参数变量随之消失。但是要知道这个变量只是对象的一个引用而已，它只是指向了对象所在的真实地址，而非对象本身，所以它的消失并不会带来什么负面影响。  
&emsp;回头来看原型变量，***原型变量本质上也是那个对象的一个引用***（和参数变量是一样一样的），当初对参数变量所指对象的改变就根本就是对原型变量所指对象的改变。所以原型变量所代表的对象就这样被改变了，而且这种改变被保存了下来。

## String
代码示例：
```
private static void changeStr(String str) {
        str = "HUAQIN";
}

public static void main(String[] args) {
        String str = "1234";
        changeStr(str);
        System.out.println(str);
}
```
运行结果：1234  
  
String类的存储是通过final修饰的char[]数组来存放结果的，不可更改。所以每次当外部一个String类型的引用传递到方法内部时候，只是把外部String类型变量的引用传递给了方法参数变量，外部String变量和方法参数变量都是实际char[]数组的引用而已。所以当我们在方法内部改变这个参数的引用时候，因为char[]数组不可改变，所以每次新建变量都是新建一个新的String实例。很显然外部String类型变量没有指向新的String实例。所以也就不会获取到新的更改。  

### 总结
a）String是最终类，因为是final修饰的class,不可被继承，也无重写一说。  
b) 实际存储字符串的是一个数组，并且是final修饰的，分配空间之后内存地址不变。  
c) 所有成员变量都是private final修饰的，并且没有提供对应的XXXSetter方法，不允许外部修改这些字段，并且 只能对它们赋值一次。  
d) 涉及value数组的操作（上面只提供了部分源码）都使用了拷贝数组元素的方法,保证了不能在内部修改字符数组。  
***所以说String在初始化之后是不可变的。***
