##  java

### jdk

> 依据 jvm 规范实现的一套 API，反射、泛型、IO、函数编程 、异常、注解等

- **核心**

- **集合**



### 并发

> 多线程、线程安全、AQS、锁、并发容器、原子类、ABA 问题、伪共享等



### jvm

> 存储级别 or 执行级别，jdk 提供了一系列工具来窥探这些信息。包含jstat、jmap、jstack、jvisualvm 等都是最常用的。
> 垃圾收集器、Class文件结构、类加载机制、参数调优、字节码、锁升级、JMM、JVM并发、JIT等



### spring

- **spring boot**



### 工具集

> fastjson、Hutool 等



## 数据库

### MySQL

> 数据库范式、字符集、索引（聚集索引、非聚集索引、复合索引、自适应哈希索引）、事务（ACID、隔离级别、MVCC）、锁（锁与同步锁、公开锁、非公平锁、悲观锁、乐观锁、互斥锁、共享锁、死锁）等



### Druid

> 数据库连接池方面，国内使用 druid 最多



### mongodb



### 数据同步

> 实时数据同步工具，都是把自己模拟成一个从库，进行数据拉取和解析。 mysql 通过 binlog 进行同步；canal、maxwell 等工具，都支持将要同步的数据写入到 mq 中进行后续处理。对于ETL（抽取、清洗、转换）来说，datax、logstash、sqoop 等，都是这样的工具。



## 中间件

### 缓存

> 分布式缓存来说，优先选择的就是 `redis`。由于 redis 是单线程的，并不适合高耗时操作。所以对于一些数据量比较大的缓存，比如图片、视频等，使用老牌的 memcached 效果会好的多。
> redis、caffeine、vernemq等



### 消息队列

> 一个大型的分布式系统，通常都会异步化，走消息总线。
> kafka 有着极高的吞吐量
> rocketmq 和 rabbitmq 都是电信级别的消息队列，在业务上用的比较多
> mqtt 具体来说是一种协议，主要用在物联网方面



### 任务调度

> quartz 是 java 中比较古老的调度方案，分布式调度采用数据库锁的方式，管理界面需要自行开发。相对来说 xxl-job 更加轻量好用



### RPC框架

> thrift、dubbo、gRPC 默认都是二进制序列化方式的 socket 通讯框架；feign、hessian 都是 onhttp 的远程调用框架。



### 通讯框架

> Java 中，netty 已经成为当之无愧的网络开发框架，包括其上的 socketio。服务的响应时间主要耗费在业务逻辑以及数据库上，**通讯层耗时在其中的占比很小**。



### 数据仓库

> 现在的企业，数据量都非常大，数据仓库是必须的。
> 搜索方面，solr 比较成熟，稳定性更好一些，但实时搜索方面不如 es。
> 列式存储方面，基于 Hadoop 的 hbase，使用最是广泛；基于 LSM 的 leveldb 写入性能优越，但目前主要是作为嵌入式引擎使用多一些。
> 时序数据库方面，opentsdb 用在超大型监控系统多一些



### 服务器

> Tomcat、Nginx、Apache等



## 前端



## 架构

### 设计思想

> DDD、Aotor模式、响应式设计、RESTful、Service Mesh等



### 设计模式



### 分布式

> 分布式系统 zookeeper 能用在很多场景，与其类似的还有基于 raft 协议的 etcd 和 consul。
> CAP/BASE、Paxos/Raft、分布式锁、API网关、CC、分布式文件系统、分布式Id、分布式事务等



### 微服务

> 注册中心默认的 eureka 不再维护，consul 已经成为首选，nacos 带有后台，比较适合国人使用习惯
> 熔断组件官方的 hystrix 不再维护，推荐阿里的 sentinel or  resilience4j
> 调用链推荐 jaeger or skywalking
> 配置中心推荐 apollo
> 对于 spring cloud 来说，zuul 系列推荐使用 zuul2，zuul1 是多线程阻塞的有硬伤。spring-cloud-gateway 是 spring cloud 亲生的，但目前用的不是很广泛



### 高并发

> 读写分离、负载均衡、分库分表（推荐使用驱动层的`sharding-jdbc`，或者代理层的`mycat`，**方案一旦确定，几乎无法回退**）进行垂直拆分、水平拆分、不停机切换、HA&FailOver等



### 高可用

> 限流、熔断（sentinel）、降级、排队、超时与重试、容灾、应用层容灾、跨机房容灾等



### 性能优化

> 内核参数优化、jvm优化、网络参数优化、事务优化、数据库优化、池化等



## 计算机基础

### 数据结构

> 基本的数据结构非常重要，无论接触什么编程语言，基本数据结构都是首先要掌握的。
> 队列、栈、链表、数组、字典、图、堆、树（红黑树、B、B+、B*树、LSM 树、二叉树、平衡二叉树、平衡二叉树、BST 二叉查找树）等



### 算法

> 算法是某些大厂的门槛，能够培养逻辑思维能力和动手能力，最快的进阶途径就是刷 leetcode。
> 排序算法、贪心算法、动态规划、回溯算法、剪枝算法、图算法等



### 计算机网络

> 熟悉 Netty 开发是入门网络开发的捷径。
> 网络基础、网络模型、Epoll、Kqueue、长连接、爬虫等



### 操作系统

> 对于计算密集型应用，就需要关注程序执行的效率；对于I/O密集型，要关注进程（线程）之间的切换以及I/O设备的优化以及调度。
> 计算机原理、CPU、内存、IO、进程线程、Linux、Windows等



## 视音频



## 运维/测试

### 安全

> web 安全（SQL注入、XSS、CSRF、DDOS、脚本注入、漏洞、验证码）、隐私信息保护、加密解密、证书体系、网络隔离、内外网隔离、跳板机、授权认证（OAuth、SSO、JWT）等



### 测试

> TDD、单元测试、压力测试、全链路压测



### 故障排查

> 内存溢出排查、堆内外层排查、网络排查、IO排查、高负载排查等



### 运维

> 服务器一般采用稳定性较好的 centos，并配备 ansible工具进行支持。
> haproxy、lvs、keepalived、APM、Docker、CI/CD、jenkins、自动化（ansible）、监控（zabbix、prometheus + grafana + telegraf、es/logstash/kibana）等



## 管理/工具

### 运营

### 项目

> 架构评审、重构、代码规范、代码评审、RUP、看板管理、SCRUM、敏捷开发、结对编程、PDCA、FMEA 管理模式等



### 团队



### 面试

 

### 工具

> IDE、代码管理、项目构建等



### 资讯

> 行业、技术趋势、行业数据分析等



## 开源项目

### 开源



### 教程



### 课程
