# Ajax-XMLHttpRequst

## 题目

- 手动编写一个ajax,不依赖第三方库

- 跨域的几种实现方式

## 知识点

## XMLHttpRequest

``` javascript
var xhr = new XMLHttpRequest()
xhr.open("GET", "http://jsonplaceholder.typicode.com/posts", false)
xhr.onreadystatechange = function () { // 每次readystate变化都会触发事件
    // 这里是函数异步执行
    if (xhr.readyState == 4) {
        if (xhr.status == 200) {
            let string = xhr.responseText   // xhr.responseText是响应头的第四部分
            let object = JSON.parse(string) // 把符合 JSON 语法的字符串装换成 JS 对应的值
            console.log(object[0])
        }
    }
}
xhr.send(null) //send('这里可以设置HTTP请求第四部分')
```

## 状态码说明

readyState状态码:

- 0: (未初始化)还没有调用send()方法

- 1: (载入)已调用send()方法,正在发送请求

- 2: (载入完成)send()方法执行完成,已经接收到全部响应内容

- 3: (交互)正在解析响应内容

- 4: (完成)响应内容解析完成,可以在客户端调用了

status状态码:

- 2XX: 表示成功处理请求,如200

- 3XX: 需要重定向,浏览器直接跳转

- 4XX: 客户端请求错误,如404

- 5XX: 服务端错误

## **跨域**

- 什么是跨域

  - 浏览器有同源策略,不允许ajax访问其他域接口,比如: 'http://www.youname.com:80'是不允许访问'http://m.imooc.com/course'的

  - 跨域条件: 协议、域名、端口,有一个不同就算跨域

  - **可以跨域的三个标签**

    - `<img src="XXX">`

    - `<link href="XXX">`

    - `<script src="XXX">`

- JSONP

- 服务器端设置 http header