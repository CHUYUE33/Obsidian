#SolidStates  #BookNote

这部分考虑的热容主要是固体中离子部分导致的热容。
## Classical Boltzmann Solid
在Boltzmann的设想下，粒子的哈密顿量可以写作
$$H= \frac{\hat{p}^2}{2m}+ \frac{k}{2}\hat{x}^2$$
由此我们可以写出经典模型的配分函数：
$$Z=\int \frac{d\hat{p}}{(2\pi \hbar)^3}\int e^{\beta H(p,x)} \, dx =\Big[\frac{1}{2\pi \hbar} \sqrt{ \frac{\pi}{\beta/m} }\sqrt{ \frac{\pi}{\beta k/2} }\Big]^3=(\beta \hbar w)^3$$
由此我们可以写出热容的表达式：
$$U=- \frac{\partial\ln{Z}}{\partial \beta}=3k_{B}T$$

<font color=orange>可以看到经典的模型是一个连续的积分。</font>
## Einstein's Calculation
Einstein假设所有的原子处于由附近原子相互作用创造的全同谐振势阱中，振动频率为$w$。
对于一维谐振子，我们可以写出其单谐振子的本征态：
$$E_n=\hbar w(n+1/2)$$
由此可得配分函数为
$$Z_{1D}=\sum\limits_{n\ge0}e^{-\beta\hbar w(n+1/2)}=\frac{e^{-\beta\hbar w(1+1/2)}}{1-e^{-\beta\hbar w(1+1/2)}}=\frac{1}{2\sinh{\beta\hbar w/2}}$$
<font color=orange>这是Einstein模型与Boltzmann模型最主要的区别，带入量子化的假设来对动量进行积分。</font>
能量期望为
$$<E>=-\frac{1}{Z_{1D}}\frac{\partial Z_{1D}}{\partial\beta}=\frac{\hbar w}{2}\coth{\Big(\frac{\beta\hbar w}{2}\Big)}=\hbar w\Big(n_B(\beta\hbar w)+1/2\Big)$$
其中$n_B$为玻色占据因子$n_B(x)=\frac{1}{e^x-1}$，所以一般$w$振动模式会被平均激发到第$n_B$能级。
所以对于单个震动子，热容写作
$$C=\frac{\partial<E>}{\partial T}=k_B(\beta\hbar w)^2\frac{e^{\beta\hbar w}}{(e^{\beta\hbar w}-1)^2}$$

现在我们来考虑三维情形：
$$E_{n_x,n_y,n_z}=\hbar w[(n_x+1/2)+(n_y+1/2)+(n_z+1/2)]$$
$$Z_{3D}=\sum\limits_{n_x,n_y,n_z\ge0}e^{-\beta E_{n_x,n_y,n_z}}=[Z_{1D}]^3$$
$$C=3k_B(\beta\hbar w)^2\frac{e^{\beta\hbar w}}{(e^{\beta\hbar w}-1)^2}$$
在$k_BT/\hbar w\rightarrow2$时，$C/3k_B\rightarrow1$。

##  Debye's Calculation
Debye认为固体的振动模式为以$w(\vec{k})=v|\vec{k}|$为频率的的声波，$v$为声速。对于每一个波矢$\vec{k}$都有三个对应的振动模式，类比Einstein可得：
$$\begin{align}\langle E\rangle&=3\sum\limits_{\vec{k}}\hbar w(\vec{k})\Big(n_B(\beta\hbar w(\vec{k}))+\frac{1}{2}\Big)\\
&=3\frac{L^3}{(2\pi)^3}\int d\vec{k}\hbar w(\vec{k})\Big(n_B(\beta\hbar w(\vec{k}))+\frac{1}{2}\Big)
\end{align}$$
这告诉我们每个频率为$w(\vec{k})$激发态都被$n_B(\beta\hbar w(\vec{k}))$玻色子占据。
由于球对称性，我们在球坐标下积分可得
$$\langle E\rangle=3\frac{4\pi L^3}{(2\pi)^3}\int_0^\infty w^2dw(1/v^2)(\hbar w)\Big(n_B(\beta\hbar w)+\frac{1}{2}\Big)$$
带入态密度$g(w)$的概念，可得
$$\langle E\rangle=\int_0^\infty dwg(w)(\hbar w)\Big(n_B(\beta\hbar w)+\frac{1}{2}\Big),$$
这里$g(w)$其实就是离散求和变为积分产生的系数$L^3/(2\pi)^3$乘以$d\vec{k}$转换为$dw$的系数$4\pi k^2dk/dw=4\pi w^2/v^2$（here from$w=v k$）再乘以三个振动模式给出的系数3：
$$\Rightarrow g(w)=L^3\frac{12\pi w^2}{(2\pi)^3v^3}=N\frac{12\pi w^2}{(2\pi)^3nv^3}=N\frac{9w^2}{w_d^3}$$
其中$nL^3=N$，$n$为原子密度，$w_d^3=6\pi^2nv^3$这是Debye频率。
与Plank得到的光子能量分布不同仅仅在于将$2/c^3$代换为$3/v^3$（将两种光子的振动模式代替为三种声波振动模式）。
所以带入$x=\beta\hbar w$
$$\begin{align}\langle E\rangle&=\frac{9N\hbar}{w_d^3(\beta\hbar)^4}\int_0^\infty dx\frac{x^3}{e^x-1}+constanat\\
&=9N\frac{(k_BT)^4\pi^4}{(\hbar w_d)^315}+T \ independent \ constant\end{align}$$
由此可以得到：
$$C=  \frac{\partial \langle E\rangle}{\partial T}=Nk_{B}\frac{(k_{B}T)^3}{(\hbar w_{d})^3} \frac{12\pi^4}{5}\sim T^3$$
此时我们可以定义Debye Temperature$\Theta_{{Debye}}:$
$$k_{B}\Theta_{Debye}=\hbar w_{d}$$
所以带入Debye T我们可以得到
$$C=Nk_{B} \frac{T^3}{T_{Debye}^3} \frac{12\pi^4}{5}$$
<font color=orange>这里的计算其实只对于温度远小于Debye Temperature的情形适用，这是因为我们在将求和推广为积分时（或者应该说是一开始在求和时就没有限制波矢的范围）积分上限为无穷大，这种情况只在$T\le \Theta_{Debye}$时可以这样近似</font>

## Debye Model进一步修正
在认识到波矢应该存在一个上限之后，我们可以定义上限为$w_{{cut-off}}$，我们对这个频率内部的态密度积分应该满足为总粒子数的三倍（粒子蕴蓄三个方向的运动）
$$3N=\int_{0}^{w_{cutoff}}  dwg(w) $$
<font color=orange>这就是对于上限频率的限制关系</font>。
计算上市并展开，我们可以得到
$$3N\int^{w_{cutoff}}_{0}dwg(w)=9N\int_{0}^{w_{cutoff}}dw \frac{w^2}{w_{d}^2}=3N \frac{w_{cutoff}^3}{w_{d}^3} $$
所以我们看到，Debye frequency就是我们的截止频率。

当然这个先定义Debye frequency再来证明这个玩意儿是我们想要的截止频率的方法是有点诡异的，我更喜欢按照这样的顺序来讲Debye frequency[[Debye定律]]。
Prefer的逻辑：由于固体中振动模式的波长不得小于两个原子之间的间距，原子间距给出了对于频率上限的约束。
其实我感觉这里更像是说明了我们通过几个系数凑出来的$g(w)$刚好满足上述的约束关系233333.
现在我们的总能量表达式优化为
$$\langle E\rangle=\int_{0}^{w_{cutoff}}dw \ g(w) \ \hbar w \ n_{B}(\beta \hbar w)   $$
然后分情况讨论
>[!note] Debye Model
>1. 高温情形
> $$n_{B}(\beta \hbar w)=\frac{1}{e^{\beta \hbar w}-1}\rightarrow \frac{k_{B}T}{\hbar w}$$
> 所以总能量可以写作$$\langle E\rangle= k_{B}T\int_{0}^{w_{cutoff}}dwg(w)=3k_{B}TN$$
>2. 低温情形
>$$C=  \frac{\partial \langle E\rangle}{\partial T}=Nk_{B}\frac{(k_{B}T)^3}{(\hbar w_{d})^3} \frac{12\pi^4}{5}\sim T^3$$
>$$C=Nk_{B} \frac{T^3}{T_{Debye}^3} \frac{12\pi^4}{5},T_{{Debye}}=\hbar w_{d}/k_{B}$$
## Summary
>[!note] Summary
>大部分材料的热容来源于原子的振动
>Boltzmann和Einstein模型将这些振动看作N个谐振子
>Boltzmann得到结果：Dulong-Petit $C=3Nk_B=3R$
>Einstein分析在温度低于振动频率时，一些自由度冻结所以热容快速下降

补充：一些数学技巧
>$$\int_{0}^\infty dx \frac{x^3}{e^x-1}=\int_{0}^\infty dx \frac{x^3e^{-x}}{1-e^{-x}}  =\int_{0}^\infty dxx^3e^{-x}\sum_{{n=0}}^\infty e^{-nx}=\sum_{n=1}^\infty \int_{0}^\infty  \, dxx^3e^{-nx}  $$
>所以这个积分可以被写作$$3!\sum_{{n=1}}^\infty n^{-4}$$
>根据Riemann-Zeta function的定义$\xi(p)=\sum_{{n=1}}^\infty n^{-p}$，所以结果为$3!\xi(4),\xi(4)=\pi^4/90$