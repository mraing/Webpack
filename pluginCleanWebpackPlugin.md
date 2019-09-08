# CleanWebpackPlugin

?> 清除历史残留文件

比如我们进行重复打包时，打包后webpack不会自动删除打包目录下的历史文件，所以我们需要这样一个插件 `CleanWebpackPlugin`

### 安装

```javascript
npm install clean-webpack-plugin -D
```

### 使用

```javascript
const { CleanWebpackPlugin } = require('clean-webpack-plugin')

module.exports = {
  plugins: [
    // 默认清除 output 输出目录下的无用历史文件
    new CleanWebpackPlugin()
  ]
}
```

[点击查看更多详细配置](https://github.com/johnagan/clean-webpack-plugin)
