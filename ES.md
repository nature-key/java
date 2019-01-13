什么是ElasticSearch？
 
  ES是一个搜索引擎，是居于Lucene搜索引擎的一个全文搜索引擎，是java开发的一个开源框架

您可以在文档上执行哪些基本操作
  
   增删改查文档

Elasticsearch中的倒排索引是什么

  倒排索引是ES的搜索的核心，他是吧一个据分解成一个个单词，每个单词记录着子啊那个doc上，用于百万级搜搜，快速获取的数据

ElasticSearch中的集群、节点、索引、文档、类型是什么

 集群：有多个节点或者是服务组成，共同保存数据，默认的明后才能elasticserch
 
 节点：就是么一个单个服务，他储存数据并参加集群索引和搜索功能
 
 索引 相当一数据库的数据库
 
 文档一条数据
 
 类型。表
？
ElasticSearch是否有架构

 有，ES的架构相当与，对描述文档类型和处理文登哪的不同字段的一个或多个描述，es成为映射

ElasticSearch中的分片是什么？

 es是一个分布式搜索引擎，所以通常被分割成到多个节点成为分片的元素

ElasticSearch中的副本是什么？

 一个分片的副本，为扩展和分发强求

ElasticSearch中的分析器是什么？

 把一句话进行分割成一个个单词，Analysis翻译为分析器，其功能是把文本切分成词项(词项是倒排索引中的基本单位

什么是ElasticSearch中的编译器

什么是ElasticSearch中的过滤器？

把toekn返回的toekn序列，进行大小写和相近语义转换
 

启用属性，索引和存储的用途是什么？


Elasticsearch是如何实现Master选举的？
 
 1.es主节点选择是ZenDiscovery模块负责的，
 2.ping所有的节点返回pingrepose
 3.过滤成为maste的节点
 4.重actienode选举
 5.获得法定人数
 6.是否是本节点 不是计入集群啊
 7等加入这达到法定任大虎，排除分master资格的节点图片小
 8成为主节点

Elasticsearch中的节点（比如共20个），其中的10个选了一个master，另外10个选了另一个master，怎么办？

 根据（n/2+1）投票选择主节点
 如果有两个，智能修改唯一的一个master候选，其他所谓data节点，避免脑裂

客户端在和集群连接时，如何选择特定的节点执行请求的？

详细描述一下Elasticsearch更新和删除文档的过程。
 1.更新删除都是写操作，
 2.每一个请求会到达固定的shard 根据路由计算
 3.存在buffer 人后进行refush进入欧式catche  ,同时生成tranlog
 4.提交到disk 叫做fulsh,清空buffer和创建显得seglenment
 5flush默认30,或者tranlog过大默认512M
 
 

详细描述一下Elasticsearch搜索的过程。

 1请求到每一个shard
 2,每一个shard排毒返回 from fsize
 3.返回给协调节点，进行排除，
 4.协调节点获取到数据，id,在批量到响应的shard获取丰富的字段
 5.返回给协调节点，返回给客户端



在Elasticsearch中，是怎么根据一个词找到对应的倒排索引的

Elasticsearch在部署时，对Linux的设置有哪些优化方法？

对于GC方面，在使用Elasticsearch时要注意什么？

1.倒排索引字典是缓存在常驻内存，无法GC,需要监控data node 的segment memory
2.一般的缓存，index ，filter filed catch 设置合理的大小，判断最坏的情况判断head是否够用
3.避免返回大量数据，如果需要使用scorll api
4.cluster state 常驻内存，无法水平扩展，可以分成多个集群
5.合理设置heap的带下，根据实际情况，设置heap大小，需要监控上heap大小

在并发情况下，Elasticsearch如果保证读写一致？

 1.实现乐观锁。版本控制
 2.一致性 all  qunum one  默认是quorum,大部分分片可用进行写操作
 可以通过版本号使用乐观并发控制，以确保新版本不会被旧版本覆盖，由应用层来处理具体的冲突；
 
另外对于写操作，一致性级别支持quorum/one/all，默认为quorum，即只有当大多数分片可用时才允许写操作。但即使大多数可用，也可能存在因为网络等原因导致写入

副本失败，这样该副本被认为故障，分片将会在一个不同的节点上重建。

对于读操作，可以设置replication为sync(默认)，这使得操作在主分片和副本分片都完成后才会返回；如果设置replication为async时，也可以通过设置搜索请求参

数_preference为primary来查询主分片，确保文档是最新版本。
 

如何监控Elasticsearch集群状态？
Marvel 让你可以很简单的通过 Kibana 监控 Elasticsearch。你可以实时查看你的集群健康状态和性能，也可以分析过去的集群、索引和节点指标

拼写纠错是如何实现的
