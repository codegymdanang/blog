---
layout: course-docker
title: Public Repository
slug : public-repository-docker
category: devops
tags: [docker]
summery: Public Repository
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta hiểu về Public Repository và cách cài đặt Public Repository.

youtubeId: a1sbo4oQpZg
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người hiểu về <b> Public Repository </b>. Sau khi chúng ta đã có Image bây giờ chúng ta muốn chia sẻ cho các thành viên trong nhóm mình có thể dùng được thì ta sẽ đẩy Image của mình lên Repository trên mạng. Các thành viên trong nhóm mình có thể lấy về và chạy trên máy của họ.

Trong ví dụ hôm nay chúng ta sẽ đưa Image tên là myimagee version TAG là 0.1 trên máy của mình lên upload lên DockerHub để mọi người trong team lấy về.

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/my_image.jpeg){:class="img-responsive"}
{: refdef}

## **1. Login DockerHub**

Đầu tiên chúng ta login vào docker hub ( https://hub.docker.com/) và tạo repository cho mình. Repository là nơi mình chứa đựng Image.

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_hub.jpeg){:class="img-responsive"}
{: refdef}


## **2. Tạo Repository**

Chúng ta đặt tên cho repository là demorep và click vào nút "Create Repository" 

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/demorep.jpeg){:class="img-responsive"}
{: refdef}

Khi repository được tạo xong thì chạy lệnh pull để kết nối với repository

{% highlight javascript  linenos %}

docker pull demousr/demorep

{% endhighlight %}

## **3. Tag Version**

Chúng ta tag lại version cho myimage giống version trên docker hub.

{% highlight javascript  linenos %}

sudo docker tag ab0c1d3744dd demousr/demorep:1.0

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_tag.jpeg){:class="img-responsive"}
{: refdef}

## **4. Đẩy Image lên DockerHub**

Login vào Docker Hub bằng terminal và cung cấp username và password giống như trên website

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_login_command.jpeg){:class="img-responsive"}
{: refdef}

Sau đó chúng ta sử dụng lệnh Push để đưa image lên repository tên demorep mà ta tạo trong bước 2.

{% highlight javascript  linenos %}

sudo docker push demousr/demorep:1.0 

{% endhighlight %}

Chúng ta sẽ nhận được kết quả

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_push.jpeg){:class="img-responsive"}
{: refdef}

## **5. Kiểm tra Image trên DockerHub**

Chúng ta vào lại trang Docker Hub và đi đến repository mà ta tạo ở bước 2. Chúng ta sẽ nhìn thấy Image của mình

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/tag_name_in_repository.jpeg){:class="img-responsive"}
{: refdef}

## **6. Lấy Image trên DockerHub**

Để lấy Image về bất kỳ máy nào chúng ta sử dụng lệnh pull.

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/docker/docker_pull_command.jpeg){:class="img-responsive"}
{: refdef}

## **7. Demo Video**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}








