---
layout: course-docker
title: Docker Container
slug : cai-dat-docker-container
category: devops
tags: [docker]
summery: Docker Container
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta hiểu về Docker Container và cách cài đặt Docker Container .

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người hiểu về <b> Docker Container </b>. Chúng ta đã có Image nhưng cái này vẫn chưa chạy được. Ví dụ như mình đã download mysql Image về thì đó chỉ là bước ban đầu. Để chạy được mysql thì chúng ta phải run lệnh docker run để tạo ra một container của mysql. Lúc này chúng ta mới có thể tạo các kết nối đến mysql.

## **1. Chạy docker container**

Chúng ta sử dụng lệnh docker run để tạo ra container dựa trên Image đã download về. Trong ví dụ này anh giả sử như chúng ta download Image về hệ điều hành centos và sau đó chạy hệ điều hành này như sau.

{% highlight javascript  linenos %}

sudo docker run –it centos

{% endhighlight %}

Sau khi chạy lệnh docker run xong thì chúng ta sẽ có 1 hệ điều hành centos trên máy của mình.

## **2. Xem docker container**

Để xem tất cả các container đang chạy  trong máy chúng ta sẽ chạy lệnh docker ps như sau :

{% highlight javascript  linenos %}

docker ps

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/listing_of_containers.jpeg){:class="img-responsive"}
{: refdef}

## **3. Xem tất cả docker container**

Để xem tất cả các container đang chạy và không chạy chúng ta sử dụng lệnh docker ps -a như sau


{% highlight javascript  linenos %}

docker ps -a

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_ps_a.jpeg){:class="img-responsive"}
{: refdef}

## **4. Xem lịch sử docker container**

Để xem các commands đã chạy Image của container chúng ta sử dụng lệnh docker history imageID

{% highlight javascript  linenos %}

sudo docker history centos

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_history.jpeg){:class="img-responsive"}
{: refdef}

## **5. Xem các top các processes container**

Để xem top các process đang chạy của container ta sử dụng command docker top ContainerID 
Ví dụ như anh muốn xem các process của ContainerID là 9f215ed0b0d3 anh thực hiện command như sau.

{% highlight javascript  linenos %}

sudo docker top 9f215ed0b0d3 

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_top.jpeg){:class="img-responsive"}
{: refdef}

## **6. Dừng (stop) container**

Để dừng hay stop một container ta sử dụng lệnh docker stop containerID.

{% highlight javascript  linenos %}

sudo docker stop 9f215ed0b0d3 

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_stop.jpeg){:class="img-responsive"}
{: refdef}

## **7. Xoá container**

Để xoá 1 container ta sử dụng lệnh docker rm containerID.

{% highlight javascript  linenos %}

sudo docker rm 9f215ed0b0d3 

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_rm.jpeg){:class="img-responsive"}
{: refdef}

## **8. Lấy thông số container**

Để lấy các thông số của container đang chạy chúng ta sử dụng command docker stats containerID.

{% highlight javascript  linenos %}

sudo docker stats 9f215ed0b0d3 

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_stats.jpeg){:class="img-responsive"}
{: refdef}

## **9. Pause container**

Để tạm dừng một container ta sử dụng command docker pause ContainerID

{% highlight javascript  linenos %}

sudo docker pause 07b0b6f434fe 


{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_pause.jpeg){:class="img-responsive"}
{: refdef}

## **10. UnPause container**

Để UnPause một container ta sử dụng command docker unpause ContainerID

{% highlight javascript  linenos %}

sudo docker unpause 07b0b6f434fe 

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_unpause.jpeg){:class="img-responsive"}
{: refdef}

## **11. Kill container**

Để Kill một container ta sử dụng command docker kill ContainerID

{% highlight javascript  linenos %}

sudo docker kill 07b0b6f434fe 

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_kill.jpeg){:class="img-responsive"}
{: refdef}

## **12. Docker Attach**

Chúng ta sử dụng lệnh docker attach để kết nối terminal mà ta đang dùng tới một container đang chạy. Cái này giống như việc mình sử dụng terminal ssh vào server.

Trong ví dụ dưới đây chúng ta start container đang chạy tên là topdemo

{% highlight javascript  linenos %}

docker run -d --name topdemo ubuntu /usr/bin/top -b


{% endhighlight %}

Sau đó chúng ta connect tới container topdemo bằng lệnh docker attach

{% highlight javascript  linenos %}


docker attach topdemo

{% endhighlight %}

## **13. Docker DeAttach**

Khi mình muốn chạy container ở chế độ ngầm định (không cần hiển thị output của container đang chạy lên terminal). Chúng ta sẽ sử dụng command --detach và viết tắt là -d.

Ví dụ như mình muốn chạy container có Image centos sau ở dạng ngầm định.

{% highlight javascript  linenos %}


docker run -d centos 

{% endhighlight %}

## **13. Xem log trong container**

Để xem được log khi container đang chạy chngs ta sử dụng câu lệnh docker logs. Trong câu lệnh này chúng ta có thể thêm tham số tails để hiển thị số dòng cần xem. Ví dụ sau đây anh muốn xem 1000 dòng logs của container 64d5f93bc97c

{% highlight javascript  linenos %}


docker logs --tail=1000 64d5f93bc97c

{% endhighlight %}


Để theo dõi lịch sử chạy của container thì chúng ta sử dụng tham số --follow hoặc -f

{% highlight javascript  linenos %}

docker logs -f 64d5f93bc97c

{% endhighlight %}

## **14. Chạy lệnh trong container đang chạy**

Để chạy được lệnh trong container đang chạy chúng ta sử dụng câu lệnh exec.

{% highlight javascript  linenos %}

docker exec -i -t 64d5f93bc97c /bin/bash

{% endhighlight %}

- -i : giữ cho sdin được mở <br>
- -t : terminal <br>

## **15. Vòng đời của một container**


{:refdef: style="text-align: center;"}
{: refdef}
![reactjs ](/images/post/docker/container_lifecycle.jpeg){:class="img-responsive"}
{: refdef}

















