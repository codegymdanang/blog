---
layout: course-spring-core
title: Tạo dự án bằng gradle trong Spring
slug : tao-du-an-spring-bang-gradle
category: laptrinhspring
tags: [spring-core]
summery: Tạo dự án bằng Gradle 
image: /images/blog/spring.png
featureImage: /images/post/javacore/feature_di.png
description : Bài viết hướng dẫn cách sử dụng Gradle để tạo dự án trong Spring. Trước hết bài viết giúp hiểu được thuật ngữ Gradle trong Spring là gì? Khi nào sử dụng? Giống và khác nhau giữa Gradle và Maven trong Spring là gì? Ở những chia sẻ tiếp theo bài viết trình bày về cách khai báo dependency trong Gradle của ngôn ngữ lập trình Spring. Ngoài ra bài viết có kèm theo một video hướng dẫn thông qua những ví dụ code demo giúp bạn tham khảo để áp dụng được công cụ Gradle vào làm việc với các dự án lập trình.
youtubeId: dzBSaNL40yk
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, chủ đề hôm nay chúng ta sẽ tìm hiểu về <b>Gradle</b> trong Spring.

<br>
## **1. Gradle là gì ?**

Gradle là tool dùng để build các dự án Java. Cũng tương tự như Maven chúng ta sử dụng gradle để quản lý thư viện và build dự án. Hiện nay chúng ta có thể dùng Gradle để build các dự án về web, mobile.

## **2. Khai báo dependency trong Gradle**

Để nhúng một thư viện vào dự án thì trong file build.gradle ta sử dụng đoạn mã sau:

{% highlight java  linenos %}
apply plugin: 'java'
apply plugin: 'eclipse'
apply plugin: 'application'

mainClassName = 'hello.HelloWorld'

// tag::repositories[]
repositories {
    mavenCentral()
}
// end::repositories[]

// tag::jar[]
jar {
    baseName = 'gs-gradle'
    version =  '0.1.0'
}
// end::jar[]

// tag::dependencies[]
sourceCompatibility = 1.8
targetCompatibility = 1.8

dependencies {
    compile "joda-time:joda-time:2.2"
    testCompile "junit:junit:4.12"
}
{% endhighlight %}

Khác với Maven nó sử dụng XML để khai báo các dependency. Ở gradle chúng ta khai báo dạng như định dạng Json. Các thư viện sử dụng trong dự án được bỏ vào thẻ dependencies. 

<br>
## **4. Video Demo**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **5. Source code**

{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/Gradle" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}
