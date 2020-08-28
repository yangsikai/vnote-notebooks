# 基本用法

## 输出

该模块提供了大量非常有用的与命令行交互的方法。

它基本上与浏览器中的 `console` 对象相同。

最基础、最常用的方法是 `console.log()`，该方法会打印传入到控制台的字符串。

如果传入对象，则它会呈现为字符串。

可以传入多个变量到 `console.log`

也可以通过传入变量和格式说明符来格式化用语。例如：
- `%s` 会格式化变量为字符串
- `%d` 会格式化变量为数字
- `%i` 会格式化变量为其整数部分
- `%o` 会格式化变量为对象

## 清空

`console.clear()` 会清除控制台（其行为可能取决于所使用的控制台）。

## 元素计数

`console.count()` 是一个便利的方法。

count 方法会对打印的字符串的次数进行计数，并在其旁边打印计数

## 打印堆栈踪迹

在某些情况下，打印函数的调用堆栈踪迹很有用，可以回答以下问题：如何到达代码的那一部分？

可以使用 `console.trace()` 实现：

```javascript
const function2 = () => console.trace()
const function1 = () => function2()
function1()
```

这会打印堆栈踪迹。 如果在 Node.js REPL 中尝试此操作，则会打印以下内容：

```txt
Trace
    at function2 (repl:1:33)
    at function1 (repl:1:25)
    at repl:1:1
    at ContextifyScript.Script.runInThisContext (vm.js:44:33)
    at REPLServer.defaultEval (repl.js:239:29)
    at bound (domain.js:301:14)
    at REPLServer.runBound [as eval] (domain.js:314:12)
    at REPLServer.onLine (repl.js:440:10)
    at emitOne (events.js:120:20)
    at REPLServer.emit (events.js:210:7)
```

## 计算耗时

可以使用 `time()` 和 `timeEnd()` 轻松地计算函数运行所需的时间：

```javascript
const doSomething = () => console.log('测试')
const measureDoingSomething = () => {
  console.time('doSomething()')
  //做点事，并测量所需的时间。
  doSomething()
  console.timeEnd('doSomething()')
}
measureDoingSomething()
```

## stdout 和 stderr

console.log 非常适合在控制台中打印消息。 这就是所谓的标准输出（或称为 `stdout`）。

`console.error` 会打印到 `stderr` 流。

它不会出现在控制台中，但是会出现在错误日志中。

## 为输出着色

可以使用[转义序列](https://gist.github.com/iamnewton/8754917)在控制台中为文本的输出着色。 转义序列是一组标识颜色的字符。

例如：

```javascript
console.log('\x1b[33m%s\x1b[0m', '你好')
```

可以在 Node.js REPL 中进行尝试，它会打印黄色的 `你好`。

当然，这是执行此操作的底层方法。 为控制台输出着色的最简单方法是使用库。 [Chalk](https://github.com/chalk/chalk) 是一个这样的库，除了为其着色外，它还有助于其他样式的设置（例如使文本变为粗体、斜体或带下划线）。

可以使用 `npm install chalk` 进行安装，然后就可以使用它：

```javascript
const chalk = require('chalk')
console.log(chalk.yellow('你好'))
```

与尝试记住转义代码相比，使用 `chalk.yellow` 方便得多，并且代码更具可读性。

更多的用法示例，详见上面的项目链接。

## 创建进度条

[Progress](https://www.npmjs.com/package/progress) 是一个很棒的软件包，可在控制台中创建进度条。 使用 `npm install progress` 进行安装。

以下代码段会创建一个 10 步的进度条，每 100 毫秒完成一步。 当进度条结束时，则清除定时器：

```javascript
const ProgressBar = require('progress')

const bar = new ProgressBar(':bar', { total: 10 })
const timer = setInterval(() => {
  bar.tick()
  if (bar.complete) {
    clearInterval(timer)
  }
}, 100)
```