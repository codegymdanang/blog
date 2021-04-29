---
layout: course-docker
title: Docker Image
slug : cai-dat-docker-image
category: devops
tags: [docker]
summery: Docker Image
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta hiểu về Docker Image và cách cài đặt Docker Image.

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người hiểu về <b> Docker Image </b>. Trong Docker mọi thứ đều dựa trên image. Anh ví dụ như anh muốn cài mysql vào máy mình thì trước hết anh sẽ lên docker hub gõ lệnh docker run image của mysql về máy. Sau đó chạy lệnh để start mysql lên dựa vào image.

Nếu các em đã từng ghost win thì các em sẽ thấy chúng ta có 1 image của win. Sau đó chúng ta giải nén (bung) nó ra nhiều máy khác nhau. Khi giải nén xong thì tất cả các máy tính đều có chung 1 cấu hình. 

## **1. Hiển thị các images có trong máy**

Chúng ta sử dụng lệnh docker images để hiển thị các image có trong máy tính.

{% highlight javascript  linenos %}

sudo docker images

{% endhighlight %}

Chúng ta sẽ thấy các images như sau:

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/displaying_docker_images.jpeg){:class="img-responsive"}
{: refdef}

Trong đó :
- Tag : Được sử dụng để đánh dấu phiên bản của image <br>
- Image Id : Định danh số của Image <br>
- Created : Ngày mà Image được tạo ra <br>
- Vỉtual size : Kích thước của image <br>

## **2. Download Docker Images**

Để download Image từ Docker Hub về máy ta sử dụng cú pháp lệnh docker run image.

{% highlight javascript  linenos %}

docker run image 

{% endhighlight %}

- Trong đó image là tên của Image mà chúng ta cần download về. Ví dụ như chúng ta muốn download ảnh hệ điều hành centos.

{% highlight javascript  linenos %}

sudo docker run centos 

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/downloading_docker_images.jpeg){:class="img-responsive"}
{: refdef}

## **3. Remove Docker Images**

Để xoá Image có trong máy ta sử dụng lệnh docker rmi với cú pháp như sau:

{% highlight javascript  linenos %}

docker rmi ImageID

{% endhighlight %}

Ví dụ như ta muốn xoá Image có Id là 7a86f8ffcb25

{% highlight javascript  linenos %}

sudo docker rmi 7a86f8ffcb25 

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/removing_docker_images.jpeg){:class="img-responsive"}
{: refdef}

## **4. Trả về Images ID**

Nếu chúng ta muốn trả về tất cả các Image Id có trong hệ thống thì chúng ta dùng command sau đây.

{% highlight javascript  linenos %}

sudo docker images -q 

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_images_q.jpeg){:class="img-responsive"}
{: refdef}

## **5. Xem chi tiết Images**

Chúng ta sử dụng docker inspect để xem chi tiết của một images. Ví dụ như chúng ta muốn xem chi tiết Image jenkins.

{% highlight javascript  linenos %}

sudo docker inspect jenkins 


{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_inspect.jpeg){:class="img-responsive"}
{: refdef}







