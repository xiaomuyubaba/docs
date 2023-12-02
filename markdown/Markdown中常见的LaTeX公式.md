[toc]

# 角标

- 上标 ^
- 下标 _

名称|数学表达式|makrdown公式
---|---|---
上标 | $a^b$ | `$a^b$`
下标 | $a_b$ | `$a_b$`

# 分数

`\frac{}{}`: 第一个{}写分子，第二个写分母

实例：

- 直接插入文本： $\frac{3+8a}{5b+6}$
- 代码片段：
```math
frac{3+8a}{5b+6}
```

# 累加

`\sum_{}^{}`

名称 | 数学表达式 | markdown公式
---|---|---
求和号 | $\sum{3x^n}$ | `$\sum{3x^n}$`
带范围求和 | $\sum_{n=1}^N{3x^n}$ | `$\sum_{n=1}^N{3x^n}$`

# 累乘

`\prod_{}^{}`

名称 | 数学表达式 | markdown公式
---|---|---
累乘号 | $\prod{3x^n}$ | `$\prod{3x^n}$`
带范围累乘 | $\prod_{n=1}^N{3x^n}$ | `$\prod_{n=1}^N{3x^n}$`

# 开方

`\prod_{}^{}`

名称 | 数学表达式 | markdown公式
---|---|---
累乘号 | $\prod{3x^n}$ | `$\prod{3x^n}$`
带范围累乘 | $\prod_{n=1}^N{3x^n}$ | `$\prod_{n=1}^N{3x^n}$`

# 开方

`\sqrt[]{}`: `[]` 中写开的是几次方，`{}` 中写的是需要开方的数值

名称 | 数学表达式 | markdown公式
---|---|---
开方号 | $\sqrt{n}$ | `$\sqrt{n}`
开几次方 | $\sqrt[m]{n}$ | `$\sqrt[m]{n}$`

# 积分

`\int_{}^{}`

名称 | 数学表达式 | markdown公式
---|---|---
积分 | $\int_{1}^5{f(x)dx}$ | `$\int_{1}^5{f(x)dx}$`
二重积分 | $\iint_{1}^5{f(x)dx}$ | `$\iint_{1}^5{f(x)dx}$`
三重积分 | $\iiint_{1}^5{f(x)dx}$ | `$\iiint_{1}^5{f(x)dx}$`

# 正无穷、负无穷

`\infty`

名称 | 数学表达式 | markdown表达式
---|---|---
正无穷 | $+\infty$ | `$+\infty$`
负无穷 | $-\infty$ | `$-\infty$`

# 极限

`\lim_{}`

名称 | 数学表达式 | markdown公式
---|---|---
右箭头 | $\lim_{n\to+\infty}n$ | `$\lim_{n\to+\infty}n$|`

# 关系运算符

名称 | 数学表达式 | markdown公式
---|---|---
大于等于 | $\geq$ | `$\geq$`
小于等于 | $\leq$ | `$\leq$`
不等于 | $\not=$ | `$not=$`
不小于 | $\not<$ | `$\not<$`

# 二元运算符

名称 | 数学表达式 | markdown公式
---|---|---
加减 | $\pm$ | `$\pm$`
点乘 | $\cdot$ | `$cdot$`
乘 | $\times$ | `$\times`
除 | $\div$ | `$\div$`

# 集合运算符

名称 | 数学表达式 | markdown公式
---|---|---
包含于 | $\subset$ | `$\subset$`
真包含 | $\subset$ | `$\subset$`
包含 | $\supset$ | `$\supset$`
真包含 | $\supsetneqq$ | `$\supsetneqq$`
不包含 | $\not\supset$ | `$\not\supset$`
属于 | $\in$ | `$\in$`
相交 | $\cap$ | `$\cap$`
相并 | $\cup$ | `$\cup$`
空集 | $\emptyset$ | `$\emptyset$`

# 三角运算符

名称 | 数学表达式 | markdown公式
---|---|---
垂直 | $\bot$ | `$\bot$`
角 | $\angle$ | `$\angle$`
30度角 | $30^\circ$ | `$30^\circ$`
正弦 | $\sin$ | `$\sin$`
余弦 | $\cos$ | `$\cos$`
正切 | $tan$ | `$tan$`

# 对数运算符

名称 | 数学表达式 | markdown公式
---|---|---
对数 | $\log$ | `$\log$`
对数 | $\log_2{18}$ | `$\log_2{18}$`
对数 | $\ln$ | `$\ln$`

# 空心字母与Fraktur字母

名称 | 数学表达式 | markdown公式
---|---|---
A | $\mathbb{A}$ | `$\mathbb{A}$`
B | $\mathfrak{B}$ | `$\mathfrak{B}$`

# 矩阵

```math
\begin{matrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{matrix} \tag{1}
```