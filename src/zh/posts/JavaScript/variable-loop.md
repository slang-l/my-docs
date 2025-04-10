---
icon: pen-to-square
date: 2022-01-04
category:
  - 苹果
  - 水果
tag:
  - 红
  - 大
  - 圆
---

# 变量提升(var-let-const)

## 4.1 区别

### 4.1.1 var 关键字

```js
function example() {
  console.log(x); // undefinded, 变量提升
  var x = 10;
  console.log(x); // 10
}
```

- **作用域**：`var`生命的变量具有函数作用域。
- **变量提升**：`var`声明的变量会被提升到其所在函数或全局作用域的顶部，但赋值不会被提升。
- **重复声明**：允许在同一作用域内重复生命同一个变量。

### 4.1.2 let 关键字

```js
function example() {
  // console.log(x); // ReferenceError，暂时性死区
  let x = 10;
  console.log(x); // 10
}
```

- **作用域**：`let` 声明的变量具有块级作用域（block scope），即在 `{}` 内声明的变量只能在该块内访问。
- **变量提升**：`let` 声明的变量也会被提升，但在声明之前访问会抛出 `ReferenceError`，这种现象称为“暂时性死区”（`Temporal Dead Zone, TDZ`）。
- **重复声明**：不允许在同一个作用域内重复声明同一个变量。

### 4.1.3 const 关键字

```js
function example() {
  // console.log(x); // ReferenceError，暂时性死区
  const x = 10;
  // x = 20; // TypeError，不能重新赋值
  console.log(x); // 10

  const obj = { a: 1 };
  obj.a = 2; // 可以修改对象属性
  console.log(obj); // { a: 2 }
}
```

- **作用域**：`const` 声明的变量也具有块级作用域。
- **变量提升**：`const` 声明的变量也会被提升，但在声明之前访问会抛出 `ReferenceError`，同样存在“暂时性死区”。

- **重复声明**：不允许在同一个作用域内重复声明同一个变量。
- **可变性**：`const` 声明的变量必须立即初始化，且不能重新赋值。但对于对象和数组，虽然不能重新赋值，但可以修改其属性或元素。
