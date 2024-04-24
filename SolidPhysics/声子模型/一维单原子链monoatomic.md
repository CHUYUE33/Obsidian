#SolidStates 
## 一维单原子链
我们假设原子之间的间距为$a$，我们定义第n个原子的位置为$x_{n}$，并且平衡时有关系$x_{n}^{eq}=na$。并且我们定义偏移平衡位置的位移$$\delta x_{n}=x_{n}-x_{n}^{eq}$$
每个原子之间的相互作用可以视作由相同劲度系数$\kappa$的弹簧链接起来，总的能量写作
$$V_{tot}=\sum_{i}V(x_{i+1}-x_{i})=\sum_{i}  \frac{\kappa}{2}(x_{i+1}-x_{i}-a)^2=\sum_{i}  \frac{\kappa}{2}(\delta x_{i+1}-\delta x_{i})^2$$
在第n个粒子上的受力为
$$F_{n}=-\frac{\partial V_{tot}}{\partial x_{n}}=\kappa(\delta x_{n+1}-\delta x_{n})+\kappa(\delta x_{n-1}-\delta x_{n})$$
由于牛顿运动方程
$$m(\ddot{\delta x_{n}})=\kappa(\delta x_{n+1}+\delta x_{n-1}-2\delta x_{n})$$
简正模（normal mode）指全体粒子以相同的频率运动，为了解这个方程，我们可以假设normal mode有以下形式的解
$$\delta x_{n}=Ae^{iwt-ikx_{n}^{eq}}=Ae^{iwt-ikna}$$
（这是假设全部粒子以k，w的模式进行行波振动，带回方程会给出系统约束下的色散关系。）
上述表达式中虽然写作复数形式，但是我们实际$\delta x_{n}$只取实数部分。将上述假设带回方程
$$-mw^2Ae^{iwt-ikna}=\kappa Ae^{iwt}\Big[e^{-ika(n+1)}+e^{-ika(n-1)}-2e^{ikan}\Big]$$
$$\Rightarrow mw^2=2\kappa[1-\cos{(ka)}]=4\kappa \sin^2(ka/2)$$
最终我们可以得到色散关系
$$w=2\sqrt{ \frac{\kappa}{m} }|\sin\left( \frac{ka}{2} \right)|$$
![[monoatomic_w.png|400]]

### 关系探讨
首先我们不加证明的给出以下原理
>[!note] Principle
>一个在实空间中以a为周期的系统，将在reciprocal space（就是k空间，也叫倒易空间）以$2\pi/a$为周期。

我们可以发现，色散关系是关于$-\pi/a\le k\le\pi/a$成周期的，我们将这个区域称为“第一布里渊区（Brillouin zone）”。
我们很容易证明，色散曲线是以$2\pi/a$为周期的，带入之前假设的表达式即可。所以在k空间中，我们可以定义一系列点等价于$k=0$，这个点集我们称之为“reciprocal lattice”。原本的周期性点集$x_{n}=na$被称作“direct lattice”，是实空间上的点集。
我们写出对应关系：
$$x_{n}\quad=\quad \cdots\quad-2a,\quad-a,\quad {0},\quad a,\quad2a,\quad \cdots$$
$$G_{n}\quad=\quad \cdots\quad-2  \left( \frac{2\pi}{a} \right),\quad-\left( \frac{2\pi}{a} \right),\quad 0,\quad \left( \frac{2\pi}{a} \right),\quad2\left( \frac{2\pi}{a} \right),\quad \cdots$$

由于在k空间中的周期性所以去找实际对应的k值是没有意义的，相差$\frac{2\pi}{a}\cdot m$的波矢都表示相同的振动模式。

对于声波，通常波长都较长，在这个尺度下我们的色散关系可以表示为线性的：$w=v_{sound}k$，则声速写为
$$v_{sound}=a\sqrt{ \frac{\kappa}{m} }$$
但是对于固体中的尺度，色散关系不再是线性，我们可以定义两种速度：
群速度，波包移动的速度，
$$v_{group}=dw/dk$$
相速度，单个极大值到极小值的速度，
$$v_{phase}=\frac{w}{k}$$

### Normal Modes数量限制
理论上说，我们应该可以取任意的位于$-\pi/a\sim \pi/a$之间的k值，但这并不正确。
我们假设系统这一行有$N$个原子，并假设系统有边界周期性（这也正是不允许任意k值的原因），即$x_{0}$左侧为$x_{N-1}$，右侧为$x_{1}$，周期关系记作$x_{n+N}=x_{n}$，这个一维链模型会形成一个环形结构。Therefore，
$$e^{iwt-ikna}=e^{iwt-ik(N+n)a}\Rightarrow e^{ikNa}=1$$
这限制了k的可能取值：
$$k=\frac{2\pi p}{Na}=\frac{2\pi p}{L}$$
这里$p$是任意整数。在整个布里渊区中，允许的modes个数刚好为N。这是因为一个原子贡献一个自由度。

## Quantum Modes: Phonons
我们这里先给出一个结论：
>[!note] Quantum Correspondence
>如果一个经典的谐振系统（任意二次的哈密顿量系统）有频率为$w$的Normal Oscillation，那么相对应的量子系统将会有如下的本征能量
>$$E_{n}=\hbar w\left( n+\frac{1}{2} \right)\tag{1}$$

很明显这个表达式对于单个谐振子成立，但是在这里我们是collective normal mode并不只是单个粒子的运动，我们在之后将对此进行证明。
对于给定的波矢$k$，存在许多可能的本征态，基态处于$n=0$，只有能量$\hbar w(k)/2$，之后的激发态依次加上能量$\hbar w(k)$。于是我们可以定义“声子（Phonon）”：
>[!note] Phonon
>声子表示振动的离散量子。（A phonon is a discrete of vibration）

我们可以将声子看作一个实际的粒子或者量子化的波。如果我们将声子看作一个粒子（类似于光子的粒子），那么我们可以将许多声子放在相同的态，那么声子就是Bosons，我们可以用Boson的占据海曙来描述其分布
$$n_{B}(\beta \hbar w)=\frac{1}{e^{\beta \hbar w}-1}$$
这也说明了波矢为$k$的normal mode在竞争中所占的比例。
那么波矢为$k$的声子的能量期望值为
$$E_{k}=\hbar w(k)\left( n_{B}(\beta \hbar w(k))+\frac{1}{2} \right)$$
我们的一维模型的能量表达式为
$$U_{total}=\sum_{k}\hbar w(k)\left( n_{B}(\beta \hbar w(k))+\frac{1}{2} \right)$$
>补充：这里我们可以直接使用$C_{V}=dU/dT$恒容热容来计算热容，这是因为在之前[[声速，热膨胀Thermal expansion]]我们说过对于晶体只有势能有高于三阶项时才会导致膨胀，所以可以把体积当作恒定的。

上式遍历所有可能normal mode求和，我们取布里渊区$-\pi/a\le k\le\pi/a$：
$$\sum_{k}\rightarrow \sum_{p=-N/2,k=(2\pi p)/(Na)}^{p=(N/2)-1}$$
对于粒子数较大的系统$k$之间非常接近所以我们可以将其转化为积分
$$\sum_{k}\rightarrow \frac{Na}{2\pi}\int_{-\pi/a}^{\pi/a}dk $$
我们可以用这个连续积分来计算系统允许的总模式数
$$\frac{Na}{2\pi}\int_{-\pi/a}^{\pi/a}dk=N $$
可以发现我们计算的思路和Debye model是一模一样的（仅对于一维模型），只是修正了色散关系表达式。总能量现在写作
$$U_{total}=\frac{Na}{2\pi}\int_{-\pi/a}^{\pi/a}dk \ \hbar w(k)\left( n_{B}(\beta \hbar w(k))+\frac{1}{2} \right) \tag{2}$$

同样的我们可以思考EInstein mode，在计算中我们将w当作固定的数值，无论k如何变化，所以Debye，Einstein，1D chain的区别仅仅在于色散关系的不同。

我们接下来需要做的就是将对于k空间的积分变换到频率空间：
$$\frac{Na}{2\pi}\int_{-\pi/a}^{\pi/a}dk=\int dw \ g(w) $$
态密度可表示为
$$g(w)=2 \frac{Na}{2\pi}|dk/dw|\tag{3}$$
其中$g(w)dw$表示$w\sim w+dw$区间内的态数。



## Quantum mode Eneregy
之前我们提到了classical的normal mode的系统能量可以用量子本征能量$E_{n}$来描述，接下来我们将给出证明。
### Classical Normal Mode to quantum eigenstates
这是对于双原子分子处于势阱中的模型的证明。
考虑两个粒子，每个的质量均为$m$，处于一维链状结构，由劲度系数为$K$的弹簧连接，同时处于等效劲度系数$k$的势阱的底部（能量最低处），我们可以写出势能
$$U=\frac{k}{2}(x_{1}^2+x_{2}^2)+\frac{K}{2}(x_{1}-x_{2})^2\tag{4}$$
经典运动方程为
$$m\ddot{x_{1}}=-kx_{1}-K(x_{1}-x_{2})$$
$$m\ddot{x_{2}}=-kx_{2}-K(x_{2}-x_{1})\tag{5}$$
我们可以定义如下坐标变换关系
$$\begin{cases}
x_{rel}=x_{1}-x_{2} \\
x_{cm}=(x_{1}+x_{2})/2
\end{cases}\tag{6}$$
将变换关系带入运动方程中
$$m \ddot{x_{cm}}=-kx_{cm}$$
$$m \ddot{x_{rel}}=-(k+2K)x_{rel}$$
所以我们可以定义两种频率如下的谐振子简正模：
>[!note] 两粒子谐振子系统简正模
>$$\begin{cases}
w_{cm}=\sqrt{ k/m } \\
w_{rel}=\sqrt{ (k+2K)/m }=\sqrt{ (k/2+K)/(m/2) }
\end{cases}\tag{7}$$

因为一开始我们有两个粒子的自由度，所以有两个normal modes。现在用量子力学的方法来描述问题，写出哈密顿量
$$H=\frac{p_{1}^2}{2m}+\frac{p_{2}^2}{2m}+U(x_{1},x_{2})\tag{8}$$
我们想要将其变换到相对坐标和质心坐标来表示，我们先定义两个动量变换
$$\begin{cases}
p_{rel}=(p_{1}-p_{2})/2 \\
p_{cm}=p_{1}+p_{2}
\end{cases}\tag{9}$$
我们证明新定义的动量和坐标算符满足对易关系
>[!note] 相对坐标、动量对易关系
>$$[p_{\alpha},x_{\gamma}]=-i\hbar \delta_{\alpha,\gamma}$$
>这里$\alpha,\gamma$取值$cm,rel$。

带入（6），（9）直接算就行：
$$\begin{align}
[p_{rel},x_{rel}]&=\frac{1}{2}([p_{1},x_{1}]-[p_{1},x_{2}]-[p_{2},x_{1}]+[p_{2},x_{2}]) \\
&=\frac{1}{2}(-i\hbar)(1-0-0+1)=-i\hbar \\
[p_{rel},x_{cm}]&=\frac{1}{4}([p_{1},x_{1}]+[p_{1},x_{2}]-[p_{2},x_{1}]-[p_{2},x_{2}]) \\
&=\frac{1}{4}(-i\hbar)(1+0-0-1)=0 \\
[p_{cm},x_{rel}]&=([p_{1},x_{1}]-[p_{1},x_{2}]+[p_{2},x_{1}]-[p_{2},x_{2}]) \\
&=(-i\hbar)(1-0+0-1)=0 \\
[p_{cm},x_{cm}]&=\frac{1}{2}([p_{1},x_{1}]+[p_{1},x_{2}]+[p_{2},x_{1}]+[p_{2},x_{2}]) \\
&=\frac{1}{2}(-i\hbar)(1+0+0+1)=-i\hbar
\end{align}$$
与此同时还有关系式$p_{rel}=-i\hbar \partial/\partial x_{rel}$。

在新的坐标下，我们可以证明，哈密顿量解耦合成为了$w_{cm},w_{rel}$的相互独立谐振子的组合。
>[!note] 相对坐标下的能级表达式
>$$E_{n_{rel},n_{cm}}=\hbar w_{rel}\left( n_{rel}+\frac{1}{2} \right)+\hbar w_{cm}\left( n_{cm}+\frac{1}{2} \right)\tag{10}$$
>这个式子说明，对于两个自由度有所耦合的系统本质上就类似于自由度被重新对角化后的单一的谐振子，所以应该把声子（弹簧耦合后的模式）看作相互独立的谐振子。

证明：我们可以直接将哈密顿量重写为
$$\begin{align}
H&=\frac{1}{2m}(p_{1}^2+p_{2}^2)+\frac{k}{2}(x_{1}^2+x_{2}^2)+\frac{K}{2}(x_{1}-x_{2})^2 \\
&=\frac{1}{2m}(p_{cm}^2/2+2p_{rel}^2)+\frac{k}{2}(2x_{cm}^2+x_{rel}^2/2)+\frac{K}{2}x_{rel}^2
\end{align}$$
很明显之前$x_{1},x_{2}$耦合的表达式被解耦合为两个独立模式
$$\begin{cases}
H_{1}=\frac{p_{cm}^2}{2(2m)}+\frac{2k}{2}x_{cm}^2 \\
H_{2}=\frac{p_{rel}^2}{2(m/2)}+\frac{k/2+K}{2}x_{rel}^2
\end{cases}$$
很明显这就是(7)中两个简正模式对应的谐振子组合，所以总能量谱可以写作
$$E_{n_{rel},n_{cm}}=\hbar w_{rel}\left( n_{rel}+\frac{1}{2} \right)+\hbar w_{cm}\left( n_{cm}+\frac{1}{2} \right)$$
在温度为$T$是，系统能量的期望写作
$$\langle E\rangle=\hbar w_{rel}(n_{B}(\beta \hbar w_{rel})+1/2)+\hbar w_{cm}(n_{B}(\beta \hbar w_{cm})+1/2)$$


### General Proof 
现在考虑类似于之前讨论的双原子模型，但是将粒子数量推广到N：$a=1,2,\cdots,N$，每个原子质量为$m_{a}$，相互作用势能写作
>[!note] 多例子模型相互作用势能
>$$U=\frac{1}{2}\sum_{a,b}x_{a}V_{a,b}x_{b}\tag{11}$$
>这里$x_{a}$是a粒子偏离平衡位置的距离，且不失一般性的我们可以假设$V_{a,b}=V_{b,a}$，也就是说V是对称的。

我们定义$y_{a}=\sqrt{ m_{a} }x_{a}$，那么运动方程可以写作
>[!note] 运动方程以及对应解
>$$\ddot{y_{a}}=-\sum_{b}S_{a,b}y_{b},\quad \text{where}  \ S_{a,b}=\frac{1}{\sqrt{ m_{a} }}V_{a,b} \frac{1}{\sqrt{ m_{b} }}\tag{12}$$
>解为
>$$y_{a}^{(m)}=e^{-iw_{m}t}S_{a}^{(m)}\tag{13}$$
>其中$-w_{m}^2$是矩阵$S$的第m个特征值，对应的特征向量为$S_{a}^{(m)}$。可以看出应该有$N$个简正模式。
>（这里可以联系常微分方程求解多元微分方程的方法，写成矩阵形式然后再将矩阵化为e指数求解）

证明：
我们写出运动方程
$$F_{a}=- \frac{\partial U}{\partial x_{a}}=-\sum_{b}V_{a,b}x_{b}$$
$$\Rightarrow m_{a}\ddot{x_{a}}=-\sum_{b}V_{a,b}x_{b}$$
在带入之前定义的$x_{a}=y_{a}/\sqrt{ m_{a} }$：
$$\ddot{y_{a}}=-\sum_{b}\frac{1}{\sqrt{ m_{a} }}V_{{a,b}} \frac{1}{\sqrt{ m_{b} }}y_{b}=-\sum_{b}S_{a,b}y_{b}$$
带入假设解$y_{a}=e^{-iwt}s_{a}$
$$w^2s_{a}=\sum_{b}S_{a,b}s_{b}\tag{14}$$
---

由于厄密矩阵的特征向量间存在正交关系，我们可以写出
$$\sum_{a}[s_{a}^{(m)}]^*[s_{a}^{(n)}]=\delta_{m,n}\tag{15}$$
$$\sum_{m}[s_{a}^{(m)}]^*[s_{b}^{(m)}]=\delta_{a,b}\tag{16}$$
$s_{a}^{(m)},s_{b}^{(m)}$表示在第m个本征值的本征空间中的两个可能相同，可能不同的向量。
因为S是一个厄密矩阵，所以本征向量可以被取为实值，构建如下坐标变换
$$Y^{(m)}=\sum_{a}s_{a}^{(m)}x_{a}\sqrt{ m_{a} }\tag{17}$$
$$P^{(m)}=\sum_{a}s_{a}^{(m)}p_{a}/\sqrt{ m_{a} }\tag{18}$$
我们可以得到如下的正则对易关系和哈密顿量表达式
>[!note] 正则对易关系&哈密顿量
>$$[P^{(m)},Y^{(m)}]=-i\hbar \delta_{n,m}\tag{19}$$
>$$H=\sum_{m}\left[ \frac{1}{2}[p^{(m)}]^2+\frac{1}{2}w_{m}^2[Y^{(m)}]^2 \right]\tag{19}$$

证明：
我们先展开表达式
$$[P^{(n)},Y^{(m)}]=\sum_{a,b}s_{b}^{(n)}s_{a}^{(m)}[p_{b},x_{a}]\sqrt{ m_{a}/m_{b} }$$
使用正则对易关系
$$[p_{b},x_{a}]=-i\hbar \delta_{ab}$$
所以
$$[P^{(n)},Y^{(m)}]=-i\hbar\sum_{a}s_{a}^{(m)}s_{a}^{(n)}=-i\hbar \delta_{nm}$$
加下来考量哈密顿量的组成，分别验算两项
$$\begin{align}
\sum_{m} \frac{1}{2}[p^{(m)}]^2&=\sum_{m}\sum_{a,b} \frac{1}{2}s_{a}^{(m)}s_{b}^{(m)}p_{a}p_{b}/\sqrt{ m_{a}m_{b} } \\
&=\sum_{a} \frac{1}{2m_{a}}p_{a}^2
\end{align}$$
结果由带入正交关系得到。
$$\begin{align}
\sum_{m} \frac{1}{2}w_{m}^2[Y^{(m)}]^2 &=\sum_{m}\sum_{a,b} \frac{1}{2}s^{(m)}_{a}w_{m}^2s_{b}^{(m)}x_{a}x_{b}\sqrt{ m_{a}m_{b} }\\
&=\sum_{m}\sum_{a,b,c} \frac{1}{2} s_{a}^{(m)}S_{b,c}s_{c}^{(m)}x_{a}x_{b}\sqrt{ m_{a}m_{b} } \\
&=\sum_{a,b} \frac{1}{2}S_{a,b}x_{a}x_{b}\sqrt{ m_{a}m_{b} }=\sum_{a,b} \frac{1}{2}x_{a}V_{a,b}x_{b}
\end{align}$$
第一行到第二行运用了(14)式，再接下来带入正交关系即可。
显然地两项组合在一起就是我们熟知的哈密顿量。
整个过程就是将原本非对角化的矩阵$V$逐步对角化，并找到对应的本征向量的过程，这些本征向量本征值就是简正模式。
对于每一个简正模式我们都可以写出这个独立谐振子的升降算符
$$\hat{a}^{\dagger}=\frac{1}{\sqrt{ 2\hbar }}(P/\sqrt{ w }+i\sqrt{ w }Y)$$
独立的哈密顿量写作
$$H=\hbar w(\hat{a}^{\dagger}\hat{a}+1/2)$$