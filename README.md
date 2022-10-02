# xqmsg

This is a js show message tip plugin.

[View Chinese documents](./zh.md)

## Install

**Browser**:

import cdn

```html
<!-- Browser -->
<script src="https://unpkg.com/xqmsg/lib/xqmsg.min.js"></script>
<!-- es module -->
<script type="module">
    import xqmsg from '../lib/xqmsg-esm.min.js';
</script>
```

## Usage

+ html

```html
<h4>1. pop</h4>
<p>
    <button class="popBtn" data-type="1" data-text="success">success</button>
    <button class="popBtn" data-type="2" data-text="error">error</button>
    <button class="popBtn" data-type="3" data-text="warning">warning</button>
    <button class="popBtn" data-type="4" data-text="info">info</button>
</p>
<h4>2.msg</h4>
<p>
    <button class="msgBtn" data-type="0" data-text="top">top</button>
    <button class="msgBtn" data-type="1" data-text="middle">middle</button>
    <button class="msgBtn" data-type="2" data-text="bottom">bottom</button>
</p>
<h4>3.confirm</h4>
<p>
    <button class="confirmBtn">confirm</button>
</p>
```

+ call

```js
// 1. pop
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

// 2.msg
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

// 3.confirm
let confirmBtn = document.querySelector('.confirmBtn');
confirmBtn.addEventListener('click', confirmSet, false);
async function confirmSet () {  
    let res = await xqmsg.confirm('You want to leave me?');
    console.log(res);
    // {type: 1, msg: 'confirm'}
    // {type: 2, msg: 'cancel'}
}
```

## View xqmsg

Run this script to view the demonstration case: `npm run test:browser`.

+ [demo](https://unpkg.com/xqmsg/test/browser.html)

## ask questions

[submit your question](https://github.com/gitguanqi/xqmsg/issues/new)

## Author

[@gitguanqi](https://github.com/gitguanqi)
