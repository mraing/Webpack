# plugin

?> 插件可以用于执行范围更广的任务。包括：打包优化，资源管理，注入环境变量。

**插件目的在于解决loader无法实现的其他事**

由于插件可以携带参数/选项，你必须在webpack配置中，向plugins属性传入new实例。

插件用过 npm 安装，在初始化插件时，命名应该是 `驼峰式命名` 的插件名称。建议为此 `使用一个常量` ，以便它可以在所有钩中复用。

下面是一个基础的例子，插件使用的方式都是以这种形式去进行的。

```javascript
const HtmlWebpackPlugin = require('html-webpack-plugin'); //通过 npm 安装

module.exports = {
  // 在plugins传入new实例
  plugins: [
    new HtmlWebpackPlugin({template: './src/index.html'})
  ]
};
```


