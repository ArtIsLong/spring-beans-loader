# 简介

该项目主要参考MyBatis中MapperScan的功能，可通过自定义注解、标志类、标志接口加载Bean，使扩展Spring框架更加便利。

- 源码地址
  - Github:https://github.com/ArtIsLong/spring-beans-loader.git
  - Gitee:https://gitee.com/artislong/spring-beans-loader.git
- 我的博客:https://artislong.gitee.io
- 简书:https://www.jianshu.com/u/46d989a94f20

**自制的小工具，欢迎使用和Star，如果使用过程中遇到问题，可以提出Issue，我会尽力完善该工具**

# 使用方式

## 引入依赖

pom.xml

~~~xml
<dependency>
  <groupId>com.github.artislong</groupId>
  <artifactId>spring-beans-loader</artifactId>
  <version>1.0</version>
</dependency>
~~~

build.gradle

~~~groovy
compile 'com.github.artislong:spring-beans-loader:1.0'
~~~

## 添加注解

~~~java
@BeansLoader(
        basePackages = "com.github.artislong",
        markerInterfaces = {
                Controller.class,
                Interceptor.class,
                Routes.class,
                Handler.class,
                Render.class
        },
        annotationClass = RouterPath.class)
@SpringBootApplication
public class JfinalApplication {

    public static void main(String[] args) {
        SpringApplication.run(JfinalApplication.class, args);
    }   
}
~~~
