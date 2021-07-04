---
layout: course-docker
title: Docker Compose
slug : su-dung-docker-compose
category: devops
tags: [docker]
summery:  Docker Compose
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta hiểu về  Docker Composeg và cách cài đặt  Docker Compose.

youtubeId: 65IDC49odgM
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người hiểu về <b>  Docker Compose </b>. Thỉnh thoảng chúng ta muốn chạy nhiều container cùng một lúc như một service. Ví dụ như ta có ứng dụng chạy cần có Nginx và MySQL. Chúng ta có thể tạo ra một file mà khi chạy file này thì 2 dịch vụ (services) Nginx và MySQL sẽ chạy. 


## **1. Cài đặt Docker Compose**

Bước 1 : Chúng ta download các file cần thiết để cài đặt docker compose

{% highlight javascript  linenos %}

curl -L "https://github.com/docker/compose/releases/download/1.10.0-rc2/dockercompose
   -$(uname -s) -$(uname -m)" -o /home/demo/docker-compose

{% endhighlight %}

Chúng ta sẽ cài đặt version 1.10.0-rc2 của docker compose và lưu nó trong thư mục /home/demo/docker-compose

Bước 2 : Chúng ta cấp quyền cho folder để có thể chạy được các file trong folder /home/demo/docker-compose

{% highlight javascript  linenos %}

chmod +x /home/demo/docker-compose

{% endhighlight %}

Để xem được version của Docker compose chúng ta sử dụng lệnh 

{% highlight javascript  linenos %}

docker-compose version 

{% endhighlight %}

Ví dụ như sau 

{% highlight javascript  linenos %}

sudo ./docker-compose -version 


{% endhighlight %}

Mình sẽ nhận được thông tin về docker compose

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_compose_installation.jpeg){:class="img-responsive"}
{: refdef}

## **2. Tạo Docker Compose**

Trong ví dụ này chúng ta sẽ tạo một file docker compose mà khi chạy file này chúng ta sẽ start 2 ứng dụng là Mysql và Nginx. Chúng ta sử dụng vim để tạo một docker compose như sau

{% highlight javascript  linenos %}

sudo vim docker-compose.yml 

{% endhighlight %}

Tiếp đến chúng ta tạo nội dung 

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/compose_file.jpeg){:class="img-responsive"}
{: refdef}

Chúng ta chạy file docker command như sau

{% highlight javascript  linenos %}

sudo ./docker-compose up 


{% endhighlight %}

Comand này sẽ đọc file docker-compose.yml mà ta tạo ở bước trên và build các container cho chúng ta. Nó sẽ download các Images cần thiết về máy và start containers.

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/start_downloading.jpeg){:class="img-responsive"}
{: refdef}


## **3. Demo Video**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}











