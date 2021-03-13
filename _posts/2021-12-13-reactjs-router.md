---
layout: course-reactjs
title: Sử dụng router trong reactjs 
slug : su-dung-router-trong-reactjs
category: laptrinhjavascript
tags: [reactjs]
summery: Keys
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta  hiểu về router trong react. Lần lượt giới thiệu và và đi qua các ví dụ về router được sử dụng trong reactjs.

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người hiểu về <b> router <b> trong reactjs. 



## **1. Cài đặt react router**

Cách đơn giản nhất để cài react-router là chạy command line sau đây

{% highlight javascript  linenos %}

C:\Users\username\Desktop\reactApp>npm install react-router

{% endhighlight %}

## **2. Tạo các component**

Trong ví dụ sau đây chúng ta sẽ tạo 4 component. Chúng ta sẽ sử dụng App component như một menu.

Chúng ta có 3 component Home, About, và Contact sẽ được hiển thị dựa vào Router thay đổi.


Chúng ta có file App.jsx như sau

{% highlight javascript  linenos %}

import React from 'react';
import ReactDOM from 'react-dom';
import { Router, Route, Link, browserHistory, IndexRoute } from 'react-router'

class App extends React.Component {
   render() {
      return (
         <div>
            <ul>
            <li>Home</li>
            <li>About</li>
            <li>Contact</li>
            </ul>
            {this.props.children}
         </div>
      )
   }
}
export default App;

class Home extends React.Component {
   render() {
      return (
         <div>
            <h1>Home...</h1>
         </div>
      )
   }
}
export default Home;

class About extends React.Component {
   render() {
      return (
         <div>
            <h1>About...</h1>
         </div>
      )
   }
}
export default About;

class Contact extends React.Component {
   render() {
      return (
         <div>
            <h1>Contact...</h1>
         </div>
      )
   }
}
export default Contact;

{% endhighlight %}

## **3. Thêm Router**

Chúng ta sử dụng thẻ Router để thực hiện việc navigate giữa các trang web như sau.

Chúng ta có file main.js

{% highlight javascript  linenos %}

import React from 'react';
import ReactDOM from 'react-dom';
import App from './App.jsx';

ReactDOM.render(<App/>, document.getElementById('app'));

{% endhighlight %}

Khi ứng dụng web chạy chúng ta sẽ thấy được 3 cái link như sau. Click vào mỗi cái link sẽ cho kết quả trang web tương ứng

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/reactjs/router.jpeg){:class="img-responsive"}
{: refdef}




