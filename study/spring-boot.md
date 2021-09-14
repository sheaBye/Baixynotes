记录一些学习springboot的内容和问题

1.启动类注解：
    1.@SpringBootApplication  
    2.@EnableAutoConfiguration：启用 SpringBoot 的自动配置机制
    3.@ComponentScan： 扫描被@Component (@Service,@Controller)注解的 bean，注解默认会扫描该类所在的包下所有的类。、
    4.@SpringBootConfiguration：注解相当于使用 @Configuration、@EnableAutoConfiguration 和 @ComponentScan 及他们的默认属性：

@Configuration
@Import 注解可用于导入其他配置类
@ComponentScan 自动扫描所有 Spring 组件，包括 @Configuration 类


springboot 启动-----

```java
//springboot 启动-----
// 方式一
@SpringBootApplication 
public class Application {

    public static void main(String[] args) {
        SpringApplication.run(Application.class, args);
    }

}

// 方式二
public static void main(String[] args) {
    SpringApplication app = new SpringApplication(MySpringConfiguration.class);
    app.run(args);
}


// 方式三
public static void main(String[] args) {
    new SpringApplicationBuilder()
        .sources(Parent.class)
        .child(Application.class)
        .run(args);
}


```


 ApplicationContext：是spring继BeanFactory之外的另一个核心接口或容器，允许容器通过应用程序上下文环境创建、获取、管理bean。为应用程序提供配置的中央接口。在应用程序运行时这是只读的，但如果实现支持这一点，则可以重新加载。


springboot 事件监听器：
 
 ```java 

 Spring Boot 启动事件顺序
1、ApplicationStartingEvent

这个事件在 Spring Boot 应用运行开始时，且进行任何处理之前发送（除了监听器和初始化器注册之外）。

2、ApplicationEnvironmentPreparedEvent

这个事件在当已知要在上下文中使用 Spring 环境（Environment）时，在 Spring 上下文（context）创建之前发送。

3、ApplicationContextInitializedEvent

这个事件在当 Spring 应用上下文（ApplicationContext）准备好了，并且应用初始化器（ApplicationContextInitializers）已经被调用，在 bean 的定义（bean definitions）被加载之前发送。

4、ApplicationPreparedEvent

这个事件是在 Spring 上下文（context）刷新之前，且在 bean 的定义（bean definitions）被加载之后发送。

5、ApplicationStartedEvent

这个事件是在 Spring 上下文（context）刷新之后，且在 application/ command-line runners 被调用之前发送。

6、AvailabilityChangeEvent

这个事件紧随上个事件之后发送，状态：ReadinessState.CORRECT，表示应用已处于活动状态。

7、ApplicationReadyEvent

这个事件在任何 application/ command-line runners 调用之后发送。

8、AvailabilityChangeEvent

这个事件紧随上个事件之后发送，状态：ReadinessState.ACCEPTING_TRAFFIC，表示应用可以开始准备接收请求了。

9、ApplicationFailedEvent

这个事件在应用启动异常时进行发送。

 ```

 

 --------------------------------
 外部配置spring boot 属性：
 外部配置属性来源及顺序：（上边得优先级大）

您的主目录（当 devtools 被激活，则为 ~/.spring-boot-devtools.properties ）中的 Devtools 全局设置属性。
在测试中使用到的 @TestPropertySource 注解。
在测试中使用到的 properties 属性，可以是 @SpringBootTest 和用于测试应用程序某部分的测试注解。
命令行参数。
来自 SPRING_APPLICATION_JSON 的属性（嵌入在环境变量或者系统属性【system propert】中的内联 JSON）。
ServletConfig 初始化参数。
ServletContext 初始化参数。
来自 java:comp/env 的 JNDI 属性。
Java 系统属性（System.getProperties()）。
操作系统环境变量。
只有 random.* 属性的 RandomValuePropertySource。
在已打包的 jar 外部的指定 profile 的应用属性文件（application-{profile}.properties 和 YAML 变量）。
在已打包的 jar 内部的指定 profile 的应用属性文件（application-{profile}.properties 和 YAML 变量）。
在已打包的 jar 外部的应用属性文件（application.properties 和 YAML 变量）。
在已打包的 jar 内部的应用属性文件（application.properties 和 YAML 变量）。
在 @Configuration 类上的 @PropertySource 注解。
默认属性（使用 SpringApplication.setDefaultProperties 指定）。

