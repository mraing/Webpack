# watch

?> 实时监控

将 `watch` 设为 `true`

```javascript
module.exports = {
  watch: true
}
```

还可以配置 `watchOptions` 的参数

```javascript
module.exports = {
  watch: true,
  watchOptions: {
    poll: 1000, // 每秒的选项，间隔多久打包一次
    aggregateTimeout: 500,  //防抖，持续变动会在500ms之后再响应
    ignored: /node_modules/ //不需要监控的文件夹
  }
}
```