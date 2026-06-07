# 工程數學第二次作業

> 科目：工程數學  
> 主題：拉普拉斯轉換與傅立葉級數

---

# （3）拉普拉斯轉換求解微分方程

## 題目

\[
x'' + 6x' + 8x = 1
\]

初始條件：

\[
x(0)=1,\quad x'(0)=0
\]

---

## Step 1：取拉普拉斯轉換

利用：

\[
\mathcal{L}\{x''\}=s^2X(s)-sx(0)-x'(0)
\]

\[
\mathcal{L}\{x'\}=sX(s)-x(0)
\]

代入得：

\[
(s^2X-s)+6(sX-1)+8X=\frac{1}{s}
\]

整理：

\[
(s^2+6s+8)X-s-6=\frac{1}{s}
\]

因此：

\[
X(s)=\frac{\frac1s+s+6}{(s+2)(s+4)}
\]

---

## Step 2：部分分式分解

化簡：

\[
X(s)=\frac{1}{8s}+\frac{3}{4(s+2)}+\frac{1}{8(s+4)}
\]

---

## Step 3：反拉普拉斯轉換

利用：

\[
\mathcal{L}^{-1}\left\{\frac1{s+a}\right\}=e^{-at}
\]

得到：

\[
x(t)
=\frac18+\frac34e^{-2t}+\frac18e^{-4t}
\]

---

## 答案

\[
\boxed{
x(t)=\frac18+\frac34e^{-2t}+\frac18e^{-4t}
}
\]

---

# （8）傅立葉級數（Fourier Series）

## 題目

\[
f(x)=x^2,\quad x\in[-\pi,\pi]
\]

求其傅立葉級數。

---

## Step 1：判斷函數奇偶性

因為：

\[
f(-x)=(-x)^2=x^2
\]

所以 \(f(x)\) 為 **偶函數**。

因此傅立葉級數只有 cosine 項：

\[
f(x)\sim \frac{a_0}{2}+\sum_{n=1}^{\infty}a_n\cos(nx)
\]

---

## Step 2：求 \(a_0\)

\[
a_0
=\frac1\pi\int_{-\pi}^{\pi}x^2dx
\]

由於為偶函數：

\[
a_0
=\frac{2}{\pi}\int_0^\pi x^2dx
\]

積分：

\[
\int_0^\pi x^2dx
=\left[\frac{x^3}{3}\right]_0^\pi
=\frac{\pi^3}{3}
\]

因此：

\[
a_0
=\frac{2}{\pi}\cdot\frac{\pi^3}{3}
=\frac{2\pi^2}{3}
\]

故：

\[
\frac{a_0}{2}
=\frac{\pi^2}{3}
\]

---

## Step 3：求 \(a_n\)

\[
a_n
=\frac{2}{\pi}\int_0^\pi x^2\cos(nx)\,dx
\]

積分後可得：

\[
a_n=\frac{4(-1)^n}{n^2}
\]

---

## 最終答案

\[
\boxed{
x^2
=
\frac{\pi^2}{3}
+
4\sum_{n=1}^{\infty}
\frac{(-1)^n}{n^2}\cos(nx)
}
\]

展開形式：

\[
\boxed{
x^2
=
\frac{\pi^2}{3}
-4\cos x
+\cos 2x
-\frac49\cos 3x
+\frac14\cos 4x
-\cdots
}
\]

---

# 完成
