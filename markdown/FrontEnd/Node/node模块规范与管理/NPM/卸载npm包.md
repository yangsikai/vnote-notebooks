# 卸载npm包

若要卸载之前在本地安装（在 `node_modules` 文件夹使用 `npm install <package-name>`）的软件包，则从项目的根文件夹（包含 `node_modules` 文件夹的文件夹）中运行：

```sh
npm uninstall <package-name>
```

如果使用 `-S` 或 `--save` 标志，则此操作还会移除 `package.json` 文件中的引用。

如果程序包是开发依赖项（列出在 `package.json` 文件的 devDependencies 中），则必须使用 `-D` 或 `--save-dev` 标志从文件中移除：

```sh
npm uninstall -S <package-name>
npm uninstall -D <package-name>
```

如果该软件包是全局安装的，则需要添加 `-g` 或 `--global` 标志：

```sh
npm uninstall -g <package-name>
```

例如：

```sh
npm uninstall -g webpack
```

可以在系统上的任何位置运行此命令，因为当前所在的文件夹无关紧要。