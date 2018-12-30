1.什么是springboot

    springboot 是spring开源的子项目，是spring一站式解决方案，简化开发，提供各种配置，是开发更容易上手
    
2.为什么要用springboot

    开发简单
    
    自动配置
    
    独立运行
    
    无代码生成和xml配置
    
    
    
3.Spring Boot 的核心配置文件有哪几个？它们的区别是什么？ 
   
    application :自动配置
    
    bootstrap
    
    两种都是应用的上下文，bootstarap是父上下文，比application更早加载，是加载外部资源的配置文件
    
    使用场景
      1.spring cloud 配置
      
      2.属性不定固定
      
      3.一些加密解密



4、Spring Boot 的配置文件有哪几种格式？它们有什么区别？
   
     yaml
     
     properties
     
     
5.Spring Boot 的核心注解是哪个？它主要由哪几个注解组成的？
    
     主类的@springbootapplication ,包含 @EnuableAutoConfiguration  @Configuration 配置文件 @ComponyScan

6、开启 Spring Boot 特性有哪几种方式？

     1.spring-boot-start-partent
     
     2.spring-boot-dependenceies
    
7Spring Boot 需要独立的容器运行吗？

 可以
 
8、运行 Spring Boot 有哪几种方式？
   
   1.main
   
   2.java -jar application.jar
   
   3.spring-boot
   
9、Spring Boot 自动配置原理是什么？
   
   1.main中的@springbootapplication
   
   2里面的@enableautoapplication
   
   3.@import 
   
   4.这个类会加载类路径会jar下的mete-inf/spring.fatories
   
   5.里面有类配置进行配置
   
   


、你如何理解 Spring Boot 中的 Starters？

  Starters可以理解为启动器，它包含了一系列可以集成到应用里面的依赖包，你可以一站式集成 Spring 及其他技术，而不需要到处找示例代码和依赖包。如你想使用 Spring JPA 访问数据库，只要加入 spring-boot-starter-data-jpa 启动器依赖就能使用了

12、如何在 Spring Boot 启动的时候运行一些特定的代码？
   1.commandlineRuner
   2.applicationRunner
   
   实现接口api
    
13、Spring Boot 有哪几种读取配置的方式？

   1.@values
   2.PropertySource
   3.ConfigurationProperties
   4.Environment

14、Spring Boot 支持哪些日志框架？推荐和默认的日志框架是哪个？

   java util loging  
   
   logback
   
   log4j2
   
   默认logback
   
15、SpringBoot 实现热部署有哪几种方式？

    1.spring-boot-devtool
    2.
16、你如何理解 Spring Boot 配置加载顺序？
    
     1.命令》环境变脸》包外properties>包下properties>包外yaml>报下yaml>@Configuration`配置文件上 `@PropertySource` 注解加载的参数；>`SpringApplication.setDefaultProperties` 指定）；
    
17、Spring Boot 如何定义多套不同环境配置？

   application.preperties
   
   application-dev.preperties
   
   application-test.preperties
   
   application-prod.preperties
   
   profile:配置不同环境的变量
   
    yaml配置
      spring.profile.active=dev
      
      
18、Spring Boot 可以兼容老 Spring 项目吗，如何做？
可以
20、Spring Boot 2.X 有什么新特性？与 1.X 有什么区别？

   1.springboot2 支持1.8
   2.支持kotlin1.2
   3.配置变更
   4.第三方版本的升级
      spring 5
    5.响应式 Spring 编程支持
    6.HTTP/2 支持
    7.配置属性绑定

   
