# JS-Web-API

## 回顾JS基础知识

- 变量类型和计算

- 原型和原型链

- 闭包和作用域

- 异步和单线程

- 其他(如: 日期、Math、各种常用API)

  **JS基础知识的特点: 表面看来并不能用于工作中开发代码(比如不能用JS基础知识让浏览器弹框)**

## JS-Web-API

- JS基础知识: ECMA262标准规定的

- JS-Web-API: 是W3C标准规定的

  - W3C标准没有规定任何JS基础相关的东西

  - 不管什么变量类型、原型、作用域和异步(这些是ECMA262标准规定的)

  - 只管定义用于浏览器中JS操作页面的API和全局变量

W3C标准中关于JS的规定有:

- DOM操作

- BOM操作

- 事件绑定

- ajax请求(包括http协议)

- 存储

页面弹框是`window.alert(1)`,浏览器需要做:

- 浏览器定义一个window全局变量,对象属性(window是浏览器作为JS执行环境注入的)

- 给他定义一个alert的属性,属性值是一个函数

获取元素`document.getElementById(id)`,浏览器需要做:

- 浏览器定义一个document全局变量,对象类型

- 给他定义一个getElementById的属性,属性值是一个函数

- 全面考虑,JS内置的全局函数和对象有哪些?

  - 有之前讲过的: Object、Array、Boolean、String、Math、JSON等

  - 还有刚刚提到的window、document

  - 和所有未定义的全局变量,如: navigation.userAgent

**总结**

- 常说的JS(浏览器执行的JS)包含两部份:

  - JS基础知识(ECMA262标准): 规定了一些基础语法

  - JS-Web-API(W3C标准)