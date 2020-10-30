---
layout: course-html
title: Sử dụng thẻ Table trong HTML   
slug : su-dung-the-table-trong-html
category: laptrinhweb
tags: [html]
summery: Table   
image: /images/blog/angular.png
description : Trình bày và hướng dẫn các cách sử dụng phổ biến và quan trọng của thẻ tạo bảng table trong lập trình web HTML bao gồm cách làm thế nào để tạo bảng, tiêu đề bảng, khoảng cách dòng và cột, trộn các dòng, cột cũng như cách thiết lập chiều cao, chiều dài và header, footer cho bảng. Để thao tác với bảng table trong HTML, chúng ta sẽ sử dụng các thẻ và các thuộc tính như thẻ table, thẻ tr, thẻ td, thẻ th, thuộc tính cellpadding, cellspacing, thuộc tính colspan, rowspan, width, height, thuộc tính caption, thead, toddy. 
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Trong quá trình học và làm việc với <b>lập trình web HTML</b>,  chắc hẳn các bạn sẽ cần sử dụng <b>thẻ tạo bảng table</b> rất nhiều. Vì vậy đòi hỏi người học lập trình web HTML như chúng ta phải nắm vững các loại thẻ cũng như cách sử dụng với mỗi loại thẻ và các thuộc tính để thao tác với bảng table trong lập trình web HTML.
<br>
Trong phạm vi bài viết này, anh sẽ trình bày và hướng dẫn các bạn các cách sử dụng phổ biến và quan trọng của <b>thẻ tạo bảng table trong lập trình web HTML</b> bao gồm cách làm như thế nào để tạo bảng, tiêu đề bảng, khoảng cách dòng và côt, trộn các dòng, cột cũng như cách thiết lập chiều cao, chiều dài và header, footer cho bảng. Để thao tác với bảng table trong HTML, chúng ta sẽ sử dụng các thẻ và các thuộc tính như thẻ table, thẻ tr, thẻ td, thẻ th, thuộc tính cellpadding, cellspacing, thuộc tính colspan, rowspan, width, height, thuộc tính caption, thead, toddy.
<br>
Cụ thể cách sử dụng <b>thẻ tạo bảng table</b> và các thuộc tính như thế nào để thao tác với bảng table trong <b>lập trình web HTML</b>? Những chia sẻ dưới đây sẽ giúp bạn giải đáp những thắc mắc trên ngay nhé.


## **1. Tạo table**

Để tạo table trong HTML chúng ta sử dụng thẻ table. Table được cấu tạo bởi các dòng (row) và các cột (colum). Để tạo row chúng ta dùng thẻ tr và để tạo table chúng ta dùng thẻ td.


{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>HTML Tables</title>
   </head>
   
   <body>
      <table border = "1">
         <tr>
            <td>Row 1, Column 1</td>
            <td>Row 1, Column 2</td>
         </tr>
         
         <tr>
            <td>Row 2, Column 1</td>
            <td>Row 2, Column 2</td>
         </tr>
      </table>
      
   </body>
</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![table1](/images/post/html/table1.png){:class="img-responsive"}
{: refdef}

- Nếu như chúng ta không muốn có border trong table thì chúng ta thiết lập thuộc tính border = 0.

## **2. Tiêu đề table**

Chúng ta tạo ra tiêu đề cho table bằng cách sử dụng thẻ th như sau

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>HTML Table Header</title>
   </head>
   
   <body>
      <table border = "1">
         <tr>
            <th>Name</th>
            <th>Salary</th>
         </tr>
         <tr>
            <td>Ramesh Raman</td>
            <td>5000</td>
         </tr>
         
         <tr>
            <td>Shabbir Hussein</td>
            <td>7000</td>
         </tr>
      </table>
   </body>
   
</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![table2](/images/post/html/table2.png){:class="img-responsive"}
{: refdef}

## **3. Khoảng cách dòng và cột**

Chúng ta có thể thiết lập khoảng cách giữa các ô trong table bằng cách sử dụng 2 thuộc tính cellpadding và cellspacing.

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>HTML Table Cellpadding</title>
   </head>
   
   <body>
      <table border = "1" cellpadding = "5" cellspacing = "5">
         <tr>
            <th>Name</th>
            <th>Salary</th>
         </tr>
         <tr>
            <td>Ramesh Raman</td>
            <td>5000</td>
         </tr>
         <tr>
            <td>Shabbir Hussein</td>
            <td>7000</td>
         </tr>
      </table>
   </body>
   
</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![table3](/images/post/html/table3.png){:class="img-responsive"}
{: refdef}

## **4. Trộn các dòng và cột**

Chúng ta có thể trộn (merge) các dòng và cột bằng cách sử dụng thuột tính colspan và rowspann như sau

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>HTML Table Colspan/Rowspan</title>
   </head>
   
   <body>
      <table border = "1">
         <tr>
            <th>Column 1</th>
            <th>Column 2</th>
            <th>Column 3</th>
         </tr>
         <tr>
            <td rowspan = "2">Row 1 Cell 1</td>
            <td>Row 1 Cell 2</td>
            <td>Row 1 Cell 3</td>
         </tr>
         <tr>
            <td>Row 2 Cell 2</td>
            <td>Row 2 Cell 3</td>
         </tr>
         <tr>
            <td colspan = "3">Row 3 Cell 1</td>
         </tr>
      </table>
   </body>
   
</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![table4](/images/post/html/table4.png){:class="img-responsive"}
{: refdef}

## **5. Thiết lập chiều cao và dài cho table**

Chúng ta sử dụng thuộc tính width và height để xát định chiều cao và rộng cho table

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>HTML Table Width/Height</title>
   </head>
   
   <body>
      <table border = "1" width = "400" height = "150">
         <tr>
            <td>Row 1, Column 1</td>
            <td>Row 1, Column 2</td>
         </tr>
         
         <tr>
            <td>Row 2, Column 1</td>
            <td>Row 2, Column 2</td>
         </tr>
      </table>
   </body>
   
</html>

{% endhighlight %} 

## **6. Tiêu đề cho table**

Chúng ta có thể thêm tiêu đề cho table bằng thuộc tính caption như sau

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>HTML Table Caption</title>
   </head>
   
   <body>
      <table border = "1" width = "100%">
         <caption>This is the caption</caption>
         
         <tr>
            <td>row 1, column 1</td><td>row 1, columnn 2</td>
         </tr>
         
         <tr>
            <td>row 2, column 1</td><td>row 2, columnn 2</td>
         </tr>
      </table>
   </body>
   
</html>
   

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![table5](/images/post/html/table5.png){:class="img-responsive"}
{: refdef}

## **7. Header Body và Footer trong table**

Chúng ta sử dụng thead để tạo header trong table, tbody để chỉ nội dung bên trong table và tfoot để tạo ra footer

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>HTML Table</title>
   </head>
   
   <body>
      <table border = "1" width = "100%">
         <thead>
            <tr>
               <td colspan = "4">This is the head of the table</td>
            </tr>
         </thead>
         
         <tfoot>
            <tr>
               <td colspan = "4">This is the foot of the table</td>
            </tr>
         </tfoot>
         
         <tbody>
            <tr>
               <td>Cell 1</td>
               <td>Cell 2</td>
               <td>Cell 3</td>
               <td>Cell 4</td>
            </tr>
         </tbody>
         
      </table>
   </body>
   
</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![table6](/images/post/html/table6.png){:class="img-responsive"}
{: refdef}







