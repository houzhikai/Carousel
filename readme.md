1.首先先了解模块的样式，构思怎么去搭建html

2.书写 css 样式
2.1 .panels > a:nth-child() 中添加背景图片与原设定的高度不匹配，要设置绝对定位覆盖到一起
2.2 注意：panels > a 设置绝对定位 carousel 包裹不了，要改变父级的高度，同时子集高度可以设置 100% 来适应父级高度
2.3 上一层 和 下一层 的箭头正常情况下隐藏，鼠标移动图片时显示 
    transform: translateX(-100%) translateY(-50%);  opacity: 0; 
将箭头向左向右移出 arrows ，然后设置 透明度为0 ，
在 .carousel:hover .arrow-pre 中
transform: translateX(0) translateY(-50%);
    opacity: 1; 
需要的时候再将它移动回来，透明度设为1

 2.4 /* 绝对定位的居中方法 */
     left: 50%;
     bottom: 10px;
     transform: translateX(-50%);
2.5 细节处理
    当点击一面 li 的时候，由于高度较低，所以最好加一个上下的padding，直接加padding的话效果不是很好，所以要添加伪元素来实现。

js处理
    3.1 首先要了解要做哪些事件
    3.2 定义事件的名称，优先写出 getIndex 指定的页面
    3.3 将 js 组件化，写成 class 类，再定义 bind（） 函数
    3.4 写完组件后调用 new Carousel 函数查看效果

添加不同的效果
    4.1 在html中添加 select 选项，写出几种不同的函数名
    4.2 在js中定义一个 Animation 函数，创建不同的效果，几个函数名之间要用逗号隔开
    4.3 改变 setPage 中内容，使得其可以操作 Animation 的参数
    4.4 在js bind（）末尾添加 setAnimation 将其调用
    4.5 在js最后设定一个函数，使其可以调用 setAnimation 函数，绑定 select的value值，可以在页面上随意调换
