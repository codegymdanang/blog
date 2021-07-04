---
layout: course-docker
title: Container linking
slug : container-linking
category: devops
tags: [docker]
summery: Docker Linking
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta hiểu về Container linking và cách cài đặt Container linking.

youtubeId: NHYCPeRKnoI
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người hiểu về <b> Container linking </b>. Sử dụng container linking cho phép chúng ta có thể kết nối hai ứng dụng trên các container khác nhau. Ví dụ như anh có ứng dụng Java chạy trên container 1. Mysql chạy trên container 2. Lúc này anh có thể linking container 1 và container 2 lại với nhau để ứng dụng Java có thể gọi xuống database được.

Trong ví dụ hôm nay anh sẽ giới thiệu một ví dụ đơn giản. Anh sẽ có 1 ứng dụng bằng SpringBoot được triển khai trên 1 container. Ứng dụng Spring Boot này sẽ kết nối với MySQL, cái database sẽ được triển khai trên một container khác. Nhiệm vụ của mình là link (kết nối) 2 container khác nhau để ứng dụng Spring Boot có thể connect được với database.

## **1. Cài đặt và chạy MYSQL**

Giả sử chúng ta đã pull MySQL Image về máy của mình và mình sử dụng docker run để start container lên

{% highlight javascript  linenos %}

docker run -p 2012:3306 --name mysqldocker -e MYSQL_ROOT_PASSWORD=123456 -d mysql:5.7.26

{% endhighlight %}

Trong đó các tham số là :

- d : ta chạy mysql ở 1 container khác không cùng với app ở trên. Nó chạy riêng biệt
- p : là port để ta có thể truy cập vào mysql. Ở máy local ta có thể truy cập bằng port 2012. 
Nhưng nếu ở máy khác hoặc một ứng dụng khác thì dùng port 3306
- 5.7.26 : version của mysql

## **2. Cài đặt và chạy Spring Boot**

Trong file properties của spring boot ta cấu hình datasource để connect vào database như sau.

{% highlight javascript  linenos %}

spring.datasource.driver-class-name=com.mysql.jdbc.Driver 
spring.datasource.url=jdbc:mysql://mysqldocker:3306/library 
spring.datasource.username=root 
spring.datasource.password=123456

{% endhighlight %}

Chúng ta thấy datasource url bây giờ trỏ vào là mysqldocker chính là tên của container mysql mà ta đặt ở bước trên.

Sau khi đã thay đổi cấu hình database thì ta dùng docker build để build docker file. Docker file dự án có nội dung như sau

{% highlight javascript  linenos %}

// Alpine Linux with OpenJDK JRE 
FROM openjdk:8-jre-alpine // Cài đặt JDK cho container . Mình cài từ openjdk 
//copy WAR into image 
COPY spring-boot-app-0.0.1-SNAPSHOT.war /app.war //Mình copy file war từ folder dự án và đổi tên thành app.war 
//run application with this command line 
CMD ["/usr/bin/java", "-jar", "-Dspring.profiles.active=default", "/app.war"] // Run command để chạy file jar như bình thường 

{% endhighlight %}

## **3. Kết nối Spring Boot và MYSQL**

Bây giờ là phần quan trọng để kết nối 2 container lại với nhau. Docker sử dụng tham số --link để kết nối container Spring Boot và MySQL như sau

{% highlight javascript  linenos %}

docker run -t --name springboot-mysql-container --link mysqldocker:mysql -p 8087:8080 spring-boot-app 

{% endhighlight %}
 

– name   	: springboot-mysql-container : tên của docker container .

- p 		: 8087:8080 : port 8087 được access từ local container , còn port 8080 sẽ được access từ ngoài. 

– link 		: kết nối container SpringBoot với container mysql. 

- mysql-docker-container : tên của container

- spring-boot-app : tên image mà chúng ta build docker cho SpringBoot.


## **4. Source code**


{:refdef: style="text-align: center;"}
<a href="https://github.com/codegymdanang/CGDN-SpringBoot-Docker" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}










