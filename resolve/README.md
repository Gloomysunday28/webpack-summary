# Resolve --- 查找文件

### 定义
```
  通过配置来查找指定路径
```

### 属性 --- 常用
```
  alias: 别名
  modules: 用来查找第三方库，根据Node的模块查询规则 默认是该文件下的node_modules, 进行递归往上找, 直到找到node_modules,但是我们通常放在根目录下, 所以直接配置绝对路径指向根目录的node_modules在一定程度上也可以优化编译速度
  mainFields:
    引入某个模块后去寻找该模块的导出文件
    根据package.json里的target的指向 分为两种情况
    1. target === 'web' 或者 target === 'webworker'
       mainFileds: ['browser', 'module', 'main']
    2. target是其他的时候
       mainFileds: ['module', 'main']
  extensions: 省略后缀名
```