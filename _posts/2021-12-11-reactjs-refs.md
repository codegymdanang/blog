---
layout: course-reactjs
title: Sử dụng refs trong reactjs 
slug : su-dung-refs-trong-reactjs
category: laptrinhjavascript
tags: [reactjs]
summery: Refs
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta  hiểu về refs trong react. Lần lượt giới thiệu và và đi qua các ví dụ về refs được sử dụng trong reactjs.

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người hiểu về <b> refs <b> trong reactjs. 



## **1. Sử dụng refs**

Refs được sử dụng để trả về tham chiếu của một phần tử trên web. Chúng ta nên hạn chế sử dụng Refs tuy nhiên Refs vẫn có hữu ích trong một số trường hợp như chúng ta muốn đo đạt hoặc thêm các phương thức cho các phần tử ở trên DOM

## **2. Ví dụ refs**

Trong ví dụ sau đây chúng ta chúng ta sử dụng refs để xoá các giá trị trong input. Hàm ClearInput sẽ tìm kiếm các phần tử trên web có giá trị ref="input", sau đó reset lại giá trị trong State và sau đó add thêm sự kiện focus khi button được click

Chúng ta có file App.jsx như sau

{% highlight javascript  linenos %}

import React from 'react';
import ReactDOM from 'react-dom';

class App extends React.Component {
   constructor(props) {
      super(props);
      
      this.state = {
         data: ''
      }
      this.updateState = this.updateState.bind(this);
      this.clearInput = this.clearInput.bind(this);
   };
   updateState(e) {
      this.setState({data: e.target.value});
   }
   clearInput() {
      this.setState({data: ''});
      ReactDOM.findDOMNode(this.refs.myInput).focus();
   }
   render() {
      return (
         <div>
            <input value = {this.state.data} onChange = {this.updateState} 
               ref = "myInput"></input>
            <button onClick = {this.clearInput}>CLEAR</button>
            <h4>{this.state.data}</h4>
         </div>
      );
   }
}
export default App;

{% endhighlight %}

Chúng ta có file main.js để chạy như sau

{% highlight javascript  linenos %}

import React from 'react';
import ReactDOM from 'react-dom';
import App from './App.jsx';

ReactDOM.render(<App/>, document.getElementById('app'));

{% endhighlight %}

Khi button được click chúng ta xoá giá trị trong textbox đồng thời focus chuột vào ô textbox.

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/reactjs/react-refs-example.jpeg){:class="img-responsive"}
{: refdef}




