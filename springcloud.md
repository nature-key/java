1.SpringCloud和Dubbo

  Dubbo是阿里来发的，是一种服务治理框架，使用rpc,他使用第三方服务实现服务注册如zookpper,没有实现网管
  
  springcloud 是apach开发的，使用restful ,他是使用自己的eureka,使用自己的zuul,还支持服务熔断，git的分布式配置晚间
  ，
3.Rest和RPC对比

  RPC服务远程调用服务之间的耦合搞，为每一个服务定义接口，持续在一起拿到版本发布，不然容易产生版本冲突，rest轻量级接口，只要约定一定的规范，但是也会产生不一致，
  
  rest比rpc更加灵活
  
  rest 
  
SpringBoot和SpringCloud

 springboot是简化开发的一个框架，简化spring的冗余开发，而springcloud是一个服务治理框架，springcloud依赖springboot,springboot不依赖springcloud
 
 也可以用doubb
 
 springboot注重个体服务的开发，
 
 springcloud是服务治理，服务熔断，网管，
 
.Eureka和ZooKeeper都可以提供服务注册与发现的功能,请说说两个的区别

1.zookpeer cp (一致性 ，容错行),eureka ap（可用性 容错行）

   zookperr服务瘫痪，服务选举，服务不可用
   
   eureka 各个节点平等，保证服务可用，但是数据不是最新的
   
   自动保护机制导致
   
    eureka不会删除长时间没有发生心跳而是过期服务
    
    仍然可以接受注册和发现，但是不会同步数据
    
    网络异常，最终服务恢复，同步数据
    
2.zookpeer半数存活，eureka自我保护

3.zookperrlead节点follower, eureka 节点平等

4.zookeeper是一个进程，eureka是一个工程
 
四.微服务之间是如何独立通讯的

20.什么是服务熔断?什么是服务降级

  微服务多个服务协作，当一个服务瘫痪，在高哦并发中，多个请求，一直等待，占用资源，发生雪崩
  
  所以当服务相当保险丝，当发生雪崩，服务熔断，当其他请求，时候，服务直接返回follback 服务降级

21.微服务的优缺点分别是什么?说下你在项目开发中碰到的坑

   优点
   
     1.服务解耦代码简单
     
     2.开发容易
     3.易于第三方开发
     4.多语言开发
     
   缺点
   
     服务维护男
     分布式系统的负责性
     数据的一致性
     系统部署依赖
     
22.你所知道的微服务技术栈有哪些?请列举一二


   1.spring boot
   
   2.springmvc
   
   spring 
   
   eureka
   
   zookeepr
   
   zuul
   
   springonfig bus
   
   kafak rabbitMQ
   

23.Eureka和ZooKeeper都可以提供服务注册与发现的功能,请说说两个的区别

