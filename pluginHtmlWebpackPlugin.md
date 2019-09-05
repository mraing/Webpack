# html-webpack-plugin

它简化创建HTML文件，每次打包后能自动生成一个 入口 html 文件，并将打包好的代码引入。

### 安装

```javascript
npm install html-webpack-plugin -D
```

### 使用

#### 单页面打包

```javascript
const path = require('path')
const HtmlWebpackPlugin = require('html-webpack-plugin')

module.exports = {
  plugins: [
    mode: 'development',
    entry: './src/index.js',
    output: {
      filename: 'index.js',
      path: path.resolve(__dirname, 'dist')
    },
    new HtmlWebpackPlugin({
      // 将目录的 index.html 做为模板
      template: './index.html',
      // 输出之后的文件名
      filename: 'index.html'
    })
  ]
};
```

打包之后的会在根目录下面生出一个 `dist` 的文件夹，里面包含两个文件

**`dist`**

+ `home.js`

+ `other.js`

#### 多页面打包
  
多页面打包的话，需要多配置一个属性 `chunks`

```javascript
const path = require('path')
const HtmlWebpackPlugin = require('html-webpack-plugin')

module.exports = {
  mode: 'development',
  // 多入口
  entry: {
    home: './src/home.js',
    other: './src/other.js'
  },
  output: {
    filename: '[name].js',
    path: path.resolve(__dirname, 'dist')
  },
  plugins: [
    new HtmlWebpackPlugin({
      // 可以指定 根路径 index.html 做为模板/ 也可以不指定使用默认的模板
      template: './index.html',
      // 输出之后的文件名
      filename: 'home.html',
      // 代码块，将需要的代码块打包进来
      chunks: ['home']
    }),
    new HtmlWebpackPlugin({
      // 可以指定 根路径 index.html 做为模板/ 也可以不指定使用默认的模板
      // template: './index.html',
      // 输出之后的文件名
      filename: 'other.html',
      // 代码块，将需要的代码块打包进来
      chunks: ['other']
    })
  ]
}
```

打包之后的会在根目录下面生出一个 `dist` 的文件夹，里面包含四个文件

**`dist`**

+ `home.html`

+ `home.js`

+ `other.html`

+ `other.js`


[更多详细参数点击这里参阅](https://github.com/jantimon/html-webpack-plugin)