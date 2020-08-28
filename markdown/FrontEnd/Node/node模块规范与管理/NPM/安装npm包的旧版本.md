# 安装npm包的旧版本

可以使用 `@` 语法来安装 npm 软件包的旧版本：

```sh
npm install <package>@<version>
```

示例：

```sh
npm install cowsay
```

以上命令会安装 1.3.1 版本（在撰写本文时）。

使用以下命令可以安装 1.2.0 版本：

```sh
npm install cowsay@1.2.0
```

全局的软件包也可以这样做：

```sh
npm install -g webpack@4.16.4
```

可能还有需要列出软件包所有的以前的版本。 可以使用 `npm view <package> versions`：

```txt
❯ npm view cowsay versions

[ '1.0.0',
  '1.0.1',
  '1.0.2',
  '1.0.3',
  '1.1.0',
  '1.1.1',
  '1.1.2',
  '1.1.3',
  '1.1.4',
  '1.1.5',
  '1.1.6',
  '1.1.7',
  '1.1.8',
  '1.1.9',
  '1.2.0',
  '1.2.1',
  '1.3.0',
  '1.3.1' ]
```