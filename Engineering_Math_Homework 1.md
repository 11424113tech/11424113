# 工程數學第二次作業

> 科目：工程數學  
> 單元：拉普拉斯轉換、傅立葉級數

---

# 第 3 題

## 題目

求解微分方程：

```math
x''+6x'+8x=1
```

初始條件：

```math
x(0)=1,\quad x'(0)=0
```

---

## 解答

對方程兩側取拉普拉斯轉換：

```math
\mathcal{L}\{x''\}+6\mathcal{L}\{x'\}+8\mathcal{L}\{x\}
=\mathcal{L}\{1\}
```

利用公式：

```math
\mathcal{L}\{x''\}=s^2X(s)-sx(0)-x'(0)
```

```math
\mathcal{L}\{x'\}=sX(s)-x(0)
```

代入初始條件：

```math
(s^2X-s)+6(sX-1)+8X=\frac1s
```

整理：

```math
(s^2+6s+8)X=s+6+\frac1s
```

因此：

```math
X(s)=\frac{\frac1s+s+6}{(s+2)(s+4)}
```

---

## 部分分式分解

```math
X(s)=\frac{1}{8s}+\frac{3}{4(s+2)}+\frac{1}{8(s+4)}
```

---

## 反拉普拉斯轉換

利用：

```math
\mathcal{L}^{-1}\left\{\frac1{s+a}\right\}=e^{-at}
```

得到：

```math
x(t)=\frac18+\frac34e^{-2t}+\frac18e^{-4t}
```

---

## 最終答案

```math
\boxed{
x(t)=\frac18+\frac34e^{-2t}+\frac18e^{-4t}
}
```

---

# 第 8 題

## 題目

令：

```math
f(x)=x^2,\quad x\in[-\pi,\pi]
```

求其傅立葉級數（Fourier Series）。

---

## 解答

因為：

```math
f(x)=x^2
```

為偶函數，因此 Fourier Series 只有 cosine 項：

```math
f(x)\sim \frac{a_0}{2}
+\sum_{n=1}^{\infty}a_n\cos(nx)
```

---

## 求 \(a_0\)

```math
a_0=\frac1\pi\int_{-\pi}^{\pi}x^2dx
```

由於為偶函數：

```math
a_0=\frac2\pi\int_0^\pi x^2dx
```

計算積分：

```math
a_0
=\frac2\pi\left[\frac{x^3}{3}\right]_0^\pi
=\frac{2\pi^2}{3}
```

因此：

```math
\frac{a_0}{2}=\frac{\pi^2}{3}
```

---

## 求 \(a_n\)

```math
a_n
=\frac2\pi\int_0^\pi x^2\cos(nx)\,dx
```

積分後得到：

```math
a_n=\frac{4(-1)^n}{n^2}
```

---

## Fourier Series

因此：

```math
x^2
=
\frac{\pi^2}{3}
+
4\sum_{n=1}^{\infty}
\frac{(-1)^n}{n^2}\cos(nx)
```

---

## 最終答案

```math
\boxed{
x^2
=
\frac{\pi^2}{3}
+
4\sum_{n=1}^{\infty}
\frac{(-1)^n}{n^2}\cos(nx)
}
```

展開形式：

```math
x^2
=
\frac{\pi^2}{3}
-4\cos x
+\cos 2x
-\frac49\cos 3x
+\frac14\cos 4x
-\cdots
```
