---
icon: pen-to-square
date: 2025-03-01
category:
  - 前端
tag:
  - JS
  - 笔记
---

# 快速开始

## 1.1 \<script>元素

将`JavaScript`插入到 HTML 的主要方法是使用`<script>`元素，`<script>`元素有 8 个属性：

- `async`：表示应该立即开始执行脚本（后续会详细介绍）。
- `charset`：使用`src`属性指定的代码字符集。
- `crossorigin`：配置相关请求的 CORS 设置。`crossorigin="anonymous"`配置文件请求不必设置凭据标志。`crossorigin="use-credentials"`设置凭据标志，意味着出站请求会包含凭据。
- `defer`：表示脚本可以延迟到文档完全被解析和显示之后再执行（后续详细介绍）。
- `integrity`：允许比对接收到资源和指定的加密签名以验证子资源完整性。
- `src`：要执行的代码的外部文件。
- `type`：表示脚本语言的内容类型

### 1.1.1 标签位置

通常情况下，所有`<script>`元素都被放到页面的`<body>`的最底部。

### 1.1.2 动态加载脚本

```javascript
let script = document.createElement("script");
script.src = "gibberish.js";
document.head.appendChild(script);
```

示例：

```html
<script>
  console.log("Hello world");
</script>
```
