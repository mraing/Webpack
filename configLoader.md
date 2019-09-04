# loader

?> loader 用于对模块的源代码进行转换。

**webpack 只能理解 `JavaScript` 和 `JSON` 文件。loader 让 webpack 能够去处理其他类型的文件，并将它们转换为有效的模块，以供应用程序使用，以及被添加到依赖图中**

loader 有三种使用方式：
  + 配置(推荐) ：在 webpack.config.js 文件中指定 loader
  + 内联 ：在每个 import 语句中显式指定 loader
  + CLI ：在 shell 命令中指定它们


### 配置(推荐)

module.rules 允许你在 webpack 配置中指定多个 loader。并且有助于使代码变得简洁和易于维护。

`loader` 有两个属性：

+ `test`: 用于标识出应该被对应的 loader 进行转换的某个或某些文件。

  (指出文件后缀名，用正则表示)，使用正则表达式匹配文件时，不需要为它添加引号。
  
+ `use`: 表示进行转换时，应该使用哪个 loader。

  !> `loader` 是有按顺序执行的，遵循 `从下至上` 、 `从右至左的` 顺序。
  
  如果顺序弄错了的话，也许你的转换并不能成功。

```javascript
module.exports = {
  module: {
    rules: [
      {
        // 处理 .css 文件的规则
        test: /\.css$/,
        // 使用 loader
        // loader 可以是一个对象，也可以是一个字符串，多个 loader 用数组表示
        // loader的顺序是：到左 <- 从右， 从下 -> 上 的执行方式
        // style-loader: 把 CSS 插入到 head 中
        // css-loader: 解析 @improt 这种语法
        use: [
          'style-loader', // 整合CSS
          'css-loader', // 解析 @inport
          'postcss-loader', // 添加内核前缀
        ]
      },
    ]
  }
};
```

### 内联

可以在 import 语句或任何 等同于 "import" 的方法 中指定 loader。使用 ! 将资源中的 loader 分开。每个部分都会相对于当前目录解析。

```javascript
import Styles from 'style-loader!css-loader?modules!./styles.css';
```

使用 ! 为整个规则添加前缀，可以覆盖配置中的所有 loader 定义。


### CLI 

```javascript
webpack --module-bind jade-loader --module-bind 'css=style-loader!css-loader'
```

这会对 `.jade` 文件使用 `jade-loader`，以及对 `.css` 文件使用 `style-loader` 和 `css-loader`。