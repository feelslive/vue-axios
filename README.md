Vue 二次封装 axios 为插件使用
基本的封装要求：

统一 url 配置
统一 api 请求
request (请求)拦截器，例如：带上 token 等，设置请求头
response (响应)拦截器，例如：统一错误处理，页面重定向等
根据需要，结合 Vuex 做全局的 loading 动画，或者错误处理
将 axios 封装成 Vue 插件使用

---- config.js axios 的默认配置
---- api.js 二次封装 axios，拦截器等
---- interface.js 请求接口文件
---- index.js 将 axios 封装成插件

在 mian.js 中做如下操作：
// 倒入 http 文件夹下的 index.js
import api from './http/index'
Vue.use(api)

// 此时可以直接在 Vue 原型上调用 \$api 了

PS: IE9 不支持 Promise 哦，需要安装一个 polyfill
import 'babel-polyfill'
