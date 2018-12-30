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

  一个启动器，

12、如何在 Spring Boot 启动的时候运行一些特定的代码？
13、Spring Boot 有哪几种读取配置的方式？
14、Spring Boot 支持哪些日志框架？推荐和默认的日志框架是哪个？
15、SpringBoot 实现热部署有哪几种方式？
16、你如何理解 Spring Boot 配置加载顺序？
17、Spring Boot 如何定义多套不同环境配置？
18、Spring Boot 可以兼容老 Spring 项目吗，如何做？
20、Spring Boot 2.X 有什么新特性？与 1.X 有什么区别？
