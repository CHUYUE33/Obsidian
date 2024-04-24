#QuantumMechanics 
## 原理
对于无法求解薛定谔方程给出具体基态能量$E_{gs}$的情形我们选择采用变分法来估计基态能量的上限：
$$\boxed{E_{gs}\le\bra{\psi}H\ket{\psi}\equiv\langle H\rangle  }\tag{1}$$
这里$\psi$是任意归一化的波函数，只有在$\psi$刚好取到基态波函数时（1）式取等。

>[!note] Example
>我们想用变分法寻找一维谐振子的基态能量
>$$H=-\frac{\hbar^2}{2m} \frac{d^2}{dx^2}+\frac{1}{2}mw^2x^2$$
>接下来我们猜测基态可能的波函数表达式是gaussian（这个guess就是变分法最核心的地方，通过猜测基态波函数去拟合基态能量）
>$$\psi(x)=Ae^{-bx^2}\tag{2}$$
>$$1=|A|^2\int_{-\infty}^{\infty} e^{-2bx^2}dx=|A|^2\sqrt{ \frac{\pi}{2b} }\quad \Rightarrow\quad A=\left( \frac{2b}{\pi} \right)^{1/4}\tag{3} $$
>这里我们$b$系数是待定的，我们可以根据之后计算的结果取不同的b值使得我们的upper bond取到最小值。
>因为$$\langle H\rangle=\langle T\rangle+\langle V\rangle\tag{4}$$
>其中
>$$\langle T\rangle=-\frac{\hbar^2}{2m}|A|^2\int_{-\infty}^{\infty}e^{-bx^2} \frac{d^2}{dx^2}(e^{-bx^2})  \, dx=\frac{\hbar^2b}{2m} \tag{5}$$
>$$\langle V\rangle=\frac{1}{2}mw^2|A|^2\int _{-\infty}^{\infty}e^{-2bx^2}x^2 \, dx=\frac{\hbar^2b}{2m} $$
>所以
>$$\langle H\rangle =\frac{\hbar^2b}{2m}+\frac{mw^2}{8b}\tag{6}$$
>b是一个待定的系数，我们取最小限制：
>$$\frac{d}{db}\langle H\rangle=\frac{\hbar^2}{2m}-\frac{mw^2}{8b^2}=0\Rightarrow\frac{mw}{2\hbar}$$
>带回我们可得
>$$\langle H\rangle_{min}=\frac{1}{2}\hbar w$$
>和我们预期的一样。


## 氦原子模型
我们可以写出氦原子的哈密顿量表达式
$$H=-\frac{\hbar^2}{2m}(\nabla^2_{1}+\nabla^2_{2})-\frac{e^2}{4\pi\epsilon_{0}}\left( \frac{2}{r_{1}}+\frac{2}{r_{2}}-\frac{1}{|r_{1}-r_{2}|} \right)\tag{7}$$
$r_{1},r_{2}$分别表示两个电子到原子核（质子）的矢量。
现在我们来求$E_{gs}$（使两个电子都被电离的能量，不同于第一电离能）。
先忽略电子间相互作用：$V_{ee}=\frac{e^2}{4\pi\epsilon_{0}} \frac{1}{|r_{1}-r_{2}|}$
现在氦原子哈密顿量可以看作两个相互独立的电子（此时单个原子核电荷为2e）的哈密顿量的组合，对应的解空间也就是单个电子的解空间的直积：
$$\psi_{0}(r_{1},r_{2})\equiv \psi_{100}(r_{1})\psi_{100}(r_{2})=\frac{8}{\pi a^3}e^{-2(r_{1}+r_{2})/a}\tag{8}$$
我们做这些工作是为了给出一个reasonable的基态波函数猜测，将这个波函数使用变分法：
$$\langle H\rangle=8E_{1}+\langle V_{ee}\rangle\tag{9}$$
其中$$\langle V_{ee}\rangle=\left( \frac{e^2}{4\pi\epsilon_{0}} \right)\left( \frac{8}{\pi a^3} \right)\int \frac{e^{-4(r_{1}+r_{2})/a}}{|r_{1}-r_{2}|}d^3r_{1}d^3r_{2}\tag{10} $$
这个积分的处理十分麻烦，我们一般先对$r_{2}$积分，化为
$$\left( \frac{e^2}{4\pi\epsilon_{0}} \right)\left( \frac{8}{\pi a^3} \right)\int \left[ 1-\left( 1+\frac{2r_{2}}{a} \right)e^{-4r_{1}/a} \right]e^{-4r_{1}/a}r_{1}\sin\theta_{1}dr_{1}d\theta_{1}d\phi_{1}$$
最后得到
$$\langle V_{ee}\rangle=\left( \frac{e^2}{4\pi\epsilon_{0}} \right)\left( \frac{8}{\pi a^3} \right) \frac{5a^2}{128}=-\frac{5}{2}E_{1}=34eV\tag{11}$$

优化变分法的方法就是找更加reasonable的基态波函数，现在我们不再忽略$V_{ee}$，将其影响看作对于内部电荷的屏蔽效应，即内部电荷不再是$2$，对于核外电子他们感受到的有效电荷变为$Z$，我们的trial波函数写作
$$\psi_{1}(r_{1},r_{2})\equiv \frac{Z^3}{\pi a^3}e^{-Z(r_{1}+r_{2})/a}\tag{12}$$
与此同时，我们将（7）式的哈密顿量重新写作
$$H=-\frac{\hbar^2}{2m}(\nabla_{1}^2+\nabla _{2}^2)-\frac{e^2}{4\pi\epsilon_{0}}\left( \frac{Z}{r_{1}} +\frac{Z}{r_2}\right)+\frac{e^2}{4\pi\epsilon_{0}}\left( \frac{Z-2}{r_{1}}+\frac{Z-2}{r_{2}}+\frac{1}{|r_{1}-r_{2}|} \right)\tag{13}$$
所以哈密顿量的期望值写作
$$\langle H\rangle=2Z^2E_{1}+2(Z-2)\left( \frac{e^2}{4\pi\epsilon_{0}} \right)\left\langle  \frac{1}{r}  \right\rangle+\langle V_{ee}\rangle\tag{14}$$
其中$\langle \frac{1}{r}\rangle$表示$\frac{1}{r}$原子核电荷为$Z$的氢原子基态$\psi_{100}$的期望值，我们可以得到其具体数值为
$$\left\langle  \frac{1}{r} \right\rangle=\frac{Z}{n^2a}=\frac{Z}{a}\tag{15}$$
对于$\langle V_{ee}\rangle$，我们发现其取值与$Z$一阶相关（可以在计算过程中发现），所以通过（11）式我们推广得到对于任意$Z$取值情形下的电子相互作用项（只有波函数改变时）
$$\langle V_{ee}\rangle=-\frac{5Z}{4}E_{1}\tag{16}$$
总的有
$$\langle H\rangle=[2Z^2-4Z(Z-2)-(5/4)Z]E_{1}=[-2Z^2+(27/4)Z]E_{1}\tag{17}$$
（这里电子相互作用项也改了：虽然能量的形式没变，但是波函数形式改变了含有Z，所以改变了）。
取极值
$$\frac{d}{dZ}\langle H\rangle=[-4Z+(27/4)]E_{1}=0\Rightarrow\quad Z=\frac{27}{16}\tag{18}$$
能量写作
$$\langle H\rangle=\frac{1}{2}\left( \frac{3}{2} \right)^6E_{1}=-77.5eV\tag{19}$$

>[!note] 推广：$Z_{0}$电荷原子核
>现在我们来考虑原子核有$Z_{0}$个质子的情形（He中只有2个质子）。
>忽略电子之间的相互作用我们可以写出波函数
>$$\psi_{0}=\frac{Z_{0}^3}{\pi a^3}e^{-Z_{0}(r_{1}+r_{2})/a}$$
>能量：$2Z_{0}^2E_{1}$
>$\langle V_{ee}\rangle=-\frac{5}{4}Z_{0}E_{1}$
>总哈密顿量：$\langle H\rangle=\left( 2Z_{0}^2-\frac{5}{4}Z_{0} \right)E_{1}$
>接下来考虑屏蔽效应的修正，我们只需要将之前讨论的He情形中的$(Z-2)$代换为$(Z-Z_{0})$：
>$$\begin{align}
&\langle H\rangle=\left[ 2Z^2-4Z(Z-Z_{0})-\frac{5}{4}Z \right]E_{1}=\left[ -2Z^2+4ZZ_{0}-\frac{5}{4}Z \right]E_{1} \\
&  \frac{\partial\left\langle H \right\rangle}{\partial Z}=\left[ -4Z+4Z_{0}-\frac{5}{4} \right]E_{1}=0\Rightarrow \boxed{Z=Z_{0}-\frac{5}{16}} \\
&\langle H\rangle_{min}=\frac{(16Z_{0}-5)^2}{128}E_{1}
\end{align}$$

<font color=orange>以上分析都是针对于两电子体系，对于有更多电子的系统不再适用！！！</font>

## 氢气离子$H_{2}^+$
我们假设氢气分子中的两个中子位置保持不变，分别用$r,r'$表示电子到两个质子的距离：
$$H=-\frac{\hbar^2}{2m}\nabla^2-\frac{e^2}{4\pi\epsilon_{0}}\left( \frac{1}{r}+\frac{1}{r'} \right)\tag{20}$$
现在开始猜测trial波函数，我们首先给出单个氢原子时基态波函数表达式：
$$\psi_{0}(r)=\frac{1}{\sqrt{ \pi a^3 }}e^{-r/a}$$
氢原子核$H^+_{2}$的区别在于，我们从无限远处带来了一个质子并放在$R$处，如果$R\gg a$，那么带来第二个质子对于电子原本轨道波函数的影响可以忽略。由于两个质子完全相同，我们可以等价的交换两个质子，所以总的波函数应该写作两者轨道的线性叠加，也就是LCAO：
$$\psi=A[\psi_{0}(r)+\psi_{0}(r')]\tag{21}$$
可以参考固体[[Tight-Binding Theory]]。
首先我们要归一化波函数：
$$\begin{align}
1=&\int |\psi|^2d^3r=|A|^2\left[ \int \psi_{0}(r)^2d^3r+\int \psi_{0}(r')^2d^3r +2\int \psi_{0}(r)\psi_{0}(r') d^3r    \right] \tag{22}
\end{align}$$
前两项为1，我们只需要考虑第三项，定义
$$I\equiv \bra{\psi_{0}(r)}\ket{\psi_{0}(r')}=\frac{1}{\pi a^3}\int e^{-(r+r')/a}d^3r\tag{23}   $$
取第一个质子位置为原点，第二个质子方向为z轴方向，我们写出
$$r'=\sqrt{ r^2+R^2-2rR\cos\theta },\tag{24}$$
因此积分写作
$$I=\frac{1}{\pi a^3}\int e^{-r/a}e^{-\sqrt{ r^2+R^2-2rR\cos\theta }/a}r^2\sin\theta  \, dr d\theta d\phi $$
定义$y\equiv \sqrt{ r^2+R^2-2rR\cos\theta }$，所以$d(y^2)=2ydy=2rR\sin\theta d\theta$，所以
$$\begin{align}
&\int_{0}^\pi e^{-\sqrt{ r^2+R^2-2rR\cos\theta }}\sin\theta \, d\theta=\frac{1}{rR}\int_{|r-R|}^{r+R}e^{-y/a}y  \, dy \\
&=-\frac{a}{rR}[e^{-(r+R)/a}(r+R+a)-e^{-|r-R|/a}(|r-R|+a)]  
\end{align}$$
之后在进行对于$r$的积分可以得到
$$I=e^{-R/a}\left[ 1+\left( \frac{R}{a} \right)+\frac{1}{3} \left( \frac{R}{a} \right)^2 \right]$$
我们称$I$为overlap integral，它表示了两个轨道的重叠程度，所以之前的归一化系数为
$$|A|^2=\frac{1}{2(1+I)}\tag{25}$$
现在可以开始计算能量的期望值
$$\begin{align}
H\psi&=A\left[ -\frac{\hbar^2}{2m}\nabla ^2-e^2.4\pi\epsilon_{0}\left( \frac{1}{r}+\frac{1}{r'} \right) \right][\psi_{0}(r)+\psi_{0}(r')] \\
&=E-1\psi-A\left( \frac{e^2}{4\pi\epsilon_{0}} \right)\left[ \frac{1}{r'}\psi_{0}(r)+\frac{1}{r}\psi_{0}(r') \right]
\end{align}$$
$$\langle H\rangle=E_{1}-2|A|^2\left( \frac{e^2}{4\pi\epsilon_{0}} \right)\left[ \left\langle  \psi_{0}(r)| \frac{1}{r'} |\psi_{0}(r) \right\rangle+\left\langle  \psi_{0}(r')| \frac{1}{r} |\psi_{0}(r') \right\rangle  \right]\tag{26}$$
我们称下式为直积：
$$D\equiv a\left\langle  \psi_{0}(r)| \frac{1}{r'} |\psi_{0}(r) \right\rangle$$
下式为交换积：
$$X\equiv\left\langle  \psi_{0}(r')| \frac{1}{r} |\psi_{0}(r') \right\rangle$$
其结果为
$$\begin{cases}
&D=\frac{a}{R}-\left( 1+\frac{a}{R} \right)e^{-2R/a}\tag{27} \\
&X=\left( 1+\frac{R}{a} \right)e^{-R/a}
\end{cases}$$
所以我们得到
$$\langle H\rangle=\left[ 1+2 \frac{(D+X)}{1+I} \right]E_{1}\tag{28}$$