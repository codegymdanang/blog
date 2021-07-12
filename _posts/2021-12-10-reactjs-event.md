---
layout: course-reactjs
title: Sử dụng event trong reactjs 
slug : su-dung-event-trong-reactjs
category: laptrinhjavascript
tags: [reactjs]
summery: Event
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta  hiểu về Event trong react. Lần lượt giới thiệu và và đi qua các ví dụ về Event được sử dụng trong reactjs.

youtubeId: cEoQ9t6jP_8
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người hiểu về <b> Event <b> trong reactjs. 



## **1. Sử dụng Event**

Trong ví dụ đơn giản này chúng ta sẽ tạo sự kiện onClick. Khi người dùng click vào nút button ta sẽ gọi hàm updateState.

Chúng ta có file App.jsx như sau.


{% highlight javascript  linenos %}

import React from 'react';

class App extends React.Component {
   constructor(props) {
      super(props);
      
      this.state = {
         data: 'Initial data...'
      }
      this.updateState = this.updateState.bind(this);
   };
   updateState() {
      this.setState({data: 'Data updated...'})
   }
   render() {
      return (
         <div>
            <button onClick = {this.updateState}>CLICK</button>
            <h4>{this.state.data}</h4>
         </div>
      );
   }
}
export default App;

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/reactjs/react-events-simple.jpeg){:class="img-responsive"}
{: refdef}

Chúng ta chạy chương trình trong file main.js như sau.

{% highlight javascript  linenos %}

import React from 'react';
import ReactDOM from 'react-dom';
import App from './App.jsx';

ReactDOM.render(<App/>, document.getElementById('app'));

{% endhighlight %}

## **2. Sử dụng Event ở component con**

Chúng ví dụ này chúng ta sẽ cập nhật giá trị state của component cha từ component con. Chúng ta tạo hàm để xử lý sự kiện updateState trong component cha, và truyền nó xuống component con thông qua thuộc tính prop updateStateProp

{% highlight javascript  linenos %}

import React from 'react';

class App extends React.Component {
   constructor(props) {
      super(props);
      
      this.state = {
         data: 'Initial data...'
      }
      this.updateState = this.updateState.bind(this);
   };
   updateState() {
      this.setState({data: 'Data updated from the child component...'})
   }
   render() {
      return (
         <div>
            <Content myDataProp = {this.state.data} 
               updateStateProp = {this.updateState}></Content>
         </div>
      );
   }
}
class Content extends React.Component {
   render() {
      return (
         <div>
            <button onClick = {this.props.updateStateProp}>CLICK</button>
            <h3>{this.props.myDataProp}</h3>
         </div>
      );
   }
}
export default App;

{% endhighlight %}

Chúng ta chạy chương trình trong file main.js như sau.

{% highlight javascript  linenos %}

import React from 'react';
import ReactDOM from 'react-dom';
import App from './App.jsx';

ReactDOM.render(<App/>, document.getElementById('app'));

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/reactjs/react-events-child-data.jpeg){:class="img-responsive"}
{: refdef}

## **3. Video Demo**


{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}




