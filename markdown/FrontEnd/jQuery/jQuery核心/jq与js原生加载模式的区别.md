# jq与js原生加载模式的区别

原生js中如果写了多个入口函数，后面写的会覆盖前面写的，但是jq如果写了多个入口函数，则会依次执行

加载时机的区别：
    jquery入口函数在document.ready时执行，而不是document.onload


