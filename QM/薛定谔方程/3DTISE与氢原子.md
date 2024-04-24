#QuantumMechanics 

## 3D定态薛定谔方程的旋转对称性
三维薛定谔方程写作：
$$\Big[-\frac{\hbar^2}{2m}\nabla^2+V(\vec{r})\Big]\psi_E=E\psi_E$$
我们可以将这种旋转对称性看作：$V(\vec{r})=V(r),\quad r=\sqrt{x^2+y^2+z^2}$
所以在球坐标下展开薛定谔方程为：
$$-\frac{\hbar^2}{2m}\Big[\frac{1}{r^2}\frac{\partial}{\partial r}\Big(r^2\frac{\partial}{\partial r}\Big)+\frac{1}{r^2\sin\theta}\frac{\partial}{\partial\theta}\Big(\sin\theta\frac{\partial}{\partial\theta}\Big)+\frac{1}{r^2\sin\theta}\frac{\partial^2}{\partial\phi^2}\Big]\psi_E+V(r)\psi_E=E\psi_E$$
我们可以用分离变量法解此方程：
$$\psi_E(r,\theta,\phi)=R(r)\Theta(\theta)\Phi(\phi),\quad Y(\theta,\phi)\equiv\Theta(\theta)\Phi(\phi)$$
将此带回TISE中可得：
$$-\frac{\hbar^2}{2m}\Big[\frac{Y^2}{r^2}\frac{\partial}{\partial r}\Big(r^2\frac{\partial R}{\partial r}\Big)+\frac{R}{r^2\sin\theta}\frac{\partial}{\partial\theta}\Big(\sin\theta\frac{\partial Y}{\partial\theta}\Big)+\frac{R}{r^2\sin\theta}\frac{\partial^2Y}{\partial\phi^2}\Big]\psi_E+VRY=ERY$$
除去$RY/r^2$有：
$$\Rightarrow-\frac{\hbar^2}{2m}\Big[\frac{1}{R}\frac{\partial }{\partial r}\Big(r^2\frac{\partial R}{\partial r}\Big)+\frac{1}{Y\sin\theta}\frac{\partial}{\partial\theta}\Big(\sin\theta\frac{\partial Y}{\partial\theta}\Big)+\frac{1}{Y\sin\theta}\frac{\partial^2 Y}{\partial\phi^2}\Big]\psi_E+r^2(V-E)=0$$

$$\Rightarrow \Big\{\frac{1}{R}\frac{\partial }{\partial r}\Big(r^2\frac{\partial R}{\partial r}\Big)-\frac{2mr^2}{\hbar^2}(V(r)-E) \Big\}+\frac{1}{Y}\Big\{\frac{1}{\sin\theta}\frac{\partial}{\partial\theta}\Big(\sin\theta\frac{\partial Y}{\partial\theta}\Big)+\frac{1}{\sin\theta}\frac{\partial^2 Y}{\partial\phi^2}\Big\}=0$$
我们需要这两部分相互独立地等于一个常数，我们可以将这个常数写作$C=l(l+1)$。

### 角项方程（球坐标下的角动量算符）
$$\Big\{\frac{1}{\sin\theta}\frac{\partial}{\partial\theta}\Big(\sin\theta\frac{\partial Y}{\partial\theta}\Big)+\frac{1}{\sin\theta}\frac{\partial^2 Y}{\partial\phi^2}\Big\}=-l(l+1)Y$$
这与之前我们得到的方程$\hat{L}^2\ket{l,m}=l(l+1)\hbar^2\ket{l,m}$相似，本质上我们有（在球坐标下写出角动量算符）：
$$\begin{align}&\hat{L}_z=-i\hbar\partial_\phi\\
&\hat{L}_x=\hat{Y}\hat{P}_z-\hat{Z}\hat{P}_y=-\hbar(y\partial_z-z\partial_y)=-i\hbar\Big(-\sin\phi\frac{\partial}{\partial\theta}-\cos\phi\cot\theta\frac{\partial}{\partial\phi}\Big)\\
&\hat{L}_y=\hat{Z}\hat{P}_x-\hat{X}\hat{P}_z=-\hbar(z\partial_x-x\partial_z)=-i\hbar\Big(-\cos\phi\frac{\partial}{\partial\theta}-\sin\phi\cot\theta\frac{\partial}{\partial\phi}\Big)\\
&\hat{L}^2=\hat{L}_x^2+\hat{L}_y^2+\hat{L}_z^2=-\hbar\Big[\frac{1}{\sin\theta}\frac{\partial}{\partial\theta}\Big(\sin\theta\frac{\partial }{\partial\theta}\Big)+\frac{1}{\sin\theta}\frac{\partial^2 }{\partial\phi^2}\Big]
\end{align}$$
那么角项方程可以写作：
$$\hat{L}^2Y_l^m=\hbar^2 l(l+1)Y_l^m$$
带入$Y_l^m=\Theta(\theta)\Phi(\phi)$到角方程中并除以$\Theta\Phi/\sin\theta$可得：
$$\Rightarrow \frac{1}{\Theta}\Big[\sin\theta\frac{d}{d\theta}\Big(\sin\theta\frac{d\Theta}{d\theta}\Big)\Big]+l(l+1)\sin^2\theta+\frac{1}{\Phi}\frac{d^2\Phi}{d\phi^2}=0$$
同理我们分别看作只与$\theta$，只与$\phi$相关的两部分，两部分独立地等于常数$m^2$。

#### $\Phi$部分
$$\boxed{\frac{d^2\Phi}{d\phi^2}=-m^2\Phi\Rightarrow\quad \Phi=e^{im\phi}}$$
因为$\phi$分部有周期性，所以$\Phi(\phi)=\Phi(\phi+2\pi)\quad\quad \Rightarrow e^{im\phi}=e^{im\phi}\cdot e^{i2m\pi}$
只有当$m=0.\pm1,\pm2,\cdots$时才存在，这就是周期性边界条件导致了量子化条件。

#### $\Theta$部分
$$\boxed{\sin\theta\frac{d}{d\theta}\Big(\sin\theta\frac{d\Theta}{d\theta}\Big)+\Big[l(l+1)\sin^2\theta-m^2\Big]\Theta=0}$$
这个可以看作是general Legendre eq.：
$$(1-x^2)\frac{df^2}{dx^2}-2x\frac{df}{dx}+\Big[l(l+1)-\frac{m^2}{1-x^2}\Big]f=0$$
我们令$x=\cos\theta$，并让$\Theta$部分的方程除以$\sin^2\theta$，带入广义勒让德方程的通解形式：
$$\Theta=AP_l^m(\cos\theta)$$
其中$P_l^m$为连带勒让德多项式，$P_l$为勒让德多项式：
$$\begin{align}&P_l^m(x)\equiv(1-x^2)^{m/2}\Big(\frac{d}{dx}\Big)^mP_l(x)\\
&P_l(x)=\frac{1}{2^ll!}\Big(\frac{d}{dx}\Big)^l(x^2-1)^l \quad (Rodrigues \ formula)
\end{align}$$
考虑上角标小于0的情形，我们将连带勒让德多项式改写为：
$$P_l^{-m}(x)=(-1)^m\frac{(l-m)!}{(l+m)!}P_l^m(x)$$

所以总的来说，角项方程的解写作：
$$Y_l^m(\theta,\phi)=\sqrt{\frac{(2l+1)}{4\pi}\frac{(l-m)!}{(l+m)!}}P_l^m(\cos\theta)e^{im\phi}$$
其中的$l=0,1,2,3,\cdots$只能是整数。


### 径向方程Radiation Part
$$\Big\{\frac{1}{R}\frac{\partial}{\partial r}\Big(r^2\frac{\partial}{\partial r}\Big)-\frac{2mr^2}{\hbar^2}\Big(V(r)-E\Big) \Big\}+\frac{1}{Y}\Big\{\frac{1}{\sin\theta}\frac{\partial}{\partial\theta}\Big(\sin\theta\frac{\partial Y}{\partial\theta}\Big)+\frac{1}{\sin^2\theta}\frac{\partial^2Y}{\partial\phi^2} \Big\}=0$$
$$\Rightarrow \frac{d}{d r}\Big(r^2\frac{dR}{d r}\Big)-\frac{2mr^2}{\hbar^2}\Big(V(r)-E\Big)R=l(l+1)R$$
通过代换变量$U(r)=rR(r)$我们可以得到新方程：
$$\Rightarrow\boxed{-\frac{\hbar^2}{2m}\frac{d^2u}{dr^2}+\Big[V+\frac{\hbar^2}{2m}\frac{l(l+1)}{r^2} \Big]u=Eu}$$
径向归一化条件可以写作像离心力一样的：
$$\int_0^\infty |R(r)|^24\pi r^2dr=1$$
本质上这个式子来源于波函数的归一化$\int|\psi_E|^2d^3x=\int|R|^2|Y_l^m|^2r^2\sin\theta d\theta d\phi dr$，这里的球谐函数和角项积分贡献了系数$4\pi$。

## 氢原子
首先写出氢原子的径向方程，其中中括号内部分为有效势：
$$-\frac{\hbar^2}{2m}\frac{d^2u}{dr^2}+\Big[-\frac{e^2}{4\pi\epsilon_0r}+\frac{\hbar^2}{2m}\frac{l(l+1)}{r^2} \Big]u=Eu$$
我们仅考虑$E<V_{eff}(\infty)=0$的束缚态（束缚态才是原子拥有的电子态）

### 级数展开方法
>Step1. 将TISE用无量纲变量展开

对于束缚态我们定义$\kappa\equiv\frac{\sqrt{-2mE}}{\hbar}$，观察量纲$[\kappa]=[L]^{-1}$，所以取无量纲变量为$\rho\equiv\kappa r$，带回原方程：
$$\frac{1}{\kappa^2}\frac{d^2u}{dr^2}=\Big[1-\frac{me^2}{2\pi\epsilon_0\hbar^2\kappa}\frac{1}{Rr}+\frac{l(l+1)}{\kappa^2r^2} \Big]u$$
其中$\frac{me^2}{2\pi\epsilon_0\hbar^2\kappa}$是无量纲的，定义为$\rho_0$，那么我们可以记
$$\Rightarrow \frac{2\pi\epsilon_0\hbar^2}{me^2}\equiv\frac{1}{2}a_0$$
$a_0$是Bhor radius。$\rho_0=\Big(\frac{me^2}{2\pi\epsilon\hbar^2}\Big)\Big(\frac{1}{\kappa}\Big)$，方程再次简化为：
$$\frac{d^2u}{d\rho^2}=\Big[1-\frac{\rho_0}{\rho}+\frac{l(l+1)}{\rho^2}\Big]u$$

>Step2. 考虑极限$\rho\rightarrow\infty,\rho\rightarrow0$

#### $\rho\rightarrow\infty$情形
$$\frac{d^2u}{d\rho^2}=u$$
通解写作$Ae^{-\rho}+Be^{\rho}$，由于归一化限制后面一项被消掉。
所以$u\sim Ae^{-\rho},\quad when \ \rho\rightarrow\infty$
#### $\rho\rightarrow0$情形
$$\frac{d^2u}{d\rho^2}=\frac{l(l+1)}{\rho^2}u$$
这是欧拉方程，所以通解形式写作：$A\rho^{l+1}+B\rho^{-l}$
同理在$\rho\rightarrow0$处不能发散所以$B=0$
$$u\sim C\rho^{l+1},\quad when \ \rho\rightarrow0$$

总结：
$$\begin{cases}&u\sim Ae^{-\rho}\quad when \ \rho\rightarrow\infty\\ &u\sim C\rho^{l+1}\quad when \ \rho\rightarrow0
\end{cases}$$

所以我们假设：
$$\boxed{u=\rho^{l+1}\nu(\rho)e^{-\rho}}$$
当$\rho\rightarrow0$时$\nu(\rho)\rightarrow1$
将这个式子带回到原方程中有：
$$\rho\frac{d^2\nu}{d\rho^2}+2(l+1-\rho)\frac{d\nu}{d\rho}+[\rho_0-2(l+1)]\nu=0$$
我们假设$\nu(\rho)$可以写作级数形式：
$$\nu(\rho)=\sum\limits_{j=0}^\infty C_j\rho^j$$
那么有：
>$\frac{d\nu}{d\rho}=\sum\limits_{j=0}^\infty jC_j\rho^{j-1}=\sum\limits_{j=0}^\infty(j+1)C_{j+1}\rho^j$
>$\frac{d^2\nu}{d\rho^2}=\sum\limits_{j=0}^\infty j(j+1)C_{j+1}\rho^{j+1}$

原方程写作：
$$\Rightarrow \sum\limits_{j=0}^\infty\Big[j(j+1)C_{j+1}+2(l+1)(j+1)C_{j+1}-2jC_j+[\rho_0-2(l+1)]C_j\Big]\rho^j=0$$
$$\Rightarrow C_{j+1}=\frac{2(j+l+1)-\rho_0}{(j+1)(j+2l+2)}C_j$$

## $\rho\rightarrow \infty$情形

当$\rho$取值很大时，我们只需考虑主导的$j$较大的项，此时递推关系可以近似为$C_{j+1}\sim\frac{2j}{j^2}C_j$
$$\Rightarrow C_j\sim \frac{2^j}{j!}C_0$$
所以对于$\rho\rightarrow\infty$，我们有：
$$\nu(\rho)=\sum\limits_{j=0}^\infty C_j\rho^j\sim\sum\limits_{j=0}^\infty C_0\frac{2^j}{j!}\rho^j=\sum\limits_{j=0}^\infty C_0\frac{(2\rho)^j}{j!}=C_0e^{2\rho}$$
此时$u\sim \rho^{l+1}e^{-\rho}C_0e^{2\rho}=C_0\rho^{l+1}e^\rho$，
这项是在无穷发散的，所以不可归一化，这就说明为了归一化，我们要求<font color=orange>级数在某个有限的$N$阶之前终结</font>。
边界条件给出：$u\rightarrow0 \quad when \ \rho\rightarrow\infty$
所以这里存在$N$使得：
$$C_{N-1}\neq0,\quad C_N=0$$
$$\Rightarrow C_N=\frac{2(N+l)-\rho_0}{N(N+2l+2)}C_{N-1}$$
$$\Rightarrow2({N+l})=\rho_0$$
对于不同的能量本征态我们有不同的$N$取值，$N=1,2,3,4,5,\cdots$
习惯上我们可以定义$n\equiv N+l,\quad n=1,2,3,\cdots,l=0,1,2,\cdots,n-1$
$$\Rightarrow2n=\rho_0=\frac{me^2}{2\pi\epsilon_0\hbar^2\kappa},\quad \kappa=\frac{\sqrt{-2mE}}{\hbar}$$
$$\Rightarrow\boxed{E=-\frac{\hbar^2k^2}{2m}=-\Big[\frac{m}{2\hbar^2}\Big(\frac{e}{4\pi\epsilon}\Big)^2\Big]\frac{1}{n^2}}$$
>补充：
>这部分说明角项上必须存在一个上限N阶项，这一项的存在限制了$n$的取值从而规定了能级。

## Summary
$$\psi_E(r,\theta,\varphi)=R_{nl}(r)Y_l^m(\theta,\phi)$$
$$R_{nl}=\frac{u(r)}{r}=\frac{1}{r}\rho^{l+1}e^{-\rho}\nu(\rho)$$
$$\nu(\rho)=\sum\limits_{j=0}^\infty C_j\rho^j,\quad C_{j+1}=\frac{2(j+l+1-n)}{(j+1)(j+2l+2)}C_j$$
$$E_n=-\Big[\frac{m}{2\hbar^2}\Big(\frac{e}{4\pi\epsilon}\Big)^2\Big]\frac{1}{n^2}$$
$\ket{E_n}$简并度：
$$degeneracy=\sum\limits_{l=0}^{n-1}(2l+1)=n^2$$
其中对于给定的$n$有$l=0,1,2,\cdots,n-1$，对于给定的$l$有$m=-l,-l+1,\cdots,l-1,l$