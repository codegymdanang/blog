---
layout: course-typescript
title: Sử dụng Enum trong TypeScript 
slug : su-dung-enum-trong-typescript
category: laptrinhjavascript
tags: [typescript]
summery: Enum   
image: /images/blog/feature_javascript.png
description : Giúp hiểu được thuật ngữ Enum trong TypeScript là gì? Tìm hiểu về Enum, Numeric Enum, Sting Enum, Heterogeneous Enum trong ngôn ngữ lập trình TypeScript. Hướng dẫn cách sử dụng các loại Enum trong TypeScript thông qua những hình ảnh ví dụ minh hoạ các thao tác làm, cú pháp thực hiện để người đọc tham khảo và áp dụng được vào thực hành hiệu quả hơn.
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn, hôm nay anh sẽ hướng dẫn mọi người về <b>Enum</b> là như thế nào? 

## **1. Enum là gì**

Typescript cũng hỗ trợ Enum giống như Enum trong Java vậy. Enum cho phép chúng ta tạo một nhóm các giá trị hằng số trong một nơi chung.

Có 3 loại Enum là Numeric, String, Heterogeneous.


## **2. Numeric Enum là gì**

Chúng ta sử dụng từ khóa enum để tạo Enum.

{% highlight javascript  linenos %}

enum PrintMedia {
  Newspaper,
  Newsletter,
  Magazine,
  Book
}

{% endhighlight %}

Các vị trí của enum được tính từ 0 và được tăng lên 1 đơn vị. Như vậy giá trị của Newspaper, Newsletter, Magazine, Book.

{% highlight javascript  linenos %}

Newspaper = 0
Newsletter = 1
Magazine = 2
Book = 3

{% endhighlight %}

Enum luôn được gán giá trị là số khi chúng được lưu. Giá trị đầu tiên luôn là 0 và các giá trị tiếp theo là tăng lên 1.

Chúng ta có thể gán giá trị khởi tạo ban đầu cho Enum.

{% highlight javascript  linenos %}

enum PrintMedia {
  Newspaper = 1,
  Newsletter,
  Magazine,
  Book
}

{% endhighlight %}

Như vậy giá trị Newspaper là 1, thì giá trị Newsletter là 2, Magazine là 3 và Book là 4. Nếu không gán giá trị thì mặc định là 0.

- Trả về giá trị Numeric Enum trong function**

Chúng ta có thể trả về kết quả Enum trong function như sau:

{% highlight javascript  linenos %}

enum PrintMedia {
    Newspaper = 1,
    Newsletter,
    Magazine,
    Book
}

function getMedia(mediaName: string): PrintMedia {
    if (  mediaName === 'Forbes' || mediaName === 'Outlook') {
        return PrintMedia.Magazine;
    }
 }

let mediaType: PrintMedia = getMedia('Forbes'); // returns Magazine

{% endhighlight %}


## **3. String Enum là gì**

Chúng ta có thể sử dụng String trong enum như sau:

{% highlight javascript  linenos %}

enum PrintMedia {
    Newspaper = "NEWSPAPER",
    Newsletter = "NEWSLETTER",
    Magazine = "MAGAZINE",
    Book = "BOOK"
}
// Access String Enum 
PrintMedia.Newspaper; //returns NEWSPAPER
PrintMedia['Magazine'];//returns MAGAZINE

{% endhighlight %}

## **4. Heterogeneous Enum là gì**

Heterogeneous là có thể chứa chữ và số.

{% highlight javascript  linenos %}

enum Status { 
    Active = 'ACTIVE', 
    Deactivate = 1, 
    Pending
}

{% endhighlight %}







