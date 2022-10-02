# xqmsg

这是一个显示消息提示的前端插件JS库。

[查看英文文档](./README.md)

## 安装

**游览器端**:

引入cdn

```html
<!-- 游览器es5 -->
<script src="https://unpkg.com/xqmsg/lib/xqmsg.min.js"></script>
<!-- es6模块 -->
<script type="module">
    import xqmsg from './lib/xqmsg-esm.min.js';
</script>
```

## 使用

+ 页面结构

```html
<h4>1. 气泡组件</h4>
<p>
    <button class="popBtn" data-type="1" data-text="操作成功">操作成功</button>
    <button class="popBtn" data-type="2" data-text="操作失败">操作失败</button>
    <button class="popBtn" data-type="3" data-text="操作警告">操作警告</button>
    <button class="popBtn" data-type="4" data-text="操作信息">操作信息</button>
</p>
<h4>2.消息组件</h4>
<p>
    <button class="msgBtn" data-type="0" data-text="我是顶部消息">顶部消息</button>
    <button class="msgBtn" data-type="1" data-text="我是中部消息">中部消息</button>
    <button class="msgBtn" data-type="2" data-text="我是底部消息">底部消息</button>
</p>
<h4>3.弹出框组件</h4>
<p>
    <button class="confirmBtn">弹出框组件</button>
</p>
```

+ 调用方法

```js
// 1. 气泡组件
let popBtn = document.querySelectorAll('.popBtn');
for (let i = 0; i < popBtn.length; i++) {
    const item = popBtn[i];
    item.addEventListener('click', popSet, false);
}

function popSet (event) {
    let e = event || window.event;
    let params = e.target.dataset;
    xqmsg.pop(params.text, params.type);
}

// 2.消息组件
let msgBtn = document.querySelectorAll('.msgBtn');
for (let i = 0; i < msgBtn.length; i++) {
    const item = msgBtn[i];
    item.addEventListener('click', msgSet, false);
}

function msgSet (event) {
    let e = event || window.event;
    let params = e.target.dataset;
    xqmsg.msg(params.text, params.type);
}

// 3.弹出框组件
let confirmBtn = document.querySelector('.confirmBtn');
confirmBtn.addEventListener('click', confirmSet, false);
async function confirmSet () {  
    let res = await xqmsg.confirm('你确定要离开我吗？');
    console.log(res);
    // {type: 1, msg: 'confirm'}
    // {type: 2, msg: 'cancel'}
}
```

## 查看示例

运行这个脚本查看展示案例：`npm run test:browser`。

+ [点击体验](https://unpkg.com/xqmsg/test/browser.html)

## 提问题

[提出问题](https://github.com/gitguanqi/xqmsg/issues/new)

## 作者

[@gitguanqi](https://github.com/gitguanqi)
