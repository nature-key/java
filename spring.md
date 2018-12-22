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
https://www.jianshu.com/p/3944792a5fff
  1.

11.

1.什么是spring?
是一个企业级开源框架，简化企业级开发


2.使用Spring框架的好处是什么？

   1.轻量
   
   2.IOC
   
   3.AOP
   
   3.统一的数据库异常处理
   
   5.事物的处理


3.Spring由哪些模块组成?

   1.test模块
   
   2.core contain
   
       beans spel context core模块
       
   3.数据访问
   
   4.web模块
   
   5，aop instrumentation messaging Aspects 


4.核心容器（应用上下文)模块。

   beans::beans实例
   
   spel：表达式
   
   beans::beans实例
   
   context：上下文
  

5.BeanFactory–BeanFactory实现举例。



6.XMLBeanFactory



7.解释AOP模块
   面向切面编程，一种编程思想


8.解释JDBC抽象和DAO模块。



9.解释对象/关系映射集成模块。

   orm 

10.解释WEB模块。



11.为什么说Spring是一个容器？



12.Spring配置文件



13.什么是SpringIOC容器？
   
    控制反转， 传统的在程序中创建一个对象是在程序中，而现在可以把对象的依赖关系交给容器，自动注入依赖


14.IOC的优点是什么？

    松耦合，不在


15.ApplicationContext通常的实现是什么?
   FilesystemXMLApplicationcontext
   ClassPathXMLApplicationcontext
   XMLWEBapplicationContext


16.Bean工厂和Applicationcontexts有什么区别？
   beanFactory 是spring的一个核心接口，实现可一个工厂模式，实现基本的spring功能，applicationcontexts是beanFactory的一个扩展，扩展的更所的功能 如国际化处理，资源加载


17.一个Spring的应用看起来象什么？



18.什么是Spring的依赖注入？
   在创建bean对象的时候，自动把需要的依赖注入


19.有哪些不同类型的IOC（依赖注入）方式？
   set注入
   构造函数


20.哪种依赖注入方式你建议使用，构造器注入，还是Setter方法注入？
   必须注入的使用构造器，可选的使用sett


21.什么是Springbeans?



22.一个SpringBean定义包含什么？



23.如何给Spring容器提供配置元数据?
   1.基于xml
   2.基于注解
   3.基于java


24.你怎样定义类的作用域?
    1.singele 单例
    2.prototype 一个bean对应多个实例
    3.request 一个http request 对应一个实例，请求完成后，失效
    4.session 一个http session 对应一个实例仅在，session中有效，过期失效
    5.groabl-session ，与Portlet容器有关，在Portlet容器部署多个应用，要共享变量，要储存在global-session


25.解释Spring支持的几种bean的作用域。



26.Spring框架中的单例bean是线程安全的吗?
  不是，


27.解释Spring框架中bean的生命周期。
  1.创建bean
  2.封装属性
  3.如果实现beannameaware ,执行setbenaname
  4.如果实现beanFactoryaware 执行setbeanFacroty
  5.BeanPostpreoces接口，就会回调postProcessBeforeInitialization
  6.initializationBean 执行afterPropertiesSet
  7.调用init-method
  8.Beanpost 的postProcessAfterInitialization
  9.DisposableBean
  10.destory-method

28.哪些是重要的bean生命周期方法？你能重载它们吗？
  


29.什么是Spring的内部bean？

   一个bean中依赖另一个bean


30.在Spring中如何注入一个java集合？

   <list>
   <set>
   <map>  
   <props>
  

31.什么是bean装配?

     把不同的bean组装在一起

32.什么是bean的自动装配？

  不需要属性，构造器，根据配置进行组装

33.解释不同方式的自动装配。

   no
   byname
   bytyoe
   constructor
   autodetect


34.自动装配有哪些局限性?

    

35.你可以在Spring中注入一个null和一个空字符串吗？
  可以i


36.什么是基于Java的Spring注解配置?给一些注解的例子.
  


37.什么是基于注解的容器配置?
    使用@configuration配置类为bean定以元数据，@bean定义bean


38.怎样开启注解装配？

   <context:annotation-config/>

39.@Required注解

    被设置的bean必须属性必须设置，通过显示装配或自懂装配，否则异常 

40.@Autowired注解

   自动注入

41.@Qualifier注解
  
   和Autowired配和使用，过滤多个bean的装配


42.在Spring框架中如何更有效地使用JDBC?



43.JdbcTemplate



44.Spring对DAO的支持



45.使用Spring通过什么方式访问Hibernate?



46.Spring支持的ORM

     mybatis

47.如何通过HibernateDaoSupport将Spring和Hibernate结合起来？



48.Spring支持的事务管理类型
    
      1.编程识事物
      2，声明式事物
      


49.Spring框架的事务管理有哪些优点？
   


50.你更倾向用那种事务管理类型？
    


51.解释AOP
   面向切面，实现了业务代码和服务代码的分离


52.Aspect切面
    
    切入点和通知的结合
    


53.在SpringAOP中，关注点和横切关注的区别是什么？
    


54.连接点
   定义的方法


55.通知
   
     实现功能，增强的逻辑


56.切点
   
    定义那些连接点可以被增强
   
   


57.什么是引入?

   把通知应用到切入点创建代理的过程

58.什么是目标对象?
  
    被曾强的的对想


59.什么是代理?

  增强的后的目标对象

60.有几种不同类型的自动代理？



61.什么是织入。什么是织入应用的不同点？

 把通知应用到目标对象的创建代理的过程

62.解释基于XMLSchema方式的切面实现。



63.解释基于注解的切面实现



64.什么是Spring的MVC框架？



65.DispatcherServlet



66.WebApplicationContext



67.什么是SpringMVC框架的控制器？



68.@Controller注解



69.@RequestMapping注解



70.返回Json用什么注解？
    
   

   
    
 
  
 
