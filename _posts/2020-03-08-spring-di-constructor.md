---
layout: course-spring-core
title: Nhúng Dependency Injection bằng Constructor
slug : dependency-injection-bang-constructor
category: laptrinhspring
tags: [spring-core]
summery: Nhúng DI bằng Constructor 
image: /images/blog/spring.png
featureImage: /images/post/javacore/feature_di.png
description : Sử dụng nhúng DI bằng Constructor trong lập trình Spring. Hiểu được nhúng DI bằng Constructor là gì. Hướng dẫn sử dụng nhúng DI bằng Constructor trong lập trình Spring.
youtubeId: 0n8_2yG5F7I
---

# **Giới thiệu nội dung bài viết**

Chào ban , chắc hẳn bạn cảm thấy khó hiểu về <b>Nhúng DI bằng Constructor</b>  gì đúng không?


<br>
# **1 .Dependency Injection thông qua cơ chế Constructor**

Ngoài cơ chế  DI thông qua setter như bài post trước, Spring IOC container cũng hỗ trợ cơ chế nhúng bean phụ thuộc thông qua hàm khởi tạo (Constructor) của đối tượng.


<br>
# **2 .Maven Pom**

- Ví dụ mình có file maven pom như sau cho dự án.

<br>

{% highlight java linenos %}

<project
    xmlns="http://maven.apache.org/POM/4.0.0"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <groupId>com.javadevsguide.springframework</groupId>
    <artifactId>spring-dependency-injection</artifactId>
    <version>0.0.1-SNAPSHOT</version>
    <dependencies>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-context</artifactId>
            <version>5.0.0.RELEASE</version>
        </dependency>
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
            <version>4.8.1</version>
            <scope>test</scope>
        </dependency>
    </dependencies>
</project>



{% endhighlight %}

<br>
# **3 .Email Service**

- Chúng ta sử dụng annotaion @Service để khi IoC container nó quyét qua thì nó sẽ tạo đối tượng (bean) EmailService trong container để quản lý.

{% highlight java linenos %}

package com.levunguyen.di;

@Service("EmailService")
public class EmailService implements MessageService{
    public void sendMsg(String message) {
        System.out.println(message);
    }
}

{% endhighlight %}


<br>
# **4 .Client Service**

- Chúng ta thêm annotaion @Autowire phía trên của hàm khởi tại ClientService. Khi Spring IOC quyét qua ClientService nó sẽ nhúng EmailService bean có sẳn trong container của nó vào cho ClientService dùng

{% highlight java linenos %}

package com.levunguyen.di;

@Component
public class ClientService {
    private EmailService emailService;

    @Autowired 
    public ClientService(EmailService messageService) {
        super();
        this.messageService = messageService;
    }

    public void processMsg(String message) {
        messageService.sendMsg(message);
    }


}

{% endhighlight %}


# **5 .Testing**

- Chúng ta sẽ tạo file cấu hình tên là AppConfiguration và annotaion là @Configure. File này có nhiệm vụ tương tự như file xml confire ở bài trước. 

- Có một annotation quan trọng là @ComponentScan là ta chỉ ra thư mục mà ta đặt file EmailService và ClientService ở đâu để Spring IOC sẽ chui vào đó và quyét 2 class này để tạo bean và nhúng bean.

{% highlight java linenos %}

@Configuration
@ComponentScan("com.levunguyen.di")
public class AppConfiguration {

}
{% endhighlight %}


{% highlight java linenos %}

public class TestApplication {
    public static void main(String[] args) {
        ApplicationContext applicationContext = new AnnotationConfigApplicationContext(AppConfiguration.class);
        ClientService  client = applicationContext.getBean(ClientService.class);
        client.processMsg(" sending email ");
    }
}

{% endhighlight %}
