---
layout: course-relationaldatabase
title: Sử dụng Stored Procedure trong database
slug : su-dung-stored-procedure-trong-database
category: database
tags: [database]
summery: Stored Procedure    
image: /images/blog/database.png
description : Những chia sẻ trong bài viết giúp hiểu được thuật ngữ Stored Procedure trong Database. Người đọc cũng sẽ được hướng dẫn cú pháp để tạo Stored Procedure trong Database thông qua các ví dụ cụ thể được đưa ra trong bài. Ngoài ra, bài viết cũng trình bày về Stored Procedure với tham số và Stored Procedure với nhiều tham số sử dụng trong Database. Từ đó áp dụng được Stored Procedure trong lập trình Database hiệu quả hơn.
youtubeId: ReeqgvOL4-w
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay chúng ta sẽ nói về chủ đề Stored Procedure trong Database là gì nhé?

## **1. Stored Procedure**

Cũng giống như lập trình vậy, chúng ta có thể tạo các phương thức các hàm trong SQL khai báo tên hàm các đối số. Sau đó chúng ta có thể gọi hàm và nhận lấy giá trị.

- Cú pháp tạo Stored Procedure

<br>
{% highlight sql linenos %}

CREATE PROCEDURE procedure_name
BEGIN
sql_statement
END;

{% endhighlight %}

- Chạy hay thực thi một Stored Procedure

<br>
{% highlight sql linenos %}

CALL procedure_name; 

{% endhighlight %}

- Ví dụ ta có bảng dữ liệu sau

{:class="table table-bordered"}
|  CustomerName  					|  ContactName	    |   Address	  					| 	City		|	PostalCode	|	Country		|
|---	            				|---	            |---	     					|---			|---			|---			|
|Alfreds Futterkiste				|Maria Anders		|Obere Str. 57					|	Berlin		|	12209		|	Germany		|		
|Ana Trujillo Emparedados y helados	|Ana Trujillo		|Avda. de la Constitución 2222	|	México D.F.	|	05021		|	Mexico		|
|Antonio Moreno Taquería			|Antonio Moreno		|Mataderos 2312					|	México D.F.	|	05023		|	Mexico		|
|Around the Horn					|Thomas Hardy		|120 Hanover Sq.				|	London		|	WA1 1DP		|	UK			|
|Berglunds snabbköp					|Christina Berglund	|Berguvsvägen 8					|	Luleå		|	S-958 22	|	Sweden		|


- Chúng ta tạo một Stored Procedure có tên là SelectAllCustomers

<br>
{% highlight sql linenos %}

CREATE PROCEDURE SelectAllCustomers
BEGIN
SELECT * FROM Customers
END;
{% endhighlight %}

- Chúng ta thực thi

<br>
{% highlight sql linenos %}

CALL SelectAllCustomers;
{% endhighlight %}

## **2. Stored Procedure với tham số**

Giống như phương thức (hàm) trong lập trình, phương thức có tham số thì Stored Procedure cũng có tham số.

- Ví dụ tạo một Stored Procedure có tham số city.

<br>
{% highlight sql linenos %}

CREATE PROCEDURE SelectAllCustomers @City nvarchar(30)
BEGIN
SELECT * FROM Customers WHERE City = @City
END;
{% endhighlight %}

- Chúng ta thực thi Stored Procedure và truyền tham số city là London vào.


<br>
{% highlight sql linenos %}

CALL SelectAllCustomers @City = 'London'; 

{% endhighlight %}

## **3. Stored Procedure với nhiều tham số**

<br>
{% highlight sql linenos %}
CREATE PROCEDURE SelectAllCustomers @City nvarchar(30), @PostalCode nvarchar(10)
BEGIN
SELECT * FROM Customers WHERE City = @City AND PostalCode = @PostalCode
END;
{% endhighlight %}

<br>
{% highlight sql linenos %}
CALL SelectAllCustomers @City = 'London', @PostalCode = 'WA1 1DP'; 
{% endhighlight %}

## **4. Demo Video**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **5. Source Code**

{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/Database-Mysql" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}


