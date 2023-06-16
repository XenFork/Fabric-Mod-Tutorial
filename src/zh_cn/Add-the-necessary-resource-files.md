# 添加必要的资源文件

## 第二步

### fabric.mod.json
- schemaVersion 数据版本
- id modid
- version 版本
- name 模组别名
- description 介绍
- authors 作者们
- contact 项目的相关链接
- license 协议
- icon 图标
- environment 环境，一般不用修改
- entrypoints 入口点，以后再说
- mixins mixin注入的json文件定义 [不是必须的]
- depends 依赖项
- custom 自定义参数选项 经典的有接口注入mixin loom:injected_interfaces
```json
{
  "schemaVersion": 1,
  "id": "tutorials",
  "version": "${version}",
  "name": "tutorials",
  "description": "",
  "authors": [],
  "contact": {
    "repo": "https://github.com/xenfork/tutorials"
  },
  "license": "MIT",
  "icon": "assets/tutorials/icon.png",
  "environment": "*",
  "entrypoints": {
    "server": [
    ],
    "client": [
    ]
  },
  "mixins": [
    "tutorials.mixins.json"
  ],
  "depends": {
    "fabricloader": ">=${loader_version}",
    "fabric": "*",
    "fabric-api": "*",
    "minecraft": "${minecraft_version}"
  },
  "custom": {
    "loom:injected_interfaces": {
    }
  }
}
```

### tutorials.mixins.json
- 它不是必须的，当你没有必要mixin代码时可以不用这个文件
- required 是否是必须的加载的
- minVersion 最小mixin版本
- package mixin所在包
- compatibilityLevel java编译版本 这里用的是java17
- injectors 注入模式
  - defaultRequire 默认需要的混合集
- mixins 允许同时支持运行在客户端和服务端 mixins
- client 只能在客户端mixins
- server 只能在服务端mixins
```json
{
  "required": true,
  "minVersion": "0.8",
  "package": "union.xenfork.tutorials.mixin",
  "compatibilityLevel": "JAVA_17",
  "injectors": {
    "defaultRequire": 1
  },
  "mixins": [
  ],
  "server": [
  ],
  "client": [
  ]
}
```

## such as
- [fabric.mod.json](../tutorials/src/main/resources/fabric.mod.json)
- [tutorials.mixins.json](../tutorials/src/main/resources/tutorials.mixins.json)
![icon](../tutorials/src/main/resources/assets/tutorials/icon.png)