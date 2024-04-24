#QuantumMechanics 
如果某个能量本征值对应两个（或更多）简并的态，那么之前[[时间无关扰动（nondegenerated）Time independent Perturbation Theory]]中得到的一阶扰动态系数$C_{nm}$的分母存在$E_{n}^0-E_{m}^0=0$的发散项，所以不再适用。现在我们来讨论存在简并时的Perturbation Theory。

## 二阶简并
假设$\psi_{a}^0,\psi_{b}^0$相互正交归一化，
$$H^{0}\psi_{a}^{0}=E^{0}\psi_{a}^{0},\quad H^{0}\psi_{b}^{0}=E^{0}\psi_{b}^{0},\bra{\psi_{a}^{0}}\ket{\psi_{b}^0}=0 \tag{1}$$
所以对于能量$E^0$的任意本征态都可以写作
$$\psi^0=\alpha \psi_{a}^0+\beta \psi_{b}^0\tag{2},\quad H^0\psi^0=E^0\psi^0$$
一般来说，扰动项$H'$会破坏简并态：我们将扰动系数$\lambda$从0增大到1，无扰动时的$E^0$将会分裂成两个能级。
![[DegPertu.png|300]]
我们从反向看这个过程，“upper” state，“lower” state都会退回某种$\psi_{a}^0,\psi_{b}^0$的线性组合，但是我们并不知道这些“good” states是如何组成的。
为什么会分裂成两个能级：因为我们这里假设$E^0$对应的本征空间是二维的，所以在扰动项的影响下会得到两个新的本征值（最多两个新本征值），这两个新本征值是由扰动项决定的。为了更好的描述扰动的影响，我们应该找到这个二维扰动矩阵对应的本征向量，这就是我们说的“good” states，对应之前我们所得到的两个新本征值。
为了找到“good” states我们可以计算$H$的本征态
>[!note] Example
>考虑一个质量为$m$二维谐振子
>$$H^0=\frac{p^2}{2m}+\frac{1}{2}mw^2(x^2+y^2)$$
>我们加上扰动
>$$H'=\epsilon mw^2xy$$
>对于无扰第一激发态$E^0=2\hbar w$，它是二重简并的，我们可以用以下基底描述
>$$\psi_{a}^0=\psi_{0}(x)\psi_{1}(y)=\sqrt{ \frac{2}{\pi} } \frac{mw}{\hbar}ye^{-\frac{mw}{2\hbar}(x^2+y^2)}$$
>$$\psi_{b}^0=\psi_{1}(x)\psi_{0}(y)=\sqrt{ \frac{2}{\pi} } \frac{mw}{\hbar}xe^{-\frac{mw}{2\hbar}(x^2+y^2)}$$
>其中$\psi_{1},\psi_{0}$是对于一维谐振子的本征函数，为了找到“good” states，我们直接求解新的哈密顿量$H=H^0+H'$的本征态，我们取$\epsilon\rightarrow_{0}$的极限，再带入变换
>$$x'=\frac{x+y}{\sqrt{ 2 }},\quad y'=\frac{x-y}{\sqrt{ 2 }}$$
>那么哈密顿量写作
>$$H=\frac{1}{2m}\left( \frac{ \partial^2  }{ \partial x'^2 }  +\frac{ \partial ^2 }{ \partial y'^2 } \right)+\frac{1}{2}m(1+\epsilon)w^2x'^2+\frac{1}{2}m(1-\epsilon)w^2y'^2$$
>我们可以看到这是两个无关谐振子的叠加，本征解写作
>$$\psi_{mn}=\psi_{m}^+(x')\psi_{n}^-(y')$$
>其中$\psi_{m}^{\pm}$是以频率为$w_{\pm}=\sqrt{ 1\pm\epsilon }w$的一维谐振子本征态，那么其能量写作
>$$E_{mn}=\left( m+\frac{1}{2} \right)\hbar w_{+}+\left( n+\frac{1}{2} \right)\hbar w_{-}$$
>![[DegPertu1.png|300]]
>对于$\epsilon=0$时能量为$2\hbar w$的态，是二重简并的，本征态分别为$m=0,n=1(\text{lower state})$和$m=1,n=0(\text{upper state})$，所以取
>$$\begin{align}
\lim_{ \epsilon \to 0 }\psi_{01}(x)&=\lim_{ \epsilon \to 0 }\psi_{0}^+(x')\psi_{1}^-(y')=\psi_{0}\left( \frac{x+y}{\sqrt{ 2 }} \right)\psi_{1}\left( \frac{x-y}{\sqrt{ 2 }} \right)   \\
&=\sqrt{ \frac{2}{\pi} } \frac{mw}{\hbar} \frac{x-y}{\sqrt{ 2 }}e^{-\frac{mw}{2\hbar}(x^2+y^2)}=\frac{-\psi_{a}^0+\psi_{b}^0}{\sqrt{ 2 }} \\
\lim_{ \epsilon \to 0 }\psi_{10}(x)&=\frac{\psi_{a}^0+\psi_{b}^0}{\sqrt{ 2 }} 
\end{align}$$
>所以“good” states写作
>$$\boxed{\psi_{\pm}^0\equiv \frac{1}{\sqrt{ 2 }}(\psi_{b}^0\pm \psi_{a}^0)}$$
>可以看到我们是写出全部新的哈密顿量，而不是只考虑扰动部分的哈密顿量。然后在取$\epsilon=0$时得到good states

接下来给出更加genernal的方法来求解good states：
写出薛定谔方程
$$H\psi=E\psi,\quad H=H^0+\lambda H'\tag{3}$$
其中$$E=E^0+\lambda E^1+\lambda^2E^2+\cdots,\quad \psi=\psi^0+\lambda \psi^1+\lambda^2\psi^2+\cdots\tag{4}$$
带入可以得到
$$H^0\psi^0+\lambda(H'\psi^0+H^0\psi^1)+\cdots=E^0\psi^0+\lambda(E^1\psi^0+E^0\psi^1)+\cdots$$
因为(2)，所以两边消掉第一项，取$\lambda$一阶项：
$$H^0\psi^1+H'\psi^0=E^0\psi^1+E^1\psi^0\tag{5}$$
很明显不论乘以哪个左矢，两边的第一项都可以消掉，现在乘以$\bra{\psi_{a}^0}$得到
$$\alpha \bra{\psi_{a}^0}H'\ket{\psi_{a}^0}+\beta \bra{\psi_{a}^0}H'\ket{\psi_{b}^0}=\alpha E^1    $$
一般我们将上式写成如下形式
>[!note] 二阶简并系数确定
>$$\alpha W_{aa}+\beta W_{ab}=\alpha E^1\tag{6}$$
>$$\alpha W_{ba}+\beta W_{bb}=\beta E^1\tag{7}$$
>其中
>$$W_{ij}\equiv \bra{\psi_{i}^0}H'\ket{\psi_{j}^0}\quad (i,j=a,b)\tag{8}  $$
>两个方程可以合并写作
>$$\begin{pmatrix}
W_{aa}&W_{ab} \\
W_{ba}&W_{bb}
\end{pmatrix}\begin{pmatrix}
\alpha\\\beta
\end{pmatrix}=E^1\begin{pmatrix}
\alpha\\\beta
\end{pmatrix}\tag{9}$$

这就是二阶简并时一阶修正能量值的特征方程，我们求解上述本征方程
$$\begin{pmatrix}
W_{aa}-E^1&W_{ab} \\
W_{ba}&W_{bb}-E^1
\end{pmatrix}\begin{pmatrix}
\alpha\\\beta
\end{pmatrix}=0$$
$$\Rightarrow \boxed{E_{\pm}^1=\frac{1}{2}[W_{aa}+W_{bb}\pm \sqrt{ (W_{aa}-W_{bb})^2+4|W_{ab}|^2 }]}\tag{10}$$
>[!note] Example
>使用之前的例子，通过对角化$W$求解good states。
>计算矩阵元
>$$\begin{align}
W_{aa}&=\int \int \psi_{a}^0(x,y)H'\psi_{a}^0(x,y) \, dx  \, dy \\
&=\epsilon mw^2\int |\psi_{0}(x)|^2xdx \int |\psi_{1}(y)|^2ydy=0  
\end{align} $$
>相似的$W_{bb}=0$，
>$$\begin{align}
W_{ab}&= \int \int \psi_{a}^0(x,y)H'\psi_{b}^0(x,y) \, dx  \, dy \\
&=\epsilon mw^2\int \psi_{0}(x)x\psi_{1}(x)dx \int \psi_{1}(y)y\psi_{0}(y)dy
\end{align}$$
>使用升降算符来表示位置算符：
>$$x=\sqrt{ \frac{\hbar}{2mw} }(a_{+}+a_{-})$$
>所以
>$$\begin{align}
W_{ab}&=\epsilon mw^2\left[ \int \psi_{0}(x)\sqrt{ \frac{\hbar}{ 2mw} }(a_{+}+a_{-})\psi_{1}(x) \, dx  \right]^2 \\
&=\epsilon  \frac{\hbar w}{2}\left[ \int \psi_{0}(x)\psi_{0}(x) \, dx  \right]^2=\epsilon\frac{\hbar w}{2}
\end{align}$$
>所以矩阵$W$写作
>$$W=\epsilon  \frac{\hbar w}{2}\begin{pmatrix}
0&1 \\
1 & 0
\end{pmatrix}$$
>我们可以找到这个矩阵的两个特征向量为
>$$\frac{1}{\sqrt{ 2 }}\begin{pmatrix}
1\\1
\end{pmatrix}, \quad\text{and}\quad \frac{1}{\sqrt{ 2 }}\begin{pmatrix}
-1\\1
\end{pmatrix}$$
>所以我们根据系数写出good states的表达式
>$$\boxed{\psi^0_{\pm}=\frac{1}{\sqrt{ 2 }}(\psi_{b}^0\pm \psi_{a}^0)},\quad E^1=\pm\epsilon  \frac{\hbar w}{2}$$

若$W_{ab}=0$，那说明原本的简并态$\psi_{a}^0,\psi_{b}^0$就是good states。

## 本征态Good States
>**Theorem**
>---
>令$\hat{A}$为与$H^0,H'$都对易的厄米算符。如果$\psi_{a}^0,\psi_{b}^0$($H^0$的简并态)都是$\hat{A}$的本征函数，有不同的本征值
>$$A\psi_{a}^0=\mu \psi_{a}^0,\quad A\psi_{b}^0=\nu \psi_{b}^0\quad \text{and } \mu \neq \nu$$
>那么$\psi_{a}^0,\psi_{b}^0$就是之前求的Good states。
>---
>证明：
>因为$H(\lambda)=H^0+\lambda H'$与$\hat{A}$对易，所以这两者存在共同的本征基$\psi_{\gamma}(\lambda)$满足
>$$H(\lambda)\psi_{\gamma}(\lambda)=E(\lambda)\psi_{\gamma}(\lambda),\quad A\psi_{\gamma}(\lambda)=\gamma \psi_{\gamma}(\lambda)\tag{11}$$
>由于A是厄密算符
>$$\begin{align}
\bra{\psi_{a}^0}A\psi_{\gamma}(\lambda)&=\bra{A\psi_{a}^0}\ket{\psi_{\gamma}(\lambda)} \\
\gamma \bra{\psi_{a}^0}\psi_{\gamma}(\lambda)&=\mu^*\bra{\psi_{a}^0}\ket{\psi_{\gamma}(\lambda)} \\
(\gamma-\mu)\bra{\psi_{a}^0}\psi_{\gamma}(\lambda)&=0       
\end{align}\tag{12}$$
>我们得到
>$$\bra{\psi_{a}^0}\ket{\psi_{\gamma}(0)}=0\quad \text{unless }\gamma=\mu  $$
>$$\bra{\psi_{b}^0}\ket{\psi_{\gamma}(0)}=0\quad \text{unless }\gamma=\nu  $$
>由于good states是$\psi_{a}^0,\psi_{b}^0$的线性组合：$\psi_{\gamma}(0)=\alpha \psi_{a}^0+\beta \psi_{b}^0$，所以要么$\gamma=\mu$，此时$\beta=0$;要么$\gamma=\nu$，此时$\alpha=0$，QED。

现在又给出了一种找到good states的方法：找到$A$的本征态。
>[!note] Example
>与前例相同的情形。$H'$只对于旋转整数$\pi$角度保持不变，而$H^0$有连续旋转对称性，所以我们先考察为逆时针旋转$\pi$的变换算符$\hat{R}(\pi)$，将$\psi_{a}^0,\psi_{b}^0$分别作用其上
>$$R(\pi)\psi_{a}^0(x,y)=\psi_{a}^0(-x,-y)=-\psi_{a}^0(x,y)$$
>$$R(\pi)\psi_{b}^0(x,y)=\psi_{b}^0(-x,-y)=-\psi_{b}^0(x,y)$$
>并没有产生两个不同的本征值，所以我们需要一个可以交换x，y的算符：$\hat{D}$，关于45度斜面进行反射，$\hat{D}$与$H',H^0$对易，现在有
>$$D\psi_{a}^0(x,y)=\psi_{a}^0(y,x)=\psi_{b}^0(x,y),$$
>$$D\psi_{b}^0(x,y)=\psi_{b}^0(y,x)=\psi_{a}(x,y)$$
>我们已知的简并本征态并非$\hat{D}$的本征函数，所以我们写出其线性组合
>$$\psi^0_{\pm}\equiv\pm \psi_{a}^0+\psi_{b}^0$$
>现在
>$$D(\pm \psi_{a}^0+\psi_{b}^0)=\pm D\psi_{a}^0+D\psi_{b}^0=\pm \psi_{b}^0+\psi_{a}^0=\pm(\pm \psi_{a}^0+\psi_{b}^0)$$

## 高阶简并
对于一个n重简并的态，我们给出其矩阵元定义式
$$W_{ij}=\bra{\psi_{i}^0}H'\ket{\psi_{j}^0} \tag{13} $$
对于三界简并，对于能量的一阶修正$E^1$是矩阵$W$的本征值：
$$\begin{pmatrix}
W_{aa} & W_{ab} & W_{ac}  \\
W_{ba} & W_{bb} & W_{bc} \\
W_{ca} & W_{cb} & W_{cc}
\end{pmatrix}\begin{pmatrix}
\alpha\\\beta\\\gamma
\end{pmatrix}=E^1\begin{pmatrix}
\alpha\\\beta\\\gamma
\end{pmatrix}\tag{14}$$
Good States写作
$$\psi^0=\alpha \psi_{a}^0+\beta \psi_{b}^0+\gamma \psi_{c}^0\tag{15}$$


