# Spring MVC + Hibernate Jpa2 + Shiro + logback + Sitemesh3 + bootstrap3 简单框架

+ web.xml文件当中的spring.profiles.default可切换项目启动模式<br>
development:以开发环境启动，采用SQLite数据库，production：以生产环境启动，采用MySQL数据库


#### 系统启动：
+ 首次启动系统时会自动创建表至数据库当中，若手动建表脚本在doc/sql目录下

+ 系统采用Shiro权限框架，库表当中若无数据，则系统只能访问首页，无法进行登录<br/>
执行InitServiceTest.init()方法初始化数据方法即可登录，注意InitServiceTest类中的@ActiveProfiles("")是不是你指的环境


### PS. 系统当中是支持memcached、solr、redis框架，修改配置文件即可正常启动
+ memcached修改web.xml，在contextConfigLocation当中加入classpath*:spring/applicationContext-memcached.xml<br/>
打开MemcachedFactory类中的@Resource(name = "memcachedClient")注释

+ solr修改web.xml，在contextConfigLocation当中加入classpath*:spring/applicationContext-solr.xml<br/>
打开BaseSolrRepositoryImpl接口实现类中的@Resource(name = "solrcloud_server")注释

+ redis修改web.xml，在contextConfigLocation当中加入classpath*:spring/applicationContext-redis.xml<br/>
打开RedisBaseService抽象类中的@Resource(name = "redisTemplate")注释


若发现问题或有疑问，欢迎大家[反馈](http://git.oschina.net/wangxinforme/springmvc-jpa/issues)，相互交流

Vincent [Git@OSC](http://git.oschina.net/wangxinforme "Vincent Git@OSC主页")

