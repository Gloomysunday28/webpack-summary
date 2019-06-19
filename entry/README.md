# Entry --- 入口文件

### 定义
```
  打包配置的入口文件, webpack3.x及以下必备属性, 4.x默认是src/index.js
```

### 语法
```
  webpack所有的路径是根据context属性配置的, context默认为根目录
  1. 
    entry: string
  2.
    entry: [string, string]
  3.
    entry: {
      xx: string || [string, string],
      yy: string || [string, string]
    }
```