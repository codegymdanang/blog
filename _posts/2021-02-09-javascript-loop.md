---
layout: course-javascript
title: Sử dụng vòng lặp trong Javascript  
slug : su-dung-vong-lap-trong-javascript
category: laptrinhjavascript
tags: [javascript]
summery: Vòng lặp   
image: /images/blog/feature_javascript.png
description : Để nhằm giải quyết các vấn đề mắc phải trong những bài toán khi lập trình web, các lập trình viên sẽ sử dụng vòng lặp, loop. Tương tự như những ngôn ngữ lập trình khác, JavaScript cũng có những vòng lặp như for, while, do-while. Bài viết này sẽ giúp bạn hiểu thêm về vòng lặp, loop trong JavaScript là gì cũng như hướng dẫn cách thao tác với các vòng lặp trên thông qua những ví dụ minh hoạ trong bài.
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

<b>Vòng lặp (Loop)</b> được xem là một trong những kiến thức lập trình cơ bản mà lập trình viên cần nắm. Tương tự như các ngôn ngữ lập trình khác, trong JavaScript cũng sử dụng các vòng lặp for, while, do-while để nhằm giải quyết các vấn đề mắc phải trong những bài toán khi <b>lập trình web</b>. Những vòng lặp này sẽ được thực hiện lặp lại nhiều lần cho tới khi các điều kiện không còn thoả mãn nữa.

Vậy cách thao tác với <b>vòng lặp (Loop)</b> trong JavaScript có khác với các ngôn ngữ khác không? Trong bài viết này, anh sẽ lần lượt trình bày về vòng lặp for, while, do-while. Các bạn hãy cùng tìm hiểu đáp án cho câu hỏi trên thông qua những chia sẻ dưới đây của anh nhé. 

## **1. Vòng lặp for là gì**

Chúng ta sử dụng vòng lặp để thực hiện đi thực hiện lại những dòng code trong vòng lặp tới khi điều kiện không còn thoả mãn nữa.

- Cú pháp

{% highlight javascript  linenos %}

for(initializer; condition; iteration)
{
    // Code to be executed
}

{% endhighlight %}

Vòng lặp for cần 3 thành phần đó là

initializer : khởi tạo giá trị ban đầu
condition   : điều kiện kết thúc vòng lặp
iteration   : biến đếm vòng lặp có thể tăng lên hoặc giảm xuống

- Ví dụ

{% highlight javascript  linenos %}

for (var i = 0; i < 5; i++)
{
    console.log(i);
}
{% endhighlight %}

Trong vòng lặp loop 3 thành phần có thể không cần thiết khai báo, mình chỉ cần khai báo giá trị initializer trước khi vòng lặp chạy vẫn được. Nhưng cách này anh khuyên không nên dùng vì gây khó hiểu

{% highlight javascript  linenos %}

var arr = [10, 11, 12, 13, 14];
var i = 0;

for (; ;) {
    
    if (i >= 5)
    break;

    console.log(arr[i]);
        
    i++;
}
{% endhighlight %}

## **2. Vòng lặp while là gì**

Vòng lặp While sẽ thực hiện các dòng code ở trong nó cho đến khi điều kiện không thoả mãn. Khác với vòng lặp for ta biết trước số lần vòng lặp sẽ chạy còn vòng lặp while thì không biết trước.

- Cú pháp

{% highlight javascript  linenos %}

while(condition expression)
{
    //code ở đây
}
{% endhighlight %}

- Ví dụ 

{% highlight javascript  linenos %}

var i =0;

while(i < 5)
{
    console.log(i);
    i++;
}
{% endhighlight %}

## **3. Vòng lặp do-while là gì**

Cũng giống như vòng lặp while. Vòng lặp do-while chạy cho đến khi điều kiện không còn đúng nữa. Khác ở vòng lặp while ở chỗ do-while luôn luôn chạy 1 lần dù có điều kiện sai.

- Cú pháp

{% highlight javascript  linenos %}

do{
    //code to be executed
}while(condition expression)

{% endhighlight %}

- Ví dụ

{% highlight javascript  linenos %}

var i = 0;

do{
   
     alert(i);
    i++;

} while(i < 5)
{% endhighlight %}





