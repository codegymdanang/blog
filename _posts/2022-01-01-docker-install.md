---
layout: course-docker
title: Cài đặt docker trên ubuntu
slug : cai-dat-docker-tren-ubuntu
category: devops
tags: [docker]
summery: Cài đặt trên Ubuntu
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta hiểu về docker và cách cài đặt docker trên Ubuntu.

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người hiểu về <b> cài đặt Docker <b> trên ubuntu. 

## **1. Bước 1**

Trước khi cài đặt docker chúng ta sẽ kiểm tra và đảm bảo rằng hệ điều hành Linux kernel đang cài đặt đúng version vì docker được thiết kế chạy trên Linux kernel 3.8 và các phiên bản cao hơn. Chúng ta kiểm tra bằng cách chạy command uname như sau.

Uname là phương thức trả về các thông tin của hệ điều hành Linux. Chúng ta gõ lệnh sau


{% highlight javascript  linenos %}

uname -a

{% endhighlight %}

Tham số a có nghĩa là chúng ta muốn trả về các thông tin của hệ điều hành. Sau khi chạy câu lệnh trên ta sẽ nhận được các kết quả như sau.

{% highlight javascript  linenos %}

kernel name
node name
kernel release
kernel version
machine
processor
hardware platform
operating system

{% endhighlight %}

Ví dụ như ta chạy command uname -a . Ta sẽ nhận được kết quả là

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/output.jpeg){:class="img-responsive"}
{: refdef}

Từ kết quả trên chúng ta thấy được rằng hệ điều hành linux của chúng là version 4.2.0-27

## **2. Bước 2**

Chúng ta cần phải cập nhật OS với phiên bản cuối cùng bằng cách thực hiện comand apt-get. Phương thức này sẽ cài đặt các package từ mạng về hệ thống Linux của chúng ta

Cú pháp 

{% highlight javascript  linenos %}

sudo apt-get update

{% endhighlight %}

Sudo : có nghĩa là ta chạy câu lệnh này với permission là quyền admin (root). 
Update : tham số có nghĩa là ta cập nhật tất cả các packages trên hệ thống Linux

Ví dụ như sau

{% highlight javascript  linenos %}

sudo apt-get update

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/example_output.jpeg){:class="img-responsive"}
{: refdef}

Command ở trên sẽ download tât cả các thư viện mới nhất về hệ thống linux của chúng ta.

## **3. Bước 3**

Chúng ta cần phải cài đặt các certificate để có thể download một số package cần thiết cho Docker. Chúng ta thực hiện command sau đây để cài đặt các certificate.

{% highlight javascript  linenos %}

sudo apt-get install apt-transport-https ca-certificates

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/necessary_docker_packages.jpeg){:class="img-responsive"}
{: refdef}

## **4. Bước 4**

Chúng ta sẽ cài đặt GPG key để đảm bảo cho việc cài đặt các thư viện mã hoá khi chúng ta cài đặt các thư viện trong docker.

Command dưới đây sẽ download key với ID là 58118E89F3A912897C070ADBF76221572C52609D từ keyserver hkp://ha.pool.sks-keyservers.net:80 sau đó thêm key này vào hệ thống keychain.

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/new_pgp_key.jpeg){:class="img-responsive"}
{: refdef}

## **5. Bước 5**

Phụ thuộc vào phiên bản của Ubuntu mà các em sẽ thêm những website liên quan của docker vào file docker.list trong apt package manager. Khi chúng ta download một thư viện nào từ docker thì OS chúng ta tự động biết cần docker site nào để lấy về.

{% highlight javascript  linenos %}

Precise 12.04 (LTS) ─ deb https://apt.dockerproject.org/repoubuntu-precise main

Trusty 14.04 (LTS) ─ deb https://apt.dockerproject.org/repo/ ubuntu-trusty main

Wily 15.10 ─ deb https://apt.dockerproject.org/repo ubuntu-wily main

Xenial 16.04 (LTS) - https://apt.dockerproject.org/repo ubuntu-xenial main

{% endhighlight %}

Ví dụ như nếu OS của chúng ta là Ubuntu 14.04 thì chúng ta sẽ sử dụng Repository có tên là "deb https://apt.dockerproject.org/repo/ ubuntu-trusty main". Chúng ta sẽ add vào docker.list với câu lệnh command như sau.

{% highlight javascript  linenos %}

echo "deb https://apt.dockerproject.org/repo ubuntu-trusty main” 
   | sudo tee /etc/apt/sources.list.d/docker.list

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_list.jpeg){:class="img-responsive"}
{: refdef}

## **6. Bước 6**

Cập nhật các thư viện trên hệ thống OS của chúng ta thông qua lệnh apt-get update.

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/apt_get_update_command.jpeg){:class="img-responsive"}
{: refdef}

## **7. Bước 7**

Chúng ta kiểm tra các package đang trỏ tới đúng repository hay không thông qua câu lệnh apt-cache command

{% highlight javascript  linenos %}

apt-cache policy docker-engine

{% endhighlight %}

Chúng ta sẽ nhận được kết quả là đang link tới 

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/apt_get_update_command1.jpeg){:class="img-responsive"}
{: refdef}

## **8. Bước 8**

Đảm bảo rằng các package trong hệ thống được cập nhật 100% done

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/packages_updation.jpeg){:class="img-responsive"}
{: refdef}

## **9. Bước 9**

Chúng ta bắt đầu cài đặt docker thông qua command sudo apt-get install –y docker-engine. Chúng ta gõ lệnh sau để cài đặt

{% highlight javascript  linenos %}

apt-cache policy docker-engine

{% endhighlight %}

Nó sẽ cài đặt và download docker từ website và cài đặt nó trên ok của chúng ta

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_engine.jpeg){:class="img-responsive"}
{: refdef}

## **10. Kiểm tra phiên bản docker**

Chúng ta sứ dụng command docker version để xem phiên bản docker của chúng ta vừa cài đặt là phiên bản bao nhiêu.

{% highlight javascript  linenos %}

sudo docker version 

{% endhighlight %}

## **11. Xem thông tin của Docker**

Để xem thông tin của docker chúng ta sử dụng command docker info như sau.

{% highlight javascript  linenos %}

docker info


{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_info_example_output.jpeg){:class="img-responsive"}
{: refdef}


