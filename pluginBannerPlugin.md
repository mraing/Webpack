# BannerPlugin

?> 在打包后的文件中前面添加版权声明

`BannerPlugin` 属于 webapck 的内置插件，所以我们直接引用 webpack 就可以了。

### 使用

```javascript
const Webapck = require('webpack')

module.exports = {
  plugins: [
    //  BannerPlugin中的参数是字符串
    new Webapck.BannerPlugin('需要声明的版权信息')
  ]
}
```