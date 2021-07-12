---
layout: course-reactjs
title: Sử dụng Component API trong reactjs 
slug : su-dung-component-api-reactjs
category: laptrinhjavascript
tags: [reactjs]
summery: Component API
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta  dùng  Component API. Lần lượt giới thiệu và và đi qua các ví dụ về Component API  được sử dụng trong reactjs.

youtubeId: e9R_obn6ZVY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách sử dụng <b> Component API <b> trong reactjs. 

Trong bài học ngày hôm nay chúng ta sẽ giải thích React component API là gì. Mình sẽ thảo luận qua 3 phương thức setSate(), forceUpdate và ReactDOM.findDOMNode().

## **1. Set State**

Phương thức setState() dùng để cập nhập state của các component. Dùng để thay đổi các giá trị trong state, phương thức này dùng để thêm những sự thay đổi xảy ra trong state chứ không thay thế các giá trị trong state.

{% highlight javascript  linenos %}

import React from 'react';

class App extends React.Component {
   constructor() {
      super();
      
      this.state = {
         data: []
      }
   
      this.setStateHandler = this.setStateHandler.bind(this);
   };
   setStateHandler() {
      var item = "setState..."
      var myArray = this.state.data.slice();
     myArray.push(item);
      this.setState({data: myArray})
   };
   render() {
      return (
         <div>
            <button onClick = {this.setStateHandler}>SET STATE</button>
            <h4>State Array: {this.state.data}</h4>
         </div>
      );
   }
}
export default App;

{% endhighlight %}

Chúng ta có một mảng data là rỗng trong state. Mỗi lần chúng ta click trên button, giá trị trong state sẽ cập nhật. Nếu chúng ta click 5 lần thì chúng ta sẽ thêm 5 giá trị "setState" vào mảng data.

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/reactjs/react-component-api-set-state.jpeg){:class="img-responsive"}
{: refdef}

## **2. Force Update**

Thỉnh thoảng chúng ta muốn cập nhật component thì mình sẽ sử dụng phương thức forceUpdate.

{% highlight javascript  linenos %}

import React from 'react';

class App extends React.Component {
   constructor() {
      super();
      this.forceUpdateHandler = this.forceUpdateHandler.bind(this);
   };
   forceUpdateHandler() {
      this.forceUpdate();
   };
   render() {
      return (
         <div>
            <button onClick = {this.forceUpdateHandler}>FORCE UPDATE</button>
            <h4>Random number: {Math.random()}</h4>
         </div>
      );
   }
}
export default App;

{% endhighlight %}

Chúng ta set giá trị số ngẫu nhiên sẽ được cập nhật mỗi lần nút button được click.

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/reactjs/react-component-api-force-update.jpeg){:class="img-responsive"}
{: refdef}

## **3. Find Dom Node**

Để thao tác với các phần tử trên website như button, text hoặc các thẻ div thì chúng ta sử dụng ReactDOM.findDOMNode().

Để sử dụng được hàm findDOMNode thì chúng ta phải import thư viện react-dom như sau

{% highlight javascript  linenos %}

import React from 'react';
import ReactDOM from 'react-dom';

class App extends React.Component {
   constructor() {
      super();
      this.findDomNodeHandler = this.findDomNodeHandler.bind(this);
   };
   findDomNodeHandler() {
      var myDiv = document.getElementById('myDiv');
      ReactDOM.findDOMNode(myDiv).style.color = 'green';
   }
   render() {
      return (
         <div>
            <button onClick = {this.findDomNodeHandler}>FIND DOME NODE</button>
            <div id = "myDiv">NODE</div>
         </div>
      );
   }
}
export default App;

{% endhighlight %}

Màu sắc của thẻ myDiv sẽ chuyển sang màu xanh mỗi lần chúng ta click vô button

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/reactjs/react-component-api-find-dom-node.jpeg){:class="img-responsive"}
{: refdef}

## **4. Video Demo**


{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}































