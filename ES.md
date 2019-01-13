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

Elasticsearch中的节点（比如共20个），其中的10个选了一个master，另外10个选了另一个master，怎么办？

客户端在和集群连接时，如何选择特定的节点执行请求的？

详细描述一下Elasticsearch更新和删除文档的过程。

详细描述一下Elasticsearch搜索的过程。

在Elasticsearch中，是怎么根据一个词找到对应的倒排索引的

Elasticsearch在部署时，对Linux的设置有哪些优化方法？

对于GC方面，在使用Elasticsearch时要注意什么？

在并发情况下，Elasticsearch如果保证读写一致？

如何监控Elasticsearch集群状态？

拼写纠错是如何实现的
详细描述一下Elasticsearch索引文档的过程。
