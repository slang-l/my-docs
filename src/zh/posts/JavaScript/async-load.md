---
icon: pen-to-square
date: 2025-03-02
category:
  - JavaScript
tag:
  -
  -
  -
star: true
---

# JS 文件的异步加载

## 2.1 加载方式

### 2.1.1 正常加载

```html
<script src="script.js"></script>
```

在渲染该`script`标签之下的文档元素之前，不需要等待后续载入的文档元素，读到就加载并且直接执行。

### 2.1.2 async 模式

```html
<script async src="script.js"></script>
```

加载和渲染后续文档元素的过程将和`script,js`的加载并行进行。当`script.js`记载完整立即执行`script.js`。执行`script.js`时，`html`解析暂停。因为是加载完成后立即执行，这就会导致执行顺序和编码的顺序无关，不能保证执行顺序和编码顺序相同。

### 2.1.3 defer 模式

```html
<script defer src="script.js"></script>
```

`defer`同样也可以做到异步加载，即加载和渲染后续文档元素的过程将和` script.js` 的加载并行进行（异步）,不同的是当`script.js`加载完成并不会立即执行，而是在所有元素解析完成之后，`DOMContentLoaded` 事件触发之前完成。因此它**会按照写的顺序执行**。
