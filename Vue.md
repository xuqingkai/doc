### 项目运行起来后用域名访问显示Invalid Host header
- 在vue.config.js的devServer节点下加入disableHostCheck: true配置项。
  ```
  devServer: {
    port: port,
    disableHostCheck: true,
    ...
  }
  ```
