---
layout: course-spring-core
title: Nhúng Dependency Injection bằng Constructor trong Spring
slug : nhung-dependency-injection-bang-constructor-trong-spring
category: laptrinhspring
tags: [spring-core]
summery: Nhúng DI bằng Constructor 
image: /images/blog/spring.png
featureImage: /images/post/javacore/feature_di.png
description : Bài viết giới thiệu về cách nhúng DI, Dependency Injection bằng Constructor trong Spring. Cụ thể trong những chia sẻ của bài viết sẽ trình bày về cơ chế nhúng bean phụ thuộc thông qua hàm khởi tạo (Constructor) của đối tượng. Bao gồm hướng dẫn cách sử dụng Maven Pom, Email Service,  Client Service và Testing trong lập trình Spring. Ở mỗi phần bài viết chia sẻ kèm theo những ví dụ hướng dẫn cú pháp thực hiện sẽ giúp người đọc hiểu được và áp dụng được thao tác nhúng DI bằng Constructor trong lập trình Spring.
youtubeId: nOIBogYy6Gg
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào bạn, chắc hẳn bạn cảm thấy khó hiểu về <b>Nhúng DI bằng Constructor</b> là gì đúng không?


<br>
## **1 .Dependency Injection thông qua cơ chế Constructor**

Ngoài cơ chế  DI thông qua setter như bài post trước, Spring IOC container cũng hỗ trợ cơ chế nhúng bean phụ thuộc thông qua hàm khởi tạo (Constructor) của đối tượng.


<br>
## **2 .Maven Pom**

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
## **3 .Email Service**

- Chúng ta sử dụng annotation @Service để khi IoC container nó quét qua thì nó sẽ tạo đối tượng (bean) EmailService trong container để quản lý.

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
## **4 .Client Service**

- Chúng ta thêm annotation @Autowire phía trên của hàm khởi tạo ClientService. Khi Spring IOC quét qua ClientService nó sẽ nhúng EmailService bean có sẵn trong container của nó vào cho ClientService dùng.

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


## **5 .Testing**

- Chúng ta sẽ tạo file cấu hình tên là AppConfiguration và annotation là @Configure. File này có nhiệm vụ tương tự như file xml confire ở bài trước. 

- Có một annotation quan trọng là @ComponentScan là ta chỉ ra thư mục mà ta đặt file EmailService và ClientService ở đâu để Spring IOC sẽ chui vào đó và quét 2 class này để tạo bean và nhúng bean.

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

## **6. Demo Video**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **7. Source code**

{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/DI-By-Contructor" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}
