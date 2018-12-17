1.什么是spring 

  是一个开源的java企业级开源框架，用于java企业级开发，简化开发模式，

2.sping的好处

  轻量：大约2MB
  
  IOC :控制反转，解耦和
  
  AOP:实现业务逻辑和系统服务的分离
  
  容器：管理bean的初始化，销毁生命周期及配置
  
  事物：提供事务管理接口，可扩展上至本地事物到全局事物
  
  MVC:提供web服务框架
  
  异常:统一的异常处理，jdbc hibernate 异常转成统一的接口
  
3.spring有哪些模块

   core container
       beans :提供了BenaFactory实现，一个工厂模式的复杂实现
       cores ：提供了基础矿机组件，IOC 依赖注入
       context：上下文，建立在beans和core模块之上，是访问所有配置和定义的对象
       spel ：表达式
  数据访问/集成
     jdbc:
     tansactions
     orm
     oxm
     jms
   web
     web:提供基本的文组件，如上传文件等
     web-mvc:web的模型-试图-控制层
     web-socket :提供了客户端和服务端的两种通信方式
     web-portlet:提供在portlet实现mvc
 其他
    aop
    aspects：集成的aspectJ, 提供成熟的aopk框架
    Instrumentation
    Messaging STOMP 提供了支持作为在应用程序中 WebSocket 子协议的使用。它也支持一个注解编程模型，它是为了选路和处理来自 WebSocket 客户端的         STOMP 信息。
test
   提供测试 ，spring 测试组件 JUnit
   
4.什么是Spring IOC
   实现控制反转，实现对象，配置对象，管理对象，并管理对象的声明周期
   
5.spring Ioc 优点
  1.降低了耦合性。灵活的控制住对象
  
6.spring IOC 缺点

   1.修改类名，要如修改xml文件
   2.不熟悉的人不容易适应
7.spring IOC 的实现方式
  1.set注入
  2.构造器注入
8.ApplicationContext通常的实现是什么?

9. Bean 工厂和 Application contexts 有什么区别？


10解释Spring框架中bean的生命周期。
  1.

11.


    


   
    
 
  
 
