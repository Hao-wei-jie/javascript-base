# BOM操作

- BOM(浏览器对象模型): Browser Object Model

**题目**

- 如何检测浏览器的类型

```
var ua = navigator.userAgent // 返回一个字符串
var isChrome = ua.indexOf('chrome') // 查看返回的字符串里有没有chrome
console.log(isChrome)
```

- 拆解url各部分

```
console.log(location.href) // URL
console.log(location.protocol) // 协议: 'http:'
console.log(location.host) // 域名
console.log(location.pathname) // 路径名
console.log(location.search) // URL里?后面的字符串
console.log(location.hash) // URL里#后面的字符串
```

**知识点**

## navigator

```
var ua = navigator.userAgent // 返回一个字符串
var isChrome = ua.indexOf('chrome') // 查看返回的字符串里有没有chrome
console.log(isChrome)
```

## screen

```
console.log(screen.width) // 打印屏幕的宽度
console.log(screen.height) // 打印屏幕的高度
```

## location

```
console.log(location.href) // URL
console.log(location.protocol) // 协议: 'http:'
console.log(location.host) // 域名
console.log(location.pathname) // 路径名
console.log(location.search) // URL里?后面的字符串
console.log(location.hash) // URL里#后面的字符串
```

## history

```
history.back() // 返回上一页
history.forward() // 前进到前一页
```