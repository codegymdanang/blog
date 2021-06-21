---
layout: course-docker
title: Docker Hub
slug : cai-dat-docker-hub
category: devops
tags: [docker]
summery: Docker Hub
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta hiểu về Docker Hub và cách cài đặt Docker Hub .

youtubeId: EZgWek-CJlY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người hiểu về <b> Docker Hub </b> 
Docker Hub là một dịch vụ lưu trữ các docker trên Cloud. Chúng ta có thể download các docker image ở trên mạng và sử dụng trên máy tính của chúng ta. Ví dụ như để cài đặt mysql thay vì anh phải download file mysql trên trang chủ mysql thì bây giờ anh chỉ gõ command để lấy image mysql từ Docker Hub về và cài đặt.

Trong phát triển phần mềm thì chúng ta thường tạo và upload các file docker image lên những Docker Hub của công ty sau đó các dev sẽ lên đây lấy về.

Trang chủ docker hub tại [đây](https://www.docker.com/products)


## **1. Bước 1**

Chúng ta sign up tạo account trên docker hub

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_hub_singup.jpeg){:class="img-responsive"}
{: refdef}

## **2. Bước 2**

Khi chúng ta đăng ký thành công thì chúng ta thấy được màn hình docker hub như sau:

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/logged_into_docker_hub.jpeg){:class="img-responsive"}
{: refdef}

## **3. Bước 3**

Chúng ta muốn tìm một phần mềm cần download về máy. Trong ví dụ này anh muốn cài đặt Jenkins lên máy mình thì anh sẽ tìm Image Jenkins 

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/jenkins_image.jpeg){:class="img-responsive"}
{: refdef}

## **4. Bước 4**

Khi đã tìm kiếm thấy Image Jenkins các em kéo xuống sẽ thấy phần hướng dẫn cài đặt bằng lệnh docker pull (khi chạy docker pull nó sẽ kéo Jenkins image về máy của mình)

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/pull_command.jpeg){:class="img-responsive"}
{: refdef}


## **5. Bước 5**

Chúng ta vào Ubuntu hoặc Docker Tool chạy docker command để pull image jenkins về bằng command

{% highlight javascript  linenos %}

sudo docker pull jenkins 

{% endhighlight %}

Sau khi chạy command chúng ta sẽ thấy kết quả của tiến trình download Jenkins Image như sau

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/ubuntu_server.jpeg){:class="img-responsive"}
{: refdef}

## **6. Bước 6**

Để chạy được Jenkins Image mà ta mới download về thì ta sẽ sử dụng command docker run như sau

{% highlight javascript  linenos %}

sudo docker run -p 8080:8080 -p 50000:50000 jenkins 

{% endhighlight %}

Tham số -p đầu tiên là port sẽ chạy jenkins trong server <br>
Tham số jenkins là tên image jenkins mà ta download về máy <br>


{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/sudo_command.jpeg){:class="img-responsive"}
{: refdef}

Như vậy là ta đã cài đặt thành công Jenkins từ docker hub 

## **7. Demo Video**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}










