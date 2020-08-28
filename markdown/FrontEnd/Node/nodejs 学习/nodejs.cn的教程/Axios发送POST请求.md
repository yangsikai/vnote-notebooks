# 发送POST请求

在 Node.js 中，有多种方式可以执行 HTTP POST 请求，具体取决于要使用的抽象级别。

使用 Node.js 执行 HTTP 请求的最简单的方式是使用 [Axios 库](https://github.com/axios/axios)：

```javascript
const axios = require('axios')

axios
  .post('http://nodejs.cn/todos', {
    todo: '做点事情'
  })
  .then(res => {
    console.log(`状态码: ${res.statusCode}`)
    console.log(res)
  })
  .catch(error => {
    console.error(error)
  })
```

Axios 需要使用第三方的库。

也可以只使用 Node.js 的标准模块来发送 POST 请求，尽管它比前面的选择冗长些：

```javascript
const https = require('https')

const data = JSON.stringify({
  todo: '做点事情'
})

const options = {
  hostname: 'nodejs.cn',
  port: 443,
  path: '/todos',
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    'Content-Length': data.length
  }
}

const req = https.request(options, res => {
  console.log(`状态码: ${res.statusCode}`)

  res.on('data', d => {
    process.stdout.write(d)
  })
})

req.on('error', error => {
  console.error(error)
})

req.write(data)
req.end()
```