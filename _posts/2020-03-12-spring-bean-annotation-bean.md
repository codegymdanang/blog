---
layout: course-spring-core
title: Sử dụng Annotation @Bean trong Spring
slug : su-dung-annotation-bean-trong-spring
category: laptrinhspring
tags: [spring-core]
summery: Bean Annotation
image: /images/blog/spring.png
featureImage: /images/post/javacore/feature_di.png
description : Bài viết trình bày về chủ đề Annotation @Bean để cấu hình cho dự án Spring. Qua những chia sẻ trong bài viết, người đọc sẽ lần lượt được giới thiệu tổng quan về @Bean Annotation và hướng dẫn cách khai báo bean bằng cách sử dụng @Bean trong Spring. Ngoài ra được tìm hiểu về Vòng đời @Bean trong lập trình Spring và được hướng dẫn cách thực hiện để thay đổi tên của một bean. Cùng với đó là những ví dụ minh hoạ kèm theo cho mỗi phần giúp người đọc tham khảo để áp dụng vào thực hành hiệu quả hơn.
youtubeId: znbHcxXKLr0
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào bạn, trong bài viết hôm nay chúng ta sẽ nói cách sử dụng Annotation Bean để cấu hình cho dự án Spring.
 
## **1. Giới thiệu @Bean Annotation**

Trong các bài trước về tạo bean trong XML chúng ta sử dụng thẻ <bean /> để tạo một bean trong Spring IoC. Ngoài cách tạo bằng XML thì chúng ta hoàn toàn có thể tạo bean bằng cách sử dụng Annotation @Bean

## **2. Khai báo bean bằng cách sử dụng @Bean**


- Tạo bean sử dụng Annotation @Bean

{% highlight java linenos %}

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

- Tạo bean bằng xml

{% highlight xml linenos %}

<beans>
        <bean id="customerService" class="com.companyname.projectname.CustomerService"/>
        <bean id="orderService" class="com.companyname.projectname.OrderService"/>
</beans>

{% endhighlight %}

## **3. Vòng đời @Bean**

Annotation @Bean cũng hỗ trợ chức năng Initialization và Destruction giống như trong Spring XML là init-method và destroy-method.
<br>
{% highlight java linenos %}

public class Foo {
        public void init() {
                // initialization logic via xml config
        }
}

public class Bar {
        public void cleanup() {
                // destruction logic via xml config
        }
}

@Configuration
public class AppConfig {

        @Bean(initMethod = "init")
        public Foo foo() {
                return new Foo();
        }

        @Bean(destroyMethod = "cleanup")
        public Bar bar() {
                return new Bar();
        }

}
{% endhighlight %}

## **4.Thay đổi tên của bean**

Chúng ta sử dụng thuộc tính name để đặt tên cho bean.
<br>
{% highlight java linenos %}
@Configuration
public class Application {

 @Bean(name = "cService")
 public CustomerService customerService() {
  return new CustomerService();
 }
 
 @Bean(name = "oService")
 public OrderService orderService() {
  return new OrderService();
 }
}
{% endhighlight %}

## **7. Video Demo**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}


## **6. Source code**

{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/Bean-Annotation" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}













