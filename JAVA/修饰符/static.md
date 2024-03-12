在Java中，static表示“静态的”，它也是一种修饰符，可以修饰属性、方法、代码块和内部类。  
  
static修饰符具有如下特性：  
&emsp;其中，静态变量、静态方法、静态常量统称为类的静态成员，归整个类所有，不属于某个单一的对象。也就是说，静态成员不属于某个对象单独拥有，而是被类的所有实例对象共享。举个例子，我们在教室里放了一台饮水机，这台饮水机是本教室所有成员共享的，不属于张三，也不属于李四，这台饮水机就是”静态成员“。而每个人还可以有自己单独的一个水杯，张三、李四都有自己独有的水杯，水杯不是共享的。另外，默认情况下，这些水杯是不能混用的，张三和李四彼此的水杯是互相隔离的。也就是说，自己的隐私不可被侵犯和窥探。  
&emsp;所以，静态成员不需要通过对象来进行访问，而是直接通过类来访问。只要这个类被加载，Java虚拟机就可以根据类名找到它们。我们调用静态成员的语法格式如下：  
***类名.静态成员***

### 注意事项
根据以上特性，我们需要注意以下几点：
1.static关键词修饰的成员变量和方法都属于类，不属于某个对象；
2.普通变量和方法属于某个对象，每个对象都有自己的变量和方法，彼此之间是隔离的；
3.静态方法不能调用非静态的变量和非静态的方法，否则编译时就会报错。也意味着静态方法中不能用this, super关键字
4.static成员在JVM加载类时被初始化，并仅在第一次使用该类时执行一次。

```
public class StaticTest {
    class Test1 {
        int t1;

        public Test1(int t1) {
            this.t1 = t1;
        }
    }

    static class Test2 {
        int t2;

        public Test2(int t2) {
            this.t2 = t2;
        }
    }

    public static void main(String[] args) {
        <font color=red>// Test1 test1 = new Test1(1); 编译错误：'StaticTest.this' cannot be referenced from a static context</font>
        StaticTest staticTest = new StaticTest();
        Test1 test1 = staticTest.new Test1(1);
        
        Test2 test2 = new Test2(2);
    }
}
```
