---
layout: course-javascript
title: Sử dụng câu điều kiện trong Javascript 
slug : su-dung-cau-dieu-kien-trong-javascript
category: laptrinhjavascript
tags: [javascript]
summery: Câu điều kiện   
image: /images/blog/feature_javascript.png
description : Tương tự như các ngôn ngữ lập trình web khác, JavaScript cũng cung cấp cho chúng ta các câu điều kiện để giải quyết các bài toán rẽ nhánh từ đó giúp quản lí luồng đi của chương trình trở nên hiệu quả hơn. Bài viết sẽ lần lượt trình bày các câu điều kiện If, Else, Else If và mệnh đề Switch sử dụng trong ngôn ngữ lập trình web JavaScript. Trong mỗi phần như vậy có kèm theo ví dụ minh hoạ cụ thể để các bạn có tham khảo thêm cho quá trình học và làm các dự án lập trình web sau này.
youtubeId: JT7ZT_jCeoo
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Tương tự như các ngôn ngữ <b>lập trình web</b> khác, JavaScript cũng cung cấp cho chúng ta <b>các câu điều kiện</b> để giải quyết các bài toán rẽ nhánh từ đó giúp quản lí luồng đi của chương trình trở nên hiệu quả hơn.

<br>
Vậy cách thao tác với các dạng <b>câu điều kiện</b> trong JavaScript có khác với các ngôn ngữ khác không? Trong bài viết này, anh sẽ lần lượt trình bày các câu điều kiện If, Else, Else If và mệnh đề Switch sử dụng trong ngôn ngữ <b>lập trình web</b> JavaScript. Các bạn hãy cùng tìm hiểu đáp án cho câu hỏi trên thông qua những chia sẻ dưới đây của anh nhé. 


## **1. Câu điều kiện là gì**

Javascript cung cấp cho chúng ta các câu điều kiện để quản lý luồng đi của chương trình. Chúng ta thường sử dụng các câu điều kiện if else và switch case trong lập trình web.


## **2. Câu điều kiện If**

Chúng ta sử dụng câu điều kiện If nếu chúng ta muốn thực hiện các đoạn code dựa trên điều kiện ta đưa vào có thoả mãn hay không.

- Cú pháp

{% highlight javascript  linenos %}

 if (điều kiện) {
   nếu đúng thực hiện các dòng code trong này
 }

{% endhighlight %}

- Ví dụ

{% highlight javascript  linenos %}

if( 1 > 0)
{
    alert("1 is greater than 0");
}

if( 1 < 0)
{
    alert("1 is less than 0");
}

{% endhighlight %}

## **3. Câu điều kiện Else**

Chúng ta sử dụng Else để chạy những trường hợp không thoả mãn điều kiện If

- Cú pháp

{% highlight javascript  linenos %}

 if (điều kiện) {
   nếu đúng thực hiện các dòng code trong này
 } else {
   thực hiện code trong else
}

{% endhighlight %}

- Ví dụ 

{% highlight javascript  linenos %}

var mySal = 500;
var yourSal = 1000;

if( mySal > yourSal)
{
    alert("My Salary is greater than your salary");
}
else
{
    alert("My Salary is less than or equal to your salary");
}

{% endhighlight %}

## **4. Câu điều kiện Else If**

Chúng ta sử dụng Else If khi chúng ta muốn sử dụng kiểm tra điều kiện có thoả mãn lần thứ 2 hay không sau khi if đã kiểm tra

- Cú pháp

{% highlight javascript  linenos %}

if(condition expression)
{
    //Execute this code block
}
else if(condition expression){ 
    //Execute this code block
}
{% endhighlight %}

- Ví dụ 

{% highlight javascript  linenos %}

var mySal = 500;
var yourSal = 1000;

if( mySal > yourSal)
{
    alert("My Salary is greater than your salary");
}
else if(mySal < yourSal)
{
    alert("My Salary is less than your salary");
}

{% endhighlight %}

## **5. Mệnh đề Switch**

Mệnh đề switch cũng giống như If. Nó hữu ích khi chúng ta muốn thực thi một hoặc nhiều các khối lệnh dựa trên kết quả trả về

- Cú pháp

{% highlight javascript  linenos %}

switch(expression or literal value){
    case 1:
        //code to be executed
      break;
    case 2:
        //code to be executed
        break;
    case n:
        //code to be executed
        break;
    default:
        //default code to be executed 
        //if none of the above case executed
}

{% endhighlight %}

- Ví dụ 

{% highlight javascript  linenos %}

var a = 3;

switch (a) {
    case 1:
        alert('case 1 executed');
        break;
    case 2:
        alert("case 2 executed");
        break;
   case 3:
        alert("case 3 executed");
        break;
    case 4:
        alert("case 4 executed");
        break;
    default:
        alert("default case executed");
}

{% endhighlight %}

- Chúng ta sử dụng break để thoát khỏi mệnh đề Switch.
- Chúng ta có từ khoá default , nếu như không rơi vào case 1,2,3,4 thì trường hợp default sẽ chạy.

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}







