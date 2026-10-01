---
title: "测试文档"
date: 2026-10-01T10:00:00+08:00
draft: false
---

## 1. 行内格式

| 语法 | 效果 |
|------|------
| `**text**` | **粗体** |
| `*text*` | *斜体* |
| `***text***` | ***粗体斜体*** |
| `` `code` `` | `代码` |
| `~~text~~` | ~~删除线~~ |

---

## 2. 标题

```markdown
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
```

渲染效果：

# 一级标题

## 二级标题

### 三级标题

#### 四级标题

##### 五级标题

###### 六级标题

---

## 3. 引用

```markdown
> 单行引用。
>
> 含 **格式**、`代码` 与 [链接](https://example.com) 的引用。
>
> > 嵌套引用。
```

渲染效果：

> 单行引用。
>
> 含 **格式**、`代码` 与 [链接](https://example.com) 的引用。
>
> > 嵌套引用。

---

## 4. 列表

### 无序列表

- 第一项
- 第二项
  - 嵌套项
  - 嵌套项
- 第三项

### 有序列表

1. 第一项
2. 第二项
3. 第三项
   1. 嵌套项
   2. 嵌套项

### 任务列表

- [x] 已完成
- [ ] 待办
- [x] 另一项已完成

---

## 5. 表格

```markdown
| 左对齐 | 居中 | 右对齐 |
|:-------|:----:|-------:|
| a      |  1   |  **10.00** |
| b      |  [22](https://example.com)  | `222.00` |
```

渲染效果：

| 左对齐 | 居中 | 右对齐 |
|:-------|:----:|-------:|
| a      |  1   |  **10.00** |
| b      |  [22](https://example.com)  | `222.00` |

单元格内支持行内格式：**粗体**、`代码`、[链接](https://example.com)。

---

## 6. 脚注与定义列表

### 脚注

脚注语法示例[^1]，第二条脚注[^2]。

[^1]: 第一条脚注内容。
[^2]: 第二条脚注内容，可含 **格式** 与 `代码`。

### 定义列表

```markdown
Hugo
: 一个静态网站生成器

Go
: 编程语言
: 由 Google 开发
```

渲染效果：

Hugo
: 一个静态网站生成器

Go
: 编程语言
: 由 Google 开发

---

## 7. 数学公式

数学渲染由 KaTeX 提供，通过 `passthrough` 扩展识别以下定界符：

| 类型 | 定界符 |
|------|--------|
| 行内 | `\( ... \)` |
| 块级 | `\[ ... \]` 或 `$$ ... $$` |

### 行内公式

质能方程 \(E = mc^2\) 是狭义相对论的核心结论。

### 块级公式

高斯积分：

$$
\int_{-\infty}^{\infty} e^{-x^2} \, dx = \sqrt{\pi}
$$

标准模型拉格朗日量：


---

## 8. 代码块

`codeFences` 已关闭 Hugo 内置高亮，代码块以纯 `<pre><code>` 输出，
由 highlight.js 在浏览器端着色。

### Rust

```rust
fn main() {
    let numbers = vec![1, 2, 3, 4, 5];
    let sum: i32 = numbers.iter().sum();
    println!("Sum = {}", sum);
}
```

### Python

```python
def greet(name: str) -> None:
    print(f"Hello, {name}!")

if __name__ == "__main__":
    greet("World")
```

### HTML

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>示例页面</title>
</head>
<body>
    <h1>欢迎</h1>
    <p>这是一个段落。</p>
</body>
</html>
```

### CSS

```css
body {
    font-family: system-ui, sans-serif;
    line-height: 1.6;
    color: #333;
    max-width: 800px;
    margin: 0 auto;
}
```

### JavaScript

```js
const items = [1, 2, 3];
const doubled = items.map(x => x * 2);
console.log(doubled); // [2, 4, 6]
```

### LaTeX

```latex
\documentclass{article}
\usepackage{amsmath}
\begin{document}
Einstein's equation:
\[
E = mc^2
\]
\end{document}
```

### C

```c
#include <stdio.h>

int main(void) {
    printf("Hello, C!\n");
    return 0;
}
```

### C++

```cpp
#include <iostream>
#include <vector>

int main() {
    std::vector<int> v{1, 2, 3};
    for (int n : v) {
        std::cout << n << " ";
    }
    std::cout << std::endl;
    return 0;
}
```

### Typst

```typst
#set page(width: 10cm, height: auto)
#set text(font: "New Computer Modern")

= 标题

这是一个 Typst 示例。

$ E = m c^2 $
```

---

## 9. 原始 HTML

`renderer.unsafe` 已开启，Markdown 中可直接嵌入 HTML。

```html
<details>
<summary>点击展开</summary>
隐藏的内容
</details>
```

渲染效果：

<details>
<summary>点击展开</summary>
隐藏的内容
</details>

行内标签亦可：

```html
按下 <kbd>Ctrl</kbd> + <kbd>C</kbd> 复制。
```

渲染效果：按下 <kbd>Ctrl</kbd> + <kbd>C</kbd> 复制。

---

## 10. 自动链接

`linkify` 默认开启，裸 URL 自动转为链接：

https://example.com 自动变链接。

