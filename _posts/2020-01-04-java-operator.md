---
layout: course-java
title: Toán tử trong lập trình Java
slug : toan-tu-trong-lap-trinh-java
category: laptrinhjava
tags: [java core]
summery: Toán tử  
image: /images/blog/java.png
description :Bài viết Toán tử này nằm trong loạt bài chia sẻ về kiến thức lập trình Java. Các bài chia sẻ đi từ cơ bản đến các kiến thức nâng cao. Toán tử trong lập trình Java hướng đối tượng là một trong những kiến thức Java căn bản cần nắm. Vậy cụ thể có bao nhiêu nhóm Toán tử, mỗi nhóm bao gồm những loại nào? Trong lập trình Java có tất cả 5 nhóm Toán tử: toán tử số học, số gán, so sánh, logic và bit; trong đó tuỳ mỗi nhóm mà có số lượng loại khác nhau.
youtubeId: jDR0dwYp8n4
codeid : 2X1r
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Đối với người học ngôn ngữ <b>lập trình Java</b>, <b>toán tử</b> đã trở thành khái niệm quen thuộc. Nhờ vào các nhóm toán tử đa dạng trong Java mà người dùng thao tác với các biến linh hoạt hơn. Bài viết dưới đây sẽ giúp bạn hiểu hơn về <b>toán tử trong lập trình hướng đối tượng Java</b>, các khái niệm, phân loại và lợi ích của việc sử dụng chúng trong lập trình. Từ đó giúp bạn áp dụng nhuần nhuyễn vào quá trình thực hành và làm việc. 

<br>
## **Trong lập trình Java, toán tử là gì**

Trong <b>lập trình Java</b>, chúng ta sử dụng toán tử để thực hiện các phép tính toán học trên giá trị và biến.

## **1.  Toán tử số học**

{:class="table table-bordered"}
|  Toán tử		  	 		|  Ví dụ		            		|   kết quả			|
|---	                 	|---	                        	|---	     	    |
| +			         		|	x = 5 + 5						| 	x = 10			|
| -							|	x = 10 - 3						|	x = 7			|
| *							|	x -= 3 * 3						|	x = 6			|
| /							|	x = 3/1							|	x = 3			|
| % 						|	x = 10%5						|	x = 2			|
| ++ 						|	++x								|	x tăng thêm 1 giá trị			|
| -- 						|	--x								|	x giảm đi 1 giá trị		|

## **2.  Toán tử số gán**

{:class="table table-bordered"}
|  Toán tử		  	 		|  Ví dụ		            		|   kết quả			|
|---	                 	|---	                        	|---	     	    |
| =			         		|	x = 5							| 	x = 5			|
| +=						|	x += 3							|	x = x + 3		|
| -=						|	x -= 3							|	x = x - 3		|
| *=						|	x *= 3							|	x = x * 3		|
| /= 						|	x /= 3							|	x = x / 3		|
| %= 						|	x %= 3							|	x = x % 3		|
| &=						|	x &= 3							|	x = x & 3		|
| \|= 						|	x |= 3							|	x = x | 3		|
| ^=		\				|	x ^= 3							|	x = x ^ 3		|
| >>=						|	x >>= 3							|	x = x >> 3		|
| <<=						|	x <<= 3							|	x = x << 3		|


## **3.  Toán tử so sánh**

{:class="table table-bordered"}
|  Toán tử		  	 		|  Ví dụ		            		|   Mô tả					|
|---	                 	|---	                        	|---	     	    		|
| ==			         	|	x == y							| 	so sánh bằng			|
| !=						|	x! = y							|	so sánh không bằng		|
| >							|	x > y 							|	so sánh lớn hơn			|
| <							|	x < y 							|	so sánh nhỏ hơn			|
| >= 						|	x >= y 							|	so sánh lớn hơn hoặc bằng			|
| <= 						|	x <= y							|	so sánh nhỏ hơn hoặc bằng			|

## **4.  Toán tử logic**

{:class="table table-bordered"}
|  Toán tử		  	 		|  Ví dụ		            		|   Mô tả											|
|---	                 	|---	                        	|---	     	    								|
| &&			         	|	x < 5 &&  x < 10				| 	trả về true nếu cả 2 mệnh đề cùng đúng 			|
| \|\|						|	x < 5 || x < 4					|	trả về truế nếu 1 trong 2 mệnh đề là đúng		|
| !							|	!(x < 5 && x < 10) 				|	phủ định lại giá trị trong  kết quả 			|

## **5.  Toán tử Bit**

{:class="table table-bordered"}
|  Toán tử		  	 		|  Ví dụ		   |   Mô tả			|		Kết quả		|	Giá trị			|	
|---	                 	|---	           |---	     			|---				|---				|
| &			         		|	5 & 1		   | 0101 & 0001		|		0001		|		 1			|
| \|							|	5 | 1		   | 0101 | 0001		|		0101		|		 5			|
| ~							|	~ 5			   |~0101				|		1010		|		10			|
| ^							|	5 ^ 1		   |0101 ^ 0001			|		0100		|		4			|
| <<						|	9 << 1		   | 1001 << 1			|		0010		|		2			|
| >>						|	9 >> 1		   | 1001 >> 1			|		1100		|		12			|
| >>>						|	9 >>> 1		   | 1001 >>> 1			|		0100		|		4			|



{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}


{:refdef: style="text-align: center;"}
{% include online-editor.html codeid=page.codeid %}
{: refdef}







