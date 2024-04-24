#SolidStates 

## 双原子模型定义
这里我们定义的双原子拥有相同的质量$m$，但是相互连接的劲度系数分别为$\kappa_{1},\kappa_{2}$。
（其实这里设两个原子有不同质量对结果的影响并不大）
我们可以发现，最小重复单元是以两个原子为单位，我们规定最小重复单元的长度为$a$，这也是晶体参数（crystal parameter）的大小。
对于第n个晶体元，我们记一号原子的平衡位置为$x_{n}$，二号原子的平衡位置为$y_{n}$。
![[diatomic.png]]

## 简正模式计算
我们可以写出运动方程
$$m \ddot{\delta x_{n}}=\kappa_{2}(\delta y_{n}-\delta x_{n})+\kappa_{1}(\delta y_{n-1}-\delta x_{n})\tag{1}$$
$$m \ddot{\delta y_{n}}=\kappa_{1}(\delta x_{n+1}-\delta y_{n})+\kappa_{2}(\delta x_{n}-\delta y_{n})\tag{2}$$
类比于之前单原子链模型，我们可以做出简正模式解的推测
$$\delta x_{n}=A_{x}e^{iwt-ikna}\tag{3}$$
$$\delta y_{n}=A_{y}e^{iwt-ikna}\tag{4}$$
我们将(3)(4)带回(1)(2)可以解得
$$\begin{align}
-w^2mA_{x}e^{iwt-ikna}&=\kappa_{2}A_{y}e^{iwt-ikna}+\kappa_{1}A_{y}e^{iwt-ik(n-1)a}-(\kappa_{1}+\kappa_{2})A_{x}e^{iwt-ikna} \\
-w^2mA_{y}e^{iwt-ikna}&=\kappa_{1}A_{x}e^{iwt-ik(n+1)a}+\kappa_{2}A_{x}e^{iwt-ikna}-(\kappa_{1}+\kappa_{2})A_{y}e^{iwt-ikna}
\end{align}$$
进一步化简得
$$-w^2mA_{y}=\kappa_{2}A_{y}+\kappa_{1}A_{y}e^{ika}-(\kappa_{1}+\kappa_{2})A_{x}$$
$$-w^2mA_{y}=\kappa_{1}A_{x}e^{-ika}+\kappa_{2}A_{x}-(\kappa_{1}+\kappa_{2})A_{y}$$
写成矩阵形式
$$\begin{pmatrix}
\kappa_{1}+\kappa_{2}-mw^2&-\kappa_{2}-\kappa_{1}e^{ika} \\
-\kappa_{2}-\kappa_{1}e^{-ika}&\kappa_{1}+\kappa_{2}-mw^2
\end{pmatrix}\begin{pmatrix}
A_{x} \\
A_{y}
\end{pmatrix}=0\tag{5}$$
特征方程写作
$$|(\kappa_{1}+\kappa_{2})-mw^2|^2-|\kappa_{2}+\kappa_{1}e^{ika}|^2=0$$
$$\Rightarrow mw^2=(\kappa_{1}+\kappa_{2})\pm|\kappa_{1}+\kappa_{2}e^{ika}|$$
RHS第二项可以简化为
$$\begin{align}
|\kappa_{1}+\kappa_{2}e^{ika}|&=\sqrt{ (\kappa_{1}+\kappa_{2}e^{ikna})(\kappa_{1}+\kappa_{2}e^{-ika}) } \\
&=\sqrt{ \kappa_{1}^2+\kappa_{2}^2+2\kappa_{1}\kappa_{2}\cos(ka) }
\end{align}$$
最终我们解出色散关系
$$w_{\pm}=\sqrt{ \frac{\kappa_{1}+\kappa_{2}}{m}\pm \sqrt{ (\kappa_{1}+\kappa_{2})^2-4\kappa_{1}\kappa_{2}\sin^2(ka/2) } }\tag{6}$$
色散关系如下图所示
![[diatomic1.png|400]]
这里我们称呼长波长低能量的激发态为 声学模式（acoustic mode），因为在k较小时色散关系近乎为线性，并且很容易计算得到声速
$$v_{sound}=\frac{dw_{-}}{dk}=\sqrt{ \frac{a^2\kappa_{1}\kappa_{2}}{2m(\kappa_{1}+\kappa_{2})} }\tag{7}$$

正如之前我们提到的[[声速，热膨胀Thermal expansion]]的
$$v^{-2}=\rho \beta$$
对于双原子链，密度表示为$\rho=(m_{1}+m_{2})/2=m/2$，等效弹簧劲度系数为$\bar{\kappa}=\kappa_{1}\kappa_{2}/(\kappa_{1}+\kappa_{2})$（两弹簧串联），所以形变模量
$$\beta=-\frac{1}{L} \frac{dL}{dF}=-\frac{1}{a} \frac{1}{\bar{\kappa}}$$
带入可以得到（7）式所得声速。

对于图像上的另一分支，我们称其为“光学模式（optical mode）“，这与固体对光线的散射有关。
对固体射入一束光$w=ck$并使其被固体吸收，对于声学模式，$v\ll c$，声子能量和动量都远小于光子，所以无法做到能量、动量守恒。这是就需要光学模式，吸收光子产生频率为$w_{optical}=ck$的声子（本质上是对光子的散射，如果吸收了光子会导致自旋不守恒，声子无自旋）。