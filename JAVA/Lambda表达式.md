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
