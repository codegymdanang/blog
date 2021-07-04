---
layout: course-docker
title: Docker log
slug : su-dung-log-trong-docker
category: devops
tags: [docker]
summery:  Docker log
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta hiểu về  Docker log và cách cài đặt  Docker log.

youtubeId: P_zAc0OBbIY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người hiểu về <b>  Docker log </b>. Nó được sử dụng trong Docker để chúng ta có thể xem thông tin về docker cũng như những lỗi xảy ra trong quá trình chạy ứng dụng. Có 4 level logs ta có thể chạy để xem lỗi và thông tin về docker.

- Debug : Hiển thị các thông tin 
- Info  : Hiển thị các thông tin và lỗi
- Error : Hiển thị các lỗi
- Fatal : Chỉ hiện thị lỗi Fatal



## **1. Các bước để xem log**

Bước 1 : Đầu tiên chúng ta sẽ stop tuyến trình deamon (Deamon là một chương trình chạy ngầm trong hệ điều hành, được kích hoạt khi có một ứng dụng, một sự kiện nào được chạy, nó không được quản lý bưởi người dùng).

{% highlight javascript  linenos %}

sudo service docker stop

{% endhighlight %}


Bước 2 : Chúng ta chạy tuyến trình deamon bằng câu lệnh sau.

{% highlight javascript  linenos %}

sudo dockerd –l debug &


{% endhighlight %}

- l : có nghĩa là tham số để ta nói log chúng ta ở level nào ví dụ debug hay info
- & : trở lại màn hình command promt sau khi log được enable.

Sau khi chạy lệnh debug thì ta sẽ nhận được các thông tin log như sau

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/debug_logs.jpeg){:class="img-responsive"}
{: refdef}

Bây giờ nếu ta thực hiện các câu lệnh Docker nào thì ta sẽ thấy thông tin hiện lên trên log. Ví dụ như anh thực hiện câu lệnh docker hiển thị tất cả các Images có trong máy, thì anh sẽ nhận được thông tin log như sau

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_images_logging.jpeg){:class="img-responsive"}
{: refdef}

## **2. Xem log trong Docker Container**

Ngoài cách xem log ở trong Deamon, chúng ta có thể xem log ở trong container mà ứng dụng đang chạy. Ví dụ như ta chạy container trong đó có hệ điều hành ubuntu như sau

{% highlight javascript  linenos %}

sudo docker run –it ubuntu /bin/bash 


{% endhighlight %}

Để xem được log trong container ubuntu chúng ta sử dụng command với cú pháp Docker logs containerID 


{% highlight javascript  linenos %}

sudo docker logs 6bfb1271fcdd  

{% endhighlight %}


Chúng ta sẽ nhận được thông tin log như sau

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/container_logging_output.jpeg){:class="img-responsive"}
{: refdef}







