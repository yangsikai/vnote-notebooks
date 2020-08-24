# Java程序的主类

一个程序中可以有多个类，但只能有一个类是主类。
在 Java 应用程序中，这个主类是指包含 main（）方法的类。
而在 Java 小程序中，这个主类是一个继承自系统类 JApplet 或 Applet 的子类。
应用程序的主类不一定要求是 public 类，但小程序的主类要求必须是 public 类。主类是 Java 程序执行的入口点。

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```

