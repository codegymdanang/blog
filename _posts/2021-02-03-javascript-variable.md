---
layout: course-javascript
title: Khai báo biến trong Javascript  
slug : khai-bao-bien-trong-javascript
category: laptrinhjavascript
tags: [javascript]
summery: Biến   
image: /images/blog/feature_javascript.png
description : Trong lập trình web, thuộc tính Biến được sử dụng để lưu lại các giá trị. Việc lưu lại dưới dạng các biến sẽ rất thuận tiện nếu sau này các bạn muốn sử dụng các giá trị đó nhiều lần. Những chia sẻ dưới đây sẽ trình bày cho các bạn hiểu được Biến là gì? Hướng dẫn để các bạn thực hiện được cách khai báo Biến, đặt tên cho Biến và chia sẻ những ví dụ minh hoạ để giúp các bạn nắm bắt kiến thức lập trình web này hiệu quả hơn.
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Trong <b>lập trình web</b>, thuộc tính <b>Biến</b> được sử dụng để lưu lại các giá trị. Việc lưu lại dưới dạng các biến sẽ rất thuận tiện nếu sau này các bạn muốn sử dụng các giá trị đó nhiều lần. Những lúc như vầy các bạn chỉ cần gọi tên <b>Biến</b> thay vì phải lặp đi lặp lại các giá trị sẽ rất mất thời gian và tốn công sức.

<br>
Trong phạm vi bài viết hôm nay, anh sẽ trình bày cho các bạn hiểu được <b>Biến</b> là gì? Hướng dẫn để các bạn thực hiện được cách khai báo Biến, Đặt tên cho Biến và chia sẻ những ví dụ minh hoạ để giúp các bạn nắm bắt kiến thức <b>lập trình web</b> này hiệu quả hơn.  


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


















