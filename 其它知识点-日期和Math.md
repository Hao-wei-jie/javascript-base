# 其它知识点-日期和Math

**题目**

- 获取2017-06-10格式的日期

```
function formatDate(dt) {
    if(!dt) {
        dt = new Date()
    }
    var year = dt.getFullYear()
    var month = dt.getMonth() + 1
    var date = dt.getDate()
    if(month < 10) {
        // 强制类型转换
        month = '0' + month
    }
    if(date < 10) {
        // 强制类型转换
        date = '0' + date
    }
    // 强制类型转换
    return year + '-' + month + '-' + date 
}
var dt = new Date()
var formatDate = formatDate(dt)
console.log(formatDate)
```

- 获取随机数,要求是长度一致的字符串格式

```
var random = Math.random()
var random = random + '0000000000' // 后面加上10个零
var random = random.slice(0, 10)   // 截取前10位
console.log(random)
```

- 写一个能遍历对象和数组的通用forEach函数

```
function forEach(obj, fn) {
    var key
    if(obj instanceof Array) {
        // 准确判断是不是数组
        obj.forEach(function(item, index) {
            fn(index, item) 
        })
    } else {
        // 不是数组就是对象
        for(key in obj) {
            fn(key, obj[key])
        }
    }
}

var arr = [1, 2, 3]
// 注意,这里参数的顺序换了,为了和对象的遍历格式一致
forEach(arr, function(index, item) {
    console.log(index, item)
})

var obj = {x: 100, y: 200}
forEach(obj, function(key, value) {
    console.log(key, value)
})
```

**知识点**

## 日期

```
Date.now() // 获取当前时间毫秒数
var date = new Date()
date.getTime()     // 获取毫秒数
date.getFullYear() // 年
date.getMonth()    // 月 (0 - 11) 月份要加一才是当前月份
date.getDate()     // 日 (0 - 31)
date.getHours()    // 小时 (0 - 23) 
date.getMinutes()  // 分钟 (0 - 59)
date.getSeconds()  // 秒 (0 - 59)
```

## Math

   - 获取随机数: Math.random() 返回一个大于0小于1的小数,一般可以清除缓存用: 将Math.random()加在链接后面

## 数组API

   - forEach(): 遍历所有元素

   ```
   var arr = [1, 2, 3]
   arr.forEach(function(item, index) { // 先item再index
       // 遍历数组的所有元素
       console.log(index, item) // item是每个元素的值,index是数组的下标
   })
   ```

   - every(): 判断所有元素是否都符合条件

   ```
   var arr = [1, 2, 3]
   var result = arr.every(function(item, index) {
       // 用来判断所有的数组元素,是否都满足一个条件
       if(item < 4) {
           return true
       }
   })
   console.log(result) // true
   ```

   - some 判断是否至少一个元素符合条件

   ```
   var arr = [1, 2, 3]
   var result = arr.some(function(item, index) {
       // 用来判断所有的数组元素,只要有一个满足条件即可
       if(item < 2) {
           return true
       }
   })
   console.log(result) // true
   ```

   - sort 从小到大排序

   ```
   var arr = [1, 4, 2, 3, 5]
   var arr2 = arr.sort(function(a, b) {
       // 从小到大排序
       return a - b

       // 从大到小排序
       // return b - a
   })
   console.log(arr2) // [1, 2, 3, 4, 5]
   ```

   - map 对元素重新组装,生成新数组

   ```
   var arr = [1, 2, 3, 4]
   var arr2 = arr.map(function(item, index) {
       // 将元素重新组装,并返回
       return '<b>' + item + '</b>'
   })
   console.log(arr2)
   ```

   - filter 过滤符合条件的元素

   ```
   var arr = [1, 2, 3]
   var arr2 = arr.filter(function(item, index) {
       // 通过某一个条件过滤数组
       if(item >= 2) {
           return true
       }
   })
   console.log(arr2) // [2, 3]
   ```

## 对象API

```
var obj = {
    x: 100,
    y: 200,
    z: 300
}
var key
for(key in obj) {
    // 如果key不是来自obj原型上的属性,那hasOwnProperty会返回true
    if(obj.hasOwnProperty(key)) {
        console.log(key, obj[key]) // x 100, y 200, z 300
    }
}
```