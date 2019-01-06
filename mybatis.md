1、#{}和${}的区别是什么？
   
    #{}防止sql注入，直接把sql的参数换成？使用prepartisStatement设置值
    ${}是变量的值直接替换，属于文本替换
    
2、Xml映射文件中，除了常见的select|insert|updae|delete标签之外，还有哪些标签？
  
    动态sql里面的标签 <if><where><choose><triem><bind><sql><include><foreach>
3、最佳实践中，通常一个Xml映射文件，都会写一个Dao接口与之对应，请问，这个Dao接口的工作原理是什么？Dao接口里的方法，参数不同时，方法能重载吗？

  DAO接口是map接口 没有实现类，工做原理使用JDK动态代理，是DAO接口生成代理，代理对象把拦截接口方法，转成mapperSatement 执行sql返回结构
   
  每一个xml配置对应一个namespace，是根据namespace+方法导到mapperstament，不能进行重载 
  
4.Mybatis是如何进行分页的？分页插件的原理是什么

   使用rowbands 实现内存分页，而不是物理分页，可以在sql写参数实现物理分页，也可以分页插件实现物理分页
   
    使用mybatis插接接口，对接口实现拦截，重写sql实现物理分页
    
5、简述Mybatis的插件运行原理，以及如何编写一个插件。
 
  Executor  statementHandler pameterHandler resultsetHandler
  
  1.每一个都会经过 palugiall 封装代理
  2.每一个都会在intercepter.invoke进行连接
  3只会拦截你指定的方法
  实现
   1.继承Interceptor
   2里面的有 intercept()拦截放的方法,palugin()封装代理.serPROPERTIES()设置属性
   3,配置要拦截的目标对象和目标方法，
   @Intercepts({@Signature(type = Executor.class, method ="update", args = {MappedStatement.class, Object.class})})
   使用Plugin.wrap方法进行代理封装
  
6、Mybatis执行批量插入，能返回数据库主键列表吗？
 
7、Mybatis动态sql是做什么的？都有哪些动态sql？能简述一下动态sql的执行原理不？
  
   以标签的实现逻辑进行配节sql,根据ognl表达式的值动态的拼接sql,
8、Mybatis是如何将sql执行结果封装为目标对象并返回的？都有哪些映射形式？

  1.resultmap标签进行封装
  2.执行sql语句进行别名封装
  
9、Mybatis能执行一对一、一对多的关联查询吗？都有哪些实现方式，以及它们之间的区别。
10、Mybatis是否支持延迟加载？如果支持，它的实现原理是什么？
 
  近支持 assocation 和collection 延迟架子啊， 配置lazyLoadingEnabled=true|false
   原理：当获取一个对象的属性的时候，当对象为空的时候，mybatis就会单独去执行sql,获取对象，然后设置，在进行获取对象属性
   
11、Mybatis的Xml映射文件中，不同的Xml映射文件，id是否可以重复？

不可以

12、Mybatis中如何执行批处理？

  实现batchExctor
  
13、Mybatis都有哪些Executor执行器？它们之间的区别是什么？

   simpleExcutor select 和update  每一个执行生成一个sttament用完就satement关闭
   reuserExcutor sselect 和update  没有就创建statement 重复使用
   batchExcutor 支队update支持，每一个都进行addbatch（）。等待执行



14、Mybatis中如何指定使用哪一种Executor执行器？

  1.下配置文件配置
  2.获取sqlsesstionfatcory配置
15、Mybatis是否可以映射Enum枚举类

 可以实现typeHandler接口 或继承BaseTypeHandler
   实现getresult 和setpropertis
 
16、Mybatis映射文件中，如果A标签通过include引用了B标签的内容，请问，B标签能否定义在A标签的后面，还是说必须定义在A标签的前面？

  可以， mybatis配置是顺序执行，但是，当解析a标签的时候，b还没有解析，就标记为为解析，当b解析后就进行解析未解析的标签

17、简述Mybatis的Xml映射文件和Mybatis内部数据结构之间的映射关系？

18、为什么说Mybatis是半自动ORM映射工具？它与全自动的区别在哪里
  
    hibernate 是全自动映射，是根据对象关系获取数据，而mybatis的关系对象是根据sql获取数据

