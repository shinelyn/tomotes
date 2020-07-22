---
title: react生命周期钩子函数
data: 2018-11-29
tags:
--- 

### 挂载期
- constructor (数据接受，实现继承super（props);es6对类的默认方法，通过new命令生成对象实例的时候自动调用该方法。如果没有定义，则会默认加上空的constructor()方法，当constructor存在的时候，必须手动调用super方法。
- componentwillMount() 组件挂载之前调用且全局只调用一次，
- render() 渲染组件 
  render是一个react组件必须定义的生命周期，用来渲染dom，
  注：不要在render里面修改state，会触发死循环导致栈溢出，render必须返回reactDOM
- componentDidMount() 组件挂载完成后
  组件挂载完成后调用，且全局只调用一次，这里可以使用refs，获取真实的Dom元素，该钩子内也可以发起异步请求，并在异步请求中进行setState。
- componentWillReceiveProps(nextProps) props即将变化之前
  props发生变化，以及父组件重新渲染时都会触发改生命周期，再该钩子内可通过参数nextProps获取变化后的props参数，通过this.props访问之前的props，该生命周期中可以进行setState。
- shouldComponentUpdate(nextProps,nextState) 是否重新渲染
  组件挂在之后，每次调用setState后都会调用shouldComponentUpdate 判断是否需要重新渲染，默认返回true，需要重新render，返回false则不触发渲染。
- componentDidUpdate() 完成组件渲染
  初始化的时候不会被调用，首次render之后调用componentDidMount，其他render结束后会调用componentDidUpdate函数，