
--- 
title:Hamiltonian Formulation哈密顿方程
date::2023-09-1919:32
categories:
tags:

---
给定一个拉格朗日量$L(x_{i},\dot x_{i})$，我们可以找到相对应的哈密顿量$H(x_i,p_i)$通过勒让德变换的方式。
这里我们先来定义共轭动量：
$$\boxed{P_i\equiv\frac{\partial L}{\partial \dot x_{i}}}$$
为什么我们要这样去定义呢，因为我们可以看欧拉拉格朗日方程：
$$\frac{\partial L}{\partial x_i}-\frac{d}{dt}(\frac{\partial L}{\partial \dot x_i})=0$$
当系统拉格朗日量不直接依赖于$x_i$时（$\frac{\partial L}{\partial x_i}=0$），共轭动量将守恒（$\frac{\partial L}{\partial \dot x_i}=0$）。
可以看到，哈密顿量$H(x_i,p_i)$可以由拉格朗日量$L(x_i,\dot x_i)$进行勒让德变换得到：
$$H\equiv\sum\limits_{i}P_{i}\dot x_{i}-L(x_{i},\dot x_{i}(x_i,p_i))$$

举例：
>$L=\frac{1}{2}m\dot x_{i}\dot x_{i}-V(x_i)$
>$P_{i}\equiv\frac{\partial L}{\partial \dot x_{i}}=m\dot x_{i}\quad \Rightarrow \quad \dot x_{i}=\frac{P_i}{m}$
>$H\equiv P_{i}\dot x_{i}-L=P_{i}\frac{P_{i}}{m}-\frac{1}{2}(\frac{P_{i}}{m})(\frac{P_{i}}{m})+V(x_{i})=\frac{P_iP_i}{2m}+V(x_i)$

对于一个保守立场中的粒子，哈密顿量H就代表着总能量。

接下来我们来考虑哈密顿量的变分问题。
哈密顿量的独立变量为$(x_i,P_i)$，$H=P_{i}\dot x_{i}-L$
$$\begin{align}dH&=dP_{i}\dot x_{i}+P_{i}d\dot x_{i}-\frac{\partial L}{\partial x_i}dx_{i}-\frac{\partial L}{\partial \dot x_{i}}d\dot x_{i}\\
&=\dot x_{i}dP_{i}-\frac{\partial L}{\partial x_{i}}dx_{i}\end{align}$$
$$dH=\frac{\partial H}{\partial x_{i}}dx_{i}+\frac{\partial H}{\partial P_{i}}dP_{i}$$
如果我们考察的系统满足保守拉格朗日方程，那么我们有：
$$\frac{\partial L}{\partial x_{i}}=\frac{d}{dt}(\frac{\partial L}{\partial \dot x_{i}})=\dot P_{i}$$
哈密顿方程可写作：
$$\Rightarrow\begin{cases}\dot x_{i}=\frac{\partial H}{\partial p_{i}}\\\dot p_{i}=-\frac{\partial H}{\partial x_{i}}\end{cases}$$
在写一个体系的哈密顿量时，先写出$p_i=\frac{\partial L}{\partial \dot x_i}$，再由$H=p_ix_i-L$得到哈密顿量。
## 时间演化方程（泊松括号）
系统的时间演化可以被压缩，写成泊松括号的形式：
>假设我们有一个观测值$w(x_i,P_i)$
>$$\dot w=\frac{\partial w}{\partial x_{i}}\dot x_{i}+\frac{\partial w}{\partial P_{i}}\dot P_{i}=\frac{\partial w}{\partial x_{i}}\frac{\partial H}{\partial P_{i}}-\frac{\partial w}{\partial p_i}\frac{\partial H}{\partial x_i}\equiv\{w,H\}$$
>$$\boxed{\dot w=\{w,H\}}$$
泊松括号定义式：
>$$\{w,\lambda\}\equiv\frac{\partial w}{\partial x_i}\frac{\partial \lambda}{\partial p_i}-\frac{\partial w}{\partial p_i}\frac{\partial \lambda}{\partial x_i}$$
性质：
>1.$\{g,f\}=-\{f,g\}$
>3.$\{g,f+h\}=\{g,f\}+\{g,h\}$
>2.$\{f,gh\}=\{f,g\}h+\{f,h\}g$

泊松括号和对易子之间有很多联系，这里我们举一些例子：
$$\{x_i,x_j\}=\frac{\partial x_i}{\partial x_k}\frac{\partial x_j}{\partial P_k}-\frac{\partial x_i}{\partial P_k}\frac{\partial x_j}{\partial x_k}=0$$
$$\{x_i,P_j\}=\frac{\partial x_i}{\partial x_k}\frac{\partial P_j}{\partial P_k}-\frac{\partial x_i}{\partial P_k}\frac{\partial P_j}{\partial x_i}=\delta_{ik}\delta{jk}=\delta{ij}$$
$$\{P_i,P_j\}=0$$

## Transformation变换
首先我们来看时域变换：
$$w(t)\rightarrow w(t+\epsilon)=w(t)+\epsilon\dot w$$
这里我们可以将变换的变分写成（带入之前得到的关系式$\dot w=\{w,H\}$）：
$$\delta w=\epsilon \frac{dw}{dt}=\epsilon\{w,H\}$$
之前我们在[[最小作用量]]这个章节中谈到，有时间平移对称性时，能量守恒。由于大多数时候哈密顿量可以被视为体系的能量，这意味着在有时间平移对称性时，哈密顿量为守恒量。


我们现在来考虑变换：
$$\begin{align}&x_{i}\rightarrow x_{i}+\epsilon\delta x_{i}\\&P_{i}\rightarrow P_{i}+\epsilon\delta P_{i}\end{align}$$
我们可以采用简化假设，假设这是一个在1方向的空间变换，我们定义$\delta x_i=\delta_{1i},\delta p_i=0$
$$\begin{align}&x_{i}\rightarrow x_{i}+\epsilon\delta_{1i}\\&P_{i}\rightarrow P_{i}\end{align}$$
要证明这是一个对称变换，我们需要证明这是关于哈密顿量对称的。也就是说：
$$0=\delta H=\frac{\partial H}{\partial x_i}(\epsilon\delta x_i)+\frac{\partial H}{\partial p_i}(\epsilon\delta p_i)=\epsilon[\frac{\partial H}{\partial x_i}\delta x_i+\frac{\partial H}{\partial p_i}\delta p_i]$$

这里我们的变化微元$\delta x_{i},\delta P_{i}$被定义为产生于'Generator"$Q(x,P)$，其中：
$$\delta x_{i}\equiv\frac{\partial Q}{\partial P_{i}},\delta P_{i}=-\frac{\partial Q}{\partial x_{i}}$$
$$\delta H=\frac{\partial H}{\partial x_{i}}\epsilon\delta x_{i}+\frac{\partial H}{\partial P_{i}}\epsilon \delta P_{i}=\epsilon[\frac{\partial H}{\partial x_i}\frac{\partial Q}{\partial P_i}-\frac{\partial H}{\partial P_i}\frac{\partial Q}{\partial x_i}]=\epsilon\{H,Q\}$$
所以H的变换$\delta H$可以看作是H和生成元Q的泊松括号。
所以说对于任何可观测的量$w$，在生成元$Q$作用下的变分都可以写成：
$$\boxed{\delta w=\epsilon\{w,Q\}}$$
<font color=orange>疑问：为什么这里的$\delta w$内是含有$\epsilon$的，而在之前[[最小作用量]]进行定义时不含$\epsilon$？</font>
这样我们写出了任意可观测量的变换，但是这个变换想要是对称的，我们需要满足：
$$\delta H=\epsilon\{H,Q\}=0$$
我们再回到时间变换，寻找时间对应的generator。
当时间发生变化时$t\rightarrow t+\epsilon$，可观测量w又该如何变化？
$$w(t)\rightarrow w(t+\epsilon)=w(t)+\epsilon\dot w=w(t)+\epsilon\{w,H\}$$
所以说，<font color=##33CCFF>H 是时间变换的生成元</font>.

><font color=orange>Example:</font>
>这里我们举一个生成元与变量的例子，我们将动量$p_j$看作是$x_j$方向空间变换的生成元，由定义式我们可得：
>$$x_i\rightarrow x_i'=x_i+\epsilon_j\frac{\partial p_j}{\partial p_i}=x_i+\epsilon_j\delta_{ji}$$
>$$p_j\rightarrow p_i'=p_i-\epsilon_{j}\frac{\partial p_j}{\partial x_i}=p_i$$
>或者我们可以直接从泊松括号写出变分的表达式：
>$$\delta x_i=\epsilon_j\{x_i,p_j\}=\epsilon_j\delta_{ji}$$
>$$\delta p_i=\epsilon_i\{p_i,p_j\}=0$$
>这就是动量生成的空间变换。
>我们还有角动量作为生成元的情况，可以生成旋转变换。