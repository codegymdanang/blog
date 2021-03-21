---
layout: course-docker
title: Cài đặt docker trên window
slug : cai-dat-docker-tren-window
category: devops
tags: [docker]
summery: Cài đặt trên Window
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta hiểu về docker và cách cài đặt docker trên Window.

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người hiểu về <b> cài đặt Docker <b> trên Window. 

Để cài đặt docker cho window chúng ta cần phải có cấu hình máy tính là chạy windows 10, 64 bit. Đồng thời Ram tối thiểu là 2GB.

Chúng ta download docker tại link [này](https://www.docker.com/products/docker-desktop)

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_toolbox.jpeg){:class="img-responsive"}
{: refdef}

## **1. Cài đặt Docker**

Sau khi download docker về chúng ta nhấn double click lên biểu tượng docker để cài đặt. Khi thấy màn hình xuất hiện ta bấm vào I accept the terms and the License Agreement và bấm nút install

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_setup.jpeg){:class="img-responsive"}
{: refdef}


Khi chương trình cài đặt xong, chúng ta bấm vào nút finish để hoàn thành quá trình cài đặt

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/finish.jpeg){:class="img-responsive"}
{: refdef}

## **2. Cài đặt Docker Toolbox**

Sau khi download file docker tool box thì mình click double vào để cài đặt docker toolbox.

- Step 1 : Click Next button để bắt đầu 

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_toolbox_next.jpeg){:class="img-responsive"}
{: refdef}

- Step 2 : Chọn folder sẽ cài đặt.

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/destination_location.jpeg){:class="img-responsive"}
{: refdef}

- Step 3 : Chọn chế độ cài mặc đinh.

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/select_components.jpeg){:class="img-responsive"}
{: refdef}

- Step 4 : Thêm một số task vụ cần thiết 

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/additional_tasks.jpeg){:class="img-responsive"}
{: refdef}

- Step 5 : Sau khi đã chọn các thông số cần thiết thì bấm Install để cài đặt docker toolbox

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/install.jpeg){:class="img-responsive"}
{: refdef}


## **3. Làm việc với Docker Toolbox**

Sau khi cài đặt xong docker toolbox thì ta sẽ thấy biểu tượng để chạy như sau :

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/quickstart_terminal.jpeg){:class="img-responsive"}
{: refdef}

Tiếp đến chúng ta sẽ thấy một số configure được chạy khi Docker toolbox được load lên

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_toolbox_launched.jpeg){:class="img-responsive"}
{: refdef}

Sau khi đã chạy xong thì chúng ta sẽ có giao diện toolbox để làm việc với docker như sau

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/interactive_shell.jpeg){:class="img-responsive"}
{: refdef}

## **4. Test Docker Toolbox**

Để test docker đã cài đặt thành công hay không chúng ta sẽ sử dụng lệnh docker run để download và chạy ứng dụng HelloWorld docker container như sau

{% highlight javascript  linenos %}

sudo docker run hello-world

{% endhighlight %}

Sau khi chạy command docker run chúng ta sẽ nhận được kết quả như sau

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_container.jpeg){:class="img-responsive"}
{: refdef}













