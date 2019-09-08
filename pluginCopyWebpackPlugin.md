# CopyWebpackPlugin

?> 复制文件到输出目录下

比如在根目录下有一个 `doc` 文件夹，我需要在打包的时候，把这个目录放入到打包文件中，这时我们就会需要用到这个插件 `CopyWebpackPlugin`

### 安装

```javascript
npm install copy-webpack-plugin -D
```

### 使用
```javascript
const CopyWebpackPlugin = require('copy-webpack-plugin')

module.exports = {
  plugins: [
    // 复制多个文件，则用多个对象去表示
    // from: 需要复制的文件的目录，也可以指定文件，比如 ./doc/hello.md
    // to: 默认就是在输出目录下
    // to: './' :表示在 ‘./dist’ 根目录下 
    // to: './doc' 表示在 './dist' 目录下新建一个叫做 `doc`的文件夹
    new CopyWebpackPlugin([
      {from: './doc', to: './'}
    ])
  ]
}
```

[点击查看更多详细配置](https://github.com/webpack-contrib/copy-webpack-plugin)