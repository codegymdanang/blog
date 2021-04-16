---
layout: course-javascript
title: Sử dụng ngoại lệ trong Javascript  
slug : su-dung-ngoai-le-trong-javascript
category: laptrinhjavascript
tags: [javascript]
summery: Ngoại lệ   
image: /images/blog/feature_javascript.png
description : Trong lập trình web, những vấn đề phát sinh trong quá trình chương trình chạy thì được gọi là Ngoại lệ, Exception. Bài viết này sẽ giúp bạn hiểu rõ hơn về những ngoại lệ, Exception thường xảy ra trong lập trình web như lỗi cú pháp, runtime error hay sai về logic. Đồng thời cũng được tìm hiểu về những đối tượng Error trong JavaScript gồm những gì? Bên cạnh đó bài viết cũng hướng dẫn cho các bạn các cách để bắt các ngoại lệ như sử dụng khối lệnh try catch hay sử dụng throw ném ngoại lệ. Cuối cùng anh sẽ trình bày về khối lệnh finally trong JavaScript, đây là khối lệnh luôn chạy các dòng code cho dù có ngoại lệ hay không.
youtubeId: tjHeAggd5-k
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Trong quá trình <b>lập trình web</b>, chắc hẳn sẽ có những lúc chương trình bạn làm ra bị dừng lại vì xảy ra lỗi trong code mình làm. Những lỗi này được gọi là <b>Ngoại lệ (Exception)</b> trong JavaScript. 
<br>

Trong bài viết hôm nay anh sẽ chia sẻ cho các bạn những <b>ngoại lệ (Exception)</b> thường xảy ra khi <b>lập trình web</b> với JavaScript như lỗi cú pháp, runtime error hay sai về logic. Cũng như cùng tìm hiểu về những đối tượng Error trong JavaScript gồm những gì? Nắm được những lỗi thường gặp này để các bạn sẽ chú ý hơn khi <b>lập trình web</b> và sau này khi xảy ra các lỗi thì sẽ biết do đâu để tìm cách khắc phục. Đồng thời trong những chia sẻ tiếp theo anh sẽ hướng dẫn cho các bạn các cách để bắt các <b>ngoại lệ</b> như sử dụng khối lệnh try-catch hay sử dụng throw ném ngoại lệ. Cuối cùng anh sẽ trình bày về khối lệnh finally trong JavaScript, đây là khối lệnh luôn chạy các dòng code cho dù có ngoại lệ hay không.


## **1. Ngoại lệ là gì**

Trong quá trình lập trình với Javascript sẽ có những lúc code mình không chạy như mình mong muốn và nó quăng ra lỗi làm cho chương trình mình dừng lại. Các lỗi đó mình gọi là ngoại lệ (Exception). Khi lập trình thì mình sẽ sử dụng các từ khoá try catch để mình bắt lại ngoại lệ xử lý để chương trình tiếp tục chạy.

Có 3 loại ngoại lệ thường xảy ra khi mình lập trình Javascript. Mình sẽ gặp lỗi cú pháp khi gõ sai cú pháp (Syntax Error) thì sẽ bị gặp lỗi. Hoặc trong quá trình chương trình mình chạy gặp lỗi thì gọi là Runtime Error. Hoặc mình bị sai về logic.

## **2. Đối tượng Error**

Khi chương trình chạy bị lỗi nó sẽ ném ra đối tượng là Error cho mình. Trong đối tượng Error có 2 thuộc tính là name (tên của lỗi) và message (nội dung của lỗi). Chúng ta sử dụng try catch để bắt lại đối tượng Error này. Tuỳ vào message (nội dung) của lỗi là gì mà chúng ta xử lý.

## **3. Sử dụng khối lệnh try-catch để bắt ngoại lệ**

- Cú pháp


{% highlight javascript  linenos %}

<script>

    try{  
        code chương trình; 
    } //code to be written.  
    catch(error){  
       bắt lỗi và xử lý lỗi nếu có khi chạy code chương trình; 
    } // code for handling the error

</script>

{% endhighlight %}

- Ví dụ

{% highlight javascript  linenos %}

<script>
try{
    var a= ["34","32","5","31","24","44","67"]; //a is an array
    document.write(a);    // displays elements of a
    document.write(b); //b is undefined but still trying to fetch its value. Thus catch block will be invoked
}catch(e){
    alert("There is error which shows "+e.message); //Handling error
}
</script>
{% endhighlight %}

- Chúng ta sử dụng e.message để lấy thông báo lỗi (e là đại diện cho Error).

## **4. Sử dụng Throw ném ngoại lệ**

Sẽ có những trường hợp trong function của mình muốn ném ra một ngoại lệ để các function khác khi gọi nó có thể bắt ngoại lệ và xử lý tiếp. Để function ném ra ngoại lệ thì ta dùng từ khóa Throw.

- Cú pháp

{% highlight javascript  linenos %}

    try{  
        throw exception; // user can define their own exception  
    }catch(error){  
        expression; 
    }  // code for handling exception.
{% endhighlight %}

- Ví dụ

{% highlight javascript  linenos %}

<script>  
try {  
   throw new Error('This is the throw keyword'); //user-defined throw statement.  
}  
catch (e) {  
  document.write(e.message); // This will generate an error message  
}  
</script>

{% endhighlight %}

## **5. Khối lệnh finally**

Khối lệnh finally là trường hợp đặc biệt ta có thể dùng hoặc không dùng chung với try catch. Khối lệnh finally luôn luôn chạy các dòng code trong nó dù ngoại lệ có được ném ra hay không.

- Cú pháp

{% highlight javascript  linenos %}

<script>  

    try{  
        expression;  
    }  
    catch(error){  
         expression;  
    }  
    finally{  
        expression; 
    } //Executable code  
</script>

{% endhighlight %}

- Ví dụ 

{% highlight javascript  linenos %}
<script>  
    try{  
        var a=2;  
        if(a==2)  
        document.write("ok");  
    } catch(Error){  
        document.write("Error found"+e.message);  
    }  finally{  
        document.write("Value of a is 2 ");  
    }  
</script>

{% endhighlight %}


{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}








