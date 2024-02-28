---
noindex: true
noheader: true
---

# Question

## Css

- 优先级计算方式
  - _follow up_
  - 内联样式还是!important 优先级高
  - 引入 Cascade Layer 后呢
- position 属性几种定位方式分别相对什么定位
- 简述 BFC 和其应用
  - _follow up_
  - 简述 Margin Collapse 逻辑
- 简述 Stacking Context 和其应用
- 简述 Compositing Layer 和其应用
- css 加载会阻塞 dom 的解析、渲染（2 steps）吗，为什么
- css 加载会阻塞 js（none,defer,async）的加载、执行（2 steps）吗，为什么

## Js

- 下面代码有哪些问题

```js
var o = {
  name: "rq",
  age: "4",
  color: "blue",
  base: "sz",
  nameBase: this.name + "." + this.base,
  getFoundYear: () => new Date().getFullYear() - this.age,
  getBaseColor: function () {
    return this.color;
  }.bind({ color: "white" }),
};
o.getFoundYear.bind({ age: 5 })();
o.getBaseColor.call({ color: "blue" });
```

- 请写出以下输出结果，并说明为什么

```js
function Foo() {
  getName = function () {
    alert(1);
  };
  return this;
}
Foo.getName = function () {
  alert(2);
};
Foo.prototype.getName = function () {
  alert(3);
};
var getName = function () {
  alert(4);
};
function getName() {
  alert(5);
}

Foo.getName();
getName();
Foo().getName();
getName();
new Foo.getName();
new Foo().getName();
new new Foo().getName();
```

- encodeURI 和 encodeURIComponent 区别
- 怎么理解 ArrayBuffer，出现用来解决什么问题

## Browser

- 两个独立打开的不同源 tab 之间通讯的纯前端方案
- 滚动懒加载的实现

## Nodejs

- 哪种更快，为什么

```js
var i = 0;
var start = new Date();
function foo() {
  i++;
  if (i < 1000) {
    setTimeout(foo, 0);
    // setImmediate(foo);
  } else {
    var end = new Date();
    console.log("Execution time: ", end - start);
  }
}
foo();
```

- 进程几种创建方式的区别与联系
  - _follow up_
  - 进程间通信方式
- 服务变更对上下游影响的管理方案

## Network

- 中间人攻击流程
  - _follow up_
  - 客户端/服务端怎么抓包
  - https 请求域名会暴露吗
- keep alive 和 http2 中多路复用的区别

## Build

- vue scoped css 是怎么实现的
- spa 架构下有哪些方法优化首屏速度
- 介绍下 Tree Shaking 和 Scope Hoisting
  - _follow up_
  - 副作用怎么优化

## Security

- 阻止 api 被机器人调用
- 介绍下常用鉴权方式
  - _follow up_
  - 双 token 机制的意义

## ViewPoint

- 帮助特别大的学习资料
- 最近在学习什么
- 沟通协作方面最难的经历，有什么反思
- 介绍下做的最满意的项目
