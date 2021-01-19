+++
title = "Automatic Configuration"
author = ["Hans Pistor"]
date = 2021-01-18T10:57:00-05:00
tags = ["java", "spring"]
draft = false
+++

Spring Boot provides auto configuration by analyzing the class path. [Spring Boot]({{< relref "20210118105602-spring_boot" >}}) offers auto configuration of the JAR dependencies you have on your classpath. For example, if you add the JPA starter, Spring Boot will automatically try to configure the JPA for your application. This includes setting up the appropriate databse connection, etc.

The

This can be manually done by using annotations such as [@Conditional]({{< relref "20210118111006-conditional" >}}).

Spring boot also you to customize application properties in a few different ways: properties file, YAML, environment variables, and command line arguments. The easiest way is to edit the application.properties file.

You can also customize the auto-configuration by defining certain beans by yourself so that Spring won't use the default configuration. For Example, the dataSource bean.

You can override the name of the applicaiton.properties file like this. For example, to use `test.properties`

```java
@SpringBootApplication
public class TestSpringApplication {
    public static void main(String[] args) {
        System.setProperty("spring.config.name", "test");
        SpringApplication.run(TestSpringApplication.class, args);
    }
}
```

You can also you the [@ConfigurationProperties]({{< relref "20210118112202-configurationproperties" >}}) annotation to embed the configuration in a POJO.


## Links to this note {#links-to-this-note}

-   [Spring Boot]({{< relref "20210118105602-spring_boot" >}})
