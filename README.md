
###### Spring-Cloud-Book-Code-1目录的代码是第一版《Spring Cloud微服务-全栈技术与案例解析》配套源码

###### Spring-Cloud-Book-Code-2目录的代码是第二版《Spring Cloud微服务 入门 实战与进阶》配套源码

###### 购买链接：http://product.m.dangdang.com/27884997.html?&unionid=P-107917558m

# spring-cloud 文章对应源码

- Spring Cloud Eureka 初探：http://cxytiandi.com/blog/detail/11988
- Spring Cloud Eureka 增加权限认证：http://cxytiandi.com/blog/detail/12171
- Spring Cloud Eureka 集群高可用：http://cxytiandi.com/blog/detail/12188
- Spring Cloud Eureka 控制台快速查看Swagger API文档：http://cxytiandi.com/blog/detail/12578
- Spring Cloud Eureka REST 接口：http://cxytiandi.com/blog/detail/12610
- Spring Cloud Eureka 服务上下线监控：http://cxytiandi.com/blog/detail/17640
- Spring Boot2中Spring Security导致Eureka注册失败 ：http://cxytiandi.com/blog/detail/19388
- Spring Cloud中如何优雅的使用Feign调用接口：http://cxytiandi.com/blog/detail/12189
- Spring Cloud Feign fallback错误解决：http://cxytiandi.com/blog/detail/12368
- Spring Cloud Feign 启动UnsatisfiedDependencyException：http://cxytiandi.com/blog/detail/12549
- Spring Cloud中如何保证各个微服务之间调用的安全性： http://cxytiandi.com/blog/detail/12267
- Spring Cloud中如何保证各个微服务之间调用的安全性(下篇)：http://cxytiandi.com/blog/detail/12300
- Spring Cloud中Feign如何统一设置验证token：http://cxytiandi.com/blog/detail/12369
- spring Cloud统一异常处理：http://cxytiandi.com/blog/detail/3106
- Spring Cloud 如何选择分布式配置中心：http://cxytiandi.com/blog/detail/12466
- Ribbon负载均衡策略介绍：http://cxytiandi.com/blog/detail/13598
- Spring Cloud Ribbon 重试机制：http://cxytiandi.com/blog/detail/12507
- Spring Cloud Zuul结合Smconf配置中心动态进行IP黑名单限制：http://cxytiandi.com/blog/detail/12508
- Spring Cloud Zuul Filter 使用小经验：http://cxytiandi.com/blog/detail/12632
- Spring Cloud Zuul过滤器获取请求参数问题:http://cxytiandi.com/blog/detail/20343
- Spring Cloud如何提供API给客户端:http://cxytiandi.com/blog/detail/14458
- Spring Cloud Sleuth 链路追踪：http://cxytiandi.com/blog/detail/12804
- Spring Cloud Sleuth Zipkin 展示追踪数据：http://cxytiandi.com/blog/detail/12828
- Spring Cloud Sleuth Zipkin 升级使用：http://cxytiandi.com/blog/detail/12855
- Spring Boot Admin管理监控数据：http://cxytiandi.com/blog/detail/12880
- Hystrix 配置信息：http://cxytiandi.com/blog/detail/13127
- Spring Cloud中使用Hystrix 线程隔离导致ThreadLocal数据丢失：http://cxytiandi.com/blog/detail/13331
- Spring Cloud中Hystrix 线程隔离导致ThreadLocal数据丢失下篇：http://cxytiandi.com/blog/detail/18782
- Spring Boot Admin监控服务上下线邮件通知：http://cxytiandi.com/blog/detail/13376
- Spring Cloud Gateway 网关尝鲜:http://cxytiandi.com/blog/detail/20430
- Spring Cloud Gateway 整合Eureka路由转发:http://cxytiandi.com/blog/detail/20518

# 项目代码工程目录讲解
- fangjia-api-client：Feign客户端，所有调用的API定义在里面，相当于API的SDK
- fangjia-auth-service：服务之间内部调用认证的服务，服务调用时需要来这边进行认证，获取访问Token
- fangjia-boot-admin：Spring Boot Admin来管理服务的监控数据
- fangjia-common：公共的包，放一些通用的工具类
- fangjia-eureka：Eureka注册中心
- fangjia-fsh-api：API网关
- fangjia-fsh-house-service：house服务
- fangjia-fsh-substitution-service：substitution服务
- fangjia-fsh-user-service：用户服务，登陆接口，swagger使用示列
- fangjia-hystrix-dashboard：hystrix-dashboard,turbine示列
- fangjia-job：分布式任务调度
- fangjia-sjdbc-read-write：数据库读写分离
- fangjia-sjdbc-sharding-db-table：数据库分库分表
- fangjia-sjdbc-sharding-table：数据库分表
- fangjia-zipkin：调用链
- hystrix：hystrix单独使用
- transaction-mq-client：可靠消息服务Feign客户端
- transaction-mq-service：可靠消息服务,提供接口
- transaction-mq-task：负责发送消息

# 注意事项
最近发现有很多同学问我项目中有一些依赖的jar包在哪里，比如redis cache, swagger等，这些都在我的Github主页中有。
查看 http://cxytiandi.com/blog/detail/20517 看看怎么启动整个项目。

# 作者
- 尹吉欢 1304489315@qq.com
- 博客 http://cxytiandi.com/blogs/yinjihuan
- 微信群请加我微信拉你进群：jihuan900
- Spring Cloud QQ技术交流群：626640827

### 欢迎加入我的知识星球，一起交流技术，免费学习猿天地的课程（http://cxytiandi.com/course）

## PS：目前星球中正在星主的带领下组队学习Sentinel，等你哦！

![微信扫码加入猿天地知识星球](https://upload-images.jianshu.io/upload_images/2685774-b11318670c1457fa.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![猿天地](https://upload-images.jianshu.io/upload_images/2685774-17a60e1ead7fd232.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)











对于这套源码，最好的学习方式是跟着我的书籍一步步去学习，这样理解的会比较深刻，如果直接一上来就想把整个项目启动还是比较麻烦的，主要是依赖于太多东西了，今天跟大家介绍下如何启动所有的项目和如何进行测试。

## 下载源码

首先将整个仓库clone到本地，或者下载源码到本地也可以。

克隆仓库命令：git clone <https://github.com/yinjihuan/spring-cloud.git>

或者下载源码压缩包：



![img](https:////upload-images.jianshu.io/upload_images/2685774-a46268093016c6aa.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1000/format/webp)

1.png

在电脑上建一个目录存储起来就可以了，如下图：



![img](https:////upload-images.jianshu.io/upload_images/2685774-c2b9b91d7eb7900c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/373/format/webp)

2.png

接着就是导入你的开发工具中去，这边不做讲解，导入进去我们会发现少了一些jar包，这些jar包分别是：

- cxytiandi-conf-client
   这是我自己写的配置中心的客户端，代码地址：<https://github.com/yinjihuan/smconf> 同样的也需要大家下载到本地，因为我没发布到中央仓库，导入到开发工具中或者安装到本地的maven仓库，私服都行。
- cxytiandi-jdbc
   是基于JdbcTemplate封装的一个简易的ORM框架，代码地址：<https://github.com/yinjihuan/smjdbctemplate> 使用方式同上
- spring-boot-starter-swagger
   API文档管理，代码地址：<https://github.com/yinjihuan/spring-boot-starter-swagger> 使用方式同上

## 启动fangjia-eureka

上面好了之后我们就可以启动项目了，首选启动的是fangjia-eureka，执行EurekaServerApplication中的main方法即可。测试的话单节点就够了，如果要启动集群可以参考我的文章。

启动后在浏览器中访问<http://localhost:8761/> 就可以打开Eureka的管理页面，这个时候会提示验证身份，输入用户名yinjihuan和密码123456就可以了。

## 启动fangjia-fsh-house-service

接着我们启动一个具体的服务，比如：fangjia-fsh-house-service，执行FshHouseServiceApplication中的main方法。

这个时候会发现一只在连接zookeeper，修改配置文件中的地址为你自己的zookeeper地址

```
zookeeper.url=192.168.10.47:2181
```

这个zookeeper是我们配置中心用到的，配置中心也需要部署起来，配置中心的使用请查看：<https://github.com/yinjihuan/smconf>

如果你不想使用注册中心里的配置可以在配置文件中指定使用本地的配置，也就是conf包中实体类中默认的值，但是zookeeper的地址还是要配置的。

```
smconf.data.status=local
```

里面还有rabbitmq的配置，mysql配置集成到了配置中心，如需修改可以直接修改实体类或者配置文件。

启动成功后访问<http://localhost:8081/house/1> 有数据就证明成功了。

## 启动fangjia-fsh-api

执行ZuulApplication的main方法即可。同样需要配置zookeeper地址。

api中默认代理了所有服务，直接通过 <http://localhost:2103/fsh-house/house/1>就可以访问我们刚刚启动的house服务了。

至于网关其他的功能大家可以慢慢的去测试。

作者：尹吉欢

链接：https://www.jianshu.com/p/677d26fb2f84

来源：简书

简书著作权归作者所有，任何形式的转载都请联系作者获得授权并注明出处。

