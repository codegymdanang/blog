---
layout: course-reactjs
title: Vòng đời của Component trong reactjs 
slug : vong-doi-component-trong-reactjs
category: laptrinhjavascript
tags: [reactjs]
summery: Vòng đời component
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta  hiểu về vòng đời của  Component trong react. Lần lượt giới thiệu và và đi qua các ví dụ về vòng đời của Component được sử dụng trong reactjs.

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người hiểu về <b> vòng đời của Component <b> trong reactjs. 


## **1. componentWillMount là gì**

Phương thức componentWillMount được thực thi trước khi giao diện được render ra màn hình ở cả server và client side.

## **2. componentDidMount là gì**

Phương thức componentDidMount được thực thi sau khi render đầu tiên được sinh ra ở phía client. Thông thường những request dạng AJAX, DOM hoặc cập nhật state chúng ta để trong phương thức này

## **3. componentWillReceiveProps là gì**

Phương thức componentWillReceiveProps được gọi khi giá trị trong props được cập nhật trước khi giao diện được render ra.

## **4. shouldComponentUpdate là gì**

Phương thức shouldComponentUpdate trả về kết quả true hoặc false. Phương thức này giúp chúng ta nhận biết component sẽ được cập nhật hay không được cập nhật. Giá trị mặt định là true. Nếu mình chắc chắn rằng component không cần phải render sau khi state hoặc props được cập nhật thì chúng ta có thể trả về kế quả false.

## **5. componentWillUpdate là gì**

Phương thức componentWillUpdate được gọi trước khi component được rendering (vẽ ra giao diện trên web)

## **6. componentDidUpdate là gì**

Phương thức componentDidUpdate được gọi sau khi component được rendering (vẽ ra giao diện trên web)

## **7. componentWillUnmount là gì**

Phương thức componentWillUnmount được gọi sau khi component unmount từ dom. Chúng ta sẽ unmount component trong file main.js

Ví dụ sau đây chúng ta sẽ set giá trị ban đầu trong state trong constructor. Sau đó setNewnumber sẽ được dùng để cập nhật state.

File App.jsx

{% highlight javascript  linenos %}

import React from 'react';

class App extends React.Component {
   constructor(props) {
      super(props);
      
      this.state = {
         data: 0
      }
      this.setNewNumber = this.setNewNumber.bind(this)
   };
   setNewNumber() {
      this.setState({data: this.state.data + 1})
   }
   render() {
      return (
         <div>
            <button onClick = {this.setNewNumber}>INCREMENT</button>
            <Content myNumber = {this.state.data}></Content>
         </div>
      );
   }
}
class Content extends React.Component {
   componentWillMount() {
      console.log('Component WILL MOUNT!')
   }
   componentDidMount() {
      console.log('Component DID MOUNT!')
   }
   componentWillReceiveProps(newProps) {    
      console.log('Component WILL RECIEVE PROPS!')
   }
   shouldComponentUpdate(newProps, newState) {
      return true;
   }
   componentWillUpdate(nextProps, nextState) {
      console.log('Component WILL UPDATE!');
   }
   componentDidUpdate(prevProps, prevState) {
      console.log('Component DID UPDATE!')
   }
   componentWillUnmount() {
      console.log('Component WILL UNMOUNT!')
   }
   render() {
      return (
         <div>
            <h3>{this.props.myNumber}</h3>
         </div>
      );
   }
}
export default App;

{% endhighlight %}

File main.js

{% highlight javascript  linenos %}

import React from 'react';
import ReactDOM from 'react-dom';
import App from './App.jsx';

ReactDOM.render(<App/>, document.getElementById('app'));

setTimeout(() => {
   ReactDOM.unmountComponentAtNode(document.getElementById('app'));}, 10000);

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/reactjs/react-component-lifecycle-initial-screen.jpeg){:class="img-responsive"}
{: refdef}








