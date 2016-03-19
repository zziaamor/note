---
title: JSON常用方法
date: 2016-03-17 11:32:33
tags: HTML5
---
## 三级联动问题中的多个NAME问题

<!--more-->



 ### 格式 
 ```javascript
var all=[

  { "name": "北京", "city":[{"name":"北京",
      "area":[
          {"name":"东城区"},  { "name":"西城区"},{"name":"朝阳区"}]}]},



  { "name": "天津", "city":[{"name":"天津","area":[
      {"name":"和平区"},  { "name":"河东区"},{"name":"塘沽区"}]}]},

  { "name": "河北", "city":[

      {"name":"石家庄","area":[{"name":"长安区"},{"name":"桥东区"},{"name":"桥西"},{"name":"新华区"}]},

      {"name":"唐山","area":[{"name":"路南区"},{"name":"路北区"},{"name":"古治"},{"name":"新区"}]},

      {"name":"秦皇岛","area":[{"name":"长安区"},{"name":"桥东区"},{"name":"桥西"},{"name":"新华区"}]},

      {"name":"邯郸","area":[{"name":"路南区"},{"name":"路北区"},{"name":"古治"},{"name":"新区"}]},

  ]}];
```
### 使用
```javascript
 var op;
  window.onload=function(){
      var sel=document.getElementById('pro');
      for(var i=0;i<all.length;i++){
          op=document.createElement('option');
          op.setAttribute('value',all[i].name);
          op.innerHTML=all[i].name;
          sel.appendChild(op);
      }

  }
  function getPro(){
      //获取选中项的内容

      var sel=document.getElementById('pro');
      var con=sel.selectedIndex;

  city.innerHTML='';
   var option1;
  for(var i=0;i<all[con].city.length;i++){
      option1=document.createElement('option');
      option1.setAttribute('value',all[con].city[i].name);
      option1.innerHTML=all[con].city[i].name;
      city.appendChild(option1);

  }

  }
  function getCity(){
      //获取选中项的内容
      var sel=document.getElementById('pro');
      var con=sel.selectedIndex;
      var se=document.getElementById('city');
      var co=se.selectedIndex;

      area.innerHTML='';
   var option2;
  for(var i=0;i<all[con].city[co].area.length;i++){
      option2=document.createElement('option');
      option2.setAttribute('value',all[con].city[co].area[i].name);
      option2.innerHTML=all[con].city[co].area[i].name;
      area.appendChild(option2);

  }
```
## 单个NAME
### 格式

```javascript
var books = [{ "name":"《神曲》" , "author":"但丁" ,"price":"32"},
            { "name":"《堂吉诃德》" , "author":"塞万提斯" ,"price":"42"},
            { "name":"《格列佛游记》" , "author":"斯维达特","price":"22"},
            { "name":" 《复活的我》" , "author":"列夫托尔斯泰" ,"price":"23"},
            { "name":"《静静的顿河》" , "author":"肖洛霍夫" ,"price":"25"}];
```
### 使用
```javascript

 function (obj) {
    testTbl.innerHTML="";
    for (var j = 5 * (obj - 1); j < obj * 5; j++) {
       // alert(books[j].name);

    //添加一行

    var newTr = testTbl.insertRow();

    //添加两列
    var newTd0 = newTr.insertCell();
    newTd0.innerText =books[j].name;
    var newTd1 = newTr.insertCell();
        newTd1.innerText =books[j].author;
    var newTd3 = newTr.insertCell();
        newTd3.innerText =books[j].price;

}
```
      

            
            




