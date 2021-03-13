---
layout: course-reactjs
title: JSX 
slug : su-dung-jsx-reactjs
category: laptrinhjavascript
tags: [reactjs]
summery: JSX
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta  dùng  JSX. Lần lượt giới thiệu và và đi qua các ví dụ về JSX  được sử dụng trong reactjs.

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách sử dụng <b> JSX <b>. Lần lượt giới thiệu và và đi qua các ví dụ về JSX  được sử dụng trong reactjs.

## **1. JSX là gì**

React sử dụng JSX (Javascript kết hợp với XML) để làm template thay thế cho Javascript. Trong ứng dụng react chúng ta có thể sử dụng jsx hoặc không cần cũng được. Tuy nhiên khi sử dụng JSX thì có những ưu điểm sau :

+ Trang web chạy nhanh hơn bởi vì quá trình optimise code được diển ra  trong khi code được biên dịch qua javascript

+ Code theo kiểu type-safe nên hầu hết các lỗi có thể được phát hiện trong giai đoạn compile code

+ Giúp chúng ta viết code nhanh hơn vì mình viết theo template nếu chúng ta có kiến thức về HTML.

## **2. Sử dụng JSX**


Sử dụng JXS cũng hơi giống sử dụng HTML trong hầu hết trường hợp. Lấy ví dụ file App.jsx sau, chúng ta hãy nhìn vào đoạn code sau câu lệnh return.

{% highlight javascript  linenos %}

import React from 'react';

class App extends React.Component {
   render() {
      return (
         <div>
            Hello World!!!
         </div>
      );
   }
}
export default App;

{% endhighlight %}

Như chúng ta thấy đoạn mã trên sẽ trả về thẻ div có nội dung là Hello World và cú pháp trong đoạn div đó là HTML.

## **3. Khác biệt với HTML**

Mặc dù chúng ta thấy JSX cũng tương tự với HTML tuy nhiên vẫn có những sự khác biệt

+ Các thẻ lồng nhau

Nếu như chúng ta muốn trả về nhiều phần tử ví dụ như trong thẻ div trên chúng ta muốn trả về Hello World và thêm các thẻ H1 và H2 thì chúng phải có 1  thẻ cha bao bọc bên ngoài các thẻ div, h1 , h2 như sau.

{% highlight javascript  linenos %}

import React from 'react';

class App extends React.Component {
   render() {
      return (
         <div>
            <h1>Header</h1>
            <h2>Content</h2>
            <p>This is the content!!!</p>
         </div>
      );
   }
}
export default App;

{% endhighlight %}


+ Thuộc tính

Chúng ta có thể tự định nghĩa một thuộc tính riêng cho mình bằng cách sử dụng từ khoá data ở đầu thuộc tính như sau. Ví dụ như anh muốn tự tạo thuộc tính my-attribute cho riêng mình.

{% highlight javascript  linenos %}

import React from 'react';

class App extends React.Component {
   render() {
      return (
         <div>
            <h1>Header</h1>
            <h2>Content</h2>
            <p data-myattribute = "somevalue">This is the content!!!</p>
         </div>
      );
   }
}
export default App;

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/reactjs/react_jsx_wrapper.jpeg){:class="img-responsive"}
{: refdef}

+ Javascript Expression

Chúng ta có thể thực hiện các phép tính trong JSX thông qua cách sử dụng {} như sau.

{% highlight javascript  linenos %}

import React from 'react';

class App extends React.Component {
   render() {
      return (
         <div>
            <h1>{1+1}</h1>
         </div>
      );
   }
}
export default App;

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/reactjs/react_jsx_expression.jpeg){:class="img-responsive"}
{: refdef}

Chúng ta không thể sử dụng if else bên trong JSX mà thay vào đó là sử dụng cú pháp ? của if else như sau.

{% highlight javascript  linenos %}

import React from 'react';

class App extends React.Component {
   render() {
      var i = 1;
      return (
         <div>
            <h1>{i == 1 ? 'True!' : 'False'}</h1>
         </div>
      );
   }
}
export default App;

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/reactjs/react_jsx_ternary_expression.jpeg){:class="img-responsive"}
{: refdef}

+ Styling màu sắc hoặc kích thước giống như việc sử dụng css trong html thì chúng ta sử dụng render như sau. Trong ví dụ này anh demo là inline css, còn trong thực tế mình sẽ có 1 file css riêng. Ví dụ như anh muốn thẻ H1 có màu đỏ

{% highlight javascript  linenos %}

import React from 'react';

class App extends React.Component {
   render() {
      var myStyle = {
         fontSize: 100,
         color: '#FF0000'
      }
      return (
         <div>
            <h1 style = {myStyle}>Header</h1>
         </div>
      );
   }
}
export default App;

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/reactjs/react_jsx_inline_style.jpeg){:class="img-responsive"}
{: refdef}

+ Convension khi sử dụng JSX như sau :
- Đối với các thẻ HTML thì chúng ta sử dụng chữ thường ví dụ như h1, div
- Đối với các Component của react thì dùng chữ hoa 
- Chúng ta sử sử dụng className hoặc classFor trong XML thay vì viết chữ thường là class không thôi. Nhớ thêm className chứ ko phải class như trong HTML mình hay viết.
 




























