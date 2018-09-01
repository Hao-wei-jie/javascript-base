# 其它知识点-日期和Math

**题目**

- 获取2017-06-10格式的日期

- 获取随机数,要求是长度一致的字符串格式

- 写一个能遍历对象和数组的通用forEach函数

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

## 对象API