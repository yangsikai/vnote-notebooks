# map方法

map方法遍历对每个元素做指定的操作

js原生的map方法：只能遍历数组，不能遍历伪数组
* 第一个参数：当前遍历到的元素
* 第二个参数：当前遍历的索引
* 第三个参数：遍历的数组
```js
arr.map(function(value, index, arr){...});
```

jquery的map方法：不仅可以遍历数组，也可以遍历伪数组
* 第一个参数：要遍历的数组
* 第二个参数：回调函数
    * 回调函数第一个参数：遍历到的元素
    * 回调函数第二个参数：遍历到的索引
```js
$.map(arr, function(value, index){......})
```

jquery中的map方法，默认返回 `[]`，如果在回调函数中返回了数据，会把返回值组合成一个新的数组返回
map方法中通过return可以对遍历的数组进行处理，生成新的数组返回
