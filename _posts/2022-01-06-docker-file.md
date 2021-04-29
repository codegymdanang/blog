---
layout: course-docker
title: Docker File
slug : cai-dat-docker-container
category: devops
tags: [docker]
summery: Docker File
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta hiểu về Docker File và cách cài đặt Docker File .

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người hiểu về <b> Docker File </b>. Các ví dụ ở bài trên các em thấy chúng ta lấy image centos từ Docker hub về và cài vào máy. Docker cũng cho phép chúng ta tự tạo Image cho riêng mình theo ý mình mong muốn.


## **1. Bước 1**

Chúng ta tạo một file tên là Dockerfile. Trên Ubuntu chúng ta sẽ sử dụng lệnh vim hoặc vi để tạo file như sau:

{% highlight javascript  linenos %}

sudo vim Dockerfile

{% endhighlight %}

## **2. Bước 2**

Sau khi tạo file xong thì mình sẽ thêm nội dung cho file như sau. Trong ví dụ này chúng ta sẽ tạo Image về hệ điều hành ubuntu và cài đặt nginx trên ubuntu cho riêng mình.

{% highlight javascript  linenos %}

FROM ubuntu 
MAINTAINER nguyen@gmail.com 

RUN apt-get update 
RUN apt-get install –y nginx 
CMD [“echo”,”Image created”]

{% endhighlight %}

- FROM : Nó nói cho docker phải tìm Image là ubuntu. <br/>
- MAINTAINER :  Tên người sẽ bảo trì Image này. <br/>
- RUN : dùng để chạy các lệnh trong Image. Trong trường hợp này chúng ta chạy lệnh apt-get install hoặc update để cài đặt và cập nhật các phần mềm trên ubuntu của chúng ta.

Sau đó chúng ta lưu file lại.

## **3. Bước 3**

Để build docker file thành Image thì chúng ta sử dụng lệnh docker build. <br/>

Cú pháp như sau : <br>

{% highlight javascript  linenos %}

docker build  -t ImageName:TagName dir

{% endhighlight %}

- t : tham số tag cho Image <br/>
- ImageName : Tên của Image <br/>
- TagName   : Tên Tag cho Image <br/>
- dir       : Folder nơi chức Docker File

Ví dụ như sau

{% highlight javascript  linenos %}

sudo docker build –t myimage:0.1 . 

{% endhighlight %}

- myimage : tên ta gán cho image.
- 0.1     : Tag Number ta gán cho image.
- .       : Chúng ta sử dụng dấu . ở cuối câu để nói  docker file biết ta đang đứng ở thư mục đang làm việc.

Khi chạy docker build chúng ta sẽ thấy kết quả sau. Ubuntu sẽ được download từ Docker Hub nếu như chưa có Image nào trong máy của ta. Nếu có rồi thì nó sẽ không lên Docker Hub pull về nữa. Do lần đầu tiên ta chạy nên máy mình không có Image Ubuntu.

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/no_image.jpeg){:class="img-responsive"}
{: refdef}

Để kiểm tra image chúng ta vừa tạo thì mình sử dụng docker images để xem các Image trong máy.


{% highlight javascript  linenos %}

docker images

{% endhighlight %}


{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/built_message_id.jpeg){:class="img-responsive"}
{: refdef}









