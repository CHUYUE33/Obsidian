#SolidStates 
## 声速
对于一个固体我们可以对其进行压缩，并且有经验公式胡克定律：
$$-\kappa(\delta x_{eq})=F$$
为了描述一个材料的可压缩性，我们定义
$$\beta=- \frac{1}{V} \frac{\partial V}{\partial P}$$
所以有
$$\beta=- \frac{1}{L} \frac{\partial L}{\partial F}=\frac{1}{\kappa x_{eq}}=\frac{1}{\kappa a}$$
对于各向同性的可压缩流体，我们可以写出速度表达式为
$$v=\sqrt{ \frac{B}{\rho} }=\sqrt{ \frac{1}{\rho \beta} }=\sqrt{ \frac{\kappa a^2}{m} }$$
## Thermal Expansion
对于一维原子链系统，对于两个相邻原子的势场我们可以作出如下图像
![[ThermalExpansion.png|400]]
很明显我们可以看到有一个能量最低的稳定平衡位置，我们可以在这个位置进行泰勒展开
$$V(x)\approx V(x_{eq})+\frac{\kappa}{2}(x-x_{eq})^2-\frac{\kappa_{3}}{3!}(x-x_{eq})^3+\cdots$$
$x_{eq}$位置只能描述无外界能量扰动时的间距分布，即$T=0$时。当温度不为0时，相邻原子间距将在$x_{min},x_{max}$之间震荡。并且由图像我们可以看出，$|x_{max}-x_{eq}|>|x_{min}-x_{eq}|$，所以此时的平均位置$\langle x\rangle>x_{eq}$。这也就是热膨胀的最根本原因。接下来从经典和量子两种模型来计算热膨胀。

### Classical Model of Thermal Expansion
首先我们可以写出位置的期望
$$\langle x\rangle_{\beta}=\frac{\int dx xe^{-\beta V(x)}}{\int dx e^{-\beta V(x)}} $$
其中的玻尔兹曼分布项泰勒展开为
$$e^{-\beta V(x)}=e^{- \beta\kappa(x-x_{0})^2/2}\left[ 1+\frac{\beta\kappa_{3}}{6}(x-x_{0})^3+\cdots\right]$$
（这里相当于取$V(x_{eq})$为势能零点，再提出二次项为公因式，最后关于三阶项小量展开）
重新定义$y=(x-x_{0})$那么有
$$\begin{align}
\langle x\rangle_{\beta}&=\frac{\int dy (y+x_{0})e^{-\frac{\beta\kappa_{3}}{2}y^2 }\left[ 1+\frac{\beta \kappa_{3}}{6}y^3+\cdots \right]}{\int dy e^{-\frac{\beta\kappa_{3}}{2}y^2 }\left[ 1+\frac{\beta \kappa_{3}}{6}y^3+\cdots \right]} \\
&=x_{0}+\frac{\frac{\beta\kappa_{3}}{6}\int dy \ y^4e^{-\frac{\beta\kappa}{2}y^2}}{\int dy e^{-\frac{\beta\kappa}{2}y^2} }+\cdots 
\end{align}$$
使用
$$\int dxe^{-ax^2}=\sqrt{ \frac{\pi}{a} } $$
分子部分可以得到
$$\int dxe^4e^{-ax^2}=(d/da)^2\int dxe^{-ax^2}=(d/da)^2\sqrt{ \pi/a }=(3/4)\sqrt{ \pi/a^5 }  $$
最后可得
$$\langle x\rangle_{T}=x_{0}+\frac{\kappa_{3}(k_{b}T)}{2\kappa^2}+\cdots$$
$$\frac{1}{x_{0}}  \frac{d\langle x \rangle_{T}}{dT}=\frac{1}{x_{0}} \frac{\kappa_{3}k_{b}}{2\kappa^2}$$
这里我们将三次项及以上当作微扰处理，这是个合理的处理方法的前提是三次项相比二次项较小。
所以，如果势能中二次项是主要作用项，那么有$\kappa(x-x_{0})^2\sim k_{b}T$，所以$|x-x_{0}|\sim \sqrt{ k_{b}T/\kappa }$，为了确保二次项大于三次项，
$$\kappa|x-x_{0}|^2\gg\kappa_{3}|x-x_{0}|^3$$
$$\Rightarrow k_{b}T\gg\kappa_{3}(k_{b}T/\kappa)\quad or \quad k_{b}T\ll\kappa^3/\kappa^2_{3}$$

### Quantum mode of thermal expansion
在量子力学中我们将哈密顿量写作
$$H=H_{0}+\delta V\tag{1}$$
其中$H_{0}=\frac{p^2}{2m}+\frac{\kappa}{2}(x-x_{0})^2$，$\delta V$是势能带来的微扰项:
$$\delta V=-\frac{\kappa_{3}}{6}(x-x_{0})^3+\cdots$$
这里我们丢掉了二次项以及更高阶项。
对于方程中的m，我们应该使用约化质量$\mu=\frac{m_{1}m_{2}}{m_{1}+m_{2}}$。
接下来我们使用微扰理论对来求解具体的态，相较于谐振子最低阶扰动为$\kappa_{3}$，可以写出
>[!note] 量子涨落中的位置期望
>$$\bra{n}x\ket{n}=x_{0}+E_{n}\kappa_{3}/(2\kappa^2)  \tag{2}$$
其中$\ket{n}$式能量为下式的谐振子的本征态
$$E_{n}=\hbar w\left( n+\frac{1}{2} \right)+O(\kappa_{3})\quad n\ge 0$$

接下来我们使用升降算符证明这个式子。
写出无微扰的谐振子的升降算符
$$\hat{a}=\sqrt{ \frac{mw}{2\hbar} }[(x-x_{0})+(i/mw)p]$$
$$\hat{a}^{\dagger}=\sqrt{ \frac{mw}{2\hbar} }[(x-x_{0})-(i/mw)p]\tag{3}$$
这里是$x-x_{0}$的原因是哈密顿量中为偏离平衡位置的距离。
所以位置可以表示为
$$x-x_{0}=\sqrt{ \hbar/(2mw) }(\hat{a}+\hat{a}^{\dagger})$$
接下来我们用$\ket{n^{(0)}}$表示无微扰时谐振子本征态，对应本征能量为$E_{n}^{(0)}=\hbar w(n+1/2)$，扰动两表示为
$$\delta V=\lambda H'=-\frac{\kappa_{3}}{6}\left( \frac{\hbar}{2mw} \right)^{3/2}(\hat{a}+\hat{a}^{\dagger})^3$$
将$\ket{n}$展开到最低阶扰动
$$\ket{n}=\ket{n^{(0)}}-\frac{\kappa_{3}}{6}\left( \frac{\hbar}{2mw} \right)^{3/2}\sum_{m\neq n}\ket{m^{(0)}} \frac{\bra{m^{(0)}}(\hat{a}+\hat{a}^{\dagger})\ket{n^{(0)}}}{E_{n}^{(0)}-E_{m}^{(0)}}     $$
所以我们可以计算出
$$\bra{n}x-x_{0}\ket{n}=-\frac{2\kappa_{3}}{6}\left( \frac{\hbar}{2mw} \right)^{2}\sum_{m\neq n} \frac{\bra{n^{(0)}}(\hat{a}+\hat{a}^{\dagger})\ket{m^{(0)}}\bra{m^{(0)}}(\hat{a}+\hat{a}^{\dagger})^3\ket{n^{(0)}}}{E_{n}^{(0)}-E_{m}^{(0)}}       $$
对于求和，只有两项不为0：
$n=m+1$时，分母为$\hbar w$，分子为：
$$\begin{align}
&\bra{n^{(0)}}\hat{a}^{\dagger}\ket{n-1^{(0)}}\bra{n-1^{(0)}}\hat{a}^{\dagger}\hat{a}\hat{a}+\hat{a}\hat{a}^{\dagger}\hat{a}+\hat{a}\hat{a}\hat{a}^{\dagger}\ket{n^{(0)}} \\
=&\sqrt{ n }(\sqrt{ n }(n-1)+n\sqrt{ n }+(n+1)\sqrt{ n })=3n^2 
\end{align}$$
$n=m-1$时，分母为$-\hbar w$，分子为：
$$\begin{align}
&\bra{n^{(0)}}\hat{a}\ket{n+1^{(0)}}\bra{n+1^{(0)}}\hat{a}^{\dagger}\hat{a}^{\dagger}\hat{a}+\hat{a}^{\dagger}\hat{a}\hat{a}^{\dagger}+\hat{a}\hat{a}^{\dagger}\hat{a}^{\dagger}\ket{n^{(0)}} \\
=&\sqrt{ n+1 }(n\sqrt{ n+1 }+(n+1)\sqrt{ n+1 }+(n+2)\sqrt{ n+1 })=3(n+1)^2    
\end{align}$$
所以我们可以得到（$w=\sqrt{ \kappa/m }$）
$$\bra{n}x-x_{0}\ket{n}=\frac{2\kappa_{3}}{6}\left( \frac{\hbar}{2mw} \right)^2 \frac{1}{\hbar w}(6n+3)=\frac{E_{n}\kappa_{3}}{2\kappa^2}  $$

我们可以看到，即使在基态，位置的期望值与$x_{0}$也有一定的偏差，这是因为谐振子并不完全处于最小值，而是在最小值附近存在“量子涨落（quantum fluctuations）”。由于在势阱最小值附近是不对称的（微扰的影响），所以位置的期望值比$x_{0}$略高。
接下来可以计算在任意温度下位置的期望值
>[!note] 考虑Blotzmann 分布的影响后的位置期望
>$$\langle x\rangle_{\beta}=\frac{\sum_{n}\bra{n}\hat{x}\ket{n}e^{-\beta E_{n}}}{\sum_{n}e^{-\beta E_{n}}}  \tag{3}$$
>我们可以看到思路就是先计算不同能级量子态下位置，再考虑不同温度导致的每个能级分布占比。

计算热膨胀系数：
$$\begin{align}
\langle x\rangle_{\beta}&=\frac{\sum_{n}\bra{n}\hat{x}\ket{n}e^{-\beta E_{n}}}{\sum_{n}e^{-\beta E_{n}}}=\frac{\sum_{n}\bra{n}(x_{0}+E_{n}\kappa_{3}/(2\kappa^2))\ket{n}e^{-\beta E_{n}}}{\sum_{n}e^{-\beta E_{n}}} \\
&=x_{0}+ \frac{\langle E \rangle_{\beta}\kappa_{3}}{2\kappa^2}
\end{align}$$
其中$\langle E\rangle_{\beta}$是在温度$\beta=1/(k_{B}T)$频率$w=\sqrt{ \kappa/m }$的谐振子能量期望值，这个能量值我们曾在计算Einstein model的时候得到过[[Specific Heat of Solid(Boltzmann,Einstein,Debye)]]：
$$\langle E\rangle_{\beta}=\left( n_{B}(\beta \hbar w)+\frac{1}{2} \right)\hbar w= \frac{\hbar w}{2}\coth(\beta \hbar w/2)\tag{4}$$
这里$n_{B}$表示Boson占据因子，所以
$$\langle x\rangle_{\beta}=x_{0}+(\kappa_{3}\hbar w/(4\kappa^2))\coth(\beta \hbar w/2)\tag{5}$$
热膨胀系数写为
$$\alpha=\frac{1}{x_{0}} \frac{d\langle E\rangle_{\beta}}{dT}=\frac{\kappa_{3}}{2x_{0}\kappa^2} \frac{d\langle E\rangle}{dT}\tag{6}$$
我们也在Einstein model中计算过热容$C=d\langle E\rangle/dT\tag{6}$，所以我们可以得到
>[!note] 量子模型 热膨胀系数
>$$\alpha=\frac{\kappa_{3}C}{2x_{0}\kappa^2}=\frac{\kappa_{3}}{2x_{0}\kappa^2}k_{b}(\beta \hbar w)^2 \frac{e^{\beta \hbar w}}{(e^{\beta \hbar w}-1)^2}\tag{7}$$
>我们可以看到热膨胀系数类似于热容，在温度较低时“freeze”，在温度较高时热容$C$趋近于$k_{b}$，所以高温极限下
>$$\alpha=(\kappa_{3}k_{b}/(2x_{0}\kappa^2)),\quad k_{b}T\gg \hbar w$$


我们这里主要考虑了三阶势能修正带来的热膨胀效应，但是对于二阶的势能系统（标准谐振子），就不存在热膨胀的效应（可以想象，势能分布是对称的，量子涨落不会导致不同温度偏离平衡位置），所以对于之后研究的一维原子链模型，就不存在热膨胀。