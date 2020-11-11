---
layout: course-javascript
title: Khai báo biến trong Javascript  
slug : khai-bao-bien-trong-javascript
category: laptrinhjavascript
tags: [javascript]
summery: Biến   
image: /images/blog/feature_javascript.png
description : Trong ngành lập trình web hiện nay có 3 ngôn ngữ chính được lựa chọn sử dụng gồm HTML, CSS và JavaScript. Trong đó ngôn ngữ lập trình JavaScript đứng đầu bảng ngôn ngữ lập trình được sử dụng phổ biến nhất. Để hiểu rõ hơn về JavaScript. Trong những chia sẻ dưới đây, bài viết sẽ lần lượt giới thiệu cho các bạn hiểu được JavaScript là gì? Và hướng dẫn cách để cài đặt môi trường cho JavaScript cũng như cách làm với thẻ JavaScript, đặt file JS ở đâu trong HTML và làm sao để hiển thị Popup Message trong lập trình web với ngôn ngữ JavaScript.
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Trong ngành <b>lập trình web</b> hiện nay có 3 ngôn ngữ chính được lựa chọn sử dụng gồm HTML, CSS và JavaScript. Trong đó ngôn ngữ lập trình JavaScript đứng đầu bảng ngôn ngữ lập trình được sử dụng phổ biến nhất theo thống kê của Stack Overflow (2018) và GitHub Octoverse (2017). Khác với ngôn ngữ <b>lập trình Java</b> hoạt động một cách độc lập, JavaScript hoạt động cùng với các ngôn ngữ khác gồm HTML và CSS trên các trang website.

<br>
Để giúp các bạn hiểu rõ hơn về ngôn ngữ <b>lập trình web</b> JavaScript. Trong những chia sẻ dưới đây anh sẽ lần lượt giới thiệu cho các bạn hiểu được JavaScript là gì? Sau đó hướng dẫn cho các bạn cách để cài đặt môi trường cho JavaScript và cách làm với thẻ JavaScript cũng như giải đáp cho bạn thắc mắc về đặt file JS ở đâu trong HTML và làm sao để hiển thị Popup Message khi thao tác <b>lập trình web</b> với ngôn ngữ JavaScript.

## **1. Biến là gì**

Chúng ta sử dụng biến để lưu lại các giá trị. Giá trị này có thể thay đổi bất cứ lúc nào. Trong Javascript chúng ta sử dung từ khoá var để khai báo một biến. Tên biến phải là duy nhất và không được đặt trùng tên với các biến khác. Chúng ta sử dụng dấu = để gán giá trị cho biến.

## **2. Khai báo Biến**

- Cú pháp khai báo biến

{% highlight javascript  linenos %}

var <variable-name>;

var <variable-name> = <value>;


{% endhighlight %}

- Ví dụ khai báo biến và giá trị mà nó sẽ chứa

{% highlight javascript  linenos %}

var one = 1; // variable stores numeric value

var two = 'two';  // variable stores string value

var three;

{% endhighlight %}

- Chúng ta có thể khai báo nhiều biến trên cùng 1 dòng

{% highlight javascript  linenos %}

var one = 1, two = 'two', three;

{% endhighlight %}

- Chúng ta có thể khai báo biến không cần dùng từ khoá var vẫn được. Nhưng anh khuyên nên dùng để code dể đọc và dể hiểu

{% highlight javascript  linenos %}

one = 1;

two = 'two';

{% endhighlight %}

## **3. Đặt tên cho biến**

Tên của biến là một phần rất quan trọng trong sử dụng biến. Đặt tên biến phải bắt đầu bằng ký tự (a-z hoặc A-Z), hoặc dấu _ hoặc dấu $. Tiếp sau đó có thể là số (0-9). Tên biến trong JS phân biệt chữ hoa và chữ thường chính vì vậy mà tên biến là x thì sẽ khác với X

- Ví dụ khai báo đúng tên biến

{% highlight javascript  linenos %}

var x = 10;  
var $value="sonoo";  

{% endhighlight %}


















