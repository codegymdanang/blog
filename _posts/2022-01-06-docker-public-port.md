---
layout: course-docker
title: Quản lý Port
slug : manage-port-in-docker
category: devops
tags: [docker]
summery: Quản lý Port
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta hiểu về Quản lý Port và cách cài đặt Quản lý Port.

youtubeId: BJUJgebCM94
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người hiểu về <b> Quản lý Port </b>. 
Trong Docker các container có thể chứa đựng nhiều ứng dụng. Ví dụ như ta có thể build container chứa cả java và mysql trong đó. Mỗi ứng dụng sẽ chạy các port khác nhau ví dụ như tomcat 8080 hoặc mysql 3306. Chính vì vậy mà chúng ta cần cấu hình port các ứng dụng trên Docker.

Trong ví dụ hôm nay mình sẽ cài đặt container có chứa ứng dụng Jenkins và cấu hình port cho nó

## **1. Đăng nhập vào Docker Hub**

Đầu tiên chúng ta đăng nhập vào Docker Hub

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/simple_sing_up.jpeg){:class="img-responsive"}
{: refdef}

## **2. Tìm ứng dụng Jenkins**

Khi login vào màn hình chính của Docker Hub, chúng ta tìm ứng dụng jenkins thông qua việc search. Khi tìm thấy ứng dụng Jenkins chúng ta sẽ thấy lệnh pull jenkins về

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/local_ubuntu_server.jpeg){:class="img-responsive"}
{: refdef}

## **3. Pull Jenkins về máy mình**

{% highlight javascript  linenos %}

sudo docker pull jenkins 

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/inspect_image.jpeg){:class="img-responsive"}
{: refdef}

## **4. Docker Inspect**

Để xem container sẽ export ra port bao nhiêu ta có thể dùng lệnh inspect để xem. Trong ví dụ này chúng ta sẽ inspect image jenkins xem nó là port bao nhiêu.

{% highlight javascript  linenos %}

sudo docker inspect jenkins 

{% endhighlight %}

Chúng ta sẽ nhận được JSON 

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_inspect_output.jpeg){:class="img-responsive"}
{: refdef}

Chúng ta nhận thấy trong JSON trả về có phần "ExposedPorts" chúng ta thấy 2 cổng là 8080 và 50000. Cổng 8080 là cổng để chạy jenkins (cổng dữ liệu) còn cổng 50000 là cổng control.

Để chạy Jenkins và map với cổng 8080 và 50000 thì khi chạy docker run ta thêm tham số -p . Tham số -p có nghĩa là cổng sẽ chạy.

{% highlight javascript  linenos %}

sudo docker run -p 8080:8080 -p 50000:50000 jenkins 

{% endhighlight %}

Câu lệnh -p 8080:8080 dùng để map ứng dụng jenkins mình có thể truy cập thông qua cổng 8080.

Còn cổng -p 50000:50000 là cổng mình của container chứa jenkins

Chúng ta chạy ứng dụng jenkins ở trên trình duyệt qua cổng 8080 như sau

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/unlock_jenkins.jpeg){:class="img-responsive"}
{: refdef}


## **5. Demo Video**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}






