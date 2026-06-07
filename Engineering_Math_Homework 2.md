# Engineering_Math_Homework 2
## Problem (3)

Solve the differential equation using the Laplace transform:

\[
x'' + 6x' + 8x = 1
\]

with initial conditions

\[
x(0)=1,\quad x'(0)=0
\]

### Solution

Taking the Laplace transform:

\[
(s^2X-s)+6(sX-1)+8X=\frac{1}{s}
\]

Simplifying:

\[
(s^2+6s+8)X-s-6=\frac{1}{s}
\]

\[
X=\frac{\frac{1}{s}+s+6}{(s+2)(s+4)}
\]

Using partial fraction decomposition:

\[
X=\frac{1}{8s}+\frac{3}{4(s+2)}+\frac{1}{8(s+4)}
\]

Taking the inverse Laplace transform:

\[
\boxed{
x(t)=\frac18+\frac34e^{-2t}+\frac18e^{-4t}
}
\]

---

## Problem (8)

Let

\[
f(x)=x^2,\quad x\in[-\pi,\pi]
\]

Find the Fourier series of \(f(x)\).

### Solution

Since \(x^2\) is an even function, its Fourier series contains only cosine terms:

\[
f(x)\sim \frac{a_0}{2}+\sum_{n=1}^{\infty}a_n\cos(nx)
\]

### Step 1: Compute \(a_0\)

\[
a_0=\frac{1}{\pi}\int_{-\pi}^{\pi}x^2dx
\]

Because the function is even:

\[
a_0=\frac{2}{\pi}\int_0^\pi x^2dx
\]

\[
a_0=\frac{2}{\pi}\left[\frac{x^3}{3}\right]_0^\pi
\]

\[
a_0=\frac{2\pi^2}{3}
\]

Therefore,

\[
\frac{a_0}{2}=\frac{\pi^2}{3}
\]

### Step 2: Compute \(a_n\)

\[
a_n=\frac{2}{\pi}\int_0^\pi x^2\cos(nx)\,dx
\]

Using integration by parts:

\[
a_n=\frac{4(-1)^n}{n^2}
\]

### Final Answer

\[
\boxed{
x^2=\frac{\pi^2}{3}+4\sum_{n=1}^{\infty}\frac{(-1)^n}{n^2}\cos(nx)
}
\]

Expanded form:

\[
x^2=\frac{\pi^2}{3}
-4\cos x
+\cos 2x
-\frac49\cos 3x
+\frac14\cos 4x
-\cdots
\]
