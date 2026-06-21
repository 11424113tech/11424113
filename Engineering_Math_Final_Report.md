# 工程數學期末報告

> 科目：工程數學  
> 單元：拉普拉斯轉換  
> 題目：第六題（二階系統：單自由度阻尼振動系統的單位衝擊回應）

---

# 第 6 題

## 題目

汽車座椅減振系統簡化為單自由度欠阻尼振動系統，初始狀態靜止，輸入為單位衝擊力：

```math
f(t)=\delta(t)
```

求位移輸出的單位衝擊回應：

```math
x(t)
```

---

## 解答

單自由度阻尼振動系統的運動方程式為：

```math
m\ddot{x}+c\dot{x}+kx=f(t)
```

由於輸入為單位衝擊力：

```math
f(t)=\delta(t)
```

因此方程式可寫成：

```math
m\ddot{x}+c\dot{x}+kx=\delta(t)
```

初始狀態靜止：

```math
x(0)=0,\quad \dot{x}(0)=0
```

---

## 拉普拉斯轉換

對方程兩側取拉普拉斯轉換：

```math
\mathcal{L}\{m\ddot{x}+c\dot{x}+kx\}
=\mathcal{L}\{\delta(t)\}
```

利用公式：

```math
\mathcal{L}\{\ddot{x}\}=s^2X(s)-sx(0)-\dot{x}(0)
```

```math
\mathcal{L}\{\dot{x}\}=sX(s)-x(0)
```

以及：

```math
\mathcal{L}\{\delta(t)\}=1
```

代入初始條件：

```math
m s^2X(s)+csX(s)+kX(s)=1
```

整理得：

```math
(ms^2+cs+k)X(s)=1
```

因此：

```math
X(s)=\frac{1}{ms^2+cs+k}
```

---

## 化為標準二階系統形式

令自然頻率為：

```math
\omega_n=\sqrt{\frac{k}{m}}
```

阻尼比為：

```math
\zeta=\frac{c}{2\sqrt{mk}}
```

則：

```math
ms^2+cs+k
=m\left(s^2+2\zeta\omega_n s+\omega_n^2\right)
```

所以：

```math
X(s)=\frac{1}{m}\cdot
\frac{1}{s^2+2\zeta\omega_n s+\omega_n^2}
```

配方：

```math
s^2+2\zeta\omega_n s+\omega_n^2
=(s+\zeta\omega_n)^2+\omega_n^2(1-\zeta^2)
```

令阻尼自然頻率為：

```math
\omega_d=\omega_n\sqrt{1-\zeta^2}
```

因為題目為欠阻尼系統：

```math
0<\zeta<1
```

因此：

```math
X(s)=\frac{1}{m}\cdot
\frac{1}{(s+\zeta\omega_n)^2+\omega_d^2}
```

---

## 反拉普拉斯轉換

利用公式：

```math
\mathcal{L}^{-1}\left\{
\frac{\omega_d}{(s+a)^2+\omega_d^2}
\right\}
=e^{-at}\sin(\omega_d t)
```

將分子補成 \(\omega_d\)：

```math
X(s)=\frac{1}{m\omega_d}\cdot
\frac{\omega_d}{(s+\zeta\omega_n)^2+\omega_d^2}
```

所以：

```math
x(t)=\frac{1}{m\omega_d}
e^{-\zeta\omega_n t}\sin(\omega_d t)
```

---

## 最終答案

```math
\boxed{
x(t)=\frac{1}{m\omega_d}
e^{-\zeta\omega_n t}\sin(\omega_d t)u(t)
}
```

其中：

```math
\omega_d=\omega_n\sqrt{1-\zeta^2}
```

```math
\omega_n=\sqrt{\frac{k}{m}}
```

```math
\zeta=\frac{c}{2\sqrt{mk}}
```

也可寫成：

```math
\boxed{
x(t)=\frac{1}{m\omega_n\sqrt{1-\zeta^2}}
e^{-\zeta\omega_n t}
\sin\left(\omega_n\sqrt{1-\zeta^2}\,t\right)u(t)
}
```

---

## 結論

此系統為欠阻尼二階系統，因此受到單位衝擊力後，位移輸出會呈現衰減振盪。指數項：

```math
e^{-\zeta\omega_n t}
```

代表振幅隨時間逐漸變小；正弦項：

```math
\sin(\omega_d t)
```

代表系統以阻尼自然頻率進行振動。
