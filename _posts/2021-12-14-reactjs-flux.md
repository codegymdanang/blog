---
layout: course-reactjs
title: Sử dụng flux trong reactjs 
slug : su-dung-flux-trong-reactjs
category: laptrinhjavascript
tags: [reactjs]
summery: Flux
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta  hiểu về flux trong react. Lần lượt giới thiệu và và đi qua các ví dụ về flux được sử dụng trong reactjs.

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người hiểu về <b> flux <b> trong reactjs. Flux là một khái niệm trong lập trình giúp chúng ta có thể quản lý flow (đường đi) của dữ liệu từ component này sang component khác theo 1 hướng duy nhất. Ví dụ như ta có component cha trong component cha ta có các component con, trong component con thì lại có thêm component con khác (cháu). Dữ liệu trong component con sẽ được nhận 1 chiều từ cha truyền xuống. Hoặc dữ liệu trong component cháu sẽ được nhận từ ông bà truyền xuống cho cha, sau đó cha mới truyền cho con theo 1 đường đi từ trên xuống dưới. Điều này giúp ta xát định, và quản lý được dữ liệu tốt hơn. Việc phán đoán và debug code cũng dể dàng hơn so với các cách làm truyền thống như Jquery. 

Trong khái niệm Flux có 4 thành phần mà chúng ta phải nhớ 

1) Action : là nới chúng ta dispatch các sự kiện. <br>
2) Dispatcher : Đây là trái tim của ứng dụng. Tất cả dữ liệu được dispatch và gửi xuống các stores <br>
3) Store : Nới chúng ta lưu trữ, cập nhật state dữ liệu <br>
4) View : Dùng để nhận data từ store và render ra giao diện <br>

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/reactjs/react-flux-concept-image.jpeg){:class="img-responsive"}
{: refdef}

## **1. Cài đặt Redux**

Trong ví dụ dưới đây chúng ta sẽ sử dụng Flux pattern thông qua việc sử dụng Redux framework. Hiện nay có rất nhiều framework được xây dựng trên Flux pattern nhưng trong bài này chúng ta chọn Redux để làm ví dụ

Chúng ta cài đặt redux thông qua command line sau

{% highlight javascript  linenos %}

C:\Users\username\Desktop\reactApp>npm install --save react-redux

{% endhighlight %}

## **2. Tạo các file và folders**

Bước tiếp theo chúng ta sẽ tạo các file và folders cho actions, reducers và component theo đúng Flux pattern như sau.

{% highlight javascript  linenos %}

C:\Users\Tutorialspoint\Desktop\reactApp>mkdir actions
C:\Users\Tutorialspoint\Desktop\reactApp>mkdir components
C:\Users\Tutorialspoint\Desktop\reactApp>mkdir reducers
C:\Users\Tutorialspoint\Desktop\reactApp>type nul > actions/actions.js
C:\Users\Tutorialspoint\Desktop\reactApp>type nul > reducers/reducers.js
C:\Users\Tutorialspoint\Desktop\reactApp>type nul > components/AddTodo.js
C:\Users\Tutorialspoint\Desktop\reactApp>type nul > components/Todo.js
C:\Users\Tutorialspoint\Desktop\reactApp>type nul > components/TodoList.js

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/reactjs/react-redux-folder-structure.jpeg){:class="img-responsive"}
{: refdef}

## **3. Tạo Actions**

Action là một đối tượng Javascript. Nó chứa đựng thông tin dữ liệu sẽ được truyền xuống cho Store. ADD_TODO action sẽ được sử dụng để thêm một item trong danh sách items có sẳn. Hàm addTodo() là hàm tạo ra action, mỗi action sẽ có một id duy nhất.

Chúng ta có file actions/actions.js như sau.

{% highlight javascript  linenos %}

export const ADD_TODO = 'ADD_TODO'

let nextTodoId = 0;

export function addTodo(text) {
   return {
      type: ADD_TODO,
      id: nextTodoId++,
      text
   };
}

{% endhighlight %}

## **4. Tạo Reducers**

Action được sử dụng cho việc trigger sự thay đổi trong app. Reducer sẽ xát định action nào sẽ được xử lý. Trong ví dụ bên dưới chúng ta sử dụng mệnh đề switch để tìm kiếm action ADD_TODO, vì trong một ứng dụng sẽ có hàm trăm action. Reducer sẽ nhận 2 tham số là action và state để xử lý và trả về cập nhật giá trị trong state.

Ta có nội dung trong file reducers/reducers.js như sau

{% highlight javascript  linenos %}

import { combineReducers } from 'redux'
import { ADD_TODO } from '../actions/actions'

function todo(state, action) {
   switch (action.type) {
      case ADD_TODO:
         return {
            id: action.id,
            text: action.text,
         }
      default:
         return state
   }
}
function todos(state = [], action) {
   switch (action.type) {
      case ADD_TODO:
         return [
            ...state,
            todo(undefined, action)
         ]
      default:
         return state
   }
}
const todoApp = combineReducers({
   todos
})
export default todoApp

{% endhighlight %}

## **5. Tạo Store**

Store là nơi chứa dữ liệu của app. Ta có nội dung trong file main.js như sau

{% highlight javascript  linenos %}

import React from 'react'

import { render } from 'react-dom'
import { createStore } from 'redux'
import { Provider } from 'react-redux'

import App from './App.jsx'
import todoApp from './reducers/reducers'

let store = createStore(todoApp)
let rootElement = document.getElementById('app')

render(
   <Provider store = {store}>
      <App />
   </Provider>,
   
   rootElement
)

{% endhighlight %}

## **6. Tạo Root Component**

App component là component cha của cả ứng dụng, chỉ có root component mới nhận biết được redux. Phần quan trọng nhất là hàm connect, được sử dụng để kết nối root component với Store.

Hàm connect sẽ có tham số là select. Tham số select sẽ lấy giá trị state từ Store và trả về Props (chứa data) và chúng được sử dụng trong component của chúng ta.

File App.jsx

{% highlight javascript  linenos %}

import React, { Component } from 'react'
import { connect } from 'react-redux'
import { addTodo } from './actions/actions'

import AddTodo from './components/AddTodo.js'
import TodoList from './components/TodoList.js'

class App extends Component {
   render() {
      const { dispatch, visibleTodos } = this.props
      
      return (
         <div>
            <AddTodo onAddClick = {text =>dispatch(addTodo(text))} />
            <TodoList todos = {visibleTodos}/>
         </div>
      )
   }
}
function select(state) {
   return {
      visibleTodos: state.todos
   }
}
export default connect(select)(App);

{% endhighlight %}

## **7. Tạo các Component**

Các component này không cần quan tâm đến redux. Chúng ta chỉ cần khai báo redux ở root component.

Chúng ta có file components/AddTodo.js

{% highlight javascript  linenos %}

import React, { Component, PropTypes } from 'react'

export default class AddTodo extends Component {
   render() {
      return (
         <div>
            <input type = 'text' ref = 'input' />
            
            <button onClick = {(e) => this.handleClick(e)}>
               Add
            </button>
         </div>
      )
   }
   handleClick(e) {
      const node = this.refs.input
      const text = node.value.trim()
      this.props.onAddClick(text)
      node.value = ''
   }
}

{% endhighlight %}

Chúng ta có file components/Todo.js

{% highlight javascript  linenos %}

import React, { Component, PropTypes } from 'react'

export default class Todo extends Component {
   render() {
      return (
         <li>
            {this.props.text}
         </li>
      )
   }
}

{% endhighlight %}

Chúng ta có file components/TodoList.js

{% highlight javascript  linenos %}

import React, { Component, PropTypes } from 'react'
import Todo from './Todo.js'

export default class TodoList extends Component {
   render() {
      return (
         <ul>
            {this.props.todos.map(todo =>
               <Todo
                  key = {todo.id}
                  {...todo}
               />
            )}
         </ul>
      )
   }
}

{% endhighlight %}

Khi ứng dụng chạy ta có kết quả như sau:

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/reactjs/react-redux-example.jpeg){:class="img-responsive"}
{: refdef}




