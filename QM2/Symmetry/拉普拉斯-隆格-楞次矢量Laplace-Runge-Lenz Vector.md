#QuantumMechanics 

库仑力比一般的旋转不变系统有更多的对称性，这些额外的对称性我们额可以用一个守恒量，Laplace-Runge-Lenz vector来描述
$$\hat{M}=\frac{\hat{P}\times\hat{L}-\hat{L}\times \hat{p}}{2m}+\hat{V(r)}$$
其中$\hat{V(r)}$表示势能，$\hat{V(r)}=-e^2/4\pi \epsilon_{0}r$。对于氢原子模型，守恒量的完整对易关系如下
$$[\hat{H},\hat{M_{i}}]=0\tag{1}$$
$$[\hat{H},\hat{L_{i}}]=0\tag{2}$$
$$[\hat{L_{i}},\hat{L_{j}}]=i\hbar \epsilon_{ijk}\hat{L_{k}}\tag{3}$$
$$[\hat{L_{i}},\hat{M_{j}}]=i\hbar\epsilon_{ijk}\hat{M_{k}}\tag{4}$$
$$[\hat{M_{i}},\hat{M_{j}}]=\frac{\hbar}{i}\epsilon_{ijk}\hat{L_{k}} \frac{2}{m}\hat{H}\tag{5}$$
对于1-4式我们解释一下物理含义：
>（1）表示$\hat{M}$是守恒量
>（2）表示$\hat{L}$是守恒量
>（3）表示$\hat{L}$是矢量
>（4）表示$\hat{M}$是矢量

除此之外我们还有两个关于$\hat{L},\hat{M},\hat{H}$之间关系的方程
$$\hat{M^2}=\left( \frac{e^2}{4\pi\epsilon_{0}} \right)^2+\frac{2}{m}\hat{H}(\hat{L^2}+\hbar^2)\tag{6}$$
$$\hat{M}\cdot \hat{L}=0\tag{7}$$
>[!note] $\hat{M}$的一系列
>由于矢量，我们可定义$$\hat{M_{+}}\psi_{nll}=c_{nl}\psi_{n(l+1)(l+1)}\tag{8}$$，最终有
>$$\hat{M_{z}}\psi_{nl l}=-\frac{1}{\sqrt{ 2 }} \frac{1}{\sqrt{ l+1 }}c_{nl}\psi n(l+1)l\tag{9}$$
>$$\hat{M_{-}}\hat{M_{+}}\psi_{nl l}=\left( \frac{e^2}{4\pi\epsilon_{0}} \right)^2\left[ 1-\left( \frac{l+1}{n} \right)^2 \right]\psi_{nll}-\hat{M_{z}}^2\psi_{nll}\tag{10}$$
>由（9）（10）我们可以计算出$c_{nl}$表达式：
>$$|c_{nl}|^2=\frac{2l+3}{2l+2} \left( \frac{e^2}{4\pi\epsilon_{0}} \right)^2\left[ 1-\left( \frac{l+1}{n} \right)^2 \right]\tag{11}$$
>这说明$c_{nl}\neq 0$除非$l=n-1$。

证明：
（9）我们首先写出
$$\begin{align}
\hat{M}\cdot  \hat{L}&=M_{x}L_{x}+M_{y}L_{y}+M_{z}L_{z} \\
&=\frac{M_{+}+M_{-}}{2} \frac{L_{+}+L_{-}}{2}+\frac{M_{+}-M_{-}}{2i} \frac{L_{+}-L_{-}}{2i}+M_{z}L_{z} \\
&=\frac{M_{+}L_{-}+M_{-}L_{+}}{2}+M_{z}L_{z}
\end{align}$$
将上面得到的结果作用到$\psi_{nll}$：
$$\begin{align}
\frac{1}{2}M_{+}L_{-}\psi_{nll}+\frac{1}{2}M_{-}L_{+}\psi_{nll}+M_{z}L_{z}\psi_{nll}&=0 \\
\frac{1}{2}(L_{-}M_{+}+[M_{+},L_{-}])\psi_{nll}+0+l\hbar M_{z}\psi_{nll}&=0 \\
\frac{1}{2}L_{-}c_{nl}\psi_{n(l+1)(l+1)}+\frac{1}{2}[M_{+},L_{-}]\psi_{nll}+l\hbar M_{z}\psi_{nll}&=0
\end{align}$$
使用[[旋转对称性Rotational Symmetry]]中最后提到的对于vector operator的对易关系（4）可得
$$\frac{1}{2}B_{l+1}^lc_{nl}\psi_{nl+1l}+\hbar N_{z}\psi_{nll}+l\hbar M_{z}\psi_{nll}=0$$
$$\sqrt{ \frac{l+1}{2} }\hbar c_{nl}\psi_{nll-1}=-(l+1)\hbar M_{z}\psi_{nll}$$
所以可得
$$\boxed{\hat{M_{z}}\psi_{nl l}=-\frac{1}{\sqrt{ 2 }} \frac{1}{\sqrt{ l+1 }}c_{nl}\psi n(l+1)l\tag{9}}$$

（10）证明：
类似于之前对于$\hat{M}\cdot  \hat{L}$的操作，
$$\hat{M}\cdot  \hat{M}=\frac{M_{+}M_{-}+M_{-}M_{+}}{2}+M_{z}^2$$
联系（6）式我们可得
$$\begin{align}
M^2\psi_{nll}&=\left[ \left( \frac{e^2}{4\pi\epsilon_{0}} \right)^2+\frac{2}{m}\hat{H}(L^2+\hbar^2) \right]\psi_{nll} \\
\frac{1}{2}M_{+}M_{-}\psi_{nll}+\frac{1}{2}M_{-}M_{+}\psi_{nll}+M_{z}^2\psi_{nll}&=\Big\{\left( \frac{e^2}{4\pi\epsilon_{0}} \right)^2+\frac{2}{m}E_{n}(l(l+1)+1)\hbar^2\Big\}\psi_{nll} \\
\frac{1}{2}[M_{+},M_{-}]\psi_{nll}+M_{-}M_{+}\psi_{nll}+M_{z}^2\psi_{nll}&=\Big(\frac{e^2}{4\pi\epsilon_{0}}\Big)^2\Big[1-\frac{l^2+l+1}{n^2}\Big]\psi_{nll}
\end{align}$$
从（5）我们可以解出对易子
$$\begin{align}
[M_{+},M_{-}]&=[M_{x},M_{x}]+i[M_{y},M_{x}]-i[M_{x},M_{y}]-[M_{y},M_{y}] \\
&=-2i[M_{x},M_{y}]=-2\hbar L_{z} \frac{2}{m}\hat{H}
\end{align}$$
带回我们有
$$-\hbar L_{z} \frac{2}{m} \hat{H}\psi_{nll}+M_{-}M_{+}\psi_{nll}+M_{z}^2\psi_{nll}=\left( \frac{e^2}{4\pi\epsilon_{0}} \right)^2\left[ 1-\frac{l^2+l+1}{n^2} \right]\psi_{n\ll}$$
$$-\hbar l\hbar \frac{2}{m} E_{n}\psi_{nll}+M_{-}M_{+}\psi_{nll}+M_{z}^2\psi_{nll}=\left( \frac{e^2}{4\pi\epsilon_{0}} \right)^2\left[ 1-\frac{l^2+l+1}{n^2} \right]\psi_{n\ll}$$
所以有
$$\boxed{\hat{M_{-}}\hat{M_{+}}\psi_{nl l}=\left( \frac{e^2}{4\pi\epsilon_{0}} \right)^2\left[ 1-\left( \frac{l+1}{n} \right)^2 \right]\psi_{nll}-\hat{M_{z}}^2\psi_{nll}}\tag{10}$$
（11）证明：
我们注意到
$$\begin{align}
|c_{nl}|^2&=\int (M_{+}\psi_{nll})^*(M_{+}\psi_{nll})d^3r \\
&=\int \psi_{nll}^*M_{-}M_{+}\psi_{nll}d^3r  
\end{align}$$
带入（10）式可得
$$\begin{align}
|c_{nl}|^2&=\left( \frac{e^2}{4\pi\epsilon_{0}} \right)^2\left[ 1-\left( \frac{l+1}{n} \right)^2 \right]-\int \psi_{nll}^* M_{z}^2\psi_{nll}d^3r  \\
&=\left( \frac{e^2}{4\pi\epsilon_{0}} \right)^2\left[ 1-\left( \frac{l+1}{n} \right)^2 \right]-\int (M_{z}\psi_{nll})^*M_{z}\psi_{nll}d^3r 
\end{align}$$
带入（9）式

$$|c_{nl}|^2=\left( \frac{e^2}{4\pi\epsilon_{0}} \right)^2\left[ 1-\left( \frac{l+1}{n} \right)^2 \right]-\frac{1}{2(l+1)}|c_{nl}|^2 \int \psi_{nl+1l}^*\psi_{nl+1l}d^3r $$
最终解得
$$\boxed{|c_{nl}|^2=\frac{2l+3}{2l+2} \left( \frac{e^2}{4\pi\epsilon_{0}} \right)^2\left[ 1-\left( \frac{l+1}{n} \right)^2 \right]}$$