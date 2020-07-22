---
title: webpack
data: 2020-01-02
---
概念
webpack是一个现代的javaScript应用程序的静态模块打包，当webpack处理应用程序时，他会在内部构建一个依赖图，此依赖图会映射项目所需的每个模块，并生成一个或多个bundle。
任何时候，一个文件依赖于另一个文件，webpack就视为此文件有依赖关系。webpack从命令行或配置文件中定义的一个模块列表开始，处理应用程序。从入口开始，webpack递归的构建一个依赖图，这个依赖图包含着应用程序所需的每个模块，将这些模块打包为少量的bundle。通常只有一个可由浏览器加载。
<!--MORE-->
核心概念
  入口
  输出
  loader
  插件
  模式
  浏览器兼容性

  入口（entry point）指示webpack应该使用那个模块，作为构建内部依赖图的开始，进入入口起点的时候，webpack会找出有哪些模块和库是入口所依赖的。默认值是 ./src/index.js。可在webpack中配置entry属性，来指定一个或多个入口。

  ### 单个入口文件语法
  用法：entry：string|Array <string>

  ``` module.export={
    extry:'path/to/my/entry/file.js'
  }
  ```
  向entry属性传入文件路径数组，将创建出一个多入口。你想要一次注入多个依赖文件，并将她们的依赖导向到一个chunk时。

  ### 对象语法
  ```module.export={
    entry:{
      app:'./src/app.js'
      adminApp:'./src/adminApp.js'
    }
  }

  输出（output) 告诉在那里输出创建的bundle,输出文件的默认值是 ./dist/main.js，其他生成的默认放置在 ./dist文件里。可以通过ouput字段来，来配置处理这些过程

  webpack.config.js

  ```const path = require('path');
  module.exports = {
    entry:'./path/to/my/entry/file.js',
    output:{
      path:path.resolve(__dirname,'dist'),
      filename:'my-first-webpack.bundle.js'
    }
  }
  ```
通过output.filename,和output.path属性，来告诉webpack bundle的名称，以及我们想要bundle生成的emit到那里。


loader 
用于对模块的源代码转换，
