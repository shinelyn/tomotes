---
title: css加载会阻塞加载吗？
data: 2018 - 11 - 27 
---
 #### css加载会阻塞DOM树的解析渲染吗？
 - css加载不会阻塞DOM树的解析。
 - css加载会阻塞DOM树的渲染。
 - css加载会阻塞后面js语句的执行。
 <!--MORE-->
 #### 这种机制的好处
 - 加载css的时候，可能会修改下面DOM节点的样式，如果CSS加载不阻塞DOM树的渲染，那么css加载完之后，DOM树可能又得重新重绘或者重排了，造成一些不必要的损耗。故而，先把DOM的结构先解析完，等css加载完之后，再根据最终的样式来渲染DOM树。
 #### 怎样提高CSS的加载速度
 - 使用CDN。
 - 对css进行压缩（使用webpack，gulp等打包工具，也可以通过开启gzip压缩）。
 - 合理的使用缓存（设置cache-control，expires,以及E-tag）。
 - 减少http请求，将多个css合并，或者干脆写成内连样式（内连样式不能设置缓存）。

 #### 原理解析（浏览器渲染流程）
 - HTML 解析文件，生成DOM tree，解析CSS文件生成CSSOM tree。
 - 将DOM tree和 CSSOM tree结合，生成Render tree。
 - 根据Render Tree渲染绘制，将像素渲染到屏幕上。
说明：
1.DOM解析和css解析是两个并行的进程，这也是css加载不会阻塞dom结构的解析。
2.Render tree 是依赖DOM Tree和CSSOM Tree，所以它必须等CSSOM tree构建完成，才会开始渲染，故而CSS加载是会阻塞DOM结构渲染。
3.js可能会操纵之前的DOM节点和CSS样式。因为浏览器会维持html中css和js的顺序，故而样式表会在后面的js执行前加载完毕，css会阻塞后面js的执行。

DOMContentLoaded
页面加载主要有两个事件，一个是DOMContentLoaded，另一个是onLoad。
onLoad就是等待页面的所有资源加载完成后才会触发，这些资源包括css，js，图片
DOMContentLoaded,就是当页面的内容解析完成后，则触发该事件。
- 页面同时存在css和js，并且js在css的后面，则DOMContentLoaded事件会在css加载完后才执行
- 其他情况，DOMContentLoaded都不会等待css加载，并且DOMContentLoaded事件也不会等待图片，视频等其他资源加载