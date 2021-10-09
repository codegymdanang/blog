---
layout: course-design-pattern
title: Sử dụng Strategy trong lập trình java
slug : strategy-design-pattern
category: craftmanship
tags: [designpattern]
summery: Strategy pattern
image: /images/blog/design-patterns.png
description : Sử dụng Strategy trong lập trình java. Hướng dẫn sử dụng Strategy factory trong học lập trình java thông qua các ví dụ. Hiểu nguyên lý  khi nào sử dụng Strategy factory trong lập trình.
youtubeId: M11bDjG2w7o
---

{% include toc.html %}

# **Giới thiệu nội dung bài viết**

Chào các em, chủ đề hôm nay của anh sẽ bàn về <b>Design Pattern</b> <b>Method Factory</b> ? Khi nào chúng ta sẽ dùng nó trong lập trình.

<br>
# **1- Strategy Pattern là gì ?**

Chúng ta dùng <b>Strategy Pattern</b> để quản lý thuật toán , các mối quan hệ giữa các object trong ứng dụng.

# **2- Khi nào nên dùng Abstract Factory**

Chúng ta sử dụng <b>Strategy</b> khi chúng ta muốn chọn một thuật toán cho một đối tượng cụ thể lúc runtime (chương trình đang chạy). Ví dụ như thuật toán thanh toán cho khi mua hàng online trên mạng. Chúng ta có thể thanh toán bằng thẻ visa hay master. Thì khi chương trình mình đang chạy nếu người dùng chọn visa thì mình sẽ dùng thuật toán tính tiền của visa để thanh toán. Như vậy ta wrap các thuật toán, các business thành một đối tượng và sử dụng nó.


# **3- Xem Video Strategy**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}