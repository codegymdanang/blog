---
layout: course-design-pattern
title: Sử dụng Singleton Design Pattern
slug : singleton-design-pattern
category: craftmanship
tags: [designpattern]
summery: Singleton
image: /images/blog/design-patterns.png
description : Sử dụng Singleton design pattern trong lập trình java. Hướng dẫn sử dụng Singleton design pattern trong học lập trình java thông qua các ví dụ. Hiểu nguyên lý  khi nào sử dụng Singleton design pattern trong lập trình.
youtubeId: QWPCGYS7XiM
---

{% include toc.html %}

# **Giới thiệu nội dung bài viết**

Chào các em, chủ đề hôm nay của anh sẽ bàn về <b>Design Pattern</b> là <b>Singleton </b> ? Khi nào chúng ta sẽ dùng nó trong lập trình.

<br>
# **1- Singleton Là gì ?**

Singleton Pattern giúp chúng ta tạo ra một đối tượng duy nhất trong hệ thống. Ví dụ như anh muốn xây dựng đối tượng cache. Thì trong toàn bộ chương trình anh chỉ có một đối tượng đó chứa các giá trị. Các modules khác trong hệ thống có thể lấy giá trị này ra. Cho dù nhiều module cùng thao tác lấy giá trị từ cache , nhưng giá trị vẫn lấy ra và cập nhật đúng vì trong cả chương trình ta chỉ có 1 đối tượng cache duy nhất. Nó được dùng để chia sẻ với các modules mà gọi nó.

# **2- Khi nào nên dùng Singleton**

+ Khi chúng ta muốn có một đối tượng duy nhất xuyên suốt ứng dụng.

<br>
# **3- Xem Video Singleton**


{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}