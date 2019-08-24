# 好食外卖

## 项目介绍
> Vue实战项目，此项目为外卖Web App(SPA)，包括商家、商品、购物车、用户等多个子
> 模块，使用Vue全家桶+ES6+Webpack等前端最新最热的技术，采用模块化、组件化、工程
> 化的模式开发，同时采用前后端分离开发

## 项目运行
> 1. 编码测试
>   - npm run dev
>   - 访问 http://localhost:8080
> 2. 打包发布
>   - npm run build
>   - npm install -g serve
>   - serve dist
>   - 访问：http://localhost:5000

## 项目分析

### 结构
```` 结构图
gshop  
   |-- build: webpack相关的配置文件夹（基本不需要修改）  
   |-- config: webpack相关的配置文件夹（基本不需要修改）
          |-- index.js: 指定的后台服务的端口号和静态资源文件夹
   |-- node_modules 依赖
   |-- src: 源码文件夹
        |-- api: 与后台交互模块文件夹
        |-- common: 通用资源文件夹，如fonts/img/stylus
        |-- components: 非路由组件文件夹
              |-- FooterGuide: 底部组件文件夹
                      |-- FooterGuide.vue: 底部组件vue
        |-- filters: 自定义过滤器模块文件夹
        |-- mock: 模拟数据接口文件夹
        |-- pages: 路由组件文件夹
              |-- Msite: 首页组件文件夹
                    |-- Msite.vue: 首页组件vue
              |-- Search: 搜索组件文件夹
                    |-- Search.vue: 搜索组件vue
              |-- Order: 订单组件文件夹
                    |-- Order.vue: 订单组件vue
              |-- Profile: 个人组件文件夹
                    |-- Profile.vue: 个人组件vue
        |-- router: 路由器文件夹
        |-- store: vuex相关模块文件夹
        |-- App.vue: 应用组件
        |-- main.js: 应用入口js
   |-- static: 静态资源文件夹
   |-- .babelrc: babel的配置文件
   |-- .editorconfig: 通过编辑器的编码/格式进行一定的配置
   |-- .eslintignore: eslint检查忽略的配置
   |-- .eslintrc.js: eslint检查的配置
   |-- .gitignore: git版本管制忽略的配置
   |-- .postcssrc.js:
   |-- index.html: 主页面文件
   |-- package.json: 应用包配置文件
   |-- package-lock.json
   |-- README.md: 应用描述说明的readme文件
````
