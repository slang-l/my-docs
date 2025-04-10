---
icon: pen-to-square
date: 2022-01-03
category:
  - JavaScript
tag:
  - 红
  - 大
  - 圆
---

# 语言基础

## 3.1 基本语法

1. JS 和 Java 相同，区分大小写
2. 标识符：
   - 第一个字符必须是一个字母、下划线`_`或美元符号`$`
   - 剩下的其他字符可以是字母、下划线、美元符号或数字。
3. 注释：
   - `//`：单行注释
   - `/**/`：多行注释
4. 严格模式：主要是对于不规范的写法，在这种模式下被判定为错误。`use strict`

## 3.2 关键字和保留字

```text
break do in typeof
case else instanceof var
catch export new void
class extends return while
const finally super with
continue for switch yield
debugger function this default
if throw delete import try
```

## 3.3 变量

### 3.3.1 var 关键字

```js
// 声明变量
var message = "hello world";
```

### 3.3.2 let 关键字

```js
// 声明变量
let message = "hello world";
```

### 3.3.3 const 关键字

```js
// 声明变量
const message = "hello world";
```

> 注：后续将详细说明三者的区别

## 3.4 数据类型

- `Undefined`：未定义
- `Boolean`：布尔值
- `String`：字符串
- `Number`：数值
- `Null`：空
- `Symbol`：表示符号是原始值，且符号实例是唯一、不可变的。
- `Object`：表示值为对象

### 3.4.1 Undefined

`undefined`类型只有一个值，一般是指变量声明了，但是未进行定义，即：

```js
let message
console.log(message) // undefined

const message2
console.log(message2) // undefined

var message3
console.log(message3) // undefined

if (message) {
    // 这个块不会执行
}

if (!message) {
    // 这个块会执行
}

// age没有声明
if (age) {
    // 这里会报错
}
```

### 3.4.2 Boolean

即`true`和`false`

尽管布尔值只有两个，但是其他类型的值都有相应布尔值的等价形式。要将一个其它类型的值转换为布尔值，可以调用特定的`Boolean()`转型函数：

```js
let message = "Hello world";
if (message) {
  console.log("value is true");
} // value is true
```

> 注：
>
> - 转换成`true`的值：`true`、`非空字符串`、`非零数值（包括无穷值）`、`任意对象`、`N/A`
> - 转成`false`的值：`false`、`""(空字符串)`、`0、NAN`、`null`、`undefined`

### 3.4.3 String

```js
let message = "hello world";
let message = "hello world";
```

### 3.4.4 Number

表示整数和浮点数

```js
let floatNum = 3.14e7; // 31400000
let floatNum2 = 3.01;
```

> 注：js 的浮点数存在精度问题。
>
> ```js
> if (0.1 + 0.2 === 0.3) {
>   // false
>   console.log("you got 0.3 ....");
> }
> ```

```js
console.log(0 / 0); // NaN
console.log(-0 / +0); // NaN
```

### 3.4.5 Null

`Null`类型同样只有一个值，即特殊值`null`，逻辑上，`null`值表示一个空对象指针，这也是给`typeof`传一个`null`会返回一个`object`的原因。

```js
console.log(null === undefined); // true

let message = null;
if (message) {
  // 不会执行
}

if (!message) {
  // 会执行
}
```

### 3.4.6 Symbol

`Symbol`是 ES6 新增的数据类型，符号是原始值，且符号实例是唯一的、不可变的。

### 3.4.7 Object

## 3.5 操作符

### 3.5.1 一元操作符

1. 递增/递减操作符
1. 一元加和减

### 3.5.2 位操作符

1. 按位非
2. 按位与
3. 按位或
4. 按位异或
5. 左移
6. 有符号右移
7. 无符号右移

### 3.5.3 布尔操作符

1. 逻辑非
2. 逻辑与
3. 逻辑或

### 3.5.4 乘性操作符

1. 乘法操作符
2. 除法操作符
3. 取模操作符

### 3.5.5 指数操作符

### 3.5.6 加性操作符

1. 加法操作符
2. 减法操作符

### 3.5.7 关系操作符

### 3.5.8 相等操作符

1. 等于和不等于
2. 全等和不全等
3. 条件操作符

### 3.5.9 条件操作符

### 3.5.10 赋值操作符

### 3.5.11 逗号操作符

## 3.6 语句

### 3.6.1 if 语句

语法如下：

```js
if (condition) {
} else if (condition2) {
} else {
}
```

### 3.6.2 do-while 语句

语法如下：

```js
do {} while (expression);
```

### 3.6.3 while 语句

语法如下：

```js
while (condition) {}
```

### 3.6.4 for 语句

语法如下：

```js
for (initialization; expression; post - loop - expression) {}
```

### 3.6.5 for-in 语句

语法如下：

```js
for (property in expression) {
  // 用于枚举对象中的非符号键属性
}
```

> 注：
>
> - 非符号键属性指的是对象中键类型部位**Symbol**属性。
>
> - `for-in` 不保证返回对象属性的顺序。
> - 如果`for-in`循环要迭代的变量是 null 或 undefined，则不执行循环体。

### 3.6.6 for-of 语句

语法如下：

```js
for (property of expression) {
}
```

> 注：
>
> - `for-of`循环会按照可迭代对象的`next()`方法产生值的顺序迭代元素。

### 3.6.7 标签语句

语法如下：

```js
label: statement;
```

### 3.6.8 break 和 continue 语句

- `break`语句：立即终止当前的循环或者`switch`语句。
- `continue`语句：跳出当前循环的剩余代码，直接进入下一次迭代。

### 3.6.9 with 语句

语法如下：

```js
with (expression) statement;
```

> 注：
>
> - 不推荐使用。

### 3.6.10 switch 语句

语法如下：

```js
switch (expression) {
  case value1:
    statement;
    break;
  case value2:
    statement;
    break;
  case value3:
    statement;
    break;
  case value4:
    statement;
    break;
  default:
    statement;
}
```

> 注：switch 语句在比较每个条件的值时会使用全等操作，因此不会强制转换数据类型。

## 3.7 函数

基本语法：

```js
function functionName(arg0, arg1,...,argN) {
  statements
}
```

- 严格模式对函数也有一些限制：

  > - 函数不能以**eval**或**arguments**作为名称。
  > - 函数的参数不能叫**eval**或**arguments**。
  > - 两个命名参数不能拥有同一个名称。
