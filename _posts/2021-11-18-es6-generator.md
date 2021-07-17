---
layout: course-es6
title: Sử dụng Generator trong ES6 
slug : su-dung-generator-trong-es6
category: laptrinhjavascript
tags: [es6]
summery: Generator
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta  dùng  Generator của ES6. Lần lượt giới thiệu và và đi qua các ví dụ về Generator  được sử dụng trong ES6.

youtubeId: Rm5nopIut6Y
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn, hôm nay anh sẽ hướng dẫn mọi người về  <b>Generator</b> của ES6. Lần lượt giới thiệu và và đi qua các ví dụ về Generator được sử dụng trong ES6.

## **1. Giới thiệu về Generator**

Các dòng code trong phương thức javascript được thực thi từ trên xuống dưới và nó không thể dừng lại giữ chừng. Anh lấy ví dụ về phương thức foo() như sau

{% highlight javascript  linenos %}

function foo() {
    console.log('I');
    console.log('cannot');
    console.log('pause');
}

{% endhighlight %}

Khi chương trình chạy anh sẽ nhận được kết quả là I cannot pause.

ES6 cung cấp một loại phương thức kiểu mới giúp chúng ta có thể dừng lại (pause) bất kỳ đâu trong phương thức. Nó được gọi là generator, anh có ví dụ về generator như sau

{% highlight javascript  linenos %}

function* generate() {
    console.log('invoked 1st time');
    yield 1;
    console.log('invoked 2nd time');
    yield 2;
}
{% endhighlight %}

Đầu tiên để khai báo 1 phương thức là generator anh sẽ sử dụng đấu * ở phía sau chữ function sau đó là tên phương thức function* generate.
Sau khi in ra console.log đầu tiên thì anh sử dụng 1 từ khoá thứ 2 đó là yield cái này sẽ trả về giá trị tại điểm đang dừng.

Như vậy khi tạo một phương thức generator chúng ta cần 2 từ khoá đó là * và yield.
Chúng ta gọi phương thức generator như sau.

{% highlight javascript  linenos %}

let gen = generate();

{% endhighlight %}

Chúng ta sẽ console.log biến gen xem nó là gì ?

{% highlight javascript  linenos %}

console.log(gen);

{% endhighlight %}

Kết quả ta nhận được sẽ là Object [Generator] {} . Như vậy biến gen của ta làm một đối tượng Generator. Để lấy giá trị dừng đầu tiên ta sử dụng phương thức next().

{% highlight javascript  linenos %}

let result = gen.next();
console.log(result);

Kết quả là 

invoked 1st time
{ value: 1, done: false }

{% endhighlight %}

Như vậy ta lấy được kết quả mà phương thức generate() dừng tại vị trí đầu tiên. Nếu muốn lấy tiếp giá trị dừng tiếp theo chúng ta sử dụng tiếp phương thức next().

{% highlight javascript  linenos %}

result = gen.next();
console.log(result);

Kết quả là 

invoked 2nd time
{ value: 2, done: false }

{% endhighlight %}

Nếu chúng ta next thêm 1 lần nữa thì sẽ nhận được kết quả undefined vì phương thức generate() chỉ dừng lại có 2 lần (yield)

{% highlight javascript  linenos %}

result = gen.next();
console.log(result);

Kết quả là 

{ value: undefined, done: true }

{% endhighlight %}

## **2. Duyệt qua Generator**

Generator là một đối tượng iterable nên chúng ta có thể duyệt qua nó bằng vòng lặp for of như sau.

{% highlight javascript  linenos %}

for (const g of gen) {
    console.log(g);
}

kết quả là

invoked 1st time
1
invoked 2nd time
2

{% endhighlight %}

## **3. Demo Video**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}








