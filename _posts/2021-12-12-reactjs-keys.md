---
layout: course-reactjs
title: Sử dụng keys trong reactjs 
slug : su-dung-keys-trong-reactjs
category: laptrinhjavascript
tags: [reactjs]
summery: Keys
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta  hiểu về keys trong react. Lần lượt giới thiệu và và đi qua các ví dụ về keys được sử dụng trong reactjs.

youtubeId: l_wdJu1II1A
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người hiểu về <b> keys <b> trong reactjs. 



## **1. Sử dụng keys**

React Keys được sử dụng trong react khi chúng ta muốn tạo ra các component động. Keys là giá trị duy nhất để nhận biết và phân biệt các component .

## **2. Ví dụ keys**

Trong ví dụ này chúng ta sẽ tạo Content component với Key có giá trị index (i). Hàm map sẽ tạo ra 3 phần tử Content dựa vào mảng data mà chúng ta tạo trong State. Vì keys là đối tượng duy nhất và không trùng lặp nên trong ví dụ này chúng ta sử dụng index (vị trí) các phần tử trong mảng để gán cho key


Chúng ta có file App.jsx như sau

{% highlight javascript  linenos %}

import React from 'react';

class App extends React.Component {
   constructor() {
      super();
      
      this.state = {
         data:[
            {
               component: 'First...',
               id: 1
            },
            {
               component: 'Second...',
               id: 2
            },
            {
               component: 'Third...',
               id: 3
            }
         ]
      }
   }
   render() {
      return (
         <div>
            <div>
               {this.state.data.map((dynamicComponent, i) => <Content 
                  key = {i} componentData = {dynamicComponent}/>)}
            </div>
         </div>
      );
   }
}
class Content extends React.Component {
   render() {
      return (
         <div>
            <div>{this.props.componentData.component}</div>
            <div>{this.props.componentData.id}</div>
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
![reactjs ](/images/post/reactjs/react-keys-example.jpeg){:class="img-responsive"}
{: refdef}

## **3. Video Demo**


{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}



