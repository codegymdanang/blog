---
layout: course-javascript
title: Sử dụng Callback trong Javascript  
slug : su-dung-callback-trong-javascript
category: laptrinhjavascript
tags: [javascript]
summery: Callback   
image: /images/blog/feature_javascript.png
description : Trong lập trình web với JavaScript, Callback được hiểu là việc truyền một function như một tham số đến một function khác và đợi để được gọi cho xử lí các vấn đề đồng bộ theo trình tự nhất định. Những chia sẻ trong bài viết này sẽ giải thích cho các bạn hiểu rõ hơn về Callback. Và hướng dẫn các bạn cách để sử dụng Callback trong lập trình web thông qua 2 ví dụ minh hoạ ở cuối bài.

youtubeId: YFedotkotLs
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Trong <b>lập trình web</b> với JavaScript, <b>Callback</b> được hiểu là việc truyền một function như một tham số đến một function khác và đợi để được gọi cho xử lý các vấn đề đồng bộ theo trình tự nhất định.

Nếu các bạn vẫn cảm thấy khó hiểu với thuật ngữ này hay chưa biết cách làm như thế nào để áp dụng nó vào thực hành. Các bạn có thể đọc thêm những chia sẻ dưới đây của anh về <b>Callback</b> để hiểu rõ hơn. Trong bài viết anh sẽ giải thích cho các bạn hiểu được <b>Callback</b> là gì? Và hướng dẫn sử dụng <b>Callback trong lập trình web</b> thông qua 2 ví dụ minh hoạ ở cuối bài.


## **1. Callback là gì**

Khái niệm callback có nghĩa là ta truyền một function như một tham số đến một function khác.

Thông thường chúng ta thấy khi khai báo hàm có tham số ví dụ:

{% highlight javascript  linenos %}

function getData(x, y) {
    
    // code logic tại đây
}

{% endhighlight %}

- Thì tham số truyền vào trong hàm getData là kiểu dữ liệu.

Còn đối với Callback là ta truyền vào một function chứ không phải kiểu dữ liệu như ví dụ dưới đây.

## **2.Ví dụ về Callback**

{% highlight javascript  linenos %}

function getData(x, y, callback){  
    document.write(" The multiplication of the numbers " + x + " and " + y + " is: " + (x*y) + "<br><br>" );  
    callback();  
}  

function showData(){  
document.write(' This is the showData() method execute after the completion of getData() method.');  
}  
getData(20, 30, showData); 

{% endhighlight %}

- Ở ví dụ trên ta có 2 function: 
- Function đầu tiên là getData với 3 tham số là x,y và callback (callback này là ta truyền vào đây một function như một tham số thứ 3 trong ví dụ trên tham số thứ 3 là function tên showData). 
- Function thứ 2 có tên là showData function này được truyền vào như 1 tham số.
- Khi chương trình chạy đầu tiên nó sẽ gọi function getData(x,y,callback) lúc này nó sẽ in ra màn hình "The multiplication of the numbers". Sau khi in ra màn hình xong thì lúc này nó mới gọi hàm showData lúc này nó sẽ in tiếp ra màn hình là "This is the showData() method execute after the completion of getData() method."

Như vậy callback mình sử dụng như làm tuần tự các công việc một cách đồng bộ. Có nghĩa là khi làm xong việc thứ nhất thì chạy tiếp các công việc thứ 2 cho mình.

## **3.Ví dụ 2 về Callback**

{% highlight javascript  linenos %}

    <html>  
    <head>  
      
    </head>  
    <body>  
    <h1> Hello World :) :) </h1>  
    <h2> This is the javaTpoint.com </h2>  
    <script>  
    function showData(name, amt) {  
    alert(' Hello ' + name + '\n Your entered amount is ' + amt);  
    }  
      
    function getData(callback) {  
    var name = prompt(" Welcome to the javaTpoint.com \n What is your name?");  
    var amt = prompt(" Enter some amount...");  
    callback(name, amt);  
    }  
      
    getData(showData);  
    </script>  
    </body>  
      
    </html>  
{% endhighlight %}

Tóm lại chúng ta sử dụng callback khi chúng ta muốn các công việc được xử lý đồng bộ theo trình tự nhất định.

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}


