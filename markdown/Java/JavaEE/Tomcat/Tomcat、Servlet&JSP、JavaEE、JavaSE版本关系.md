# Tomcat、Servlet&JSP、JavaEE、JavaSE版本关系

首先JavaSE、JavaEE都是SUN公司自己定义的官方标准，Servlet/JSP是有自己的版本的，每次版本的升级都会带啦重大的更新，而Tomcat则是第三方的实现，由于它自身就是使用[Java](http://lib.csdn.net/base/javase "Java SE知识库")开发的，所以它的版本也和前面三个标准有密切的关系，而且具有一定的对应关系，详见下图。

 servlet /JSP             tomcat版本                     实际修订版本                 最低支持Java JDK版本

![](_v_images/20200830230625156_30744)

    下面这篇是对这些版本的之间的关系娿一些扩充。

JSR 53: Java<sup>TM</sup> Servlet 2.3 and JavaServer Pages<sup>TM</sup> 1.2

JSR 154: Java<sup>TM</sup> Servlet 2.4

JSR 154: Java<sup>TM</sup> Servlet 2.5(Maintenance Release 2)

JSR 315: Java<sup>TM</sup> Servlet 3.0（This JSR will be an update to the existing Servlet 2.5 specification. ）

JSR 152: JavaServer Pages<sup>TM</sup> 2.0

JSR 245: JavaServer<sup>TM</sup> Pages 2.1

JSR 127: JavaServer<sup>TM</sup> Faces

JSR 252: JavaServer<sup>TM</sup> Faces 1.2

JSR 314: JavaServer<sup>TM</sup> Faces 2.0

[admin10000.com](http://www.admin10000.com/) 整理

Servlet和JSP规范版本对应关系：

|       <br>       |      <br>       |      <br>       |     <br>     |
| ---------------- | --------------- | --------------- | ------------ |
|  Servlet规范版本 |  JSP版本        |  JSF版本        |  JAVA EE版本 |
|  Servlet2.3      |  JSP1.2、JSP1.1 |                 |  J2EE1.3     |
|  Servlet2.4      |  JSP2.0         |  JSF1.1         |  J2EE1.4     |
|  Servlet2.5      |  JSP2.1         |  JSF1.2、JSF2.0 |  Java EE5    |
|  Servlet3.0      |  JSP2.2         |                 |  Java EE6    |

Tomcat所对应的Servlet/JSP规范和JDK版本：

| Servlet/JSP Spec | Apache Tomcat version | Actual release revision | Minimum Java Version |
| ---------------- | --------------------- | ----------------------- | -------------------- |
| 3.0/2.2          | 7.0.x                 | 7.0.12                  | 1.6                  |
| 2.5/2.1          | 6.0.x                 | 6.0.32                  | 1.5                  |
| 2.4/2.0          | 5.5.x                 | 5.5.33                  | 1.4                  |
| 2.3/1.2          | 4.1.x (archived)      | 4.1.40 (archived)       | 1.3                  |
| 2.2/1.1          | 3.3.x (archived)      | 3.3.2 (archived)        | 1.1                  |

Apache官方对各版本的解释

| Servlet Spec |  JSP Spec  |  EL Spec   | WebSocket Spec | Apache Tomcat version | Actual release revision |              Support Java Versions               |
| ------------ | ---------- | ---------- | -------------- | --------------------- | ----------------------- | ------------------------------------------------ |
| 4.0          | TBD (2.4?) | TBD (3.1?) | TBD (1.2?)     | 9.0.x                 | None                    | 8 and later                                      |
| 3.1          | 2.3        | 3.0        | 1.1            | 8.0.x                 | 8.0.15                  | 7 and later                                      |
| 3.0          | 2.2        | 2.2        | 1.1            | 7.0.x                 | 7.0.57                  | 6 and later  (WebSocket 1.1 requires 7 or later) |
| 2.5          | 2.1        | 2.1        | N/A            | 6.0.x                 | 6.0.43                  | 5 and later                                      |
| 2.4          | 2.0        | N/A        | N/A            | 5.5.x (archived)      | 5.5.36 (archived)       | 1.4 and later                                    |
| 2.3          | 1.2        | N/A        | N/A            | 4.1.x (archived)      | 4.1.40 (archived)       | 1.3 and later                                    |
| 2.2          | 1.1        | N/A        | N/A            | 3.3.x (archived)      | 3.3.2 (archived)        | 1.1 and later                                    |


jdk：java development kit，是程序员编写java程序需要的软件。
jre：java runtime environment，顾名思义是程序员运行java程序的软件。
java se：java standard edition，是桌面或者比较简单的服务器java平台。
java ee：java enterprise edition，是复杂的服务器java平台。
java me：java micro edition，是微型手机和其他小型设备的java平台。
java ee sdk：是一款免费的用于编译、测试、发布java ee的整合软件。

JDK和J2EE 版本对应关系：

JDK1.4 对应 [J2EE](https://www.baidu.com/s?wd=J2EE&tn=44039180_cpr&fenlei=mv6quAkxTZn0IZRqIHckPjm4nH00T1Yznvm3nynLn1w9uHuWmhu-0ZwV5Hcvrjm3rH6sPfKWUMw85HfYnjn4nH6sgvPsT6KdThsqpZwYTjCEQLGCpyw9Uz4Bmy-bIi4WUvYETgN-TLwGUv3EnWckrjD4PjR1) 1.4
JDK5.0 ----> [J2EE](https://www.baidu.com/s?wd=J2EE&tn=44039180_cpr&fenlei=mv6quAkxTZn0IZRqIHckPjm4nH00T1Yznvm3nynLn1w9uHuWmhu-0ZwV5Hcvrjm3rH6sPfKWUMw85HfYnjn4nH6sgvPsT6KdThsqpZwYTjCEQLGCpyw9Uz4Bmy-bIi4WUvYETgN-TLwGUv3EnWckrjD4PjR1)5.0
JDK6.0 ----> [J2EE](https://www.baidu.com/s?wd=J2EE&tn=44039180_cpr&fenlei=mv6quAkxTZn0IZRqIHckPjm4nH00T1Yznvm3nynLn1w9uHuWmhu-0ZwV5Hcvrjm3rH6sPfKWUMw85HfYnjn4nH6sgvPsT6KdThsqpZwYTjCEQLGCpyw9Uz4Bmy-bIi4WUvYETgN-TLwGUv3EnWckrjD4PjR1)6.0
