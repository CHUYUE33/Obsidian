
--- 
title:Dirac Delta Function
date::2023-09-1919:32
categories:
tags:

---
$$\delta(x-x')=\delta(x'-x)$$
$$\int_{-\infty}^{\infty}dxf(x)\delta(a(x-x'))=\frac{1}{a}\int_{-\infty}^{\infty}duf(\frac{u}{a})\delta(u-u')=\frac{1}{a}f(\frac{u'}{a})=\frac{1}{a}f(x')$$
$$\delta(a(x-x'))=\frac{1}{|a|}\delta(x-x')$$
$$\boxed{\delta'(x-x')\equiv\frac{d}{dx}\delta(x-x')}$$
这里可以参考讲微分算子时使用的分部积分方法：[[无限维向量空间]]（不过这个方法非常直观，也不太需要专门提一嘴hhhh）：
$$\int_{-\infty}^{\infty}f(x)\frac{d}{dx}\delta(x-x')dx=-\int_{-\infty}^{\infty}\frac{df}{dx}\delta (x-x')dx=-\frac{df}{dx}\Big|_{x=x'}$$
所以有：
$$\int_{-\infty}^{\infty}f(x)\frac{d}{dx}\delta(x-x')dx=-f'(x')$$
$$\boxed{\frac{d}{dx}\delta(x-x')=-\frac{d}{dx'}\delta(x-x')}$$
关于1的傅里叶变换：
$$\int_{-\infty}^{\infty}dke^{ik(x-x')}=2\pi\delta(x-x')$$