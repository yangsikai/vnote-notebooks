# package.json 指南

如果使用 JavaScript、或者曾经与 JavaScript 项目、Node.js 或前端项目进行过交互，则肯定会遇到过 `package.json` 文件。

它有什么用途？应该了解它的什么，可以使用它完成哪些有趣的事情？

`package.json` 文件是项目的清单。 它可以做很多完全互不相关的事情。 例如，它是用于工具的配置中心。 它也是 `npm` 和 `yarn` 存储所有已安装软件包的名称和版本的地方。

## 文件结构

这是一个示例的 package.json 文件：

```json
{}
```

它是空的！ 对于应用程序，`package.json` 文件中的内容没有固定的要求。 唯一的要求是必须遵守 JSON 格式，否则，尝试以编程的方式访问其属性的程序则无法读取它。

如果要构建要在 `npm` 上分发的 Node.js 软件包，则必须具有一组可帮助其他人使用它的属性。 稍后会详细介绍。

这是另一个 package.json：

```json
{
  "name": "nodejs_cn"
}
```

它定义了 `name` 属性，用于告知应用程序或软件包的名称。

这是一个更复杂的示例，该示例是从 Vue.js 应用程序示例中提取的：

```json
{
  "name": "test-project",
  "version": "1.0.0",
  "description": "A Vue.js project",
  "main": "src/main.js",
  "private": true,
  "scripts": {
    "dev": "webpack-dev-server --inline --progress --config build/webpack.dev.conf.js",
    "start": "npm run dev",
    "unit": "jest --config test/unit/jest.conf.js --coverage",
    "test": "npm run unit",
    "lint": "eslint --ext .js,.vue src test/unit",
    "build": "node build/build.js"
  },
  "dependencies": {
    "vue": "^2.5.2"
  },
  "devDependencies": {
    "autoprefixer": "^7.1.2",
    "babel-core": "^6.22.1",
    "babel-eslint": "^8.2.1",
    "babel-helper-vue-jsx-merge-props": "^2.0.3",
    "babel-jest": "^21.0.2",
    "babel-loader": "^7.1.1",
    "babel-plugin-dynamic-import-node": "^1.2.0",
    "babel-plugin-syntax-jsx": "^6.18.0",
    "babel-plugin-transform-es2015-modules-commonjs": "^6.26.0",
    "babel-plugin-transform-runtime": "^6.22.0",
    "babel-plugin-transform-vue-jsx": "^3.5.0",
    "babel-preset-env": "^1.3.2",
    "babel-preset-stage-2": "^6.22.0",
    "chalk": "^2.0.1",
    "copy-webpack-plugin": "^4.0.1",
    "css-loader": "^0.28.0",
    "eslint": "^4.15.0",
    "eslint-config-airbnb-base": "^11.3.0",
    "eslint-friendly-formatter": "^3.0.0",
    "eslint-import-resolver-webpack": "^0.8.3",
    "eslint-loader": "^1.7.1",
    "eslint-plugin-import": "^2.7.0",
    "eslint-plugin-vue": "^4.0.0",
    "extract-text-webpack-plugin": "^3.0.0",
    "file-loader": "^1.1.4",
    "friendly-errors-webpack-plugin": "^1.6.1",
    "html-webpack-plugin": "^2.30.1",
    "jest": "^22.0.4",
    "jest-serializer-vue": "^0.3.0",
    "node-notifier": "^5.1.2",
    "optimize-css-assets-webpack-plugin": "^3.2.0",
    "ora": "^1.2.0",
    "portfinder": "^1.0.13",
    "postcss-import": "^11.0.0",
    "postcss-loader": "^2.0.8",
    "postcss-url": "^7.2.1",
    "rimraf": "^2.6.0",
    "semver": "^5.3.0",
    "shelljs": "^0.7.6",
    "uglifyjs-webpack-plugin": "^1.1.1",
    "url-loader": "^0.5.8",
    "vue-jest": "^1.0.2",
    "vue-loader": "^13.3.0",
    "vue-style-loader": "^3.0.1",
    "vue-template-compiler": "^2.5.2",
    "webpack": "^3.6.0",
    "webpack-bundle-analyzer": "^2.9.0",
    "webpack-dev-server": "^2.9.1",
    "webpack-merge": "^4.1.0"
  },
  "engines": {
    "node": ">= 6.0.0",
    "npm": ">= 3.0.0"
  },
  "browserslist": ["> 1%", "last 2 versions", "not ie <= 8"]
}
```

这里有很多东西：

- `name` 设置了应用程序/软件包的名称。
- `version` 表明了当前的版本。
- `description` 是应用程序/软件包的简短描述。
- `main` 设置了应用程序的入口点。
- `private` 如果设置为 `true`，则可以防止应用程序/软件包被意外地发布到 `npm`。
- `scripts` 定义了一组可以运行的 node 脚本。
- `dependencies` 设置了作为依赖安装的 `npm` 软件包的列表。
- `devDependencies` 设置了作为开发依赖安装的 `npm` 软件包的列表。
- `engines` 设置了此软件包/应用程序在哪个版本的 Node.js 上运行。
- `browserslist` 用于告知要支持哪些浏览器（及其版本）。

以上所有的这些属性都可被 `npm` 或其他工具使用。

## 属性分类

本节详细介绍了可以使用的属性。

其中大多数属性仅可用于 [https://www.npmjs.com/](https://www.npmjs.com/)，其他属性则可被与代码交互的脚本（例如 `npm` 或其他工具）使用。

### name

设置软件包的名称。

示例：

```json
"name": "nodejs_cn"
```

名称必须少于 214 个字符，且不能包含空格，只能包含小写字母、连字符（`-`）或下划线（`_`）。

这是因为当软件包在 `npm` 上发布时，它会基于此属性获得自己的 URL。

如果在 GitHub 上公开地发布此软件包，则 GitHub 仓库的名称是作为此属性的不错选择。

### author

列出软件包的作者名称。

示例：

```json
{
  "author": "NodeJS中文网 <mail@nodejs.cn> (http://nodejs.cn)"
}
```

也可以使用以下格式：

```json
{
  "author": {
    "name": "NodeJS中文网",
    "email": "mail@nodejs.cn",
    "url": "http://nodejs.cn"
  }
}
```

### contributors

除作者外，该项目可以有一个或多个贡献者。 此属性是列出他们的数组。

示例：

```json
{
  "contributors": ["NodeJS中文网 <mail@nodejs.cn> (http://nodejs.cn))"]
}
```

也可以使用以下格式：

```json
{
  "contributors": [
    {
      "name": "NodeJS中文网",
      "email": "mail@nodejs.cn",
      "url": "http://nodejs.cn"
    }
  ]
}
```

### bugs

链接到软件包的问题跟踪器，最常用的是 GitHub 的 issues 页面。

示例：

```json
{
  "bugs": "https://github.com/nodejscn/node-api-cn/issues"
}
```

### homepage

设置软件包的主页。

示例：

```json
{
  "homepage": "http://nodejs.cn"
}
```

### version

指定软件包的当前版本。

示例：

```json
"version": "1.0.0"
```

此属性遵循版本的语义版本控制记法，这意味着版本始终以 3 个数字表示：`x.x.x`。

第一个数字是主版本号，第二个数字是次版本号，第三个数字是补丁版本号。

这些数字中的含义是：仅修复缺陷的版本是补丁版本，引入向后兼容的更改的版本是次版本，具有重大更改的是主版本。

### license

指定软件包的许可证。

示例：

```json
"license": "MIT"
```

### keywords

此属性包含与软件包功能相关的关键字数组。

示例：

```json
"keywords": [
  "email",
  "machine learning",
  "ai"
]
```

这有助于人们在浏览相似的软件包或浏览 [https://www.npmjs.com/](https://www.npmjs.com/) 网站时找到你的软件包。

### description

此属性包含了对软件包的简短描述。

示例：

```json
"description": "NodeJS中文网入门教程"
```

如果要将软件包发布到 `npm`，则这个属性特别有用，人们可以知道该软件包是干啥用的。

### repository

此属性指定了此程序包仓库所在的位置。

示例：

```json
"repository": "github:nodejscn/node-api-cn",
```

注意 `github` 前缀。 其他流行的服务商还包括：

```json
"repository": "gitlab:nodejscn/node-api-cn",
```

```json
"repository": "bitbucket:nodejscn/node-api-cn",
```

可以显式地设置版本控制系统：

```json
"repository": {
  "type": "git",
  "url": "https://github.com/nodejscn/node-api-cn.git"
}
```

也可以使用其他的版本控制系统：

```json
"repository": {
  "type": "svn",
  "url": "..."
}
```

### main

设置软件包的入口点。

当在应用程序中导入此软件包时，应用程序会在该位置搜索模块的导出。

示例：

```json
"main": "src/main.js"
```

### private

如果设置为 `true`，则可以防止应用程序/软件包被意外发布到 `npm` 上。

示例：

```json
"private": true
```

### scripts

可以定义一组可以运行的 node 脚本。

示例：

```json
"scripts": {
  "dev": "webpack-dev-server --inline --progress --config build/webpack.dev.conf.js",
  "start": "npm run dev",
  "unit": "jest --config test/unit/jest.conf.js --coverage",
  "test": "npm run unit",
  "lint": "eslint --ext .js,.vue src test/unit",
  "build": "node build/build.js"
}
```

这些脚本是命令行应用程序。 可以通过调用 `npm run XXXX` 或 `yarn XXXX` 来运行它们，其中 `XXXX` 是命令的名称。 例如：`npm run dev`。

可以为命令使用任何的名称，脚本也可以是任何操作。

### dependencies

设置作为依赖安装的 `npm` 软件包的列表。

当使用 npm 或 yarn 安装软件包时：

```sh
npm install <PACKAGENAME>
yarn add <PACKAGENAME>
```

该软件包会被自动地插入此列表中。

示例：

```json
"dependencies": {
  "vue": "^2.5.2"
}
```

### devDependencies

设置作为开发依赖安装的 `npm` 软件包的列表。

它们不同于 `dependencies`，因为它们只需安装在开发机器上，而无需在生产环境中运行代码。

当使用 npm 或 yarn 安装软件包时：

```sh
npm install --dev <PACKAGENAME>
yarn add --dev <PACKAGENAME>
```

该软件包会被自动地插入此列表中。

示例：

```json
"devDependencies": {
  "autoprefixer": "^7.1.2",
  "babel-core": "^6.22.1"
}
```

### engines

设置此软件包/应用程序要运行的 Node.js 或其他命令的版本。

示例：

```json
"engines": {
  "node": ">= 6.0.0",
  "npm": ">= 3.0.0",
  "yarn": "^0.13.0"
}
```

### browserslist

用于告知要支持哪些浏览器（及其版本）。 Babel、Autoprefixer 和其他工具会用到它，以将所需的 polyfill 和 fallback 添加到目标浏览器。

示例：

```json
"browserslist": [
  "> 1%",
  "last 2 versions",
  "not ie <= 8"
]
```

此配置意味着需要支持使用率超过 1％（来自 [CanIUse.com](https://caniuse.com/) 的统计信息）的所有浏览器的最新的 2 个主版本，但不含 IE8 及更低的版本。

([查看更多](https://www.npmjs.com/package/browserslist))

### 命令特有的属性

`package.json` 文件还可以承载命令特有的配置，例如 Babel、ESLint 等。

每个都有特有的属性，例如 `eslintConfig`、`babel` 等。 它们是命令特有的，可以在相应的命令/项目文档中找到如何使用它们。

## 软件包版本

在上面的描述中，已经看到类似以下的版本号：`〜3.0.0` 或 `^0.13.0`。 它们是什么意思，还可以使用哪些其他的版本说明符？

该符号指定了软件包能从该依赖接受的更新。

鉴于使用了 semver（语义版本控制），所有的版本都有 3 个数字，第一个是主版本，第二个是次版本，第三个是补丁版本，具有以下规则：

- `~`: 如果写入的是 `〜0.13.0`，则只更新补丁版本：即 `0.13.1` 可以，但 `0.14.0` 不可以。
- `^`: 如果写入的是 `^0.13.0`，则要更新补丁版本和次版本：即 `0.13.1`、`0.14.0`、依此类推。
- `*`: 如果写入的是 `*`，则表示接受所有的更新，包括主版本升级。
- `>`: 接受高于指定版本的任何版本。
- `>=`: 接受等于或高于指定版本的任何版本。
- `<=`: 接受等于或低于指定版本的任何版本。
- `<`: 接受低于指定版本的任何版本。

还有其他的规则：

- 无符号: 仅接受指定的特定版本。
- `latest`: 使用可用的最新版本。

还可以在范围内组合以上大部分内容，例如：`1.0.0 || >=1.1.0 <1.2.0`，即使用 1.0.0 或从 1.1.0 开始但低于 1.2.0 的版本。