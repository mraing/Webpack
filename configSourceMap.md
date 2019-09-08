# source map

?> 映射源代码，定位错误代码

```javascript
module.exports = {
  // source-map:映射源码，会单独生成一个 sourcemap 文件，出错了会标识当前报错的列和行，大而全
  // eval-source-map: 不会生成单独的文件，但是可以显示行和列
  // cheap-module-source-map: 不会产生列，但是是一个单独文件，产生后可以保留起来
  // cheap-module-eval-soource-map: 不会产生文件，集成在打包后的文件中，不会产生列
  devtool: 'cheap-module-eval-soource-map',
}
```