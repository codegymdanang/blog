---
layout: course-python
title: Toán tử trong Python
slug : toan-tu-trong-python
category: laptrinhpython
tags: [python]
summery: Toán tử
image: /images/blog/feature_javascript.png
description : Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách sử dụng toán tử trong python là gì

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách <b>  sử dụng toán tử trong Python </b>. 
Chúng ta sẽ đi qua các loại toán tử khác nhau của python

## **1. Toán học**

{:class="table table-bordered"}
|  Toán tử         	|  Tên    					| Ví dụ 						|
|---               	|---   	     				| ---							|
|	+				|	Toán cộng				| x + y							|
|	-				|	Toán trừ				| x - y 						|
|	*				|	Toán nhân				| x * y 						|
|	/				|	Toán chia				| x / y 						|
|	%				|	Toán tử mode			| x % y 						|
| 	**				|	Lũy thừa				| x ** y   						|
| 	//				|	Chia thập phân			| x // y						|

Ví dụ về phép Lũy thừa

{% highlight python  linenos %}

    x = 2
	y = 5

	print(x ** y) #tương tự với lấy sô 2 nhân lên 5 lần 2*2*2*2*2

{% endhighlight %}

Kết quả là 32.

Ví dụ về chia thập phân lấy số nguyên dương.

{% highlight python  linenos %}

    x = 15
	y = 2

	print(x // y)

{% endhighlight %}

Kết quả là 7.

## **2. Toán tử gán**

{:class="table table-bordered"}
|  Toán tử         	|  Ví dụ    					| tương tự như 						|
|---               	|---   	     					| ---								|
|=					|x = 5							|x = 5								|	
|+=					|x += 3							|x = x + 3							|	
|-=					|x -= 3							|x = x - 3							|	
|*=					|x *= 3							|x = x * 3							|	
|/=					|x /= 3							|x = x / 3							|	
|%=					|x %= 3							|x = x % 3							|	
|//=				|x //= 3						|x = x // 3							|	
|**=				|x **= 3						|x = x ** 3							|
|&=					|x &= 3							|x = x & 3							|	
|^=					|x ^= 3							|x = x ^ 3							|	
|>>=				|x >>= 3						|x = x >> 3 						|	
|<<=				|x <<= 3						|x = x << 3							|



## **3. Toán tử So sánh**

{:class="table table-bordered"}
|  Toán tử         	|  Tên    						| Ví dụ 	 						|
|---               	|---   	     					| ---								|
|==					|Equal							|x == y								|
|!=					|Not equal						|x != y 							|	
|>					|Greater than					|x > y 								|	
|<					|Less than						|x < y								|
|>=					|Greater than or equal 			|x >= y 							|	
|<=					|Less than or equal to			|x <= y 							|

## **4. Toán tử logic**

{:class="table table-bordered"}
|  Toán tử         	|  Tên    						| Ví dụ 	 						|
|---               	|---   	     					| ---								|
|and 				|đúng nếu cả 2 cùng đúng		|x < 5 and  x < 10					|
|or					|đúng khi 1 trong 2 đúng		|x < 5 or x < 4						|
|not				|đảo ngược kết quả đúng thành sai	|not(x < 5 and x < 10)			|

## **5. Toán tử IS**

{:class="table table-bordered"}
|  Toán tử         	|  Tên    						| Ví dụ 	 						|
|---               	|---   	     					| ---								|
|is 				|trả về đúng nếu x và y giống nhau |	x is y						|
|is not				|trả về đúng nếu x khác y		|x is not y 						|

## **6. Toán tử IN**

{:class="table table-bordered"}
|  Toán tử         	|  Tên    								| Ví dụ 	 				|
|---               	|---   	     							| ---						|
|in 				|trả về true nếu giá trị x có trong y	| x in y 					|	
|not in 			|trả về true nếu giá trị x ko có trong y| x not in y 				|

## **7. Toán tử Bitwise**

{:class="table table-bordered"}
|  Toán tử         	|  Tên  | 	 			
|---               	|---   	| 
| & 				|AND	|
| \|				|OR		|
| ^					|XOR	|
| ~ 				|NOT	|				
| <<				|Zero 	| 
| >>				|Signed |







