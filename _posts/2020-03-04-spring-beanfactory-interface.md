---
layout: course-spring-core
title: Ví dụ sử dụng Spring Bean Factory Interface trong Spring
slug : vi-du-su-dung-spring-bean-factory-interface-trong-spring
category: laptrinhspring
tags: [spring-core]
summery: Bean Factory 
image: /images/blog/spring.png
featureImage: /images/post/javacore/feature_di.png
description : Bài viết trình bày về chủ đề BeanFactory Interface trong Spring. Những chia sẻ trong bài viết sẽ giúp hiểu được thuật ngữ BeanFactory Interface là gì? Hướng dẫn cách để tạo dự án Maven trong Spring, thao tác để thêm các thư viện Spring vào Maven và tìm hiểu về cấu hình HelloWorld Spring Bean bằng Java, cấu hình Metadata cho HelloWorld Spring Java. Trong bài viết cũng trình bày về cách tạo Spring Container và thao tác để lấy đối tượng bean HelloWorld và gọi phương thức trong lập trình Spring.
youtubeId: Ecgj2Be1rGY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào bạn, chắc hẳn bạn cảm thấy khó hiểu về <b>Bean Factory</b>? Có phải bạn không rõ khái niệm của nó trong lập trình?

<br>
## **1 .BeanFactory Interface là gì**

BeanFactory Interface cung cấp cho chúng ta các cách để quản lý các đối tượng trong Spring IOC Container.

Spring beans là những đối tượng java và được quản lý bởi Spring IoC Container. Spring IoC Container có nhiệm vụ khởi tạo, cấu hình, quản lý các beans này. Từ các lớp java bình thường chúng thêm các Meta data để mô tả cho lớp này. Dựa vào meta data này mà Spring IoC có thể tạo chúng thành những beans.

BeanFactory quản lí bean, tạo bean khi client cần. 


## **2 .Tạo dự án Maven**




## **3 .Thêm các thư viện Spring vào Maven**

{% highlight xml linenos %}

<project xmlns="http://maven.apache.org/POM/4.0.0"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <groupId>net.javaguides.spring</groupId>
    <artifactId>spring-ioc-example</artifactId>
    <version>0.0.1-SNAPSHOT</version>
    <url>http://maven.apache.org</url>

    <properties>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    </properties>

    <dependencies>
        <!-- https://mvnrepository.com/artifact/org.springframework/spring-context -->
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-context</artifactId>
            <version>5.1.0.RELEASE</version>
        </dependency>
    </dependencies>
    <build>
        <sourceDirectory>src/main/java</sourceDirectory>
        <plugins>
            <plugin>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>3.5.1</version>
                <configuration>
                    <source>1.8</source>
                    <target>1.8</target>
                </configuration>
            </plugin>
        </plugins>
    </build>
</project>


{% endhighlight %}

## **4 .Cấu hình HelloWorld Spring Bean bằng Java**

{% highlight java linenos %}

package com.levunguyen.spring.ioc;

public class HelloWorld {
    private String message;

    public void setMessage(String message) {
        this.message = message;
    }

    public void getMessage() {
        System.out.println("My Message : " + message);
    }
}
{% endhighlight %}

## **5 .Cấu hình Metadata cho HelloWorld Spring Java**

- Như bài 1 giới thiệu về Spring IOC container ta có thể dùng XML để tạo các bean. 

{% highlight xml linenos %}

<?xml version = "1.0" encoding = "UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xsi:schemaLocation="http://www.springframework.org/schema/beans
   http://www.springframework.org/schema/beans/spring-beans-3.0.xsd">
   
 <bean id="helloWorld" class="com.levunguyen.spring.ioc">
  <property name="message" value="Hello World!" />
 </bean>
</beans>

{% endhighlight %}


## **6 .Tạo Spring Container**

{% highlight java linenos %}

import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;

public class Application {
    public static void main(String[] args) {
        ApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");
    }
}

{% endhighlight %}

## **7 .Lấy đối tượng bean HelloWorld và gọi phương thức**

- Chúng ta sử dụng phương thức getBean để lấy đối tượng bean từ container.

{% highlight java linenos %}

import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;

public class Application {
    public static void main(String[] args) {
        XmlBeanFactory factory = new XmlBeanFactory (new ClassPathResource("applicationContext.xml"));
        HelloWorld obj = (HelloWorld) factory.getBean("helloWorld");
 obj.getMessage();
    }
}

{% endhighlight %}

- Kết quả ta nhận được là text : Hello World

## **8. Demo Video**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **9. Source code**

{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/Bean-Factory" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}

