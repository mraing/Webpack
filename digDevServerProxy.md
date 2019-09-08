# proxy

### 什么是跨域？

不想过多解释，想了解的可以自行去百度或者谷歌。

简单来说就是

?> 因为浏览器的安全机制，不允许一个域下的文档或脚本试图去请求另一个域下的资源

### 模拟后台请求地址

代理请求，以达到欺骗浏览器的目的。

我们可以在创建 JS 文件，建立本地服务，模拟后台请求地址。

```javascript
// server.js
// express 是 node 的框架，实现服务端的一些功能
const express = require('express')

const app = express()

app.get('/home',(req, res) => {
  res.json({
    name: 'My name is Mr.Lee',
    age: '0000'
  })
})

app.listen(3000)
```
这样就建立好了一个本地服务，启动服务后打开浏览器 `http://localhost:3000/home`, 便能看到我们刚刚建好的 JSON 数据。

### 配置代理

```javascript
// webpack.config.js
devServer: {
  proxy: {
    '/api': {
      target: 'http://localhost:3000', // 相当于配置了一个代理，只有有访问到'/api'的就代理到 3000 端口下
      pathRewrite: {  //重定向
        '^/api': ''
      }
    }
  }
}
```


