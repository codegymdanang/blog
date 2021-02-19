---
layout: course-relationaldatabase
title: các loại toán tử trong database
slug : cac-loai-toan-tu-trong-database
category: database
tags: [database]
summery: Toán tử    
image: /images/blog/database.png
description : Trình bày về các loại toán tử trong Database. Thông qua những chia sẻ kèm theo các ví dụ được đưa ra trong bài viết sẽ giúp người đọc hiểu được và áp dụng được các phép toán tử vào lập trình Database. Bài viết lần lượt đề cập về toán tử tính toán, toán tử Bitwise, toán tử so sánh, toán tử kết hợp, toán tử logic trong Database. Cuối bài viết, tác giả cung cấp một video code demo để minh hoạ cho người đọc tham khảo thêm.
youtubeId: b-WGaGYAUQw
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay chúng ta sẽ nói về chủ đề toán tử trong Database là gì nhé?

## **1. Toán tử tính toán**


{:class="table table-bordered"}
|  Toán tử  						|  Mô tả										|
|---								|---											|
|	+								| Toán cộng										|
|	-								| Toán trừ										|
|	*								| Toán nhân										|
|	/								| Toán chia										|
|	%								| Toán mod										|

## **2. Toán tử Bitwise**

{:class="table table-bordered"}
|  Toán tử  						|  Mô tả										|
|---								|---											|
|	&								| Toán And										|
|	\| 								| Toán OR										|
|	^								| Trả về 1 nếu có 1 mệnh đề là 1 và ngược lại	|

## **3. Toán tử so sánh**

{:class="table table-bordered"}
|  Toán tử  						|  Mô tả										|
|---								|---											|
|	=								| Toán bằng										|
|	>								| Lớn hơn										|
|	<								| Nhỏ hơn										|
| 	>=								| Lớn hơn hoặc bằng								|
|	<=								| Nhỏ hơn hoặc bằng								|
|	<>								| Không bằng									|

## **4. Toán tử kết hợp**

{:class="table table-bordered"}
|  Toán tử  						|  Mô tả										|
|---								|---											|
|	+=								| Thêm giá trị bằng								|
|	-=								| Giảm giá trị bằng								|
|	\*=								| Nhân giá trị bằng								|
|	/=								| Chia giá trị bằng								|
|	%=								| Mod giá trị bằng								|
|	&=								| And giá trị bằng								|
|	^-=								| không bằng giá trị							|
| 	|\*=							| OR bằng giá trị								|

## **5. Toán tử logic**

{:class="table table-bordered"}
|  Toán tử  						|  Mô tả										|
|---								|---											|
|	ALL								| TRUE nếu tất cả câu truy vấn con là TRUE		|
| 	And 							| TRUE nếu tất cả điều kiện là TRUE 			|
|	ANY 							| TRUE nếu query con là đúng					|
| 	BETWEEN							| TRUE nếu tất cả nằm trong range					|
| 	EXITS							| TRUE nếu câu query con có trả về kết quả		|
|	IN 								| TRUE nếu câu query thoả mãn 1 trong những điều kiện|
|	LIKE							| TRUE nếu thoả mãn pattern đưa ra 				|
|	NOT 							| Hiển thị dữ liệu nếu điều kiện không phải True |
|	OR 								| TRUE nếu 1 trong 2 điều kiện là TRUE 			|
|	SOME							| TRUE nếu 1 hoặc nhiều câu query con thoả mãn điều kiện |


 
<br>
## **6. Demo Video**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **7. Source Code**

{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/Database-Mysql" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}













