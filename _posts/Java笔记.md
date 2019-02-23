# Java 学习笔记
## Java类的初始化顺序

1. 基类的静态代码块，基类的静态成员变量（优先级相同，根据在代码中的出现顺序执行，且只有在类的一次加载时执行）。
2. 派生类静态代码块，派生类静态成员变量（优先级相同，根据在代码中的出现顺序执行，且只有在类的一次加载时执行）。
3. 基类普通代码块，基类普通成员字段（优先级相同，根据在代码中的出现顺序执行）。
4. 基类的构造函数。
5. 派生类普通代码块，派生类普通成员字段（优先级相同，根据在代码中的出现顺序执行）。
6. 派生类构造函数。


```
public class Client {

    public static void main(String[] args) {
        CarFactory  factory = new LuxuryCarFactory();
        Engine e = factory.createEngine();
        e.run();
        e.start();
    }
}
```