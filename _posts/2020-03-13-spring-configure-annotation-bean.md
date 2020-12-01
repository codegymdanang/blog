---
layout: course-spring-core
title: Sử dụng Annotation Configure trong Spring
slug : su-dung-annotation-configure-trong-spring
category: laptrinhspring
tags: [spring-core]
summery: Configure Annotation
image: /images/blog/spring.png
featureImage: /images/post/javacore/feature_di.png
description : Qua những chia sẻ trong bài viết người đọc hiểu được tổng quan về @Configure Annotation, một thành phần trong Spring Core Framework. Bên cạnh đó biết được khi nào nên dùng annotation @Configuration trong lập trình Spring. Trong những chia sẻ tiếp theo của bài viết sẽ hướng dẫn cách để khai báo @Configure Annotation sử dụng trong lập trình Spring như thế nào để đạt được hiệu quả. Trong bài viết cũng có chia sẻ kèm theo các ví dụ minh hoạ cú pháp và cách thực hiện.
youtubeId: 0n8_2yG5F7I
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào bạn, trong bài viết hôm nay chúng ta sẽ nói cách sử dụng Annotation Configure để cấu hình cho dự án Spring.
 
## **1. Giới thiệu @Configure Annotation**

Spring @Configuration là một thành phần trong Spring Core Framework. @Configuration Annotation chỉ ra rằng trong Class đó có @Bean. Vì vậy khi Spring IoC quét qua các Class mà có Annotation là @Configuration nó sẽ hiểu trong Class đó có khai báo một số bean và vào đó tạo các bean.

Thường những cấu hình file cấu hình dự án mình sẽ dùng Annotation @Configuration để đánh dấu cho Spring IoC biết.

## **2. Khai báo @Configure Annotation**

- Chúng ta sử dụng Annotation @Configuration để đánh dấu là Class đó là Class dùng để cấu hình và có các bean cấu hình trong đó.

{% highlight java linenos %}

import org.springframework.boot.SpringApplication;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

import com.companyname.projectname.customer.CustomerService;
import com.companyname.projectname.order.OrderService;

@Configuration
public class Application {

     @Bean
     public CustomerService customerService() {
         return new CustomerService();
     }
 
     @Bean
     public OrderService orderService() {
         return new OrderService();
     }
}

{% endhighlight %}

- Class Application trên được khai báo bằng Java. Nếu chuyển sang XML thì có dạng như sau

{% highlight java linenos %}

<beans>
        <bean id="customerService" class="com.companyname.projectname.CustomerService"/>
        <bean id="orderService" class="com.companyname.projectname.OrderService"/>
</beans>
{% endhighlight %}








