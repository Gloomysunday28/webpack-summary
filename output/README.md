# Output --- 输出目录

### 定义
```
  输出打包后的文件, webpack3.x必备, 4.x默认为dist
```

### 属性 -- 常用
```
  filename: 输出文件的名称
  path: 输出文件的路径, 建议使用绝对路径
  library: 使用script的时候命名的全局变量
  libraryTarget:
    umd: 兼容cmd, amd, script, es6的写法
    commonjs: exports出来的变量
    commonjs2: module.exports出来的变量
    cmd: require
  libraryExport: es6导出的模块在default属性下, 这里可以设置default
  chunkFilename: 按需加载输出的文件名称
  publicPath: 用于线上环境路径
```