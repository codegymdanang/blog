---
layout: course-typescript
title: Sử dụng vòng lặp trong TypeScript
slug : su-dung-vong-lap-trong-typescript
category: laptrinhjavascript
tags: [typescript]
summery: Vòng lặp   
image: /images/blog/feature_javascript.png
description : Tìm hiểu về vòng lặp và cách sử dụng vòng lặp trong ngôn ngữ lập trình TypeScript. Bài viết lần lượt trình bày về vòng lặp for, While, doWhile áp dụng trong ngôn ngữ lập trình TypeScript. Trong những chia sẻ trong bài, có kèm theo những ví dụ mình hoạ cụ thể cú pháp thực hiện của mỗi vòng lặp để người đọc áp dụng được vào thực tế khi lập trình web.
youtubeId: soiEapMFxIU
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn, hôm nay anh sẽ hướng dẫn mọi người về <b>vòng lặp</b> là như thế nào? 

## **1. Vòng lặp for**

Typescript hỗ trợ cho chúng ta 3 loại vòng lặp for là forloop, for of loop và for in loop.

- Vòng lặp for Loop

Cú pháp

{% highlight javascript  linenos %}

for (first expression; second expression; third expression ) {
    // statements to be executed repeatedly
}

{% endhighlight %}


Ví dụ

{% highlight javascript  linenos %}

for (let i = 0; i < 3; i++) {
  console.log ("Block statement execution no." + i);
}

{% endhighlight %}

- Vòng lặp for of Loop

Dùng để trả lại từng phần tử của tập hợp. Nó tiện hơn vòng lặp for. Vì vòng lặp for trả về index, dựa vào index ta mới lấy được phần tử. 

Ví dụ

{% highlight javascript  linenos %}

let arr = [10, 20, 30, 40];

for (var val of arr) {
  console.log(val); // prints values: 10, 20, 30, 40
}

{% endhighlight %}

- Vòng lặp for in Loop

Duyệt qua các phần tử của mảng và trả về vị trí index của các phần tử trong mảng.

{% highlight javascript  linenos %}

let arr = [10, 20, 30, 40];

for (var index in arr) {
  console.log(index); // prints indexes: 0, 1, 2, 3

  console.log(arr[index]); // prints elements: 10, 20, 30, 40
}

{% endhighlight %}

## **2. Vòng lặp While**

Nó cũng tương tự nguyên lý vòng lặp while bên Javascript. Kiểm tra điều kiện trước khi chạy các dòng code trong while.

Cú pháp

{% highlight javascript  linenos %}

while (condition expression) {
    // code block to be executed
}

{% endhighlight %}

Ví dụ

{% highlight javascript  linenos %}

let i: number = 2;

while (i < 4) {
    console.log( "Block statement execution no." + i )
    i++;
}

{% endhighlight %}


## **3. Vòng lặp doWhile**

Vòng lặp dowhile thì mình chạy các câu lệnh trong do trước sau đó kiểm tra điều kiện. Vòng lặp dowhile ít nhất chạy 1 lần cho dù điều kiện không thoả mãn. 

Cú pháp

{% highlight javascript  linenos %}

do {
// code block to be executed
}
while (condition expression);

{% endhighlight %}

Ví dụ

{% highlight javascript  linenos %}

let i: number = 2;
do {
    console.log("Block statement execution no." + i )
    i++;
} while ( i < 4)

{% endhighlight %}

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}




















