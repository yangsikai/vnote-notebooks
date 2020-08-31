# ServletContext

web容器在启动的时候，它会为每个web程序都创建一个对应的ServletContext对象，它代表了当前的web应用；

1、ServletContext 是一个接口，它表示 Servlet 上下文对象
2、一个 web 工程，只有一个 ServletContext 对象实例。
3、ServletContext 对象是一个域对象。
4、ServletContext 是在 web 工程部署启动的时候创建。在 web 工程停止的时候销毁。

## 获取web.xml中配置的上下文参数

```xml
<!--context-param 是上下文参数(它属于整个 web 工程)-->
<context-param>
    <param-name>username</param-name>
    <param-value>context</param-value>
</context-param>

<!--context-param 是上下文参数(它属于整个 web 工程)-->
<context-param>
    <param-name>password</param-name>
    <param-value>root</param-value>
</context-param>
```

```java
String username = context.getInitParameter("username");
System.out.println( "当前工程路径:" + context.getContextPath() );
System.out.println("工程部署的路径是:" + context.getRealPath("/"));
System.out.println("工程下 css 目录的绝对路径是:" + context.getRealPath("/css"));
System.out.println("工程下 imgs 目录 1.jpg 的绝对路径是:" + context.getRealPath("/imgs/1.jpg"));
```

## 获取当前的web工程信息

## 存取数据、共享数据

是一个域对象，可以向一个Map一样存取数据的对象，叫做域对象
这里的域指的是存取数据的操作范围，整个web工程

- 存数据：setAttribute()
- 取数据：getAttribute()
- 删除数据：removeAttribute()

