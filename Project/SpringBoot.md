## SpringBoot

### 1. why?

配置简化：

Servert  -->  Spring  --> SpringBoot

Servert需要配置： Tomcat，JDBC 等

<img src="/Users/ruanmingzhe/Library/Containers/com.tencent.xinWeChat/Data/Library/Caches/com.tencent.xinWeChat/2.0b4.0.9/2bf314859ef09a179ef7d53c69d3ad7f/dragImgTmp/WeChata200c410179054f75a39e387bd7cacb5.png" alt="WeChata200c410179054f75a39e387bd7cacb5" style="zoom:30%;" />

Spring需要配置： Tomcat，JDBC 等

SpringBoot需要配置： Tomcat，JDBC 等

```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-thymeleaf</artifactId>
</dependency>
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
</dependency>

<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-devtools</artifactId>
    <scope>runtime</scope>
    <optional>true</optional>
</dependency>
<dependency>
    <groupId>org.projectlombok</groupId>
    <artifactId>lombok</artifactId>
    <optional>true</optional>
</dependency>
```



### Springboot: Features

Create stand-alone Spring applications

Embed Tomcat, Jetty or Undertow directly (no need to deploy WAR files)

Provide opinionated 'starter' dependencies to simplify your build configuration

Automatically configure Spring and 3rd party libraries whenever possible

Provide production-ready features such as metrics, health checks, and externalized configuration

Absolutely no code generation and no requirement for XML configuration