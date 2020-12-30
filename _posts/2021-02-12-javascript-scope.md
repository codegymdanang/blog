---
layout: course-javascript
title: Sử dụng Scope trong Javascript 
slug : su-dung-scope-trong-javascript
category: laptrinhjavascript
tags: [javascript]
summery: Scope   
image: /images/blog/feature_javascript.png
description : Bài viết trình bày về Scope hay còn gọi là phạm vi truy cập trong lập trình web. Những chia sẻ trong bài sẽ giúp các bạn lần lượt tìm hiểu về 2 loại Scope trong JavaScript là Global, phạm vi toàn cục và Local, phạm vi nhất định. Đồng thời trình bày cho các bạn về Hoisting biến và Hoisting function trong ngôn ngữ lập trình web JavaScript là gì? Trong mỗi phần sẽ có các ví dụ minh hoạ kèm theo để hướng dẫn cụ thể cách sử dụng cho các bạn dễ dàng nắm bắt và áp dụng được vào thực hành trong lập trình web hiệu quả hơn.
youtubeId: YoXuyu1Ys4g
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Khi thao tác với các biến, đối tượng và function trong <b>lập trình web</b> với ngôn ngữ JavaScript, không phải khi nào chúng cũng tồn tại và có thể gọi được bất cứ lúc nào để sử dụng. Mà còn tuỳ thuộc vào phạm vi hoạt động của chúng. Trong JavaScript, phạm vi hoạt động đó được gọi là <b>Scope</b>.

Bài viết này sẽ giúp bạn hiểu rõ hơn về <b>Scope</b> là gì? Tìm hiểu về 2 loại <b>Scope</b> trong JavaScript là Global (phạm vi toàn cục) và Local (phạm vi nhất định). Đồng thời trình bày cho các bạn về Hoisting biến và Hoisting function trong ngôn ngữ <b>lập trình web</b> JavaScript là gì? Trong mỗi loại anh sẽ có các ví dụ minh hoạ kèm theo để hướng dẫn cụ thể cách sử dụng cho các bạn dễ dàng nắm bắt và áp dụng được vào thực hành trong <b>lập trình web</b> hiệu quả hơn.


## **1. Scope là gì**

Trong Javascript chúng ta định nghĩa Scope nghĩa là phạm vi hoạt động của biến, đối tượng và function. Khi nào chúng tồn tại và khi nào có thể gọi được chúng.

Có 2 loại scope trong javascript là Global (phạm vi toàn cục) và Local (phạm phi nhất định) 

## **2. Global scope là gì**

Các biến khai báo ngoài các function được gọi là global. Biến này được dùng chung cho các funcation, các function có thể thấy được biến này và thay đổi giá trị của biến này

- Ví dụ

{% highlight javascript  linenos %}

<script>

    var userName = "Bill";

    function modifyUserName() {
            userName = "Steve";
        };

    function showUserName() {
            alert(userName);
        };

    alert(userName); // display Bill
    
    modifyUserName();
    showUserName();// display Steve

</script>

{% endhighlight %}

Trong ví dụ trên biến userName là global nên function modifyUserName và showUserName có thể thấy được và sử dụng được

Các biến khai báo trong function nhưng không có từ khoá var, thì cũng được xem là biến có scope global.

{% highlight javascript  linenos %}

<script>

    function createUserName() {
        userName = "Bill";
    }

    function modifyUserName() {
        if(userName)
            userName = "Steve";
    };

    function showUserName() {
        alert(userName);  
    }
    
    createUserName();
    showUserName(); // Bill 

    modifyUserName();
    showUserName(); // Steve 

    
</script>

{% endhighlight %}

## **3. Local scope là gì**

Các biến được khai báo bên trong function và có từ khoá var được gọi là local. Biến local chỉ được sử dụng bên trong function. Các function khác bên ngoài không thể sử dụng được biến local này

{% highlight javascript  linenos %}

<script>
    
    function createUserName() {
        var userName = "Bill";
    }

    function showUserName() {
        alert(userName);
    }

    createUserName();
    showUserName(); // throws error: userName is not defined

</script>

{% endhighlight %}

Trong ví dụ trên biến userName chỉ được sử dụng trong function createUserName mà thôi, các function khác không thấy được biến này.

## **4. Hoisting biến gì**

Hoising là một khái niệm được đưa vào Javascript, nó khác với các ngôn ngữ lập trình khác. Ý chính của hoisting là các biến và function có thể được dùng trước khi mình khai báo.

Thông thường chúng ta code như sau. 

{% highlight javascript  linenos %}

var x;

x = 1;

alert('x = ' + x); // display x = 1

{% endhighlight %}

Chúng ta khai báo var x, sau đó chúng ta gán giá trị x = 1, cuối cùng là thực hiện function alert.

Hoisting cho phép chúng ta sử dụng biến x trước khi khai báo như sau

{% highlight javascript  linenos %}

x = 1;

alert('x = ' + x); // display x = 1

var x;
{% endhighlight %}

Như vậy ta thấy khai báo var x ở dòng cuối cùng. Khi Javascript biên dịch nó sẽ tự động đưa dòng var x lên phía trên cùng của file javascript. Như vậy sẽ không có lỗi xảy ra.

## **5. Hoisting function gì**

Cũng tương tự như biến chúng ta cũng có thể hoisting cho function. Khi Javascript biên dịch nó sẽ di chuyển định nghĩa function lên phía trên cùng. Như vậy sẽ không có lỗi xảy ra.

{% highlight javascript  linenos %}

alert(Sum(5, 5)); // 10

function Sum(val1, val2)
{
    return val1 + val2;
}
{% endhighlight %}

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}
