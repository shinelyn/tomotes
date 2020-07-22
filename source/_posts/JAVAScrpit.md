---
title: javascript类型
date: 2020-04-20
tags: 
---
#### 经典问题
<!--MORE-->
1. 为什么有些编程要求用void 0代替 undefined？
2. 字符串有最大长度吗？
3. 0.1 + 0.2 为什么不等于 0.3？
4. es6 中的Symbol是个什么东西？
5. 为什么给对象添加的方法能用在基本类型上？
如果你还有疑问，那么你对这部分内容还有遗漏。今天将会带你一起补上，我们的js模块将从运行时，文法和执行过程去刨析js的知识体系。

类型：
 js的每一个值都代表了一种数据类型。规定了7种数据类型
    1. Undefined；
    2. Boolean；
    3. Number；
    4. Object；
    5. String；
    6. Null;
    7. Symbol;

#### （1）Undefined 和 Null 
undefined类型表示为定义，它的类型只有一个值就是undefined，任何变量在赋值前都是undefined类型，值为undefined,而undefined是一个变量而非一个关键字，为了避免无意中修改。建议使用void 0 来代替Undefined。


Null表示定义了但值为空，在实际的开发中一般不会把变量赋值为undefined，这样就可以保证所有值为undefined的变量都是从未赋值的状态。另外Null是javaScript的关键字，在任何代码中可以放心的使用null关键字来获取null值。

#### （2）Boolean 类型有两个值，true和false。

#### （3）String
string用于文本数据。有最大长度2^53-1.这个最大长度并不是字符的个数。其实String的意义并非是“字符串”，而是字符串的UTF16编码


#### （4）Number
非整数的Number类型无法用==来比较。也就是0.1+0.2不等于0.3,是因为浮点运算的精度问题导致不相等。正确的比较方法是使用 JavaScript 提供的最小精度值：检查等号左右两边的绝对值是否小于最小精度。


#### （5）Object
为什么给对象添加的方法能用在基本类型上？
. 运算符提供了装箱操作，它会根据基础类型构造一个临时对象，使得我们能在基础类型上调用对应对象的方法。


装箱转换
Number，String，Boolean，Symbol在对象中都有对应的类，所谓的装箱转换正是把基本类型转换成对应的对象。


拆箱转换
规定了toPrimitive函数，它是对象类型到基本类型的转换（即拆箱转换）
对象到String和Number的转换都遵守“先拆箱在转换”的原则。通过拆箱转换把对象变成基本类型。再从基本类型转换到String和Number。拆箱转换会试着调用valueOf和toString来获取拆箱后的基本类型。如果valueOf和toString都不存在。或者没有返回基本类型，则会产生类型错误TypeError
