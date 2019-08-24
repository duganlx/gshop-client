# Stylus基本使用
## 介绍
> CSS 预处理，顾名思义，预先处理 CSS

## 说明
### &
> 父级引用
````
.list-item
.text-box
    &:hover
        background-color: powderblue

// 翻译为css
.list-item:hover,
.text-box:hover {
  background-color: #b0e0e6;
}
````

### @media
> 使用 @media 查询，你可以针对不同的媒体类型定义不同的样式。  
> @media 可以针对不同的屏幕尺寸设置不同的样式，特别是如果你需要设置设计响应式的页面，@media 是非常有用的。  
> 当你重置浏览器大小的过程中，页面也会根据浏览器的宽度和高度重新渲染页面。
````
@media print
  #header
  #footer
    display none

// 翻译为css
@media print {
  #header,
  #footer {
    display: none;
  }
}
````

## mixins.styl部分代码解读
### zoom:1
> 兼容IE6、IE7、IE8浏览器，经常会遇到一些问题，可以使用zoom:1来解决,如：
> 触发IE浏览器的haslayout。解决ie下的浮动，margin重叠等一些问题。  
> 另外，用css中的zoom属性可以让网页实现IE7中的放大缩小功能。
````
// 清除浮动
clearFix()
  *zoom 1
  &::after
    content ''
    display block
    clear both
````

### @media only screen
> 手机端适配判断
````
/*iphone 4  screen-width:320px*/
@media only screen and (min-width: 320px) and (max-width: 360px) {}

/*三星Galaxy S5  screen-width:360px*/
@media only screen and (min-width: 360px) and (max-width: 375px) {}

/*iphone 6  screen-width:375px*/
@media only screen and (min-width: 375px) and (max-width: 414px) {}

/*iphone 6plus  screen-width:414px*/
@media only screen and (min-width: 414px) and (max-width: 768px) {}

/*iPad Mini  screen-width:768px*/
@media only screen and (min-width: 768px){}
````

### -webkit-min-device-pixel-ratio
> 响应式布局—设备像素密度测试
````
设备像素为:2.0    (-webkit-min-device-pixel-ratio)
所有mac视网膜显示器 
苹果iPhone 4 
苹果iPhone 4 s 
三星Galaxy S三世 
...

设备像素为:3.0    (-webkit-min-device-pixel-ratio)
HTC(M7) 
HTC的蝴蝶 
相对应的人找到7(X9076) 
三星Galaxy S4 
三星Galaxy注3 
...

````

### transform: none|transform-functions;
> scaleY(y):通过设置 Y 轴的值来定义缩放转换
