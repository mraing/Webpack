# mode

?> webpack 内置的优化模式

通过选择 `development` 或 `production` 之中的一个，来设置 mode 参数，你可以启用相应模式下的 webpack 内置的优化。

其默认值为 `production`， 或者你也可以选择不优化选项 `none` 。

```javascript
module.exports = {
  mode: 'development'   // 开发模式
}
```

+ **区别**
  
  + 在开发模式中，为了便于代码调试方便我们快速定位错误，不会压缩混淆源代码。
  
  + 但在生产模式中，就不需要调试代码，而是需要更快的页面加载，缓存优化等来提高用户体验。
  
  **webpack官方建议开发模式和生产模式的配置分开，然后将两者的公共配置提取出来。**
