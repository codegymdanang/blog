---
layout: course-reactjs
title: Component trong reactjs 
slug : su-dung-component-reactjs
category: laptrinhjavascript
tags: [reactjs]
summery: Component
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta  dùng  Component. Lần lượt giới thiệu và và đi qua các ví dụ về Component  được sử dụng trong reactjs.

youtubeId: jrbTsvLgjSk
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách sử dụng <b> Component <b> trong reactjs. Chúng ta sẽ học cách tạo ra các component cho các thành phần của một website, nó giúp chúng ta dể dàng bảo trì, mở rộng hoặc thay đổi giao diện mà không ảnh hưởng đến các thành phần khác của website.

Khi nói về component thì các em cứ tưởng như như 1 chiếc xe hơi. Để tạo thành 1 chiếc xe hơi thì gồm có nhiều thành phần (component) kết hợp lại với nhau như khung xe, bánh xe, động cơ. Một component có thể chức các component khác, anh ví dụ như bánh xe thì được tạo thành từ nhiều component (các thành phần) như khung bánh xe, lốp xe.

Tương tư như vậy ta có thể hình dung trong một trang web có nhiều component (thành phần) kết hợp với nhau tạo thành trang web, như phần header, phần thân (body), phần footter. Trong mỗi phần header có thể chức các thành phần khác như ảnh, button, slider là những thành phần con tạo nên header.

## **1. Stateless là gì**

Trong ví dụ sau đây chúng ta tạo ra một component chứa Header và Content. Chúng ta sẽ tạo Header và Content là những component sau đó nhúng vào component cha (App component).

Để tạo component ta sử dụng extends React.Component như sau


{% highlight javascript  linenos %}

import React from 'react';

class App extends React.Component {
   render() {
      return (
         <div>
            <Header/>
            <Content/>
         </div>
      );
   }
}
class Header extends React.Component {
   render() {
      return (
         <div>
            <h1>Header</h1>
         </div>
      );
   }
}
class Content extends React.Component {
   render() {
      return (
         <div>
            <h2>Content</h2>
            <p>The content text!!!</p>
         </div>
      );
   }
}
export default App;

{% endhighlight %}

- Như vậy ta thấy trong phần render của component cha App. Ta nhúng 2 component con là <Header/> và <Content /> vào.

- Hàm render() có nhiệm vụ vẽ các component ra màn hình.

Để có thể hiển thị được các component thì trong hàm main.js ta gọi hàm reactDom.render() như sau

{% highlight javascript  linenos %}

import React from 'react';
import ReactDOM from 'react-dom';
import App from './App.jsx';

ReactDOM.render(<App />, document.getElementById('app'));

{% endhighlight %}


{:refdef: style="text-align: center;"}
![reactjs ](/images/post/reactjs/react_components_stateless.jpeg){:class="img-responsive"}
{: refdef}

## **2. Stateful là gì**

Trong ví dự stateless chúng ta không khởi tạo hoặc thêm giá trị cho các component. Trong ví dụ dưới đây chúng ta khởi tạo dữ liệu và gán giá trị cho các component. Ví dụ sau anh sẽ render dữ liệu cho một table.

Đầu tiên anh sẽ khởi tạo một mảng dữ liệu json và chứa trong biến state như sau.

{% highlight javascript  linenos %}

import React from 'react';

class App extends React.Component {
   constructor() {
      super();
      this.state = {
         data: 
         [
            {
               "id":1,
               "name":"Foo",
               "age":"20"
            },
            {
               "id":2,
               "name":"Bar",
               "age":"30"
            },
            {
               "id":3,
               "name":"Baz",
               "age":"40"
            }
         ]
      }
   }
   render() {
      return (
         <div>
            <Header/>
            <table>
               <tbody>
                  {this.state.data.map((person, i) => <TableRow key = {i} 
                     data = {person} />)}
               </tbody>
            </table>
         </div>
      );
   }
}
class Header extends React.Component {
   render() {
      return (
         <div>
            <h1>Header</h1>
         </div>
      );
   }
}
class TableRow extends React.Component {
   render() {
      return (
         <tr>
            <td>{this.props.data.id}</td>
            <td>{this.props.data.name}</td>
            <td>{this.props.data.age}</td>
         </tr>
      );
   }
}
export default App;

{% endhighlight %}

Các em chú ý trong component TableRow anh sử dụng phương thức this.pros để lấy giá trị từ component cha truyền xuống cho component con để nó render giá trị thông qua đoạn code

{% highlight javascript  linenos %}

<TableRow key = {i}  data = {person} />

{% endhighlight %}

Để chạy được chương trình và render kết quả thì trong file main.js anh chạy như sau

{% highlight javascript  linenos %}

import React from 'react';
import ReactDOM from 'react-dom';
import App from './App.jsx';

ReactDOM.render(<App/>, document.getElementById('app'));

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/reactjs/react_components_statefull.jpeg){:class="img-responsive"}
{: refdef}


## **3. Video Demo**


{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}







