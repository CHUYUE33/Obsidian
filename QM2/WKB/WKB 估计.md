#QuantumMechanics 
对于以能量$E$通过常势能区域的粒子，如果$E>V$，其波函数写作
$$\psi(x)-Ae^{\pm ikx},\quad k \equiv \sqrt{ 2m(E-{V}) }/\hbar$$
由此我们想用相同的形式来表示那些势能变化速度不大的场景，也就是将$\psi$假设仍保持正余弦函数形式，只是波长和振幅随着x变化。
类似的，如果$E<V$我们可以写作
$$\psi(x)=Ae^{\pm\kappa x},\quad \kappa \equiv \sqrt{ 2m(V-E) }/\hbar$$

## 经典区域
薛定谔方程
$$-\frac{\hbar^2}{2m} \frac{d^2\psi}{dx_{2}}+V(x)\psi=E\psi$$
可被改写作
$$\frac{d^2\psi}{dx^2}=-\frac{p^2}{\hbar^2}\psi,\quad p(x)\equiv \sqrt{ 2m[E-V(x)] }\tag{1}$$
其中$p(x)$是粒子动量的经典表达式。现在我们假设$E>V(x)$，所以$p(x)$是实数，我们称之为经典区域（因为经典理论给出粒子会被限制在这个范围内），此时的波函数可以写作由振幅$A(x)$和相位函数$\phi(x)$组成：
$$\psi(x)=A(x)e^{i\phi(x)}\tag{2}$$
所以有
$$\begin{cases}
&\frac{d\psi}{dx}=(A'+iA\phi')e^{i\phi}, \\
&\frac{d^2\psi}{dx^2}=[A''+2iA'\phi'+iA\phi''-A(\phi')^2]e^{i\phi}\tag{3}
\end{cases}$$
带回（1）中可得
$$A''+2iA'\phi'+iA\phi''-A(\phi')^2=-\frac{p^2}{\hbar^2}A\tag{4}$$
取等式两边实部虚部分别相等：
$$A''-A(\phi')^2=-\frac{p^2}{\hbar^2}A,\quad\text{or } A''=A\left[ (\phi')^2-\frac{p^2}{\hbar^2} \right]\tag{5}$$
和
$$2A'\phi'+A\phi''=0,\quad \text{or }(A^2\phi')'=0\tag{6}$$
第二个方程容易解得
$$A=\frac{C}{\sqrt{ |\phi'| }}\tag{7}$$
为了简化第一个方程，我们假设$A$变化的很慢，这也正是估计的来源，可得
$$(\phi')^2=\frac{p^2}{\hbar^2},\quad \text{or } \frac{d\phi}{dx}=\pm \frac{p}{\hbar}$$
$$\Rightarrow\quad \phi(x)=\pm \frac{1}{\hbar} \int p(x) \, dx \tag{8}$$
所以
$$\boxed{\psi(x)\approx \frac{C}{\sqrt{ p(x) }}e^{\pm i/\hbar \int p(x) \, dx }}\tag{9}$$
注意到$$|\psi(x)|^2\approx \frac{|C|^2}{p(x)}\tag{10}$$
也就是说招待粒子位于$x$位置的概率反比于其位于$x$处时的经典动量值。

>[!note] Example:两侧势能墙
>假设无限深方势阱写作
>$$V(x)=\begin{cases}
&\text{some function},\quad &(0<x<a) \\
&\infty,\quad &(\text{otherwise})
\end{cases}\tag{11}$$
>在势阱内部我们有
>$$\psi(x)\approx\frac{1}{\sqrt{ p(x) }}[C_{+}e^{i\phi(x)}+C_{-}e^{-i\phi(x)}]\tag{12}$$
>或者我们可以写作
>$$\psi(x) \approx\frac{1}{\sqrt{ p(x) }}[C_{1}\sin \phi(x)+C_{2}\cos \phi(x)]\tag{13}$$
>其中$\phi(x)=\frac{1}{\hbar}\int_{0}^x p(x') \, dx'$
>由于无限深势阱的限制，我们会有$\psi(0)=\psi(a)=0$，即
>$$C_{2}=0,\quad \phi(a)=n\pi\quad (n=1,2,3,\cdots)\tag{14}$$
>$$\Rightarrow \boxed{\int_{0}^a p(x) \, dx=n\pi \hbar }$$
带入边界条件可以给出不同势能条件$V(x)$下允许的能量范围，如上例中无限深势阱的两侧约束将给出量子化能级，非截断式势阱将给出一个连续的能谱。

## 隧穿效应
之前我们的讨论中$E>V$所以$p(x)$均为正，但在$E<V$的非经典区域，按照相同方法得到的表达式也是相同的，不过$p(x)$是虚数罢了：
$$\boxed{\psi(x)\approx \frac{C}{\sqrt{ |p(x)| }}e^{\pm 1/\hbar \int |p(x)| \, dx }}\tag{15}$$
现在来考虑一个突起的不平整的方块势垒的散射问题，对于势垒左侧的波函数$(x<0)$可以写作
$$\psi(x)=Ae^{ikx}+Be^{-ikx}\tag{16}$$
$k\equiv \sqrt{ 2mE }/\hbar$，对于势垒右侧$x>a$，
$$\psi(x)=Fe^{ikx},\tag{17}$$
所以透射概率写作
$$T=\frac{|F|^2}{|A|^2}\tag{18}$$
对于隧道区域$0<x<a$使用WKB估计可以得到
$$\psi(x)\approx \frac{C}{\sqrt{ |p(x)| }}e^{1/\hbar \int_{0}^{x}|p(x')|  \, dx' }+\frac{D}{\sqrt{ p(x) }}e^{-1/\hbar \int_{0}^x |p(x')| \, dx' }\tag{19}$$
对于较宽的势垒，透射概率小，所以内部势能增大项的系数$C$较小（无限宽势垒对应的C系数为0）。入射波和透射波的相对振幅主要由递减的指数波决定：
$$\frac{|F|}{|A|}\sim e^{-1/\hbar \int_{0}^a |p(x')| \, dx' }$$
所以
$$\boxed{T\approx e^{-2\gamma},\quad \gamma \equiv \frac{1}{\hbar}\int _{0}^a |p(x)| \, dx }\tag{20}$$
![[WKB.png|400]]


## 过渡公式
之前的例子的边界条件都很简单，现在我们来考虑不那么陡峭的势函数和$E=V$处于经典与非经典临界的情形。
为了简化表达式，我们将势阱两侧的入射、透射波函数都放到原点，那么表达式写作
$$\psi(x)\begin{cases}
&\frac{1}{\sqrt{ p(x) }}\left[ Be^{\frac{i}{\hbar}\int _{x}^0 p(x')\, dx' }+Ce^{-\frac{i}{\hbar}\int_{x}^0 p(x') \, dx' } \right],\quad &x<0, \\
&\frac{1}{\sqrt{ |p(x)| }}De^{-\frac{i}{\hbar}\int _{0}^x |p(x')|\, dx' },\quad &x>0.
\end{cases}\tag{21}$$
![[WKB01.png|400]]
这里我们直接略去了透射区域的指数递增项（为了积分收敛）。
能量的限制一般由边界情况决定，在此情形中，边界条件涉及经典到非经典的转变（$p(x)\rightarrow_{0}$），此过程发散。
所以我们寻找一个合适的连接两个区间的波函数。
现在连接波函数$\psi_{p}(x)$作用区域在原点附近，我们估计势能为$$V(x)\approx E+V'(0)x,\tag{22}$$
我们将势能线性化表示后解这个小区间的薛定谔方程：
$$-\frac{\hbar^2}{2m} \frac{d^2\psi_{p}}{dx^2}+(E+V'(0)x)\psi_{p}=E\psi_{p}$$
$$\Rightarrow \frac{d^2\psi_{p}}{dx^2}=\alpha^2x\psi_{p},\quad \alpha \equiv\left[ \frac{2m}{\hbar^2}V'(0) \right]^{1/3}\tag{23}$$
换元吸收系数$\alpha^3$：
$$Z\equiv\alpha x\tag{24}$$
$$\frac{d^2\psi_{p}}{dx^2}=z\psi_{p}\tag{25}$$
这就是*Airy‘s equation*，通解称为*Airy functions*。这个二阶微分方程解空间是二维的，写作
$$\psi_{p}(x)=aAi(\alpha x)+bBi(\alpha x)\tag{26}$$

>[!note] Airy functions
>Differential equation
>$$\frac{d^2y}{dz^2}=zy$$
>solution’s integral representation:
>$$\begin{align}
&Ai(z)=\frac{1}{\pi}\int_{0}^\infty \cos\left( \frac{s^3}{3}+sz \right)  \, ds \\
&Bi(z)=\frac{1}{\pi}\int _{0}^\infty\left[ e^{-\frac{s^3}{3}+sz}+\sin\left( \frac{s^3}{3}+sz \right) \right] \, ds 
\end{align} $$
>Asymptotic Forms:
>$$Z\gg 0\begin{cases}
&Ai(z)\sim \frac{1}{2\sqrt{ \pi }z^{1/4}}e^{-\frac{2}{3}z^{3/2}} \\
&Bi(z)\sim\frac{1}{\sqrt{ \pi }z^{1/4}}e^{\frac{2}{3}z^{3/2}}
\end{cases}\quad Z\ll 0\begin{cases}
&Ai(z)\sim \frac{1}{{\sqrt{ \pi }(-z)^{1/4}}}\sin\left[ \frac{2}{3}(-z)^{3/2}+\frac{\pi}{4} \right] \\
&Bi(z)\sim \frac{1}{{\sqrt{ \pi }(-z)^{1/4}}}\cos\left[ \frac{2}{3}(-z)^{3/2}+\frac{\pi}{4} \right]
\end{cases}$$

现在我们需要将原点附近的连接函数在与两侧WKB解重合的区域match好：
![[WKB02.png|400]]
我们带入过渡区域中线性势能变化的假设来计算WKB：
$$p(x)\approx \sqrt{ 2m(E-E-V'(0)x) }=\hbar\alpha^{3/2}\sqrt{ -x }\tag{27}$$
对于右侧重叠区域，
$$\int _{0}^x|p(x')| \, dx'\approx \hbar\alpha^{3/2}\int _{0}^x\sqrt{ x' } \, dx'=\frac{2}{3}\hbar(ax)^{3/2}  $$
所以透射区域的波函数写作
$$\psi(x)\approx \frac{D}{\sqrt{ \hbar }\alpha^{3/4}x^{1/4}}e^{-\frac{2}{3}(\alpha x)^{3/2}}\tag{28}$$
我们采用之前$z\gg 0$情况下的近似Airy functions，在右侧区域的连接函数写作
$$\psi_{p}(x)\approx \frac{a}{2\sqrt{ \pi }(\alpha x)^{1/4}}e^{-\frac{2}{3}(\alpha x)^{3/2}}+\frac{b}{\sqrt{ \pi }(\alpha x)^{1/4}}e^{\frac{2}{3}(\alpha x)^{3/2}}\tag{29}$$
令两式相等，可得
$$a=\sqrt{ \frac{4\pi}{\alpha \hbar} }D,\quad b=0\tag{30}$$
接下来考察左侧重叠区域：
$$\int _{x}^0p(x') \, dx'\approx \frac{2}{3}\hbar(-\alpha x)^{3/2}\tag{31} $$
WKB波函数写作
$$\psi(x)\approx \frac{1}{\sqrt{ \hbar }\alpha^{3/4}(-x)^{1/4}}[Be^{i \frac{2}{3}(-\alpha x)^{3/2}}+Ce^{-i\frac{2}{3}(-\alpha x)^{3/2}}]\tag{32}$$
此时取$z\ll 0$的极限，连接函数写作
$$\begin{align}
\psi_{p}(x)&\approx \frac{1}{\sqrt{ \pi }(-\alpha x)^{1/4}}\sin\left[ \frac{2}{3}(-\alpha x)^{3/2}+\frac{\pi}{4} \right] \\
&=\frac{a}{\sqrt{ \pi }(-\alpha x)^{1/4}} \frac{1}{2i}[e^{i\pi/4}-e^{-\pi/4}e^{-i\frac{2}{3}(-\alpha x)^{3/2}}]
\end{align}$$
联立可得
$$B=-ie^{i\pi/4}D,\quad C=ie^{-i\pi/4}D\tag{33}$$
所以现在整个WKB估计得到的波函数可以写作
$$\psi(x)\approx \begin{cases}
&\frac{2D}{\sqrt{ p(x) }}\sin\left[ \frac{1}{\hbar}\int _{x}^{x_{2}}p(x') \, dx' +\frac{\pi}{4} \right],\quad &x<x_{2} \\
& \frac{D}{\sqrt{ |p(x)| }}\exp{\left[ -\frac{1}{\hbar}\int _{x_{2}}^x|p(x')| \, dx'  \right]},\quad &x>x_{2}
\end{cases}\tag{34}$$
其中$x_{2}$表示turning point。
>[!note] Example
>考虑一个在$x=0$处垂直的势场，右侧势场单调递增。
>也就是说$\psi(0)=0$，我们有
>$$\int _{0}^{x_{2}}p(x) \, dx =\left( n-\frac{1}{4} \right)\pi \hbar\tag{35}$$
>更具体的，我们假设右侧势能分布为半个谐振子：
>$$V(x)=\begin{cases}
& \frac{1}{2}mw^2x^2,\quad &(x>0) \\
&\infty,\quad &(\text{otherwise})
\end{cases}\tag{36}$$
>此时$$p(x)=\sqrt{ 2m[E-(1/2)mw^2x^2] }=mw\sqrt{ x_{2}^2-x^2 },\quad x_{2}=\frac{1}{2} \sqrt{ \frac{2E}{m} }$$
>这里$x_{2}$为turning point，那么
>$$\int _{0}^{x_{2}}p(x) \, dx=mw\int _{0}^{x_{2}}\sqrt{ x_{2}^2-x^2 } \, dx=\frac{\pi}{4}mwx_{2}^2=\frac{\pi E}{2w}  $$
>所以量子化的能量本征态写作
>$$E_{n}=\left( 2n-\frac{1}{2} \right)\hbar w,\quad n=1,3,5,\cdots$$
这里可以联系[[QM/薛定谔方程/量子谐振子|量子谐振子]]中的推导关系较为容易的得到上述表达式。

### 不同变化趋势
上述例子中的波函数表达式这只适用于upward slope的势函数（非经典区域在右侧），对于downward slope的势函数，其应该写作
$$\psi(x)\approx \begin{cases}
&\frac{D'}{\sqrt{ |p(x)| }}\exp\left[ -\frac{1}{\hbar}\int _{x}^{x_{1}}|p(x')| \, dx'  \right],\quad &x<x_{1} \\
& \frac{2D'}{\sqrt{ p(x) }}\sin\left[ \frac{1}{\hbar}\int _{x_{1}}^x p(x') \, dx'+\frac{\pi}{4}  \right],\quad &x>x_{1}
\end{cases}\tag{37}$$
![[WKB03.png|400]]
现在我们来处理（c）图中势阱的情形，图中内部区域（$x_{1}<x<x_{2}$）可以分别用我们提到的两组公式来描述，先用（37）式得到：
$$\psi(x)\approx \frac{2D}{\sqrt{ p(x) }}\sin\theta_{2}(x),\quad \theta_{2}(x)\equiv \frac{1}{\hbar}\int _{x}^{x_{2}}p(x') \, dx'+\frac{\pi}{4} $$
或者（34）式可得
$$\psi(x)\approx -\frac{2D'}{\sqrt{ p(x) }}\sin\theta_{1}(x),\quad \theta_{1}(x)\equiv -\frac{1}{\hbar}\int _{x_{1}}^xp(x') \, dx' $$
显然我们需要两个正弦函数取值相同，那么有$\theta_{2}=\theta_{1}+n\pi$，也就是
$$\int _{x_{1}}^{x_{2}}p(x) \, dx=\left( n-\frac{1}{2} \right)\pi \hbar,\quad n=1,2,3,\cdots $$
上述限制条件对于所有的左减右增势阱（极小值处）适用（比如谐振子）
上述方法可以在不解薛定谔方程的前提下给出允许的能量范围。

>[!note] Example:谐振子
>根据上述公式：
>$$\int _{x_{1}}^{x_{2}}p(x) \, dx =\left( n-\frac{1}{2} \right)\pi{\hbar };\quad p(x)=\sqrt{ 2m\left( E-\frac{1}{2}mw^2x^2 \right) };x_{2}=-x_{1}=\frac{1}{w}\sqrt{ \frac{2E}{m} }$$
>$$\begin{align}
\left( n-\frac{1}{2} \right)\pi \hbar&=2mw\int _{-x_{2}}^{x_{2}}\sqrt{ x_{2}^2-x^2 } \, dx=mw[x\sqrt{ x_{2}^2-x^2 }+x_{2}^2\sin^{-1}(x/x_{2})]_{0}^{x_{2}} \\
&=mwx_{2}^2\sin^{-1}(1)=\frac{\pi}{2}mwx_{2}^2=\frac{\pi}{2}mw \frac{2E}{mw^2}=\frac{\pi E}{w}
\end{align} $$
>$$\boxed{E_{n}=\left( n-\frac{1}{2} \right)}\hbar w,\quad n=1,2,3,\cdots$$
