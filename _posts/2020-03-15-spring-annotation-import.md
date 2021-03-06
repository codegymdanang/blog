---
layout: course-spring-core
title: Sử dụng Annotation Import trong Spring
slug : su-dung-spring-annotation-import-trong-spring
category: laptrinhspring
tags: [spring-core]
summery: Import Annotation
image: /images/blog/spring.png
featureImage: /images/post/javacore/feature_di.png
description : Nhằm giúp người đọc hiểu và áp dụng được Annotation Import trong lập trình Spring. Bài viết lần lượt giới thiệu để bạn hiểu được @Import Annotation trong Spring là gì? Khi nào thì được sử dụng trong Spring? Đồng thời trong những chia sẻ tiếp theo của bài viết, người đọc sẽ được hướng dẫn để sử dụng import bằng XML và sử dụng import bằng Annotation khi lập trình Spring như thế nào cho hiệu quả.
youtubeId: NgTrEKBfTjU
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào bạn, trong bài viết hôm nay chúng ta sẽ nói cách sử dụng Annotation Import để cấu hình cho dự án Spring.
 

## **1. Giới thiệu @Import Annotation**

Chúng ta sử dụng Annotation Import khi muốn có một hoặc nhiều Class cấu hình sẽ được import (nhúng vào) Class.

## **2. Sử dụng import bằng XML**

Ví dụ ta có file xml sau là web.xml. Trong file web.xml này ta muốn nhúng các file xml khác là spring-common.xml, spring-dao.xml và spring-beans. 

Thì ta dùng thẻ <import>

{% highlight java linenos %}

<beans xmlns="http://www.springframework.org/schema/beans"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xsi:schemaLocation="http://www.springframework.org/schema/beans
 http://www.springframework.org/schema/beans/spring-beans.xsd">

 <import resource="common/spring-common.xml"/>
        <import resource="dao/spring-dao.xml"/>
        <import resource="beans/spring-beans.xml"/>
 
</beans>

{% endhighlight %}


## **3. Sử dụng import bằng annotation**

{% highlight java linenos %}

@Configuration
public class Common {

    @Bean
    public Share share() {
        return new Share();
    }
}

@Configuration
public class Dao {

    @Bean
    public Connection connect() {
        return new Connection();
    }
}


@Configuration
@Import(value = {Common.class,Dao.class } )
public class Web {

    @Bean
    public Page page() {
        return new Page();
    }
}

{% endhighlight %}

## **4. Video Demo**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **5. Source code**

{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/Import-Annotation" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}

