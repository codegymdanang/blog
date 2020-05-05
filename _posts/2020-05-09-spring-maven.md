---
layout: blog
title: maven là gì ? 
slug : maven 
category: laptrinhspring
tags: [spring]
summery: maven là gì ? 
image: /images/blog/spring.png
description : maven là gì  .học lập trình  ngôn ngữ lập trình lập trình java java cơ bản khóa học lập trình java học ngôn ngữ lập trình java
youtubeId: WNfuVJptPnQ
---

### **1. Giới thiệu nội dung bài viết**

Chào các em ,chủ để hôm nay chúng ta sẽ tìm hiểu về Maven là gì ?
Nội dung mình sẽ giải thích trong bài này sẽ xoay quanh các chủ đề sau đây.

- Maven là gì
- Repository chứa đựng các thư viện
- Cài đặt Maven
- Kết luận

### **2. Maven là gì ?** 

Maven là một tool ta sử dụng chung với các dự án java . Mục đích chính của Maven dùng để quản lý các thư viện được dùng chung với dự án java. 
Ví dụ như mình muốn tích hợp chức năng login của facebook vào ứng dụng của mình, thì mình phải nhúng thư viện  của facebook vào dự án của mình. 
Trong trường hợp này mình sử dụng Maven để lấy thư viện facebook và nhúng vào dự án. Từ đó code của mình viết sẽ gọi được các thư viện của facebook.
Ngoài việc quản lý thư viện và version của thư viện. Thì mình dùng Maven để tự động build dự án của mình , đồng thời mình có thể thực hiện các lệnh maven
để deploy sản phẩm của mình lên các con server khác nhau

### **3. Khai báo dependency trong POM**

Để nhúng một thư viện vào dự án Trong file pom.xml ta sử dụng đoạn mã sau

{% highlight xml  linenos %}
<dependency>
        <groupId>org.slf4j</groupId>
        <artifactId>slf4j-api</artifactId>
        <version>${slf4j.version}</version>
        <type>jar</type>
</dependency>
{% endhighlight %}

{% highlight java linenos %}
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>

  <modules>

    <module>dao</module>
    <module>webservice</module>
    <module>common</module>

    <module>business-service</module>
  </modules>

  <parent>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-parent</artifactId>
    <version>2.1.5.RELEASE</version>
  </parent>

  <groupId>codegymdanang</groupId>
  <artifactId>parent</artifactId>
  <version>1.0-SNAPSHOT</version>
  <packaging>pom</packaging>

  <properties>
    <project.version>${project.version}</project.version>
    <jdkVersion>1.8</jdkVersion>
    <slf4j.version>1.7.2</slf4j.version>
  </properties>
  
  <dependencyManagement>
    <dependencies>
      <dependency>
        <groupId>org.slf4j</groupId>
        <artifactId>slf4j-api</artifactId>
        <version>${slf4j.version}</version>
        <type>jar</type>
      </dependency>
    </dependencies>
  </dependencyManagement>

  <dependencies>
    <dependency>
      <groupId>org.hamcrest</groupId>
      <artifactId>hamcrest-all</artifactId>
      <version>1.3</version>
      <scope>test</scope>
    </dependency>

  </dependencies>

</project>

{% endhighlight %}

### **3. Maven Repository**

Bạn có thắc mắc vì sao ta chỉ khai báo cách dưới đây mà dự án của ta lấy được file slf4j-api và nhúng vào dự án mình không ? 

{% highlight xml linenos %}
<dependency>
        <groupId>org.slf4j</groupId>
        <artifactId>slf4j-api</artifactId>
        <version>${slf4j.version}</version>
        <type>jar</type>
</dependency>
{% endhighlight %}

Thực ra khi ta khai báo ở trên . Maven sẽ chạy lên trang chủ repository của mình . Nơi lưu trữ tất cả gói thư viện . Sau đó nó sẽ lấy cái mình muốn và 
download về máy của mình. 
 
Repository của maven tại đây : https://mvnrepository.com/

Chúng ta chỉ tìm kiếm thư viện mong muốn. Sau đó ta search thì nó sẽ hiện cho chúng ta danh sách các thư viện và thẻ dependency mong muốn.

Ví dụ như mình search từ khoá facebook api để lấy các thư viện facebook về thì mình sẽ nhận được kết quả như sau. Mình chỉ cần copy và dán vào file pom là xong
. Khi ứng dụng mình build bằng maven . Thì nó sẽ lên maven repository và download gói spring-social-facebook.jar về máy của mình và nhúng vô dự án
của mình
 
 
<!-- https://mvnrepository.com/artifact/org.springframework.social/spring-social-facebook -->
<dependency>
    <groupId>org.springframework.social</groupId>
    <artifactId>spring-social-facebook</artifactId>
    <version>2.0.3.RELEASE</version>
</dependency>

Ngoài ra mình có thể hoàn toàn tự build hệ thống maven reposioty ở local cho team mình dùng. Không cần public gói thư viện đó ra cho tất cả mọi người
Vì có những dự án bảo mật thì các goi thư viện mà team mình xây dựng chỉ phục vụ cho team nội bộ không công khai ra ngoài
