# Webpack日常使用

## webpack是干什么的？
```
  webpack是根据配置的规则将代码打包成js文件
```

## 如何打包?
```
  webpack根据入口文件开始递归解析所有的依赖文件, 每找到一个module, 就是用相对应的转换规则进行转换, 然后在递归解析module下所依赖的module。
  chunk是以入口文件为单位, 将入口文件及其所依赖的文件笼合成一个chunk, 在打包过程中的某些恰当时机会执行对应的插件Plugin
```

## 浅度解析webpack打包流程
```
  webpack是基于Node.js的一个应用, 也可以简单理解为是一个串行应用

  1. webpack将配置文件以及npm script配置的参数合并, 得出最终的参数
  2. webpack在初始化的时候会生成一个全局对象Compiler, 进行对文件的监控以及启动编译, 插件加载等等
  3. 从入口文件触发, 以对应的loader来加载该module,并且进行递归解析文件依赖
  4. 完成编译, 最终得到了文件和其依赖模块的内容以及关系
  5. 根据入口与模块之间的关系, 组装成一个个多模块的chunk, 把chunk转换成一个个单独的文件到输出列表里, 这是最后一个可以更改文件内容的机会了
  6. 根据输出的路径和文件名, 将其写入到文件系统中
```


### 内置变量

变量 | 解释
:---: | :---:|
id|Chunk 的唯一标识，从0开始
name | Chunk 的名称
hash |  Chunk 的唯一标识的 Hash 值, 可以指定长度[hash:8], 代表webpack编译时的hash,如果一旦某一个文件改动，webpack会重新编译,从而导致全部hash值不同
chunkhash |  Chunk 内容的 Hash 值, 可以指定长度[chunkhash:8], 代码的hash值
contenthash | 显示Css源文件的内容


### 详情
- [入口Entry](https://github.com/Gloomysunday28/webpack-summary/tree/master/entry)
- [输出Output](https://github.com/Gloomysunday28/webpack-summary/tree/master/output)
- [文件路径Resolve](https://github.com/Gloomysunday28/webpack-summary/tree/master/resolve)
