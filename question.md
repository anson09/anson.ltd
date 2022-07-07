# Css

## selector

- 优先级计算方式
- 内联样式还是!important 优先级高

## layout

- position 属性几种定位方式分别相对什么定位
- 画出以下颜色块和数字的排列

```html
<body>
  <div class="div1">1</div>
  <div class="div2">2</div>
  <div class="div3">3</div>
</body>
<style>
  div {
    width: 100px;
    height: 100px;
    font-size: 50px;
  }
  .div1 {
    float: left;
    background-color: red;
  }
  .div2 {
    background-color: green;
  }
  .div3 {
    float: left;
    background-color: blue;
  }
</style>
```

## engine

- css 加载会阻塞 dom 的解析、渲染（2 steps）吗，为什么
- css 加载会阻塞 js（none,defer,async）的加载、执行（2 steps）吗，为什么
- DOMContentLoaded 和 load 事件的触发时机

# Js

## basic

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
console.log(1);

setTimeout(() => {
  console.log("setTimeout");
}, 0);

let promise = new Promise((resolve) => {
  console.log(3);
  resolve();
})
  .then((data) => {
    console.log(100);
  })
  .then((data) => {
    console.log(200);
  });

console.log(2);
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

- encodeURI 和 EncodeURIComponent 区别

## cross-domain

- CORS 的流程是怎样的
- 服务端收到一个请求，但拿不到 cookie，可能是哪些原因
- 两个独立打开的不同源 tab 之间通讯的纯前端方案

# Nodejs

## Eventloop

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

- nextTickQueue 和 microTaskQueue 中的递归调用会 block 程序吗

# Network

- 浏览器中 https 加解密流程
- keep alive 和 http2 中多路复用的区别

# Build

- 聊聊 js 和 css 的浏览器向下兼容方案
- vue 文件在构建过程中都发生了什么
- scoped css 是怎么实现的
- spa 架构下有哪些方法优化首屏速度
