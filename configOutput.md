# output

?> `output` 属性告诉 webpack 在哪里输出它所创建的 `打包好的文件` ，以及如何命名这些文件。

主要输出文件的默认值是 `./dist/main.js`，其他生成文件默认放置在 `./dist` 文件夹中。

!> 需要注意的是: 输出路径必须是绝对路径

如果只设置文件名，`webapck` 会默认配置将一个单独的bundle.js文件输出到dist目录中。

```javascript
// 把相对路径转换为绝对路径
const path = require('path');

module.exports = {
  // 输出配置
  output: {
    // 输出的文件名称-自定义
    filename: 'bundle.js',
    // 路径必须是个绝对路径, `__dirname` 表示在当前目录下创建一个文件夹
    path: path.resolve(__dirname, 'dist')
  }
};
```