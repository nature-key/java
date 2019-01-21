1、什么是Redis？

  redis是一个开源的内存中数据结构存储，可用来做数据库，缓存消息中间件
  
2、Redis相比memcached有哪些优势？
  
   1.速度快
   
   2.存储类型多
   
   3.可以进行持久化
   
3、Redis支持哪几种数据类型？
   
   string list  set  sort set  hash   geo  hyperloglog
   
4、Redis主要消耗什么物理资源？
    
    内存
5、Redis的全称是什么？

   remote  dicaration server
   
6、Redis有哪几种数据淘汰策略？
  
    1.valatile-lru :过期数据，去除频率少的数据
    
    2. valatile-ttl:过期数据，去除快过期数据
    
    3.valatile-random
    
    4.allkeys-random
    
    5allkeys-lru
    6.noeviction
7、Redis官方为什么不提供Windows版本？

8、一个字符串类型的值能存储最大容量是多少？

512m
9、为什么Redis需要把所有数据放到内存中？
  
   加快读写速度，如果放到磁盘中，Io速度影响速度，

10、Redis集群方案应该怎么做？都有哪些方案？

  1.twemproxy，相当与一个代理，链接redis改成链接twemproxy，接受请求，使用一致性hash，请求道具体redis,但是如果增加节点，是不能请求的到新的节点
  
  2.cods。和twemproxy一样，但是增加节点，可以回复到新的节点
  
  3.redis cluster

11、Redis集群方案什么情况下会导致整个集群不可用？

  a b c 集群 如果b节点宕机，就会失去部分曹不可用
  
12、MySQL里有2000w数据，redis中只存20w的数据，如何保证redis中的数据都是热点数据？ ，

  redis内存上升到一定大小的时候，就会实施淘汰策略
  
13、Redis有哪些适合的场景？  

  1.队列
  
  2.消息中间件
  
  3.计数器
  
  4.回话缓存
  
14、Redis支持的Java客户端都有哪些？官方推荐用哪个？

   jedis  Redisson、Jedis、lettuce等等，官方推荐使用Redisson。
15、Redis和Redisson有什么关系？
Redisson是一个高级的分布式协调Redis客服端，能帮助用户在分布式环境中轻松实现一些Java的对象
16、Jedis与Redisson对比有什么优缺点？
    
    jedis 是java实现的客户端，功能全面，相比redisson他使用简单，但是不支持，事物，管道，他的宗旨是对redis额关注分离，从而集中业务处理

17、Redis如何设置密码及验证密码？
  设置密码：config set requirepass 123456

授权密码：auth 123456

18、说说Redis哈希槽的概念？
  
   rediscluster没有实现一致性hash,而是实现了槽的概念，使用crch16对可以取莫。刷出子啊那个节点

19、Redis集群的主从复制模型是怎样的？
     异步

20、Redis集群会有写操作丢失吗？为什么

  会，
？21、Redis集群之间是如何复制的？
    
      使用全量复制，和部分复制，
      全量复制：从节点psync ，主节点，进行pgsava保存rdb，同时新的写操作，记录子啊buffer总中，返回给slave.清除salva数据，架子啊rdb, 架子啊buffer
      
       部分复制：获取slava的ofset果果早fbuffer的对类范围内，就从这个offset开始复制

22、Redis集群最大节点个数是多少？
   
   16384
23、Redis集群如何选择数据库？
   没有数据库，只有 0
24、怎么测试Redis的连通性？
  ping
25、Redis中的管道有什么用？

26、怎么理解Redis事务？
   事物是一个隔离操作，事物里面的命令都是进行持久化，有序的进行，在事物执行的时候，不会被其他客户端请求打断
    事物是一个原子操作， 要么成功要么时报

27、Redis事务相关的命令有哪几个？
   
      MULTI、EXEC、DISCARD、WATCH

28、Redis key的过期时间和永久有效分别怎么设置？

   expire   PERSIST
   
29、Redis如何做内存优化？
      
      尽可能的和私用散列表，比如一个用户不需要吧每一个属性都设置成key 
   
30、Redis回收进程如何工作的？

   命令执行的后后，如果大于最大内训，就会触发淘汰机制

31、Redis回收使用的是什么算法？3

  lru
2、Redis如何做大量数据插入？33、

  使用pipline
  
为什么要做Redis分区？
   
    使用更多的内存，让redis的性能更高，计算耿立更快

34、你知道有哪些Redis分区实现方案？
    
      1.客户端分区
      
      2.代理分区，实现请求给代理，代理会秦秋到正确的节点上
      
      3,查询路由，请打到一个sredia实例，实例自动去正确的节点
     
35、Redis分区有什么缺点？
    涉及多个key的操作通常不会被支持。例如你不能对两个集合求交集，因为他们可能被存储到不同的Redis实例（实际上这种情况也有办法，但是不能直接使用交集指令）。

同时操作多个key,则不能使用Redis事务.

分区使用的粒度是key，不能使用一个非常长的排序key存储一个数据集（The partitioning granularity is the key, so it is not possible to shard a dataset with a single huge key like a very big sorted set）.

当使用分区的时候，数据处理会非常复杂，例如为了备份你必须从不同的Redis实例和主机同时收集RDB / AOF文件。

分区时动态扩容或缩容可能非常复杂。Redis集群在运行时增加或者删除Redis节点，能做到最大程度对用户透明地数据再平衡，但其他一些客户端分区或者代理分区方法则不支持这种特性。然而，有一种预分片的技术也可以较好的解决这个问题


36、Redis持久化数据和缓存怎么做扩容？

    1.作为缓存 ，使用一致性hash
    
    2持久化数据，使用key t0 ndoe, 一旦节点数目确定不能变化，或者还是用一套平衡系统，
    
37、分布式Redis是前期做还是后期规模上来了再做好？为什么？
      前期做好，既然Redis是如此的轻量（单实例只使用1M内存）,为防止以后的扩容，最好的办法就是一开始就启动较多实例。即便你只有一台服务器，你也可以一开始就让Redis以分布式的方式运行，使用分区，在同一台服务器上启动多个实例。

一开始就多设置几个Redis实例，例如32或者64个实例，对大多数用户来说这操作起来可能比较麻烦，但是从长久来看做这点牺牲是值得的。

这样的话，当你的数据不断增长，需要更多的Redis服务器时，你需要做的就是仅仅将Redis实例从一台服务迁移到另外一台服务器而已（而不用考虑重新分区的问题）。一旦你添加了另一台服务器，你需要将你一半的Redis实例从第一台机器迁移到第二台机器。

版权声明：本文为博主原创文章，转载请附上博文链接！
38、Twemproxy是什么？

    一个缓存代理，实现memcach和redis协议，速度快，自动提供分区，redis不可用就会派出，不存在单点，是客户端和redis的衣蛾中间层，
39、支持一致性哈希的客户端有哪些？
40、Redis与其他key-value存储有什么不同？
       redis.可以支持持久化
       提供更复杂的数据结构
     
41、Redis的内存占用情况怎么样？
     
42、都有哪些办法可以降低Redis的内存使用情况呢？
如果你使用的是32位的Redis实例，可以好好利用Hash,list,sorted set,set等集合类型数据，因为通常情况下很多小的Key-Value可以用更紧凑的方式存放到一起。
43、查看Redis使用情况及状态信息用什么命令？
info
44、Redis的内存用完了会发生什么？
  f
   命令执行失败，但是可以读
   
45、Redis是单线程的，如何提高多核CPU的利用率？
   可以在同一个服务器部署多个Redis的实例，并把他们当作不同的服务器来使用，在某些时候，无论如何一个服务器是不够的， 所以，如果你想使用多个CPU，你可以考虑一下分片（shard）
46、一个Redis实例最多能存放多少的keys？List、Set、Sorted Set他们最多能存放多少元素？
   
     232

47、Redis常见性能问题和解决方案？


  1.master不要记性持久化
  2. 数据重要启用aof,每秒一次
  3.master和slavaz在同一个局域网
  4. 尽量避免在压力很大的主库上增加从库
  5.尽量实现链式布局

48、Redis提供了哪几种持久化方式？

   1.rdb 能够快速储存快照
   2.aof,是追加日志的放肆，还会进行aof重写
   3.redis重启，优先使用aof,因为数据比较完整
   
    
   
   
49、如何选择合适的持久化方式？

       如果要做持久化，数据中药，但是不敢洗数据跌势，用rdb, 有的用户使用aof,但是不建议，rdb易于储存，数据恢复也举哀


50、修改配置不重启Redis会实时生效吗？
。
  使用config set 
  针对运行实例，有许多配置选项可以通过 CONFIG SET 命令进行修改，而无需执行任何形式的重启。 从 Redis 2.2 开始，可以从 AOF 切换到 RDB 的快照持久性或其他方式而不需要重启 Redis。检索 ‘CONFIG GET *’ 命令获取更多信息
