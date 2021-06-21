---
layout: course-docker
title: Docker Command
slug : docker-command
category: devops
tags: [docker]
summery: Docker Command
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta hiểu về Docker Command và cách cài đặt Docker Command.

youtubeId: 8jxipATUM84
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người hiểu về <b> Docker Command </b>. Docker xây dựng sẳn các câu lệnh chỉ dẫn trong docker file. Để thực hiện các ý định ta mong muốn. Ví dụ như lấy thư viện từ link nào, mở port bao nhiêu, thực hiện câu lệnh gì trên container.

## **Câu lệnh chỉ dẫn CMD**

Câu lệnh này được thực thi khi một container được chạy.

Cú pháp như sau

{% highlight javascript  linenos %}

CMD command param1 

{% endhighlight %}

- Trong đó command 	: câu lệnh sẽ được chạy khi container được load lên
- Trong đó param1 	: tham số truyền vào cho command.


Ví dụ như anh muốn in ra từ Hello World khi container được load lên. Thì trong file docker file anh làm như sau. 

## **Bước 1- Tạo Dockerfile**

Đầu tiên anh tạo một docker file

{% highlight javascript  linenos %}

FROM ubuntu 
MAINTAINER demousr@gmail.com 
CMD [“echo” , “Hello World”]

{% endhighlight %}

Trong CMD các em thấy anh sử dụng lệnh echo để in ra màn hình chữ Hello World.

## **Bước 2- Build Image từ dockerfile**

Chúng ta sử dụng lệnh docker build để tạo Image từ dockerfile

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/build_command.jpeg){:class="img-responsive"}
{: refdef}

## **Bước 3- Chạy container**

Chúng ta sử dụng lệnh docker run để start container 

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/run_a_container.jpeg){:class="img-responsive"}
{: refdef}

Chúng ta sẽ thấy khi container load lên thì chữ Hello World hiện lên trên terminal.


## **Câu lệnh chỉ dẫn EntryPoint**

Câu lệnh chỉ dẫn Entry Point cũng khác giống với câu lệnh CMD. Nhưng khác ở chỗ Entry Point không cho phép chúng ta ghi đè giá trị.

Anh lấy ví dụ như anh có file docker file sau sử dụng CMD.

{% highlight javascript  linenos %}

FROM ubuntu:latest
RUN apt-get update && \
    apt-get install -y apache2-utils && \
    rm -rf /var/lib/apt/lists/*
CMD ab

{% endhighlight %}

Tiếp đến anh sẽ build Image dựa trên docker file này và đặt tên là ab. Mục đích đặt tên ab để anh có thể chạy docker run ab sau khi build xong Image.

{% highlight javascript  linenos %}

docker build -t ab .

{% endhighlight %}

Tiếp đến anh chạy container lên bằng lệnh docker run 

{% highlight javascript  linenos %}

docker run ab

{% endhighlight %}

Khi anh chạy lên thì sẽ bị báo lỗi 

{% highlight javascript  linenos %}

ab: wrong number of arguments
Usage: ab [options] [http[s]://]hostname[:port]/path
Options are:
    -n requests     Number of requests to perform
    -c concurrency  Number of multiple requests to make at a time
    -t timelimit    Seconds to max. to spend on benchmarking
                    This implies -n 50000
    -s timeout      Seconds to max. wait for each response
                    Default is 30 seconds
{% endhighlight %}

Nguyên nhân là do trong CMD chúng có định nghĩa CMD ab, nhưng chúng ta không chỉ ra ab là gì. Tuy nhiên do ta sử dụng CMD nên ta có thể ghi đè giá trị ab bằng một URL. 

{% highlight javascript  linenos %}

docker run ab ab https://levunguyen.com/

{% endhighlight %}

Khi chúng ta thêm ab https://levunguyen.com/ ở đằng sau câu lệnh docker run ab. Chúng ta đã ghi đè giá trị của chỉ dẫn CMD trong docker file.

Như vậy ngược lại với CMD. Entry Point không cho phép chúng ta ghi đè. Các tham số sau câu lệnh docker run sẽ được add thêm vào trong command. Để chạy lại ví dụ CMD ở trên bằng Entry Point ta chạy lệnh như sau

{% highlight javascript  linenos %}

docker run ab https://levunguyen.com/

{% endhighlight %}

## **Câu lệnh chỉ dẫn ENV**

Dùng để thiết lập các giá trị biến môi trường cho container

- Cú pháp

{% highlight javascript  linenos %}

ENV key value 

{% endhighlight %}

- Ví dụ  mình có file docker file với 2 biến môi trường var1 và var2 như sau:

{% highlight javascript  linenos %}

FROM ubuntu 
MAINTAINER demousr@gmail.com 
ENV var1=Tutorial var2=point 

{% endhighlight %}

Tiếp đến chúng ta buidl Image bằng docker build .

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/env_docker_build_command.jpeg){:class="img-responsive"}
{: refdef}

Tiếp đến chúng ta chạy container.

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/env_run_a_container.jpeg){:class="img-responsive"}
{: refdef}

Cuối cùng chúng ta chạy lệnh env để xem các giá trị biến môi trường

 {:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/env_command.jpeg){:class="img-responsive"}
{: refdef}

## **Câu lệnh chỉ dẫn WORKDIR**

Command WorkDir dùng để chỉ folder đang làm việc của container

- Cú pháp

{% highlight javascript  linenos %}

WORKDIR dirname 

{% endhighlight %}

- Ví dụ ta có docker file sau

{% highlight javascript  linenos %}

FROM ubuntu 
MAINTAINER demousr@gmail.com 
WORKDIR /newtemp 
CMD pwd 

{% endhighlight %}


- Khi chúng ta chạy container thì nhận được là

 {:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/workdir_run_command.jpeg){:class="img-responsive"}
{: refdef}

## **7. Demo Video**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}












