---
layout: course-reactjs
title: Sử dụng react hook trong reactjs 
slug : su-dung-react-hook-trong-reactjs
category: laptrinhjavascript
tags: [reactjs]
summery: React Hook
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta  hiểu về Redux Hook trong react. Lần lượt giới thiệu và và đi qua các ví dụ về Redux Hook được sử dụng trong reactjs.

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người hiểu về <b> Redux Hook <b> trong reactjs. Trước khi vào nội dung chính mình tìm hiểu qua về Class Component và Function component trước nhé.



## **1. Class component**

Class component là những component được viết theo cú pháp class của javascript của ES6, bao gồm đầy đủ các thành phần tạo nên một component như contructor, state, hàm render và đầy đủ các method của life cycle trong ReactJs. 

Bên dưới là ví dụ cho class component: 

{% highlight javascript  linenos %}

import React, { Component } from 'react'; 

class App extends Component { 

render() { 

return (<h1>I'm a class component!</h1>); 

} 

} 

export default App; 

{% endhighlight %}

## **2. Function component**

Function component cũng là một component nhưng được viết dưới dạng function, chắc hẳn có nhiều bạn thắc mắc đã có class component rồi sao còn sinh ra function component để làm gì, thì các bạn nhìn vào một đoạn code ví dụ cho function component như bên dưới. 

Page Break
 
{% highlight javascript  linenos %}

function App() { 

return ( 

<h1>hello word</h1> 

); 

} 
 

export default App; 

{% endhighlight %}


- Đây chính là function component, cách viết khá ngắn gọn,  lưu ý là nó không có hàm render, không có contructor, không có các method life cycle giống như class component. Nó rất thích hợp để mình viết nhanh một component chỉ có UI và không có các xử lý phức tạp liên quan đến state, life cycle... 

- Ngày xưa nó ra đời chỉ với mục đích là tạo nhanh những component đơn giản không thiên về xử lý logic, tuy nhiên từ khi version 16.8 của Reactjs với sự xuất hiện của React hook thì cuộc chơi đã thay đổi, với sự hỗ trợ của React hook đã giúp cho function component xuất hiện cực kỳ phổ biến và chiếm phần lớn trong các dự án hiện nay. Vậy React Hook là gì? 

## **3. React Hook**

Về bản chất hook là những  FUNCTION khắc phục các nhược điểm của function component, nếu ngày xưa mình viết component không thể sử dụng được state , hoặc các method như componentDidMount hoặc componentDidUpdate, thì giờ đây những việc đó đã được giải quyết.  

Bây giờ mình sẽ đi qua 2 cái hook cực kỳ phổ biến là useState và useEffect. 

## **4. useState**

 
{% highlight javascript  linenos %}

import { useState } from 'react' 

function Counter() { 

const [count, setCount] = useState(0); 

return ( 

<div> 

<p>You clicked {count} times</p> 

<button onClick={() => setCount(count + 1)}>Click me</button> 

</div> 

) 

} 

{% endhighlight %}

Muốn sử dụn useState bạn cần import nó vào, và cách sử dụng cũng khá đơn giản: 

const [count, setCount] = useState(0); 

Có thể thấy nó nhận vào một giá trị đầu vào để khởi tạo giá trị cho state và trả về một cặp [count, setcount]. 

count: state hiện tại 

setCount: gọi hàm này khi cần update state để rerender lại component. (Nó tương tự với setState trong Class Component) 

## **5. useEffect**
 

useEffect là một hàm khá là hay của Reacthook, một mình nó cân được tới 3 hàm trong class component: componentDidMount, componentDidUpdate, componentWillUnmount. 

Với componentDidMount và componentDidUpdate 

{% highlight javascript  linenos %} 

import { useState, useEffect } from 'react' 

function Example() { 

const [count, setCount] = useState(0) 

useEffect(() => { 

document.title = `You clicked ${count} times` 

}) 

 
return ( 

<div> 

<p>You clicked {count} times</p> 

<button onClick={() => setCount(count + 1)}>Click me</button> 

</div> 

) 

} 

{% endhighlight %}


Viết useEffect như này giống như tương tự như componentDidMount và componentDidUpdate, tuy nhiên viết như này nó có một vấn đề phát sinh là nó sẽ gọi vào useEffect mỗi lần re-render, điều naỳ nó có thể sẽ gây ra dư thừa và ảnh hưởng đến peformance, đế optimize chỗ này mình có thể sử dụng: 

{% highlight javascript  linenos %} 

useEffect(() => { 

document.title = `You clicked ${count} times` 

}, [dependency]) 

{% endhighlight %}

Nếu giá trị dependency này mình bỏ trống thì nó chỉ gọi sau lần render đầu tiên (giống componentDidMout), nếu dependency này mình truyền vô một biến, thì nó chỉ gọi vô useEffect khi giá trị biến đó thay đổi. 

Cuối cùng sử dụng useEffect như componentWillUnmount 

{% highlight javascript  linenos %} 

useEffect(() => { 

const id = setInteval(() => setCount(count + 1), 100) 

return () => clearInteval(id) 

}) 

{% endhighlight %}


Để sử dụng như là componentWillUnmount thì mình chỉ cần thêm xử lý vô chỗ return là được, ví dụ trên khi mình unmount component  nó sẽ gọi vô hàm của câu lệnh return để xóa cái inteval này đi, tránh bị lỗi memory leak! 

Các function react hook còn khá là nhiều, tuy nhiên trong phạm vi của bài viết này mình đi qua 2 cái hook cơ bản và phổ biến, hẹn gặp lại các bạn trong các bài viết tiếp theo! 








