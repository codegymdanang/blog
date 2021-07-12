---
layout: course-reactjs
title: Sử dụng form trong reactjs 
slug : su-dung-form-trong-reactjs
category: laptrinhjavascript
tags: [reactjs]
summery: Form
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta  hiểu về Form trong react. Lần lượt giới thiệu và và đi qua các ví dụ về Form được sử dụng trong reactjs.

youtubeId: ugCEqN_DYgQ
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người hiểu về <b> Form <b> trong reactjs. 



## **1. Sử dụng Form**

Trong ví dụ hôm nay chúng ta sẽ tạo ra một form. Chúng ta sẽ gán giá trị input cho form với giá trị là value = {this.state.data}. Với cách gán giá trị đó nó cho phép chúng ta cập nhật lại giá trị trong state khi giá trị trong text input thay đổi. Chúng ta sử dụng sự kiện onChange để bắt lại sự kiện khi giá trị trong input thay đổi.

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
   updateState(e) {
      this.setState({data: e.target.value});
   }
   render() {
      return (
         <div>
            <input type = "text" value = {this.state.data} 
               onChange = {this.updateState} />
            <h4>{this.state.data}</h4>
         </div>
      );
   }
}
export default App;

{% endhighlight %}

Chúng ta có hàm main.js để chạy ứng dụng như sau

{% highlight javascript  linenos %}

import React from 'react';
import ReactDOM from 'react-dom';
import App from './App.jsx';

ReactDOM.render(<App/>, document.getElementById('app'));

{% endhighlight %}

Khi giá trị trong input thay đổi thì state sẽ cập nhật giá trị

## **2. Sử dụng Form từ component con**

Trong ví dụ sau chúng ta sẽ làm một cái phức tạp hơn. Chúng ta sẽ tạo form từ component con sau đó nhúng vào component cha. Sự kiện onChange sẽ bắt giá trị thay đổi và truyền giá trị này xuống cho component con để hiển thị ra màn hình. Bất cứ khi nào chúng ta cập nhật giá trị trong State từ component con, chúng ta cần truyền function mà sẽ cập nhật (updateState) như giá trị prop (updateStateProp)

Ta có file App.jsx như sau

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
   updateState(e) {
      this.setState({data: e.target.value});
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
            <input type = "text" value = {this.props.myDataProp} 
               onChange = {this.props.updateStateProp} />
            <h3>{this.props.myDataProp}</h3>
         </div>
      );
   }
}
export default App;

{% endhighlight %}

Ta có file main.js như sau

{% highlight javascript  linenos %}

import React from 'react';
import ReactDOM from 'react-dom';
import App from './App.jsx';

ReactDOM.render(<App/>, document.getElementById('app'));

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/reactjs/react-forms-complex.jpeg){:class="img-responsive"}
{: refdef}

## **3. Video Demo**


{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}













