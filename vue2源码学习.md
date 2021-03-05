# vue2-source-code-learn

## vue 源码结构 
```
    dist 打包出来的代码  common 、runtime-common、esm
            dist/config.js=>包含所有配置打包出来不同的代码
             Runtime only (vue运行时：在执行器运行的过程中保存的一种状态)
              runtime+compiler
                   离线编译：template=>webpack=>vue-loader=>js=>html
                   <template>
                        <div id="app">
                            <img alt="Vue logo" src="./assets/logo.png">
                            <HelloWorld msg="Welcome to Your Vue.js App"/>
                        </div>
                    </template>
                    在线编译：=>js=>with()=>js render()
                        new Vue({
                            template:'<div>{{data}}</div>'
                        })   
    examples 模版样例
    flow:一个框架 ts 是一门语言  都可以规范变量
    packages  基于leran多包管理工具
    scripts 打包脚本 不一样的脚本打成不一样的包
    src 核心代码
```