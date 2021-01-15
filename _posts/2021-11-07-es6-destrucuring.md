---
layout: course-es6
title: Sử dụng Destructuring trong ES6 
slug : su-dung-destructuring-trong-es6
category: laptrinhjavascript
tags: [es6]
summery:  Destructuring
image: /images/blog/feature_javascript.png
description : Trình bày về cách cách sử dụng Destructuring của ES6. Lần lượt giới thiệu và giải thích khái niệm Destructuring trong của ES6 là gì? 

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn, hôm nay anh sẽ hướng dẫn mọi người về  cách khai báo và sử dụng <b>Destructuring </b> của ES6. Lần lượt giới thiệu và giải thích khái niệm và ví dụ về Destructuring của ES6 là gì? 

## **1. Giới thiệu về Destructuring**

ES6 cung cấp cho chúng ta một chức năng mới được gọi là Destructuring tham số nghĩa là chúng ta có thể gán giá trị thuộc tính của một đối tượng hoặc một mảng vào trong các biến. Nghe có vẻ khó hiểu nên anh sẽ giải thích thông qua ví dụ sau đây. Giả sử ta có phương thức getScore trả về một mảng các giá trị là 70,80,90 như sau.

{% highlight javascript  linenos %}

function getScores() {
   return [70, 80, 90];
}

{% endhighlight %}


Tiếp đến ta khai báo biến scores sẽ gọi hàm getScores và chứa mảng giá trị là 70,80,90 như sau.

{% highlight javascript  linenos %}

let scores = getScores();

{% endhighlight %}

Như vậy biến scores sẽ chứa mảng các giá trị 70,80,90. Để lấy các giá trị ra ta sử dụng index . Ví dụ scores[0] tương ứng với giá trị 70.

{% highlight javascript  linenos %}

let x = scores[0], 
    y = scores[1], 
    z = scores[2];

{% endhighlight %}

Ở ví dụ trên ta gán scores[0] cho biến x , scores[1] cho biến y và scores[2] cho biến z. Lúc này x = 70, y = 80 và z = 90.

Trong ES6 chúng ta hoàn toàn có thể gán các giá trị cho x,y,z là 70,80,90 chỉ cần 1 dòng code thay vì cách làm ở trên như sau

{% highlight javascript  linenos %}

let [x, y, z] = getScores();

{% endhighlight %}

Cách khai báo ở trên được gọi là Destructuring chúng ta khai báo biến [x,y,z] nó sẽ tương ứng với từng giá trị mảng trả về của hàm getScores(). Khi hàm thực thi xong các giá trị mảng (70,80,90) sẽ tự động gán vào biến x,y,z theo thứ tự tương ứng. Nếu chúng ta thêm console.log ta sẽ nhận các kết quả sau. 

{% highlight javascript  linenos %}

let [x, y, z] = getScores();

console.log(x); // 70
console.log(y); // 80
console.log(z); // 90

{% endhighlight %}

Như vậy x sẽ được gán cho vị trí đầu tiên của mảng trong hàm getScores(). Lúc này vị trí đầu tiên là 70.
Như vậy y sẽ được gán cho vị trí thứ 2 của mảng trong hàm getScores(). Lúc này vị trí thứ 2 là 80.
Như vậy z sẽ được gán cho vị trí thứ 3 của mảng trong hàm getScores(). Lúc này vị trí thứ 3 là 90.


## **2. Các trường hợp ngoại lệ**

Trong trường hợp hàm getScores chỉ trả về mảng có 2 giá trị, thì lúc này biến z sẽ nhận giá trị là undefined như sau

{% highlight javascript  linenos %}

function getScores() {
   return [70, 80];
}

let [x, y, z] = getScores();

console.log(x); // 70
console.log(y); // 80
console.log(z); // undefined

{% endhighlight %}

Trong trường hợp hàm getScores trả về hơn 3 giá trị thì các giá trị bị dư ra sẽ bị loại bỏ đi.

{% highlight javascript  linenos %}

function getScores() {
   return [70, 80, 90, 100];
}

let [x, y, z] = getScores();

console.log(x); // 70
console.log(y); // 80
console.log(z); // 90

{% endhighlight %}

Trong trường hợp getScores trả về hơn 3 giá trị chúng ta có thế sử dụng tham số Rest để chứa các giá trị bị dư


{% highlight javascript  linenos %}

let [x, y ,...args] = getScores();

console.log(x); // 70
console.log(y); // 80
console.log(args); // [90, 100]

{% endhighlight %}










