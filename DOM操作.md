# DOM操作

- DOM(文档对象模型): Document Object Model

## 题目

- DOM是哪种基本的数据结构

  - 树结构

- DOM操作的常用API有哪些

  - 获取DOM节点,以及节点的property和Attribute

  - 获取父节点,获取子节点

  - 新增节点,删除节点

- DOM节点的attr和property有何区别

  - property是对JS对象的属性进行修改和获取

  - Attribute是对HTML标签属性的修改和获取

**知识点**

## DOM本质

  - DOM可以理解为: 浏览器把拿到的HTML代码,结构化为一个浏览器能识别并且JS可操作的一个模型

## DOM节点操作

   - 获取DOM节点

   ```
   var div1 = document.getElementById('div1') // 元素
   var divList = document.getElementsByTagName('div') // 集合
   console.log(divList.length)
   console.log(divList[0])

   var containerList = document.getElementsByClassName('.container') // 集合
   var pList = document.querySelectorAll('p') // 集合
   ```

   - property  
     property: JS对象的属性

   ```
   var pList = document.querySelectorAll('p')
   var p = pList[0] // p是一个JS对象(不然JS怎么操作),JS对象是可拓展属性的  
   console.log(p.style.width) // 获取样式
   p.style.width = '100px' // 修改样式
   console.log(p.className) // 获取className
   p.className = 'p1' // 修改class
   // 以上的属性是浏览器添加的

   // 获取nodeName和nodeType
   console.log(p.nodeName)
   console.log(p.nodeType)
   ```

   - Attribute  
     Attribute: HTML标签的属性

   ```
   var pList = document.querySelectorAll('p')
   var p = pList[0]
   p.getAttribute('data-name')
   p.setAttribute('data-name', 'imooc')
   p.getAttribute('style')
   p.setAttribute('style', 'font-size: 30px;')
   ```

## DOM结构操作

   - 新增节点

   ```
   var div1 = document.getElementById('div1')
   // 添加新节点
   var p1 = document.createElement('p')
   p1.innerHTML = 'this is p1'
   div1.appendChild(p1) // 添加新创建的元素
   // 移动已有节点
   var p2 = document.getElementById('p2')
   div1.appendChild(p2)
   ```

   - 获取父元素

   ```
   var div1 = document.getElementById('div1')
   var parent = div1.parentElement
   ```

   - 获取子节点

   ```
   var div1 = document.getElementById('div1')
   var child = div1.childNodes
   // 注意: childNodes获取的数组里会有空字符(就是元素与元素之间的空格): #text,可以通过nodeType(或nodeName)来判断是否是元素,例:
   console.log(div1.childNodes[0].nodeType) // 如果打印1那说明是元素,如果打印3那说明是text
   ```

   - 删除节点

   ```
   var div1 = document.getElementById('div1')
   var child = div1.childNodes
   div1.removeChild(child[0])
   ```