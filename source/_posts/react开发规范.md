---
title: react开发规范
date: 2018-11-24
tags: 
---

#### react开发规范
##### 命名规范
- 扩展名：使用.js作为组件的扩展名
- 文件名使用大驼峰命名法
- 组件命名   组件名称与文件名称一致，一个目录的根组件使用index.js命名，以目录名称作为组件的名称

##### 属性设置
- 一般在行内设置属性，不在外部单独设置
- 属性较多时使用 {...this.props} 语法
- 重复设置属性时，后面的会将前面设置的覆盖掉

##### 属性对齐方式
- 属性较少时可以行内排列
- 属性较多时每行一个属性，闭合标签单独成行

##### 其他的代码格式
- 组件之间注释要用 {} 包裹
- 条件 html
  简单的可以直接行内三元
  复杂的结构，可以在render方法后，定义一个以Html结尾的变量
  ```js 
    var dinosaurHtml = '';

    if (this.state.showDinosaurs) {
      dinosaurHtml = (
        <section>
          <DinosaurTable />
          <DinosaurPager />
        </section>
      );
    }

    return (
      <div>
        ...
        {dinosaurHtml}
        ...
      </div>
    );
  ```

