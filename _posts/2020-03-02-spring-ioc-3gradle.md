---
layout: course-spring-core
title: Tạo dự án bằng gradle trong Spring
slug : tao-du-an-spring-bang-gradle
category: laptrinhspring
tags: [spring-core]
summery: Tạo dự án bằng Gradle 
image: /images/blog/spring.png
featureImage: /images/post/javacore/feature_di.png
description : Hướng dẫn tạo dự án Spring bằng gradle. Demo cách tạo dự án spring bằng gradle trong lập trình spring
youtubeId: dzBSaNL40yk
---

{% include toc.html %}

# **Giới thiệu nội dung bài viết**

Chào các em,chủ để hôm nay chúng ta sẽ tìm hiểu về <b>Gradle</b> là gì ?

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

Khác với Maven nó sử dụng XML để khai báo các dependency. Ở gradle chúng ta khai báo dạng như định dạng Json. Các thư viện sử dụng trong dự án được bỏ vào thẻ dependecies 

<br>
## **3. Và bây giờ, hãy cùng xem code demo ở bên dưới để hiểu rõ hơn nhé**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}
