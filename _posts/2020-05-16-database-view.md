---
layout: course-relationaldatabase
title: Sử dụng View trong database
slug : su-dung-view-trong-database
category: database
tags: [database]
summery: View    
image: /images/blog/database.png
description : Trước khi đi vào hướng dẫn sử dụng View trong Database cụ thể như thế nào gồm cách thao tác để tạo View, Update View và xoá View trong Database. Tác giả sẽ giới thiệu cho người đọc hiểu được khái niệm View trong Database là gì. Sau đó sẽ hướng dẫn cú pháp thực hiện với View trong lập trình Database thông qua các ví dụ minh hoạ trong bài.
youtubeId: QZHScccM500
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay chúng ta sẽ nói về chủ đề View trong Database là gì nhé?

## **1. Tạo View**

View là một dạng Table giả hay Table ảo, không phải là Table thật. Mình thường tạo ra các Table ảo để truy vấn dữ liệu cho nhanh.

Thông thường khi câu truy vấn lặp đi lặp lại nhiều lần ta thường tạo một View cho câu truy vấn đó.

- Cú pháp tạo View

<br>
{% highlight sql linenos %}

CREATE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition; 

{% endhighlight %}

- Ví dụ tạo View dưới đây

<br>
{% highlight sql linenos %}

CREATE VIEW [Brazil Customers] AS
SELECT CustomerName, ContactName
FROM Customers
WHERE Country = 'Brazil'; 

{% endhighlight %}

- Chúng ta thực thi câu lệnh để chạy View

<br>
{% highlight sql linenos %}

SELECT * FROM [Brazil Customers]; 

{% endhighlight %}


- Ví dụ tạo View để xem sản phẩm và giá trong bảng sản phẩm

<br>
{% highlight sql linenos %}

CREATE VIEW [Products Above Average Price] AS
SELECT ProductName, Price
FROM Products
WHERE Price > (SELECT AVG(Price) FROM Products); 

{% endhighlight %}


## **2. Update View**

- Cú pháp

<br>
{% highlight sql linenos %}

CREATE OR REPLACE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition; 
{% endhighlight %}

- Ví dụ

<br>
{% highlight sql linenos %}

CREATE OR REPLACE VIEW [Brazil Customers] AS
SELECT CustomerName, ContactName, City
FROM Customers
WHERE Country = 'Brazil';

{% endhighlight %}

## **3. Xoá View**

- Cú pháp

<br>
{% highlight sql linenos %}

DROP VIEW view_name; 

{% endhighlight %}

- Ví dụ

<br>
{% highlight sql linenos %}

DROP VIEW [Brazil Customers]; 

{% endhighlight %}

## **4. Demo Video**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **5. Source Code**

{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/Database-Mysql" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}
