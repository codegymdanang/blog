---
layout: course-html
title: Sử dụng media trong HTML
slug : su-dung-media-trong-html
category: laptrinhweb
tags: [html]
summery: Media
image: /images/blog/angular.png
description : Sử dụng các media như âm thanh, hình ảnh, video để nhúng vào trong HTML trong lập trình web
youtubeId: 56tXo8Y6N88
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Nếu bạn quan sát trên các trang website, bạn có thể thấy các trang web hiện nay có thể hiển thị cả chữ và phần media bao gồm hình ảnh, video, nhạc, audio, phim, âm thanh. Trong đó, để nhúng các thành phần <b>media vào website trong lập trình web HTML</b>, chúng ta phải sử dụng thẻ media.
<br>
Cụ thể sử dụng <b>thẻ media</b> như thế nào để nhúng media vào trang web? Bài viết hôm nay anh sẽ lần lượt giới thiệu cho các bạn hiểu được Multimedia là gì? Các định dạng Multimedia trong HTML? Sau đó hướng dẫn cụ thể các bạn cách để thêm các video, âm thành và video từ YouTube vào website trong <b>lập trình web HTML</b>.


## **1. Multimedia là gì**

Trong <b>lập trình web html</b> chúng ta có thể thêm hình ảnh, video, nhạc, film, âm thanh vào trang web. Những cái trên được gọi là Media.

Trước đây trình duyệt chỉ hỗ trợ chữ (text) thôi, không hiển thị được âm thanh, ảnh và video.

## **2. Định dạng Multimedia**

Chúng ta có rất nhiều định dạng khác nhau cho Media. Anh ví dụ như video thì mình có các định dạng là avi, mpeg, wmv, mov, mp4.

Nếu nói về âm thanh thì mình có các định dạng như mid, wav, mp3, wma.

Chúng ta chỉ cần nhúng vào HTML thì có thể sử dụng được.

## **3. Nhúng video vào website**

Để nhúng video vào website ta sử dụng thẻ html là video. Trong thẻ video chúng ta khai báo kích thước chiều rộng của video và nơi mình chứa video như đoạn code sau. Nếu như trình duyệt mình không hỗ trợ video thì mình sẽ nhận được thông báo là trình duyệt chưa hỗ trợ thẻ video. Lúc này mình cần cập nhật lại phiên bản mới của trình duyệt

{% highlight html linenos %}

<!DOCTYPE html> 
<html> 
<body> 

<video width="400" controls>
  <source src="mov_bbb.mp4" type="video/mp4">
  Trình duyệt mình không hỗ trợ video
</video>

<p>
Video courtesy of 
<a href="https://www.bigbuckbunny.org/" target="_blank">Big Buck Bunny</a>.
</p>

</body> 
</html>

{% endhighlight %} 

## **4. Nhúng âm thanh vào website**

Để nhúng âm thanh vào trang website chúng ta sử dụng thẻ audio. Trong đó chúng ta khai báo nơi chứa file video và định dạng của file là gì

{% highlight html linenos %}

<audio controls>
  <source src="horse.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>

{% endhighlight %} 

Thuộc tính controls sẽ giúp ta hiển thị các nút play, pause âm thanh

## **5. Nhúng video từ youtube vào website**

Để nhúng một video từ youtube vào website chúng ta sử dụng thẻ iframe. Trong thẻ này chúng ta quy định kích thước dài, rộng, và đường link youtube tới video của chúng ta.

{% highlight html linenos %}

<!DOCTYPE html>
<html>
<body>

<iframe width="420" height="345" src="https://www.youtube.com/embed/tgbNymZ7vqY">
</iframe>

</body>
</html>

{% endhighlight %} 


## **6. Video Demo**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}


## **7. Thực hành online và source code**

{:refdef: style="text-align: center;"}
<a href="https://levunguyen.com/hoc-lap-trinh-online-editor-js/" target="_blank"> ![Sourcecode ](/images/icon/tryit.png){:class="img-responsive"} </a>
{: refdef}

{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/HTML-Media" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}










