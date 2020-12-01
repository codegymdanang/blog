---
layout: course-spring-core
title: Phạm vi hoạt động của Bean
slug : pham-vi-hoat-dong-cua-bean
category: laptrinhspring
tags: [spring-core]
summery: Phạm vi hoạt động của bean 
image: /images/blog/spring.png
featureImage: /images/post/javacore/feature_di.png
description : Bài viết trình bày về chủ đề Bean Scope hay còn gọi là phạm vi hoạt động của Bean trong Spring. Người đọc sẽ được lần lượt tìm hiểu về các Scope gồm Singleton Scope, Prototype Scope, Request Session Application và WebSocket Scope, Request Scope, Session Scope và Application Scope trong lập trình Spring. Trong mỗi loại Scope, bài viết chia sẻ kèm theo những hình ảnh ví dụ minh hoạ cú pháp thực hiện giúp tham khảo và áp dụng được vào thực hành hiệu quả hơn.
youtubeId: 0n8_2yG5F7I
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào bạn, chắc hẳn bạn cảm thấy khó hiểu về <b>Bean Scope (Phạm vi hoạt động của Bean) </b> là gì đúng không? Trong bài viết hôm nay chúng ta sẽ trình bày về 6 phạm vi (Scope) của một Bean được tạo ra trong container.

Có bao giờ bạn tự hỏi các Beans (đối tượng) được tạo ra như thế nào và khi nào nó được tạo ra trong container không? Các Scope dưới đây sẽ giúp giải đáp thắc mắc này của bạn.


## **1 .Singleton Scope**

- Khi một Bean được khai báo là Singleton thì Bean đó là duy nhất trong Spring IoC và được share cho tất cả các Beans khác nếu cần sử dụng nó. Như vậy ta chỉ cần tạo một Bean duy nhất và sử dụng cho toàn hệ thống. Anh lấy ví dụ mình có 1 Bean về connect database thì mình chỉ tạo một lần duy nhất. Các Bean khác muốn dùng thì nhúng vào chứ không phải mình có 10 Beans khác nhau dùng Bean Connect Database thì mình tạo 10 Bean Database trong Spring IoC.

- Scope mặc định khi một Bean được tạo ra là Singleton.

- Định nghĩa Scope Singletion bằng XML.


{% highlight xml linenos %}

<bean id="accountService" class="com.foo.DefaultAccountService"/>

<!-- the following is equivalent, though redundant (singleton scope is the default) -->
<bean id="accountService" class="com.foo.DefaultAccountService" scope="singleton"/>

{% endhighlight %}

- Định nghĩa Scope Singleton bằng Java base.

{% highlight java linenos %}

@Configuration
public class AppConfiguration {

 @Bean
 @Scope("singleton") // default scope 
 public UserService userService(){
  return new UserService();
 }
}

{% endhighlight %}

## **2 .Prototype Scope**

Khác với Singleton Scope, Bean (đối tượng) sẽ được tạo ra mới mỗi khi có một yêu cầu tạo Bean. Như vậy mỗi lần gọi tới Bean mà có Scope là Prototype thì nó sẽ tạo ra một đối tượng (Bean) trong Spring IoC container.

- Định nghĩa Scope Singletion bằng XML.


{% highlight xml linenos %}

<bean id="accountService" class="com.foo.DefaultAccountService" scope="prototype"/>

{% endhighlight %}

- Định nghĩa Scope Singleton bằng Java base.

{% highlight java linenos %}

@Configuration
public class AppConfiguration {

 @Bean
 @Scope("prototype")
 public UserService userService(){
  return new UserService();
 }
}

{% endhighlight %}

## **3 .Request Session Application và WebSocket Scope**

Những Scope như Request, Session, Application và Websocket thì chỉ có tồn tại ở những ứng dụng là Web Application. Nếu ta sử dụng ở những ứng dụng Spring độc lập thì sẽ nhận được thông báo lỗi IllegalExection unknow bean scope vì ứng dụng này không phải là ứng dụng web nên không có Scope nêu trên.

Để sử dụng được các Scope trên thì chúng ta phải Configure (cấu hình) dự án web thêm một vài thông số như thêm SpringDispatchServlet vào file cấu hình trong file web.xml trước khi sử dụng các Scope trên.

{% highlight xml linenos %}

<web-app>
    ...
    <filter>
        <filter-name>requestContextFilter</filter-name>
        <filter-class>org.springframework.web.filter.RequestContextFilter</filter-class>
    </filter>
    <filter-mapping>
        <filter-name>requestContextFilter</filter-name>
        <url-pattern>/*</url-pattern>
    </filter-mapping>
    ...
</web-app>

{% endhighlight %}


## **4 .Request Scope**

- Cấu hình Request Scope cho XML.

{% highlight xml linenos %}

<bean id="loginAction" class="com.foo.LoginAction" scope="request"/>

{% endhighlight %}

- Cấu hình Request Scope cho Java.

{% highlight java linenos %}

@RequestScope
@Component
public class LoginAction {
    // ...
}

{% endhighlight %}

- Spring Container sẽ tạo bean (đối tượng) LoginAction mới khi có một request (yêu cầu) từ người dùng. Sau khi Request (yêu cầu) xử lý xong thì Bean sẽ bị xoá đi.


## **5 .Session Scope**

Scope Session sẽ tồn tại chừng nào Sesion ở HTTP. Nó sẽ bị xoá đi khỏi Spring IoC khi Session ở Web bị xoá hoặc hết hiệu lực.

{% highlight xml linenos %}

<bean id="loginAction" class="com.foo.LoginAction" scope="session"/>

{% endhighlight %}

- Cấu hình Request Scope cho Java

{% highlight java linenos %}

@SessionScope
@Component
public class UserPreferences {
    // ...
}

{% endhighlight %}

## **6 .Application Scope**

Application Scope được tạo một lần cho toàn bộ ứng dụng Web Application. Application Scope được chứa đựng như một ServletContext, nó cũng gần tương tự như Singleton Scope nhưng nó là Singleton cho từng ServeletContext.

{% highlight xml linenos %}

<bean id="appPreferences" class="com.foo.AppPreferences" scope="application"/>

{% endhighlight %}

- Cấu hình Request Scope cho Java

{% highlight java linenos %}

@ApplicationScope
@Component
public class AppPreferences {
    // ...
}

{% endhighlight %}




