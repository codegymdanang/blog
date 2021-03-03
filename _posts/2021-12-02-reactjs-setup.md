---
layout: course-reactjs
title: Tạo ứng dụng ReactJS 
slug : tao-ung-dung-reactjs
category: laptrinhjavascript
tags: [reactjs]
summery: Tạo ứng dụng
image: /images/blog/feature_javascript.png
description : Trình bày cách tạo ứng dụng web với reactjs.

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách <b> tạo ứng dụng reactjs <b> bằng công cụ create react app.  
Hiểu được cách cài đặt các công cụ để chạy được ứng dụng reactjs. Hiểu được nodejs và npm được sử dụng trong dự án react js.

## **1. Cài đặt môi trường**

Trong bài này chúng ta sẽ học cách cấu hình và cài đặt các thư viện để chạy được ứng dụng reactjs. Chúng ta cần sử dụng NodeJS để chạy ứng dụng reactjs nếu như các em chưa cài đặt NodeJS thì việc đầu tiên chúng ta sẽ cài NodeJS ở link [sau](https://nodejs.org/en/download/). 

Sau khi cài đặt NodeJS xong thì bước tiếp theo chúng ta sẽ cài đặt npm để quản lý các thư viện và lấy các thư viện cần dùng cho dự án reactjs về. Nếu các em đã từng học maven thì npm cũng giống các tính năng của maven.

Có 2 cách để tạo ứng dụng reactjs như sau


+ Cách 1 : Chạy ứng dụng bằng cách sử dụng webpack và babel
+ Cách 2 : Chạy ứng dụng bằng command line create-react-app.

Trong khoá học này chúng ta sẽ sử dụng cách 2 để tạo ứng dụng reactjs. Bởi vì nó rất tiện lợi cho những người mới bắt đầu học reactjs.

## **2. Sử dụng create-react-app**

+ Bước 1 : Để tạo được ứng dụng bằng lệnh create-react-app yêu cầu chúng ta phải sử dụng phiên bản node >= 10.16 và npm >=5.6
Để tạo ứng dụng reactjs chúng ta sử dụng câu lệnh sau. Trong ví dụ này chúng ta tạo ứng dụng tên my-app


{% highlight javascript  linenos %}

C:\Users\Tutorialspoint\Desktop>npx create-react-app my-app

{% endhighlight %}

+ Bước 2 : Xoá hết các source code có sẳn mà tool đã tạo

{% highlight javascript  linenos %}

C:\Users\Tutorialspoint\Desktop>cd my-app/src
C:\Users\Tutorialspoint\Desktop\my-app\src>del *
C:\Users\Tutorialspoint\Desktop\my-app\src\*, Are you sure (Y/N)? y

{% endhighlight %}

+ Bước 3 : Thêm các file index.js và index.css vào trong folder src để tạo giao diện riêng cho mình

{% highlight javascript  linenos %}

C:\Users\Tutorialspoint\Desktop\my-app\src>type nul > index.css
C:\Users\Tutorialspoint\Desktop\my-app\src>type nul > index.js

{% endhighlight %}

+ Bước 4 : Thêm nội dung cho file index.js

{% highlight javascript  linenos %}

import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';

{% endhighlight %}

+ Bước 5 : Chạy ứng dụng thông qua lệnh command

{% highlight javascript  linenos %}

npm start

{% endhighlight %}

+ Bước 6 : Chúng ta nhận được kết quả như sau

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/reactjs/run_the_project_reactjs.jpg){:class="img-responsive"}
{: refdef}









