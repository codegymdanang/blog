---
layout: course-reactjs
title: State trong reactjs 
slug : su-dung-state-reactjs
category: laptrinhjavascript
tags: [reactjs]
summery: State
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta  dùng  State. Lần lượt giới thiệu và và đi qua các ví dụ về State  được sử dụng trong reactjs.

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách sử dụng <b> State <b> trong reactjs. Chúng ta sẽ học cách sử dụng state để quản lý luồng đi dữ liệu từ component cha xuống các component con.



## **1. State là gì**

State được hiểu là nơi tập trung và chứa dữ liệu của các component. Ví dụ như mình có 10 components cần dữ liệu từ state, thì chúng ta sẽ tạo ra một component cha chứa tất cả dữ liệu trong state. Sau đó từ component cha dữ liệu sẽ được truyền đi tới các component theo một hướng dọc từ cha xuống con. Giúp chúng ta dễ dàng phát hiện được luồng đi của dữ liệu trong ứng dụng web

Chúng ta sẽ tạo component và sử dụng state để chứa dữ liệu như sau.


{% highlight javascript  linenos %}

import React from 'react';

class App extends React.Component {
   constructor(props) {
      super(props);
      
      this.state = {
         header: "Header from state...",
         content: "Content from state..."
      }
   }
   render() {
      return (
         <div>
            <h1>{this.state.header}</h1>
            <h2>{this.state.content}</h2>
         </div>
      );
   }
}
export default App;

{% endhighlight %}

Chúng ta sử dụng this.state để chứa mảng dữ liệu json là header và content.

Hai component h1 và h2 lấy giá trị header và content thông qua state như sau

{% highlight javascript  linenos %}


 <h1>{this.state.header}</h1>
 <h2>{this.state.content}</h2>

export default App;

{% endhighlight %}

Để chay được ứng dụng ta code file  main.js như sau

{% highlight javascript  linenos %}

import React from 'react';
import ReactDOM from 'react-dom';
import App from './App.jsx';

ReactDOM.render(<App />, document.getElementById('app'));

{% endhighlight %}






