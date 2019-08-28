# 硅谷外卖

## 项目介绍
> Vue实战项目，此项目为外卖Web App(SPA)，包括商家、商品、购物车、用户等多个子
> 模块，使用Vue全家桶+ES6+Webpack等前端最新最热的技术，采用模块化、组件化、工程
> 化的模式开发，同时采用前后端分离开发


## 效果展示
![image](https://github.com/duganlx/gshop/blob/master/static/photo/result.gif)

## 环境搭建
- 下载node.js
- 下载ide工具，如WebStorm
- 下载依赖
```text
//一键下载所有依赖
npm install

// 分开下载
// css模板 stylus
npm install stylus stylus-loader --save-dev
// vue路由管理器
npm install vue-router --save
// 分页插件
npm install --save swiper
// ajax插件
npm install --save axios
// 全局状态管理
npm install --save vuex
// vue的移动端组件库
npm install --save mint-ui
// 与mint-ui配套，实现按需打包
npm install --save-dev babel-plugin-component
// 模拟json数据
npm install --save mockjs
// 做滚动的插件
npm install --save better-scroll
// 图片懒加载
npm install --save vue-lazyload
// moment与date-fns做日期格式化，这里使用轻量级的date-fns
//npm install --save moment
npm install --save date-fns
```

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
            |-- ajax.js: ajax请求函数模块
            |-- index.js: 接口请求函数的模块
        |-- common: 通用资源文件夹，如fonts/img/stylus
            |-- images: 图片文件夹
                  |-- loading.gif: 食品详情页中图片加载过程中的等待gif图
            |-- stylus: 存放stylus相关文件
                  |-- mixins.styl: stylus模板
        |-- components: 非路由组件文件夹
              |-- AlertTip: 提示框组件文件夹
                    |-- AlertTip.vue: 提示框组件vue
              |-- CartControl: 购物控制组件文件夹
                    |-- CartControl.vue: 购物控制组件vue
              |-- Food: 食品详情页组件文件夹
                    |-- Food.vue 食品详情页组件vue
              |-- FooterGuide: 主页底部组件文件夹
                    |-- FooterGuide.vue: 底部组件vue
              |-- HeaderTop: 主页头部组件文件夹
                    |-- HeaderTop.vue 头部组件vue
              |-- ShopCart: 底部购物车组件文件夹
                    |-- ShopCart.vue: 底部购物车组件vue
              |-- ShopHeader: 商店详情页头部组件文件夹
                    |-- ShopHeader.vue: 商店详情页头部组件vue
              |-- ShopList: 商店列表组件文件夹
                    |-- images:  图片文件夹
                          |-- shop_back.svg: 数据加载时占位置图片
                    |-- ShopList.vue: 商店列表组件vue
              |-- Star: 星级评分组件文件夹
                    |-- images: 图片star[星星尺寸:24/36/48]_[全星/半星/空星]@[设备像素:2/3]x.png
                    |-- Star.vue: 星级评分组件
        |-- filters: 自定义过滤器模块文件夹
              |-- index.js: 日期格式化过滤器
        |-- mock: 模拟数据接口文件夹
              |-- data.json: 商店的数据，json
              |-- mockServer.js: 提供获取data.json数据的接口
        |-- pages: 路由组件文件夹
              |-- Login: 登录组件文件夹
                    |-- Login.vue: 登录组件vue
              |-- Msite: 首页组件文件夹
                    |-- images: 图片文件夹
                          |-- msite_back.svg: 数据加载时占位置图片
                    |-- Msite.vue: 首页组件vue
              |-- Order: 订单组件文件夹（未开发）
                    |-- images: 图片文件夹
                          |-- person.png: 一个外卖员
                    |-- Order.vue: 订单组件vue
              |-- Profile: 个人组件文件夹
                    |-- Profile.vue: 个人组件vue
              |-- Search: 搜索组件文件夹
                    |-- Search.vue: 搜索组件vue
              |-- Shop: 商店组件文件夹（二级组件）
                    |-- ShopGoods: 食品列表组件文件夹
                          |-- note.txt: 两个列表滑动设计思路
                          |-- ShopGoods.vue: 食品列表组件vue
                    |-- ShopInfo: 商店信息组件文件夹
                          |-- ShopInfo.vue: 商店信息组件vue 
                    |-- ShopRatings: 商店评论组件文件夹
                          |-- ShopRatings: 商店评论组件vue
                    |-- Shop.vue: 商店组件vue
        |-- router: 路由器文件夹
              |-- index.js: 路由器对象模块
        |-- store: vuex相关模块文件夹
              |-- actions.js: 通过mutation间接更新state的多个方法的对象
              |-- getters.js: 包含多个基于state的getter计算属性的对象
              |-- index.js: vuex最核心的管理对象
              |-- mutation-types.js: 包含n个mutation的type名称常量
              |-- mutations.js: 直接更新state的多个方法的对象
              |-- state.js: 状态对象
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
