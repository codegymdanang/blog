---
layout: course-spring-core
title: Nhúng Dependency Injection bằng phương thức Setter trong Spring
slug : nhung-dependency-injection-bang-phuong-thuc-setter-trong-spring
category: laptrinhspring
tags: [spring-core]
summery: Nhúng DI bằng Setter 
image: /images/blog/spring.png
featureImage: /images/post/javacore/feature_di.png
description : Nhúng DI, Dependency Injection bằng Setter trong Spring là gì? Những chia sẻ trong bài viết sẽ giúp hiểu được khái niệm này. Đồng thời qua bài viết người đọc sẽ được hướng dẫn cách làm đề nhúng Dependency Injection, DI thông qua cơ chế Setter. Bao gồm cách sử dụng Maven Pom, Email Service, Client Service và Testing trong lập trình Spring. Bài viết kèm theo các ví dụ hướng dẫn cụ thể cú pháp thực hiện của mỗi phương thức Setter để người đọc tham khảo thêm.
youtubeId: Cdc8QPX1bzA
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào bạn, chắc hẳn bạn cảm thấy khó hiểu về <b>Nhúng DI bằng Setter</b> là gì đúng không?


<br>
## **1 .Dependency Injection thông qua cơ chế Setter**

Trong cơ chế DI thông qua setter, Spring IOC container sẽ nhúng bean phụ thuộc thông qua method set của đối tượng.

Anh sẽ giải thích thông qua ví dụ sau. Giả sử chúng ta viết chương trình gửi email. Ta sẽ có 1 file service là gửi mail là EmailService. Ta sẽ nhúng đối tượng EmailService vào lớp Client thông qua phương thức setter như sau.

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

- Chúng ta sử dụng @Component để khi Ioc container quét qua thì nó tạo đối tượng ClientService.
- Trong ClientService ta có khai báo đối tượng emailService nhưng tại thời điểm này nó là null. 
- Để Spring IoC có thể nhúng đối tượng email service ở bước 3 vào biến emailService thì ta có
hàm setMessageService(MessageService emailService) và được thêm annotation là @Autowire. 
Điều này có nghĩa là khi Spring IOC quét qua lớp ClientService nó thấy trong ClientService có annotation @Autowire cho EmailService thì nó hiểu là sẽ nhúng đối tượng EmailService có trong container của nó vào cho đối tượng ClientService.
- Nó nhúng vào dựa vào cơ chế tên giống nhau. Như các em thấy ở bước 3 nó sẽ tạo ra bean có tên là EmailService. Trong class Client Service cũng có EmailService nên nó sẽ lấy đối tượng có tên là EmailService trong container của nó mà nhúng vào cho lớp EmailService thông qua hàm set.

{% highlight java linenos %}

package com.levunguyen.di;

@Component
public class ClientService {
    private EmailService emailService;

    @Autowired
    public void setMessageService(MessageService emailService) {
        this.emailService = emailService;
    }

    public void processMsg(String message) {
        emailService.sendMsg(message);
    }
}

{% endhighlight %}


## **5 .Testing**

- Chúng ta sẽ tạo file cấu hình tên là AppConfiguration và annotation là @Configure. File này có nhiệm vụ tương tự như file xml config ở bài trước. 

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
<a href="https://github.com/levunguyen/DI-By-Setter" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}
