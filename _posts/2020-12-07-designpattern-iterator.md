---
layout: course-design-pattern
title: Iterator Design Pattern
slug: iterator-design-pattern
category: craftmanship
tags: [designpattern]
summery: Iterator
image: /images/blog/design-patterns.png
description : Hiểu Iterator design pattern là gì ? vì sao sử dụng Iterator design pattern. Hướng dẫn các mẫu Iterator design pattern trong học lập trình java.
youtubeId: YrQzSycsPUY
---

{% include toc.html %}

# **Giới thiệu nội dung bài viết**

Chào các em, chủ đề hôm nay của anh sẽ bàn về <b> Design Pattern</b> <b>Iterator</b> ? Khi nào chúng ta sẽ dùng nó trong lập trình.

<br>
# **1- Iterator Pattern là gì ?**

Đây là pattern giúp chúng ta có thể duyệt qua tất các tập hợp một cách như nhau. Anh lấy ví dụ mình có thể lưu mảng 10 phần tử sinh viên trong mảng array, arraylist hoặc set. Do các mảng lưu trữ dữ liệu khác nhau như Array mình dùng index để lấy giá trị phần tử như student[1] còn ArrayList thì dùng method get(1). Như vậy có cách nào mà mình có thể duyệt qua mảng mà không quan tâm cấu trúc dữ liệu của nó là Array hay ArrayList không? Thì Iterator có thể làm được.

# **2- Khi nào nên dùng Iterator**

Chúng ta sử dụng <b>Iterator</b> khi chúng ta muốn duyệt qua các phần tử trong tập hợp và không quan tâm cấu trúc nó là gì miễn là cài đặt đúng các phương thức của Iterator.


# **3- Xem Video Demo Iterator**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}