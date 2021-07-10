---
layout: course-typescript
title: Sử dụng Union Any Void Never any void never trong TypeScript 
slug : su-dungt-union-any-void-never-any-void-never-trong-typescript
category: laptrinhjavascript
tags: [typescript]
summery: Union Any Void Never   
image: /images/blog/feature_javascript.png
description : Những thuật ngữ Union, Any, Void, Never được sử dụng trong ngôn ngữ lập trình TypeScript sẽ được giải thích và làm rõ trong bài viết. Bên cạnh đó, bài viết cũng sẽ giúp người đọc nắm được mục đích sử dụng và biết khi nào nên sử dụng loại nào cho phù hợp. Ngoài ra với những ví dụ minh hoạ cụ thể cho từng bước làm, cú pháp thực hiện mỗi loại trong bài viết, sẽ hướng dẫn cho người đọc sử dụng được Union Any Void Never trong TypeScript đạt được hiệu quả nhất.
youtubeId: x9sMpHjzo_I
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn, hôm nay anh sẽ hướng dẫn mọi người về <b>Union Any Void Never</b> là như thế nào? 

## **1. Union là gì**

Cho phép chúng ta sử dụng nhiều kiểu dữ liệu cho một biến. 

{% highlight javascript  linenos %}

let code: (string | number);
code = 123;   // OK
code = "ABC"; // OK
code = false; // Compiler Error

let empId: string | number;
empId = 111; // OK
empId = "E111"; // OK
empId = true; // Compiler Error

{% endhighlight %}


{% highlight javascript  linenos %}

function displayType(code: (string | number))
{
    if(typeof(code) === "number")
        console.log('Code is number.')
    else if(typeof(code) === "string")
        console.log('Code is string.')
}

displayType(123); // Output: Code is number.
displayType("ABC"); // Output: Code is string.
displayType(true); //Compiler Error: Argument of type 'true' is not assignable to a parameter of type string | number


{% endhighlight %}

## **2. Any là gì**

Any sử dụng khi ta không biết kiểu dữ liệu là gì. Thường được sử dụng khi chúng ta gọi một webservice bên ngoài hoặc dịch vụ của nhà phát triển thứ 3.

{% highlight javascript  linenos %}

let something: any = "Hello World!"; 
something = 23;
something = true;

{% endhighlight %}

Đoạn code trên sẽ được dịch ra Javascript như sau khi compile.

{% highlight javascript  linenos %}

var something = "Hello World!";
something = 23;
something = true;

{% endhighlight %}

Chúng ta có thể tạo mảng với any như sau:

{% highlight javascript  linenos %}

let arr: any[] = ["John", 212, true]; 
arr.push("Smith"); 
console.log(arr); //Output: [ 'John', 212, true, 'Smith' ] 

{% endhighlight %}

## **3. Void là gì**

Cũng giống như Java, void được sử dụng để thông báo function không trả về kiểu dữ liệu gì.

{% highlight javascript  linenos %}

function sayHi(): void { 
    console.log('Hi!')
} 

let speech: void = sayHi(); 
console.log(speech); //Output: undefined

{% endhighlight %}

## **4. Never là gì**

TypeScript có một kiểu dữ liệu mới là never có nghĩa giá trị đó sẽ không xảy ra. Never được sử dụng khi ta chắc chắn việc gì đó không xảy ra. Ví dụ sau chúng ta viết function nó sẽ không bao giờ trả về lỗi vì while luôn true nên vòng lặp while chạy vô hạn không bao giờ bị lỗi.

{% highlight javascript  linenos %}

function throwError(errorMsg: string): never { 
            throw new Error(errorMsg); 
} 

function keepProcessing(): never { 
            while (true) { 
         console.log('I always does something and never ends.')
     }
}

{% endhighlight %}


## **5. Và bây giờ, hãy cùng xem code demo ở bên dưới để hiểu rõ hơn nhé**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}



