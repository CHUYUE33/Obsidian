#QuantumMechanics 

当一个原子放在均匀的外磁场$B_{ext}$中时，能级会发生移动，这种现象称为Zeeman Effect。对于单电子，扰动可以写作
$$H'_{z}=-(\mu_{l}+\mu_{s})\cdot B_{ext}\tag{1}$$
其中$$\mu_{s}=-\frac{e}{m}S\tag2$$
是由电子自旋产生的磁矩，而
$$\mu_{l}=-\frac{e}{2m}L\tag{3}$$
是由电子轨道运动产生的磁矩，所以
$$H_{z}'=\frac{e}{2m}(L+2S)\cdot B_{ext}\tag{4}$$
一般自然的塞曼效应依赖于外加磁场的大小，要出现明显劈裂需要外磁场大于质子绕电子产生的内磁场$B_{int}$：[[氢原子精细结构]]（16）。如果$B_{ext} \ll B_{int}$，那么精细结构的影响占据主导，此时$H_{z}'$可以被看作是微扰；但如果$B_{ext}\gg B_{int}$此时塞曼效应占据主导，此时精细结构作为微扰；在intermediate区域，两者的影响量级相同，我们需要仔细分析微扰原理的机理并手动对角化哈密顿矩阵。接下来我们逐一分析氢原子模型下的对应情况。

## Weak-Field Zeeman Effect
如果$B_{ext}\ll B_{int}$，精细结构占主导，我们可以将$H_{Bohr}+H'_{fs}$看作无微扰哈密顿量，并将$H_{z}'$看作微扰。此时的无扰本征态写作$\ket{nljm_{j}}$，本征能级写作$E_{nj}$（[[氢原子精细结构]]25）。虽然精细结构解除了一些原有的Bohr模型的简并态，但是这些态仍是简并的，因为能量并不依赖于$m_{j},l$但是比较好的是$\ket{nljm_{j}}$是微扰$H_{z}'$的good states因为$H_{z}'$与$J_{z},L^2$对易，并且每个简并态都独立的被$m_{j},l$标记。
对于一阶微扰原理，塞曼修正为
$$E_{z}^1=\bra{nljm_{j}}H_{z}'\ket{nljm_{j}}=\frac{e}{2m}B_{ext}\hat{k}\cdot\langle \vec{L}+2\vec{S} \rangle  \tag{5}$$
我们可以将$\vec{L}+2\vec{S}$写作$\vec{J}+\vec{S}$，但是自旋算符的期望并不能直接计算，但由于$\vec{J}=\vec{L}+\vec{S}$是守恒量，所以我们可以画出
![[ZeemanEffect.png|300]]
$\vec{L},\vec{S}$绕着固定的向量$\vec{J}$快速进度，所以，对于自旋算符的时间平均就是沿着$\vec{J}$的投影：
$$S_{ave}=\frac{\vec{S}\cdot\vec{J}}{J^2}\vec{J}\tag{6}$$
但是$\vec{L}=\vec{J}-\vec{S}$，所以$L^2=j^2+s^2-2\vec{J}\cdot\vec{S}$，所以
$$\vec{S}\cdot\vec{J}=\frac{1}{2}(J^2+S^2-L^2)=\frac{\hbar^2}{2}[j(j+1)+s(s+1)-l(l+1)]\tag{7}$$
所以我们可以写出
$$\langle \vec{L}+2\vec{S} \rangle=\langle\left( 1+\frac{\vec{S}\cdot\vec{J}}{J^2}\vec{J} \right)=\left[ 1+\frac{j(j+1)-l(l+1)+s(s+1)}{2j(j+1)} \right]\langle \vec{J}\rangle\tag{8}$$
我们将中括号中的部分称为Lande g-factor，$g_{J}$。
那么能量修正项写作
$$E_{z}^1=\mu_{B}g_{J}B_{ext} m_{j}\tag{9}$$
其中$$\mu_{B}\equiv \frac{e\hbar}{2m}\approx 5.788\times 10^-5eV/T$$
是波尔磁子。
此时的总能量为精细结构和塞曼效应的总和。

## strong-field Zeeman Effect
如果$B_{ext}\gg B_{int}$，此时塞曼效应占据主导，我们取$H_{Bohr}+H'_{z}$为无扰动时的哈密顿量，设$H_{fs}'$为微扰项，由于Zeeman哈密顿量写作
$$H_{z}'=\frac{e}{2m}B_{ext}(L_{z}+2S_{z})$$
所以我们先计算出无扰动状态下的能量表达式
$$E_{nm_{l}m_{s}}=-\frac{13.6eV}{n^2}+m\mu_{B}B_{ext}(m_{l}+2m_{s})\tag{10}$$
我们采用的标准基为$\ket{nlm_{l}m_{s}}$，这个标准基很明显是简并的（因为能量表达式不含有$l$，如$m_{l}=3,m_{s}=-1/2$和$m_{l}=1,m_{s}=1/2$简并），但是这个基对于我们的扰动来说是good states（$H_{fs}'$与$L^2,J_{z}$对易，所以用这两个量label的态可以作为$H'_{fs}$的good states，前一个算符描述了在$l$中的简并关系，后一个算符由于$m_{l}+2m_{s}=m_{j}+m_{s}$所以刚好可以刻画我们所列举的简并情况。
由此我们由一阶微扰理论写出精细结构（相对论+SO）对于能级的能量修正：
$$E_{fs}^1=\bra{nlm_{l}m_{s}}(H_{r}'+H_{SO}')\ket{nlm_{l}m_{s}}  \tag{11}$$
相对论项与[[氢原子精细结构]]中保持相同，为了计算自旋-轨道耦合想的影响，我们需要
$$\langle \hat{S}\cdot  \hat{L}\rangle=\langle S_{x}\rangle\langle L_{x}\rangle+\langle S_{y}\rangle\langle L_{y}\rangle+\langle S_{z}\rangle\langle L_{z}\rangle=\hbar^2m_{l}m_{s}$$
将两项修正相加可以得到
$$\boxed{E_{fs}^1=\frac{13.6eV}{n^3}\alpha^2\left\{ \frac{3}{4n}-\left[ \frac{l(l+1)-m_{l}m_{s}}{l(l+1/2)(l+1)} \right] \right\}}\tag{12}$$

## Intermediate-Field Zeeman Effect
此时$H_{z}',H_{fs}'$都不再是主导项，所以我们应该同等对待两者，此时的扰动写作
$$H'=H_{z}'+H_{fs}'\tag{13}$$
我们讨论$n=2$的情形。找出合适的good states是一件十分困难的事情，所以我们将一步步慢慢分析。首先采用由$l,j,m_{j}$描述的态作为基底（这是$H_{fs}'$的good states，我们需要分析$H_{Z}'$在其上的作用），使用Clebsch-Gordan系数将$\ket{jm_{j}}$展开为$\ket{lsm_{l}m_{s}}$，我们有：
$$\begin{align}
l=0:& \\
\psi_{1}\quad&\equiv\quad\ket{\frac{1}{2} \frac{1}{2}} &=\quad \ket{0 \frac{1}{2} 0 \frac{1}{2}}, \\
  \psi_{2}\quad&\equiv\quad\ket{\frac{1}{2} \frac{-1}{2}}&=\quad \ket{0 \frac{1}{2} 0 \frac{-1}{2}}, \\
l=1:& \\
\psi_{3}\quad&\equiv\quad\ket{\frac{3}{2} \frac{3}{2}}&=\quad \ket{1 \frac{1}{2} 1 \frac{1}{2}}, \\
\psi_{4}\quad&\equiv\quad\ket{\frac{3}{2} \frac{-3}{2}} &=\quad \ket{1 \frac{1}{2} 1 \frac{-1}{2}}, \\ 
\psi_{5}\quad&\equiv\quad\ket{\frac{3}{2} \frac{1}{2}} &=\quad \sqrt{ 2/3 }\ket{1 \frac{1}{2} 0 \frac{1}{2}}\quad &+\quad\sqrt{ 1/3 }\ket{1 \frac{1}{2}1 \frac{-1}{2}} , \\
\psi_{6}\quad&\equiv\quad\ket{\frac{1}{2} \frac{1}{2}} &=\quad -\sqrt{ 1/3 }\ket{1 \frac{1}{2} 0 \frac{1}{2}}\quad &+\quad\sqrt{ 2/3 }\ket{1 \frac{1}{2}1 \frac{-1}{2}} , \\
\psi_{7}\quad&\equiv\quad\ket{\frac{3}{2} \frac{-1}{2}} &=\quad \sqrt{ 1/3 }\ket{1 \frac{1}{2} -1 \frac{1}{2}}\quad &+\quad\sqrt{ 2/3 }\ket{1 \frac{1}{2}0 \frac{-1}{2}} , \\
\psi_{8}\quad&\equiv\quad\ket{\frac{1}{2} \frac{-1}{2}} &=\quad -\sqrt{ 2/3 }\ket{1 \frac{1}{2} -1 \frac{1}{2}}\quad &+\quad\sqrt{ 1/3 }\ket{1 \frac{1}{2}0 \frac{-1}{2}} .
\end{align}$$
在这个基下$H_{fs}'$是对角化（在good states的基下展开）的，取值为
$$E_{fs}^1=\frac{(E_{n})^2}{2mc^2}\left( 3-\frac{4n}{j+1/2} \right)$$
而$H'_{Z}$有四项非对角元，其矩阵形式$W$写作：
$$\begin{pmatrix}
5\gamma-\beta&0&0&0&0&0&0&0 \\
0 & 5\gamma+\beta & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & \gamma-2\beta & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & \gamma+2\beta & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & \gamma-\frac{2}{3}\beta & \frac{\sqrt{ 2 }}{3}\beta & 0 & 0 \\
0 & 0 & 0 & 0 & \frac{\sqrt{ 2 }}{3}\beta & 5\gamma-\frac{1}{3}\beta & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & \gamma+\frac{2}{3}\beta & \frac{\sqrt{ 2 }}{3}\beta \\
0 & 0 & 0 & 0 & 0 & 0 & \sqrt{ 2 }\beta & 5\gamma+\frac{1}{3}\beta
\end{pmatrix}$$
其中
$$\gamma \equiv(\alpha/8)^213.6eV,\quad \beta \equiv \mu_{B}B_{ext}$$
对于这个矩阵，前四个特征值即为前四个对角项，剩下即为求解$2\times 2$矩阵的特征值，第一个矩阵块写出特征方程为
$$\lambda^2+\lambda(6\gamma-\beta)+\left( 5\gamma^2-\frac{11}{3}\gamma \beta \right)=0$$
求解得
$$\lambda_{\pm}=3\gamma-(\beta/2)\pm \sqrt{ 4\gamma^2+(2/3)\gamma \beta +(\beta^2/4)}$$
剩下的矩阵块的特征值为
$$\lambda_{\pm}=3\gamma+(\beta/2)\pm \sqrt{ 4\gamma^2-(2/3)\gamma \beta +(\beta^2/4)}$$
![[Zeeman.png]]