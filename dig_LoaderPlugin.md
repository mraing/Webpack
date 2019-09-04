# loader 和 plugin 的区别

在学习过程中，我发现 loader 和 plugin 容易混淆，因此我去查阅了相关资料，去了解这两个的区别，并记录下来。

## loader

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

