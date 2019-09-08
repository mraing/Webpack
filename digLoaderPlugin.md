# loader 和 plugin 的区别

在学习过程中，我发现 loader 和 plugin 容易混淆，因此我去查阅了相关资料，去了解这两个的区别，并记录下来。

## loader

?> 对于loader，它就是一个转换器，将A文件进行编译形成B文件，这里操作的是文件。比如将A.scss或A.less转变为B.css，单纯的文件转换过程。

#### 安装

  一般安装loader 的插件的时候，loader 插件的命名都是 `name-loader`

  常用的 loader :
  + 样式：style-loader、css-loader、less-loader、sass-loader等
  + 文件：raw-loader、file-loader 、url-loader等
  + 编译：babel-loader、coffee-loader 、ts-loader等
  + 校验测试：mocha-loader、jshint-loader 、eslint-loader等

#### 使用
  
  loader 有三种使用方式，不过我们最常用的，也是官方建议的使用方式是在`配置文件`中去使用它。

  在 `module.rules` 中去配置 loader，下面代码就是一个很经典的例子。

  ```javascript
  module: {
    // 规则
    rules: [
      {
        // 处理 .css 文件的规则
        test: /\.css$/,
        use: [
          'style-loader',
          'css-loader',
          'postcss-loader'
        ]
      }
    ]
  }
  ```

## plugin

?> webpack 的 `plugin` 比 `loader` 强大，通过钩子可以涉及整个构建流程，可以做一些在构建范围内的事情。

对于plugin，它就是一个扩展器，它丰富了wepack本身，针对是loader结束后，webpack打包的整个过程，它并不直接操作文件，而是基于事件机制工作，会监听webpack打包过程中的某些节点，执行广泛的任务。

webpack插件是一个具有 apply 属性的JavaScript对象。apply属性会被webpack compiler调用，并且compiler对象可在整个编译周期访问。


#### 安装

loader 插件的命名都是 `name-plugin` 

常用的 plugin:
+ `ProvidePlugin`: 自动加载模块，代替require和import

+ `html-webpack-plugin`: 可以根据模板自动生成html代码，并自动引用css和js文件

+ `extract-text-webpack-plugin`: 将js文件中引用的样式单独抽离成css文件

+ `DefinePlugin`: 编译时配置全局变量，这对开发模式和发布模式的构建允许不同的行为非常有用

+ `HotModuleReplacementPlugin`: 热更新

+ `babili-webpack-plugin、transform-runtime 、transform-object-rest-spread`: 将高级语法解析成低级语法

+ `optimize-css-assets-webpack-plugin`: 不同组件中重复的css可以快速去重

+ `webpack-bundle-analyzer`: 一个webpack的bundle文件分析工具，将bundle文件以可交互缩放的treemap的形式展示

+ `compression-webpack-plugin`: 生产环境可采用gzip压缩JS和CSS

+ `happypack`: 通过多进程模型，来加速代码构建

#### 使用

  下面将展示一个很基础的例子

  ```javascript
  // 找到 mini-css-extract-plugin 插件
  const MiniCSSExtractPlugin = require('mini-css-extract-plugin')

  plugin [
    new MiniCSSExtractPlugin ({
      // 整合CSS之后的文件名
      filename: 'main.css'
    })
  ]
  ```