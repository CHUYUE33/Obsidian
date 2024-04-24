#QuantumMechanics 

在量子力学以及量子场论中的传播子（propagator；核子，kernel），是描述粒子在特定时间由一处移动到另一处的几率幅，或是粒子以特定能量及动量移动的几率幅。传播子也是场的运动方程的格林函数。物理学家使用核子计算费曼图以及散射过程的概率。
>[!note] 自由粒子的传播子
>$$K(x,x';t)=\frac{1}{\sqrt{2\pi}}\int_{-\infty}^\infty dke^{ik(x-x')}e^{-i\hbar k^2t/(2m)}=\Big(\frac{m}{2\pi i\hbar t}\Big)^{1/2}e^{-m(x-x')^2/(2i\hbar t)}$$

传播子满足：
$$\ket{\psi(t)}=\hat{U}(t)\ket{\psi(x)}$$
## 自由粒子
我们可以写出非定态薛定谔方程的解：
$$\ket{\psi}=\ket{E}e^{-iEt/\hbar}$$
其中$\ket{E}$是定态薛定谔方程的解，又由于$\hat{P}$和$\hat{H}=\hat{P^2}$的共同本征态可以表示为标准正交基，所以我们采用$\ket{P}$表象：
$$\frac{\hat{P}^2}{2m}\ket{p}=E\ket{p}$$
所以$p$的可能取值为$p=\pm(2mE)^{1/2}$
所以对于一个给定的能量$E$，有两个正交的可能本征态：
$$\ket{E,+}=\ket{p=(2mE)^{1/2}}$$
$$\ket{E,-}=\ket{p=-(2mE)^{1/2}}$$
我们发现本征值$E$对应一个简并的二维本征空间，由上述向量张成。在给定能量$E$时粒子可能向左可能向右，所以我们把本征态$\ket{E}$写作：
$$\ket{E}=\beta\ket{p=(2mE)^{1/2}}+\gamma\ket{p=-(2mE)^{1/2}}$$
为了避免简并带来的麻烦，我们考虑非简并算符$\hat{P}$的本征态来表示。
那么传播子写作：
$$\begin{align}U(t)&=\int_{-\infty}^{\infty}\ket{p}\bra{p}e^{-iE(p)t/\hbar}dp\\
&=\int_{-\infty}^{\infty}\ket{p}\bra{p}e^{-ip^2t/2m\hbar}dp
\end{align}$$
我们知道本征态$\ket{p}$随时间的演化，所以传播子就是把初始分布函数投影到本征态上再加上演化函数。
传播子也可以在$\{\ket{x}\}$表象下表达：（也就是把$\ket{p}$写在x表象下）
$$\begin{align}U(x,t;x')&=\bra{x}\hat{U}(t)\ket{x}=\int_{-\infty}^{\infty}\bra{x}\ket{p}\bra{p}\ket{x'}e^{-ip^2t/2m\hbar}dp\\
&=\frac{1}{2\pi\hbar}\int_{-\infty}^{\infty}e^{ip(x-x')/\hbar}\cdot e^{-ip^2t/2m\hbar}dp\\
&=\Big(\frac{m}{2\pi\hbar it}\Big)e^{im(x-x')^2/2\hbar t}
\end{align}$$
这里表示$x'$处的粒子对于$x$处在时间$t$产生的影响，我们用格林函数可以有：
$$\psi(x,t)=\int U(x,t;x')\psi(x',0)dx'$$
或者：
$$\psi(x,t)=\int U(x,t;x',t')\psi(x',t')dx'$$

### 高斯波包的演化
考虑初始态为高斯波包的波函数：
$$\psi(x',0)=e^{ip_0x/\hbar}\frac{e^{-x^2/2b^2}}{(\pi b^2)^{1/4}}$$
这个形态的波包意味着$<X>=0$，不确定度为$\Delta X=b/\sqrt{2}$，平均动量为$p_0$，不确定度为$\hbar/\sqrt{2}$，带入之前的表达式可以写出含时波函数：
>[!note] 高斯波包的含时演化
>$$\psi(x,t)=\Big[\pi^{1/2}\Big(b+\frac{i\hbar t}{mb}\Big)\Big]^{-1/2}\cdot \exp{\Big[\frac{-(x-p_0t/m)^2}{2b^2(1+i\hbar t/mb^2)}\Big]}\cdot\exp{\Big[\frac{ip_0}{\hbar}\Big(x-\frac{p_0t}{2m}\Big)\Big]}$$
>概率密度：
>$$P(x,t)=\frac{1}{\pi^{1/2}}(b^2+\hbar^2t^2/m^2b^2)^{1/2}\cdot\exp{\Big\{\frac{-[x-(p_0/m)t]^2}{b^2+\hbar^2t^2/m^2b^2}\Big\}}$$
>粒子的平均位置：
>$$<X>=\frac{p_0t}{m}=\frac{<P>t}{m}$$
>波包宽度随时间增长：
>$$\Delta X(t)=\frac{\Delta(t)}{\sqrt{2}}=\frac{b}{\sqrt{2}}\Big(1+\frac{\hbar^2t^2}{m^2b^4}\Big)^{1/4}$$

补充：这里还有另一种表示高斯波包演化的方式：
$$\hat{U}(t)=\exp{\Big[\frac{i}{\hbar}\Big(\frac{\hbar^2t}{2m}\frac{d^2}{dx^2}\Big)\Big]}=\sum\limits_{n=0}^{\infty}\frac{1}{n!}\Big(\frac{i\hbar t}{2m} \Big)^n\frac{d^{2n}}{dx^{2n}}$$


## 无限深势阱内粒子
传播子在无限深势阱本征基下表达：
$$\hat{U}(t)=\sum\limits^{\infty}_{n=1}\ket{n}\bra{n}\exp{\Big[-\frac{i}{\hbar}\Big(\frac{\hbar^2\pi^2n^2}{2mL^2}\Big)t\Big]}$$
在x表象下的表达：
$$\begin{align}\bra{x}\hat{U}(t)\ket{x'}&=U(x,t;x')\\
&=\sum\limits_{n=1}^{\infty}\psi_n(x)\psi^*_n(x')\exp{\Big[-\frac{i}{\hbar}\Big(\frac{\hbar^2\pi^2n^2}{2mL^2}\Big)t\Big]}\end{align}$$