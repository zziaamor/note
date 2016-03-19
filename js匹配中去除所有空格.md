---
title: js匹配中去除所有空格
date: 2016-03-17 18:18:12
tags: HTML5
---
#   trim()仅仅是去除字符串左右两边的空格

<!--more-->

## 具体代码如下
```javascript
var text = document.getElementById('input_search').value;//获取输入值

            var   reg   =   /\s/g;                                
            var   text1   =   text.replace(reg,   "");            //去除所有的空格
            alert(text1);
```