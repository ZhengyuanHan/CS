## 为什么要用 Lambda表达式？
1. 避免匿名内部类定义过多。
2. 让代码看起来很简洁。
3. 去掉无意义代码只留下核心逻辑。

## 关键：理解函数式接口
### 定义
任何接口，如果只包含唯一一个抽象方法，那么它就是一个函数式接口
```
public interface Runnable {
    public abstract void run();
}
```
## 代码示例
```
public class LambdaTest {
    public static void main(String[] args) {
        // 原始方法，用接口 new 出一个实现类
        LambdaExpression lambdaExpression = new Test();
        lambdaExpression.test();

        // 匿名内部类，没有类的名称，必须借助接口或父类
        lambdaExpression = new LambdaExpression(){
            @Override
            public void test() {
                System.out.println("匿名内部类测试通过");
            }
        };
        lambdaExpression.test();

        // 简化成 Lambda表达式
        lambdaExpression = ()->{System.out.println("Lambda表达式 测试成功");};
        lambdaExpression.test();
        LambdaExpression2 lambdaExpression2 = n -> System.out.println("带参 Lambda表达式 测试成功，参数：" + n);
        // 原型：LambdaExpression2 lambdaExpression2 = (int n)->{System.out.println("带参 Lambda表达式 测试成功，参数：" + n);};
        // 原型：LambdaExpression2 lambdaExpression2 = (n)->{System.out.println("带参 Lambda表达式 测试成功，参数：" + n);};
        // 原型：LambdaExpression2 lambdaExpression2 = n->{System.out.println("带参 Lambda表达式 测试成功，参数：" + n);};
        lambdaExpression2.test(25);
    }
}

interface LambdaExpression {
    void test();
}

interface LambdaExpression2 {
    void test(int n);
}

class Test implements LambdaExpression {
    @Override
    public void test() {
        System.out.println("测试通过");
    }
}
```
运行结果：  
```
测试通过
匿名内部类测试通过
Lambda表达式 测试成功
带参 Lambda表达式 测试成功，参数：25
```
注意：
1. lambda表达式 只在仅有一行代码的情况下，才可以省略大括号
2. 多个参数也可以去掉参数类型，要去掉，就都去掉，且这种情况下无法省略小括号
