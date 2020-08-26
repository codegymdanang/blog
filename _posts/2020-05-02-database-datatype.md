---
layout: course-relationaldatabase
title:  Kiểu dữ liệu trong database
slug : database-datatype
category: database
tags: [database]
summery: Kiểu dữ liệu    
image: /images/blog/database.png
description : Trình bày kiểu dữ liệu của database. Hướng dẫn cách sử dụng kiểu dữ liệu trong database
youtubeId: tKLOuvrHCNw
---

# **Giới thiệu nội dung bài viết**

Chào các em, hôm nay chúng ta sẽ nói về chủ đề kiểu dữ liệu trong database là gì nhé ?

# **1. Kiểu dữ liệu**

Mỗi column(cột) trong database điều có kiểu dữ liệu để lưu trữ thông tin về đối tượng. Kiểu dữ liệu có thể lưu trong các cột có thể là kiểu số, chữ , tiền tệ hoặc ngày tháng v.v

Trong database có 3 kiểu dữ liệu chính là chuỗi, số và ngày tháng

# **2. Kiểu dữ liệu chuỗi**

{:class="table table-bordered"}
|  Kiểu dữ liệu  					|  Mô tả											    	|
|---								|---														|
|	Char(size)						| chứa từ 0 - 255 ký tự. mặc định là 1						|
|	Varchar(size)					| chứa từ 0 - 65535 ký tự									|
|	Binary(size)					| giống như char nhưng chứa giá trị là binary byte			|
|	VarBinary(size)					| giống như varchar nhưng chứa giá trị binary byte			|
|	TinyBlob						| chứa kiểu BLOB (cho những object lớn) max length là 255 bytes |
|	TinyText						| chứa giá trị chuỗi với max độ dài là 255 ký tự			|
|	Text(size)						| chứa giá trị chuỗi với max độ dài là 65.535 bytes			|
|	BLOB(size)						| chứa kiểu BLOBs có thể chứa đến 65.535 bytes dữ liệu				|
|	MediumText						| chứa kiểu string với giá trị max là 16,777,215 ký tự		|
|	MediumBlob						| chứa kiểu BLOB có thể chứa đến 16,777,215 bytes 			|
|	LongText						| chứa kiểu string chứa đến 4,294,967,295 ký tự				|
|	LongBlob						| chứa đến 4,294,967,295 bytes dữ liệu						|

# **2. Kiểu dữ liệu số**

{:class="table table-bordered"}
|  Kiểu dữ liệu  					|  Mô tả											    	|
|---								|---														|




<br>
{% highlight sql linenos %}

SELECT * FROM Customers;

{% endhighlight %}





