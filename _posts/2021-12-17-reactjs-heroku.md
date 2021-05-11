---
layout: course-reactjs
title: Deploy reactjs trên Heroku 
slug : deploy-reactjs-tren-heroku
category: laptrinhjavascript
tags: [reactjs]
summery: Deploy Heroku
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta  hiểu về Deploy reactjs trên Heroku trong react. Lần lượt giới thiệu và và đi qua các ví dụ về Deploy reactjs trên Heroku được sử dụng trong reactjs.

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người hiểu về <b>Deploy reactjs trên Heroku <b> trong reactjs. Trước khi vào nội dung chính mình tìm hiểu qua về 

## **1. Giới thiệu Heroku**

Heroku là một nền tảng cloud cho phép deploy các ứng dụng miễn phí. Các developer có thể sử dụng heroku  để triển khai việc deploy, quản lý và mở rộng ứng dụng. 

Hiện tại Heroku đã hỗ trợ nhiều ngôn ngữ lập trình: javaScript, Ruby, PHP,… 

Heroku nó rất tiện lợi và linh hoạt, nó cũng có một   vài ưu nhược điểm như sau: 

Ưu điểm: Hỗ trợ database, SSL free, liên kết với Github đơn giản. 

Nhược điểm:  

- Heroku chỉ cho phép người dùng sử dụng 550 giờ miễn phí, nếu muốn sử dụng thêm giờ thì mình phải trả thêm tiền. 

- Sau vài giờ nếu không có người truy cập thì server nó sẽ chuyển về trạng thái sleep,  đó là lý do tại sao nếu các bạn để lâu không truy cập vô ứng dụng, khi truy cập cập lại lần đầu thì ứng dụng sẽ load hơi lâu một tý.  

## **2. Cài đặt**

Để cài đặt Heroku trên hệ điều hành ubuntu linux, các bạn bật teminal và chạy lệnh dưới đây: 

{% highlight javascript  linenos %}

sudo snap install heroku --classic 

{% endhighlight %}

Để kiểm tra đã cài đặt ok chưa thì các bạn chạy: 

{% highlight javascript  linenos %}

heroku –version 

{% endhighlight %}

Nếu hiện kết quả như bên dưới nghĩa là đã cài đặt thành công nhé 

 
Đối với các hệ điều hành khác các bạn xem hướng dẫn ở đây nhé: 

https://devcenter.heroku.com/articles/getting-started-with-nodejs#set-up 

## **3. Khởi tạo ứng dụng**


Các bạn tạo một ứng dụng reactjs bằng lệnh teminal như bên dưới 

{% highlight javascript  linenos %}

create-react-app deploy_with_heroku 

{% endhighlight %}

Tiếp theo cd tới folder của ứng dụng: 

{% highlight javascript  linenos %}

cd deploy_with_heroku 

{% endhighlight %}

## **4. Deploy ứng dụng**

Để deploy ứng dụng, đầu tiên các bạn cần login vào heroku trước, chạy lệnh bên dưới để login: 

{% highlight javascript  linenos %}

heroku login 

{% endhighlight %}

Sau khi login thành công, thì các bạn chạy lệnh  

{% highlight javascript  linenos %}

heroku create 

{% endhighlight %}

để khởi tạo ứng dụng trên Heroku. Khi chạy xong, một ứng dụng với  tên mặc định đã sẵn sàng để bắt đầu quá trình deploy, đồng thời một git repository cũng đã được khởi tạo và đã liên kết với git local của các bạn.  

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/reactjs/heroku1.png){:class="img-responsive"}
{: refdef}
 
Trong ví dụ của mình các bạn có thể thấy sau khi mình khởi tạo thành công thì một ứng dụng đã được tạo ra với tên là damp-oasis-22998, tiếp theo mình git branch để kiểm tra thì mình thấy đang đứng trên nhánh master, và git remote -v  để xem remote repository của heroku mà mình đã liên kết tới. 

Ok giờ thì deploy thôi, để bắt đầu deploy thì các bạn chỉ cần push code lên.

Các bạn chạy lệnh git push heroku master để push code lên nhé. 

Vậy là xong, các bạn chạy lệnh heroku open để  open ứng dụng vừa deploy nhé, nếu màn hình hiện ra như này nghĩa là các bạn đã deploy thành công! 



{:refdef: style="text-align: center;"}
![reactjs ](/images/post/reactjs/heroku2.png){:class="img-responsive"}
{: refdef}







