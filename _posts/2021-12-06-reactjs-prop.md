---
layout: course-reactjs
title: Sử dụng Props trong reactjs 
slug : su-dung-props-reactjs
category: laptrinhjavascript
tags: [reactjs]
summery: Props
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta  dùng  Props. Lần lượt giới thiệu và và đi qua các ví dụ về Props  được sử dụng trong reactjs.

youtubeId: mNg71ajWRSY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách sử dụng <b> Props <b> trong reactjs. Chúng ta sẽ học cách sử dụng state để quản lý luồng đi dữ liệu từ component cha xuống các component con.

Sự khác nhau của state và props là dữ liệu chứa trong props là không bị thay đổi. Ví dụ như component cha truyền giá trị abc xuống cho component con thì giá trị abc không bị thay đổi, ngược lại giá trị trong state có thể bị thay đổi

## **1. Sử dụng Props**

Khi chúng ta cần dữ liệu hiển thị mà giá trị không thay đổi trong component thì chúng ta sử dụng props trong phương thức render của component. Ví dụ như anh có component là APP trong đó giá trị h1 và h2 là được lấy từ component cha truyền xuống và không thay đổi được giá trị. Chúng ta sử dụng từ khoá this.props để lấy giá trị như sau

Chúng ta tạo file tên App.jsx

{% highlight javascript  linenos %}

import React from 'react';

class App extends React.Component {
   render() {
      return (
         <div>
            <h1>{this.props.headerProp}</h1>
            <h2>{this.props.contentProp}</h2>
         </div>
      );
   }
}
export default App;

{% endhighlight %}

Chúng ta truyền giá trị headerProp và contentProp từ compnent cha trong hàm render như sau.

Chúng ta tạo file main.js như sau.

{% highlight javascript  linenos %}

import React from 'react';
import ReactDOM from 'react-dom';
import App from './App.jsx';

ReactDOM.render(<App headerProp = "Header from props..." contentProp = "Content
   from props..."/>, document.getElementById('app'));

export default App;

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/reactjs/react_props_example.jpeg){:class="img-responsive"}
{: refdef}

## **2. Default Props**

Chúng ta có thể set giá trị mặc định cho component thông qua constructor như sau


{% highlight javascript  linenos %}

import React from 'react';

class App extends React.Component {
   render() {
      return (
         <div>
            <h1>{this.props.headerProp}</h1>
            <h2>{this.props.contentProp}</h2>
         </div>
      );
   }
}
App.defaultProps = {
   headerProp: "Header from props...",
   contentProp:"Content from props..."
}
export default App;

{% endhighlight %}

Trong file main.js ta tạo như sau

{% highlight javascript  linenos %}

import React from 'react';
import ReactDOM from 'react-dom';
import App from './App.jsx';

ReactDOM.render(<App/>, document.getElementById('app'));

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/reactjs/react_props_default_example.jpeg){:class="img-responsive"}
{: refdef}

## **3. State và Props**

Chúng ta có thể kết hợp State và Props trong ứng dụng React. Chúng ta sử dụng State để khởi tạo và chứa các giá trị sau đó truyền các giá trị này xuống cho các component con 

{% highlight javascript  linenos %}

import React from 'react';

class App extends React.Component {
   constructor(props) {
      super(props);
      this.state = {
         header: "Header from props...",
         content: "Content from props..."
      }
   }
   render() {
      return (
         <div>
            <Header headerProp = {this.state.header}/>
            <Content contentProp = {this.state.content}/>
         </div>
      );
   }
}
class Header extends React.Component {
   render() {
      return (
         <div>
            <h1>{this.props.headerProp}</h1>
         </div>
      );
   }
}
class Content extends React.Component {
   render() {
      return (
         <div>
            <h2>{this.props.contentProp}</h2>
         </div>
      );
   }
}
export default App;

{% endhighlight %}


Trong file main.js ta tạo như sau

{% highlight javascript  linenos %}

import React from 'react';
import ReactDOM from 'react-dom';
import App from './App.jsx';

ReactDOM.render(<App/>, document.getElementById('app'));

{% endhighlight %}

Chúng ta cũng nhận được kết quả tương tự như ví dụ 1 và 2 tuy nhiên có một điểm khác biệt trong ví dụ 3 là giá trị của chúng ta xuất phát và tạo ra được đến từ State. Nếu chúng ta muốn cập nhập giá trị thì chúng ta sẽ phải thay đổi trong State.

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/reactjs/react_props_state_example.jpeg){:class="img-responsive"}
{: refdef}

## **4. Kiểm tra giá trị trong Props**

React sử dụng phương thức App.propTypes để kiểm tra giá trị truyền vào có đúng như định dạng mong muốn hay không. Ví dụ sau đây ta kiểm tra giá trị truyền vào.

{% highlight javascript  linenos %}

import React from 'react';

class App extends React.Component {
   render() {
      return (
         <div>
            <h3>Array: {this.props.propArray}</h3>
            <h3>Bool: {this.props.propBool ? "True..." : "False..."}</h3>
            <h3>Func: {this.props.propFunc(3)}</h3>
            <h3>Number: {this.props.propNumber}</h3>
            <h3>String: {this.props.propString}</h3>
            <h3>Object: {this.props.propObject.objectName1}</h3>
            <h3>Object: {this.props.propObject.objectName2}</h3>
            <h3>Object: {this.props.propObject.objectName3}</h3>
         </div>
      );
   }
}

App.propTypes = {
   propArray: React.PropTypes.array.isRequired,
   propBool: React.PropTypes.bool.isRequired,
   propFunc: React.PropTypes.func,
   propNumber: React.PropTypes.number,
   propString: React.PropTypes.string,
   propObject: React.PropTypes.object
}

App.defaultProps = {
   propArray: [1,2,3,4,5],
   propBool: true,
   propFunc: function(e){return e},
   propNumber: 1,
   propString: "String value...",
   
   propObject: {
      objectName1:"objectValue1",
      objectName2: "objectValue2",
      objectName3: "objectValue3"
   }
}
export default App;

{% endhighlight %}

Trong file main.js ta tạo như sau

{% highlight javascript  linenos %}

import React from 'react';
import ReactDOM from 'react-dom';
import App from './App.jsx';

ReactDOM.render(<App/>, document.getElementById('app'));

{% endhighlight %}

## **5. Video Demo**


{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}













