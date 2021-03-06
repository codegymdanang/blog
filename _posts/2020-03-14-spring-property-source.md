---
layout: course-spring-core
title: Sử dụng Annotation PropertySource trong Spring
slug : su-dung-annotation-property-source-trong-spring
category: laptrinhspring
tags: [spring-core]
summery: PropertySource Annotation
image: /images/blog/spring.png
featureImage: /images/post/javacore/feature_di.png
description : Với những chia sẻ trong bài viết, người đọc sẽ nắm được tổng quan về @PropertySource Annotation trong lập trình Spring. Cùng với đó, với những ví dụ minh hoạ được đưa ra trong bài viết sẽ hướng dẫn người đọc cách thực hiện để load nhiều file configure trong Spring và cách thức để sử dụng @Value khi lập trình Spring.
youtubeId: uIzp7XPH8qQ
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào bạn, trong bài viết hôm nay chúng ta sẽ nói cách sử dụng Annotation PropertySource để cấu hình cho dự án Spring.
 

## **1. Giới thiệu @PropertySource Annotation**

Chúng ta sử dụng Annotation PropertySource để đọc các giá trị từ file và gán vào các thuộc tính trong Bean. Anh lấy ví dụ như trong dự án chúng ta thường có 1 file cấu hình database trong file này chúng ta điền tham số của database như username và password. Sau đó trong Class Java bean chúng ta chỉ cần lấy giá trị lưu đó từ file ra thông qua Annotation @Value hoặc @Eviroment. 

Trong thực tế chúng ta không điền thẳng giá trị user name và password trực tiếp trong code mà phải tạo 1 file riêng chứa các thông tin này. Sau đó dùng @PropertySource để load thông tin ra.

- Giả sử ta có 1 file tên config.properties


{% highlight java linenos %}
jdbc.driver = com.mysql.driver
jdbc.url    = http://localhost:3306/example
jdbc.user   = test
jdbc.password = test

{% endhighlight %}

- Chúng ta sẽ dùng @PropertySource để load file config.properties. Sau đó sử dụng lấy các giá trị.

- Chúng ta khai báo 1 đối tượng Environment. Nếu muốn lấy giá trị jdbc driver nào ta chỉ cần dùng phương thức env.getProperty("jdbc.driver")

<br>
{% highlight java linenos %}

import org.springframework.beans.factory.InitializingBean;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.context.annotation.Configuration;
import org.springframework.context.annotation.PropertySource;
import org.springframework.core.env.Environment;

@Configuration
@PropertySource("classpath:config.properties")
public class ProperySourceDemo implements InitializingBean {

 @Autowired
 Environment env;

 @Override
 public void afterPropertiesSet() throws Exception {
  setDatabaseConfig();
 }

 private void setDatabaseConfig() {
  DataSourceConfig config = new DataSourceConfig();
  config.setDriver(env.getProperty("jdbc.driver"));
  config.setUrl(env.getProperty("jdbc.url"));
  config.setUsername(env.getProperty("jdbc.username"));
  config.setPassword(env.getProperty("jdbc.password"));
  System.out.println(config.toString());
 }
}

{% endhighlight %}

## **2. Load nhiều file configure**

Chúng ta có thể load nhiều file properties cùng một lúc nếu dự án có nhiều file properties.
<br>
{% highlight java linenos %}

 @Configuration
 @PropertySources({
  @PropertySource("classpath:config.properties"),
  @PropertySource("classpath:db.properties")
 })
 public class AppConfig {
  //...
 }

{% endhighlight %}

## **3. Sử dụng @Value**

Ngoài cách sử dụng đối tượng Environment, ta có thể sử dụng @Value để lấy giá trị trong file properties. Cách này thì anh hay dùng.

{% highlight java linenos %}

@Configuration
@PropertySource("classpath:config.properties")
public class ProperySourceDemo implements InitializingBean {

 private static final Logger LOGGER = LoggerFactory.getLogger(ProperySourceDemo.class);

 @Value("${jdbc.driver}")
 private String driver;

 @Value("${jdbc.url}")
 private String url;

 @Value("${jdbc.username}")
 private String username;

 @Value("${jdbc.password}")
 private String password;

 @Autowired
 Environment env;

 @Override
 public void afterPropertiesSet() throws Exception {
  LOGGER.info(driver);
  LOGGER.info(url);
  LOGGER.info(password);
  LOGGER.info(username);
  setDatabaseConfig();
 }

 private void setDatabaseConfig() {
  DataSourceConfig config = new DataSourceConfig();
  config.setDriver(env.getProperty("jdbc.driver"));
  config.setUrl(env.getProperty("jdbc.url"));
  config.setUsername(env.getProperty("jdbc.username"));
  config.setPassword(env.getProperty("jdbc.password"));
  System.out.println(config.toString());
 }
}


{% endhighlight %}

## **4. Video Demo**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}


## **5. Source code**

{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/Property-Source-Annotation" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}












