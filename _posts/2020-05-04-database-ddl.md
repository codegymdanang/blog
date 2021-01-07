---
layout: course-relationaldatabase
title: Các câu lệnh cấu trúc DDL trong database
slug : cac-cau-lenh-cau-truc-ddl-trong-database
category: database
tags: [database]
summery: Câu lệnh DDL    
image: /images/blog/database.png
description : Người đọc được tìm hiểu về chủ đề các câu lệnh cấu trúc DDL trong Database. Bài viết lần lượt trình bày theo các phần từ giới thiệu tổng quan các câu lệnh DLL, cho đến hướng dẫn sử dụng các câu lệnh DLL để tạo Database, xoá Database, tạo bảng, xoá bảng, xoá hết dữ liệu trong bảng và thao tác để chỉnh sửa lại bảng trong lập trình Database. Trong phần cuối, tác giả cung cấp một video code demo giúp người đọc hiểu rõ hơn về các câu lệnh cấu trúc DLL trong Database.
youtubeId: w7GoXo5PIvI
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay chúng ta sẽ nói về chủ đề các câu lệnh DLL trong Database là gì nhé?

## **1. Các câu lệnh DDL**

Data Definition Language (DDL): Các câu lệnh định nghĩa cấu trúc để lưu trữ dữ liệu. Chúng ta sử dụng các câu lệnh này dùng cho việc thao tác trên Database (cơ sở dữ liệu), Table (bảng), các trường (cols).

## **2. Tạo Database**

Chúng ta dùng từ khoá CREATE DATABASE để tạo cơ sở dữ liệu. 

- Cú pháp

<br>
{% highlight sql linenos %}

CREATE DATABASE databasename; 

{% endhighlight %}

- Ví dụ tạo database tên testDB

<br>
{% highlight sql linenos %}

CREATE DATABASE testDB;

{% endhighlight %}

## **3. Xoá Database**

Chúng ta sử dụng từ khoá DROP DATABASE để xoá cơ sở dữ liệu.

- Cú pháp

<br>
{% highlight sql linenos %}

DROP DATABASE databasename; 

{% endhighlight %}

- Ví dụ xoá Database trên testDB

<br>
{% highlight sql linenos %}

DROP DATABASE testDB;

{% endhighlight %}

## **4. Tạo bảng**

Chúng ta sử dụng từ khoá CREATE TABLE để tạo bảng trong cơ sở dữ liệu.

- Cú pháp

<br>
{% highlight sql linenos %}

CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    column3 datatype,
   ....
)

{% endhighlight %}

- Ví dụ 

<br>
{% highlight sql linenos %}

CREATE TABLE Persons (
    PersonID int,
    LastName varchar(255),
    FirstName varchar(255),
    Address varchar(255),
    City varchar(255)
);
{% endhighlight %}

## **5. Xoá bảng**

Chúng ta sử dụng từ khoá DROP TABLE để xoá bảng trong cơ sở dữ liệu.

- Cú pháp

<br>
{% highlight sql linenos %}

DROP TABLE table_name; 

{% endhighlight %}

- Ví dụ 

<br>
{% highlight sql linenos %}

DROP TABLE Shippers;

{% endhighlight %}

## **6. Xoá hết dữ liệu trong Bảng**

Chúng ta sử dụng từ khoá TRUNCATE TABLE để xoá hết các dữ liệu trong bảng. Khác với Drop table ở chỗ là TRUNCATE chỉ xoá dữ liệu còn cấu trúc bảng vẫn giữ nguyên, còn Drop thì nó xoá hết tất cả mọi thứ về cấu trúc bảng và dữ liệu.

- Cú pháp

<br>
{% highlight sql linenos %}

TRUNCATE TABLE table_name; 

{% endhighlight %}

- Ví dụ 

<br>
{% highlight sql linenos %}

TRUNCATE TABLE Shippers;

{% endhighlight %}

## **7. Chỉnh sửa lại Bảng**

Chúng ta sử dụng ALTER TABLE để chỉnh sửa, xoá, thêm lại các col trong Table đã có sẵn.

- Cú pháp sau đây thêm 1 column vào bảng có sẵn

<br>
{% highlight sql linenos %}

ALTER TABLE table_name
ADD column_name datatype;

{% endhighlight %}

- Ví dụ 

<br>
{% highlight sql linenos %}

ALTER TABLE Customers
ADD Email varchar(255);
{% endhighlight %}

- Cú pháp sau đây xoá 1 column vào bảng có sẵn

<br>
{% highlight sql linenos %}

ALTER TABLE table_name
DROP COLUMN column_name; 

{% endhighlight %}

- Ví dụ 

<br>
{% highlight sql linenos %}

ALTER TABLE Customers
DROP COLUMN Email;

{% endhighlight %}

- Cú pháp sau đây thay đổi kiểu dữ liệu 1 column vào bảng có sẵn

<br>
{% highlight sql linenos %}

ALTER TABLE table_name
MODIFY COLUMN column_name datatype; 

{% endhighlight %}

- Ví dụ 

<br>
{% highlight sql linenos %}

ALTER TABLE Customers
MODIFY COLUMN Email varchar(255); 

{% endhighlight %}

<br>
## **8. Và bây giờ, hãy cùng xem code demo ở bên dưới để hiểu rõ hơn nhé**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}




