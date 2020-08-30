# Electron例子一

```js
var electron = require("electron");

var app = electron.app; // 引用 app
var BrowserWindow = electron.BrowserWindow; // 窗口引用

var mainWindow = null; // 声明要打开的主窗口

app.on("ready", () => {
  mainWindow = new BrowserWindow({ width: 800, height: 800 });
  mainWindow.loadFile("index.html"); // 加载HTML页面
  mainWindow.on("closed", () => {
    // 关闭时释放窗口引用
    mainWindow = null;
  });
});
```

使用 `electron .` 运行
> 注意：要将package.json的main属性修改成自己的入口文件

