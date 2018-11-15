> 使用DomReady 不使用onload

```javascript
// DomReay 简单实现

const myReady = (fn) => {
  if (document.addEventListener) {
    document.addEventListener('DOMContentLoaded', fn, false);
  } else {
    IEContentLoaded(fn);
  }

  // IE模拟DOMContentLoaded
  var IEContentLoaded = (fn) => {
    // 只执行一次用户的回调函数 init()
    var d = window.document;
    var done = false;

    var init = () => {
      if (!done) {
        done = true;
        fn();
      }
    }

    var hacker = () => {
      try {
        d.documentElement.doScroll('left');
      } catch (e) {
        // 延迟
        setTimeout(arguments.callee, 50);
        return;
      }
      init();
    }
    hacker();

    // 监听document的加载状态
    d.onreadystatechange = () => {
      // 如果用是在domReady之后绑定的函数，就立马执行
      if (d.readyState == 'complete') {
        d.onreadystatechange = null;
        init();
      }
    }
  }
}

```

##### 元素节点类型的判断

- isElement
- isHTML
- isXML
- contains

```js
var isElement = (el) => {  
  return !!el && el.nodeType === 1;
}

var isXML = (el) => {
  var documentElement = el && (el.ownerDocument || el).documentElement;
  return documentElement ? documentElement.nodeName !== 'HTML' : false;
}

var pNode = document.getElementById('div1')
var cNode = document.getElementById('div2')
if (pNode.contains(cNode)) {
    return true;
}
```