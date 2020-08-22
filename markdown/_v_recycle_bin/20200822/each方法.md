# each方法

each 是jq的一个静态方法，用来遍历数组

原生js的写法：原生的forEach方法只能遍历数组，不能遍历伪数组
```js
arr.forEach(function(value, index){......});
```

jq的each方法不仅可以遍历数组，也可以遍历伪数组
* 第一个参数：当前遍历的索引
* 第二个参数：当前遍历的值
```js
$.each(arr, function(index, value){......});
```

jquery中的each方法，默认是遍历谁就返回谁
each方法不支持在回调函数中对数组进行处理
