# Vue项目开发规范

## 前端项目开发环境

开发环境 windows10 + node6.8

主要技术栈 vue2 + element-ui + axios + vue-router + vuex + webpack + ES6/7 + scss

## 基于vue-cli的配置文件修改添加

通过vue-cli构建vue项目开发环境，另需在vue-cli基础上添加css预编译工具sass，及添加babel-polyfill兼容IE浏览器；

> 添加sass依赖

```
cnpm install node-sass --save-dev

cnpm install node-sass --save-dev
```

注：由于vue-cli内置scss语法规则所以只需安装依赖即可，即可在项目中使用scss语法规则

>添加babel-polyfill

```
cnpm install babel-polyfill --save-dev
```

入口文件main.js中引入babel-polyfill.js

```
import 'babel-polyfill'
```

修改webpack配置文件webpack.base.conf.js

```
//修改前

module.exports = { 
	entry: { 
		app: './src/main.js' 
	} 
} 

//修改后

module.exports = {
  entry: {
    app: ["babel-polyfill", "./src/main.js"]
  }
}
```

## vue-cli 配置proxyTable解决前后端跨请求域问题

>修改config文件夹下面的index.js

```
//修改前
module.exports = {
  dev: {
    proxyTable: {},
}

//修改后
module.exports = {
  dev: {
    proxyTable: {
       '/api':{
            target:"http://192.168.18.81:9093",//这里是代理接口的位置
            changeOrigin:true, //允许跨域，如果这不写，调用接口接口时会有跨域错误说缺少请求头
            pathRewrite:{
                '^/api':'/api' //请求路径重写
            }
        }
    },
}
```

## 所有与后台交互接口请求统一在src/api/getData.js中

## 其他开发规范

* es6/es7: 尽量去使用es6/es7的书写格式, 极大程度的简化项目代码( 例: 箭头函数, 解构赋值... )

* vuex: 统一使用vuex提供的语法糖( mapState,  mapGetters, mapMutation,  mapAction )

* 模块化: 在项目开发中应该将复杂的模块按照功能不同来拆分, 以及通用模块的抽离.封装

* 代码书写位置: 生命周期一般放在methods上面, 注册组件components 一般放在最上面

* 文件引入根路径: src下一级目录用的多的统一再webpack配置，直接使用配置的变量替代相对路径

* 代码精简: 代码中不要出现过多的注释, 所有的代码都应该是有价值的代码, 不要出现无意义的代码, 没用的代码全部删掉( console调式完成后删掉 )

* 组件划分: components用于存放单一功能的逻辑组件, pages存放业务功能的各个模块组件, ( 不可互相胡乱放置 )

* 错误警告及时处理: 项目开发中出现的警告和错误( 控制台.可能不会影响当前开发 ), 在团队开发中请保持控制台的干净, 方便大家单独调试


<img src="https://github.com/zhuzeliang/9client/blob/master/images/scss.png" />


