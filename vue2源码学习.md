# vue2-source-code-learn

## vue 源码结构 
```
    dist 打包出来的代码  common 、runtime-common、esm
            dist/config.js=>包含所有配置打包出来不同的代码
            Runtime only   离线编译：(vue运行时：在执行器运行的过程中保存的一种状态)
                离线编译：template=>webpack=>vue-loader=>js=>html
                   <template>
                        <div id="app">
                            <img alt="Vue logo" src="./assets/logo.png">
                            <HelloWorld msg="Welcome to Your Vue.js App"/>
                        </div>
                    </template>
            runtime+compiler 在线编译
                    在线编译：=>js=>with()=>js render()
                        new Vue({
                            template:'<div>{{data}}</div>'
                        })  

    examples 模版样例
    flow:一个框架 ts 是一门语言  都可以规范变量
    packages  打包之后的  基于leran多包管理工具  可以单独拿出来发布的包 运用了node.js的VM(虚拟机)
              vue SSR =>vue-server-renderer=>js=>VM
    scripts 打包脚本 不一样的脚本打成不一样的包
    src 核心代码 
        compiler 编译模版 离线编译的代码 把vue代码编译成js 
        core Vue.js的核心 
            components:keep-alive的实现
            global-api:全局暴露的API，
            instance：vue 实例 生命周期的一些逻辑
            observer：数据收集和依赖
            util：常用工具方法
            vdom：虚拟dom
            config.js
            index.js 暴露出来的东西 
        entries 生产打包的入口(最新版本已经不用)
        platforms ：平台代码 最新版本里有web weex
        server 处理服务端渲染
        sfc 处理单文件 解析.vue文件的代码
        shared 辅助工具 提供全局用到的工具函数

结论：Vue.js的组成是有core + 对应的‘平台’补充代码构成（独立构建和运行时构建只是platforms下的web或weex两种选择）

```
## vue  双向数据绑定
```
![Image text](https://github.com/shiqicong/vue-source-code/blob/master/learn-imgs/data-bind.png)
    observer:对数据做监听
```
## Virtual-dom 虚拟dom
## diff算法
## 整体流程
## 运行时优化
## 前端技术框架选型