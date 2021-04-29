---
layout: course-relationaldatabase
title: Các câu lệnh SQL DML trong database
slug : cac-cau-lenh-sql-dml-trong-database
category: database
tags: [database]
summery: Các câu lệnh SQL DML    
image: /images/blog/database.png
description : Những chia sẻ trong bài viết sẽ giúp hiểu rõ hơn về các câu lệnh SQL DML trong Database. Tác giả lần lượt trình bày về các kiến thức SQL Select, SQL Select DISTINCT, SQL Where, SQL And, SQL OR, SQL NOT. Đồng thời trong những chia sẻ tiếp theo của bài viết, tác giả sẽ hướng dẫn sử dụng cách thao tác để kết hợp AND OR NOT, SQL ORDER BY, SQL Insert, SQL Update và SQL Delete trong lập trình Database. Ở mỗi mục của bài viết, tác giả đưa ra những ví dụ minh hoạ cụ thể hướng dẫn cú pháp thực hiện.
youtubeId: BL7FFKPETMs
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay chúng ta sẽ nói về các câu lệnh SQL DML trong Database là gì nhé?

## **1. SQL Select**

Chúng ta sử dụng từ khoá SELECT để lấy dữ liệu từ một bảng trong Database.

- Cú pháp 

<br>
{% highlight sql linenos %}

SELECT column1, column2, ...
FROM table_name; 

{% endhighlight %}

- Ví dụ ta có Table sau đây:

{:class="table table-bordered"}
|  CustomerName                     |  ContactName      |   Address                     |   City        |   PostalCode  |   Country     |
|---                                |---                |---                            |---            |---            |---            |
|Alfreds Futterkiste                |Maria Anders       |Obere Str. 57                  |   Berlin      |   12209       |   Germany     |       
|Ana Trujillo Emparedados y helados |Ana Trujillo       |Avda. de la Constitución 2222  |   México D.F. |   05021       |   Mexico      |
|Antonio Moreno Taquería            |Antonio Moreno     |Mataderos 2312                 |   México D.F. |   05023       |   Mexico      |
|Around the Horn                    |Thomas Hardy       |120 Hanover Sq.                |   London      |   WA1 1DP     |   UK          |
|Berglunds snabbköp                 |Christina Berglund |Berguvsvägen 8                 |   Luleå       |   S-958 22    |   Sweden      |

- Ví dụ ta chỉ muốn lấy CustomerName và City từ bảng Customers ta thực hiện câu truy vấn sau:

<br>
{% highlight sql linenos %}

SELECT CustomerName, City FROM Customers;

{% endhighlight %}

- Chúng ta sử dụng dấu * nếu muốn lấy tất cả các cột không chỉ là CustomerNam và City:

<br>
{% highlight sql linenos %}

SELECT * FROM Customers;

{% endhighlight %}

## **2. SQL Select DISTINCT**

Chúng ta sử dụng Distinct để loại bỏ các giá trị giống nhau. Ví dụ như Table Customers ở trên nếu ta viết câu lệnh:

<br>
{% highlight sql linenos %}

SELECT City FROM Customers;

{% endhighlight %}

Ta sẽ nhận lại kết quả là:
- Germany 
- Mexico 
- Mexico 
- UK 
- Sweden 
- Germany 
- France 
- Spain 

Như vậy ta thấy có 2 dòng dữ liệu City giống nhau là Mexico.

Nếu ta sử dụng Distinct thì nó sẽ gộp 2 cái Mexico lại và chỉ trả về 1 kết quả Mexico.
<br>
{% highlight sql linenos %}
SELECT DISTINCT Country FROM Customers;
{% endhighlight %}

- Germany 
- Mexico 
- UK 
- Sweden 
- Germany 
- France 
- Spain 

## **3. SQL Where**

Chúng ta sử dụng mệnh đề Where khi muốn lọc lại các kết quả. Chúng ta thêm điều kiện muốn lọc sau từ khoá Where.

- Cú pháp

<br>
{% highlight sql linenos %}

SELECT column1, column2, ...
FROM table_name
WHERE condition; 

{% endhighlight %}

- Ví dụ chúng ta muốn lấy tất cả dữ liệu nhưng chỉ cho thành phố là Mexico thôi. Không lấy kết quả các thành phố khác.

<br>
{% highlight sql linenos %}

SELECT * FROM Customers
WHERE Country='Mexico';

{% endhighlight %}

- Các loại toán tử có thể sử dụng trong mệnh đề where là 

{:class="table table-bordered"}
|  Toán tử                          |  Mô tả                                        |
|---                                |---                                            |
|   =                               | Toán bằng                                     |
|   >                               | Lớn hơn                                       |
|   <                               | Nhỏ hơn                                       |
|   >=                              | Lớn hơn hoặc bằng                             |
|   <=                              | Nhỏ hơn hoặc bằng                             |
|   <>                              | Không bằng                                    |

{:class="table table-bordered"}
|  Toán tử                          |  Mô tả                                        |
|---                                |---                                            |
|   ALL                             | TRUE nếu tất cả câu truy vấn con là TRUE      |
|   And                             | TRUE nếu tất cả điều kiện là TRUE             |
|   ANY                             | TRUE nếu query con là đúng                    |
|   BETWEEN                         | TRUE nếu tất cả nằm trong range                   |
|   EXITS                           | TRUE nếu câu query con có trả về kết quả      |
|   IN                              | TRUE nếu câu query thoả mãn một trong những điều kiện|
|   LIKE                            | TRUE nếu thoả mãn pattern đưa ra              |
|   NOT                             | Hiển thị dữ liệu nếu điều kiện không phải True |
|   OR                              | TRUE nếu 1 trong 2 điều kiện là TRUE          |
|   SOME                            | TRUE nếu một hoặc nhiều câu query con thoả mãn điều kiện |

## **4. SQL And**

Chúng ta sử dụng từ khóa And khi muốn kết hợp hai hay nhiều điều kiện. 

- Cú pháp
<br>
{% highlight sql linenos %}

SELECT column1, column2, ...
FROM table_name
WHERE condition1 AND condition2 AND condition3 ...;

{% endhighlight %}

- Ví dụ ta muốn tìm tất cả dữ liệu mà Country phải là Germany và City phải là Berlin

<br>
{% highlight sql linenos %}

SELECT * FROM Customers
WHERE Country='Germany' AND City='Berlin';

{% endhighlight %}

## **5. SQL OR**

Chúng ta sử dụng OR để kiểm tra một trong hai điều kiện có đúng hay không. Ví dụ ta muốn tìm tất cả dữ liệu của khách hàng nếu City là Berlin hoặc nếu không tìm thấy Berlin thì City là Munchen thì cũng hiển thị kết quả. Chỉ cần một trong hai điều kiện thỏa mãn là được.

<br>
{% highlight sql linenos %}

SELECT * FROM Customers
WHERE City='Berlin' OR City='München';

{% endhighlight %}

## **6. SQL NOT**

Chúng ta sử dụng NOT để phủ định lại kết quả điều kiện. Ví dụ tìm tất cả khách hàng mà Country không phải là Germany.

<br>
{% highlight sql linenos %}

SELECT * FROM Customers
WHERE NOT Country='Germany';

{% endhighlight %}

## **7. Kết hợp AND OR NOT**

Chúng ta có thể kết hợp AND OR NOT trong một câu truy vấn như sau:

<br>
{% highlight sql linenos %}

SELECT * FROM Customers
WHERE Country='Germany' AND (City='Berlin' OR City='München');

{% endhighlight %}

- Câu lệnh sẽ ưu tiên thực thi trong dấu () trước sau đó so sánh And.

<br>
{% highlight sql linenos %}

SELECT * FROM Customers
WHERE NOT Country='Germany' AND NOT Country='USA'; 
{% endhighlight %}

## **8. SQL ORDER BY**

Chúng ta sử dụng từ khoá ORDER BY khi muốn sắp xếp dữ liệu tăng dần hoặc giảm dần.

- Cú Pháp
<br>
{% highlight sql linenos %}

SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC; 

{% endhighlight %}

- Ví dụ
<br>
{% highlight sql linenos %}

SELECT * FROM Customers
ORDER BY Country DESC; 

{% endhighlight %}

- Chúng ta sử dụng từ khóa ASC|DESC để chỉ ra sự tăng hoặc giảm. Nếu tăng thì dùng ASC và giảm thì dùng DESC.

- Chúng ta có thể sắp xếp cho nhiều Column.
<br>
{% highlight sql linenos %}

SELECT * FROM Customers
ORDER BY Country, CustomerName; 

{% endhighlight %}


## **9. SQL Insert**

Chúng ta sử dụng từ khoá Insert để thêm 1 dòng vào Database.

- Cú pháp
<br>
{% highlight sql linenos %}

INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...); 

{% endhighlight %}

- Ví dụ
<br>
{% highlight sql linenos %}

INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES ('Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway');

{% endhighlight %}

- Chúng ta có thể thêm một dữ liệu cho một Column, cụ thể trong Table như ví dụ dưới đây. Ta chỉ muốn thêm dữ liệu cho Column CustomerName, City, Country mà thôi.

<br>
{% highlight sql linenos %}

INSERT INTO Customers (CustomerName, City, Country)
VALUES ('Cardinal', 'Stavanger', 'Norway');

{% endhighlight %}

## **10. SQL Update**

Chúng ta sử dụng từ khoá Update để cập nhật lại giá trị trong Table.

- Cú pháp
<br>
{% highlight sql linenos %}

UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition; 

{% endhighlight %}

- Ví dụ
<br>
{% highlight sql linenos %}

UPDATE Customers
SET ContactName = 'Alfred Schmidt', City= 'Frankfurt'
WHERE CustomerID = 1;
{% endhighlight %}

## **11. SQL Delete**

Chúng ta sử dụng từ khoá Delete khi muốn xoá một dòng trong Table.

- Cú pháp
<br>
{% highlight sql linenos %}

DELETE FROM table_name WHERE condition;

{% endhighlight %}

- Ví dụ
<br>
{% highlight sql linenos %}
 DELETE FROM Customers WHERE CustomerName='Alfreds Futterkiste'; 
{% endhighlight %}

- Để xóa tất cả các dữ liệu ta làm như sau:

<br>
{% highlight sql linenos %}

DELETE FROM Customers;

{% endhighlight %}

## **12. Demo Video**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **13. Source Code**

{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/Database-Mysql" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}






























