#SolidStates 

## 分子轨道和紧密连接理论(Genernal)
我们首先写出两个氢原子的哈密顿量，因为原子核相对于核外电子非常重，所以我们将原子核视作保持不动的，固定原子核位置而求解电子的薛定谔方程（与原子核间距的方程），这也就是“Born-Oppenheimer” approximation。
为简化问题，先考虑单电子核两个相同的正电质子，写出哈密顿量
$$H=K+V_{1}+V_{2},\quad K+\frac{\vec{p}^2}{2m}$$
$K$是电子的动能并且
$$V_{i}=\frac{e^2}{4\pi\epsilon_{0}|\vec{r}-\vec{R}_{i}|}$$
表示位于$\vec{r}$的电子与位置$\vec{R_{i}}$的质子的库伦相互作用势能。
我们尝试将解写作如下形式
$$\ket{\psi}=\phi_{1}\ket{1}+\phi_{2}\ket{2}   \tag{1}$$
其中$\phi_{i}$表示复系数，ket$\ket{1},\ket{2}$表示原子轨道（或者说“tight-binding”轨道），我们将这种解的表示方法称为“LCAO”。我们这里使用的轨道是指只考虑单个质子影响时的薛定谔方程解
$$(K+V_{1})\ket{1}=\epsilon_{0}\ket{1}  $$
$$(K+V_{2})\ket{2}=\epsilon_{2}\ket{2}\tag{2}  $$
其中$\epsilon_{0}$时单原子模型的基态能量，所以$\ket{1},\ket{2}$分别表示电子bound to 质子1，质子2的基态轨道。
我们现在做一个较为粗糙的估计，假设$\ket{1},\ket{2}$正交，所以
$$\bra{i}\ket{j}=\delta_{ij}\tag{3}  $$
当两个原子核足够接近时，轨道正交的假设很明显不正确，但是我们所感兴趣的事情不太依赖于轨道之间是否正交。
由于LCAO的假设，我们可以将薛定谔方程展开成以下特征值问题
$$\sum_{j}H_{ij}\phi_{j}=E\phi_{i}\tag{4}$$
其中$$H_{ij}=\bra{i}H\ket{j}  $$
对于只有两个原子核的情形，我们可以将矩阵元具体表达式写出来
$$\begin{align}
&H_{11}=\bra{1}H\ket{1}=\bra{1}K+V_{1}\ket{1}+\bra{1}V_{2}\ket{1}=\epsilon_{0}+V_{cross}\tag{5} \\
&H_{22}=\bra{2}H\ket{2}=\bra{2}K+V_{2}\ket{2}+\bra{2}V_{1}\ket{2}=\epsilon_{0}+V_{cross}\tag{6} \\
&H_{12}=\bra{1}H\ket{2}=\bra{1}K+V_{2}\ket{2}+\bra{1}V_{1}\ket{2}=0-t\tag{7} \\
&H_{21}=\bra{2}H\ket{1}=\bra{2}K+V_{2}\ket{1}+\bra{2}V_{1}\ket{1}=0-t^*\tag{8}      
\end{align}$$
其中$$V_{cross}=\bra{1}V_{2}\ket{1}=\bra{2}V_{1}\ket{2}    $$
表示在轨道$\ket{1}$上感受到的来自原子核2的库伦势，或者相同的在轨道$\ket{2}$上感受到的原子核1的库伦势。
在（7）（8）中我们定义了hopping term：
$$t=-\bra{1}V_{2}\ket{2}=-\bra{1}V_{1}\ket{2}    $$
所以薛定谔方程化简为如下特征方程形式
$$\begin{pmatrix}
\epsilon_{0}+V_{cross}&-t \\
-t^*&\epsilon_{0}+V_{cross}
\end{pmatrix}\begin{pmatrix}
\phi_{1}\\ \phi_{2}
\end{pmatrix}=E\begin{pmatrix}
\phi_{1}\\ \phi_{2}
\end{pmatrix}\tag{9}$$
我们尝试解释方程的含义，可以看到轨道$\ket{1},\ket{2}$的能量为$\epsilon_{0}$加上由于另一个原子核存在导致的能量变化$V_{cross}$，并且电子可以从一个轨道跳跃（hopping）到另一个轨道，我们用非对角项$t$描述。非对角项的存在允许原本的轨道$\ket{1}$随着时间演化振动在两种轨道之间。
计算本征值我们可以得到
$$E_{\pm}=\epsilon_{0}+V_{cross}\pm|t|  $$
其中低能量的轨道是成键轨道（bonding orbital），高能量的轨道为反键轨道（anti-bonding orbital），相对应的波函数可以写作
$$\ket{\psi_{bonding}}=\frac{1}{\sqrt{ 2 }}(\ket{1}\pm \ket{2}  )\tag{10} $$
$$\ket{\psi_{antibonding}}=\frac{1}{\sqrt{ 2 }}(\ket{1}\mp \ket{2} ) \tag{11}$$
这分别是轨道的对称叠加和反对称叠加，其中的$\pm$主要是根据$t$的正负取值情况灵活变化，使得$\psi_{bonding}$对应能量更低的情形。
接下来我们考量如果两个原子核被紧密连接但是并不相同。这种情形下两种轨道$\ket{1},\ket{2}$的基态能量$\epsilon_{0}$将不再相同，所以（9）式中矩阵对角元不再相等，导致$\phi_{1},\phi_{2}$占比不同，低能量的态将在基态中占据更多。$\ket{1},\ket{2}$能量相差越大，电子将更多的转移到低能级态中，逐渐形成离子键。

除此之外，我们还忽略了两个原子核之间的相互作用。作为一阶修正估计，库伦斥力刚好抵消掉电子与原子核之间的相互吸引力（对于离原子核较远的距离，我们可以将原子核和核外电子看作一体，也就是电中性的，此时远处的原子核将无作用效果），也就是说我们可以抵消掉$V_{cross}$（轨道1受到原子核2吸引的能量影响）：
$$E_{\pm}\approx\epsilon_{0}+|t|$$


### Covalent in detail
(a) 原子轨道线性组合LCAO
之前的讨论中只考虑了原子核1，2的原子轨道的组合，我们现在将基底推广到一组原子轨道：$\ket{n},n=1,\cdots,N$，并假设$\delta \bra{n}\ket{m}=\delta_{nm}$（其实这个假设并不太科学，在之后我们会讨论不正交的情形），所以基态波函数写作
$$\ket{\Psi}=\sum_{n}\phi_{n}\ket{n}  $$
我们的原子轨道数量越多，最后的线性组合结果就越接近真实情况，claim：基态的薛定谔方程可以写作如下形式
>[!note] 基态约化薛定谔方程
>$$\mathscr{H} \phi=E\phi$$
>其中$\phi$是由N个$\phi_{i}$组成的矢量，$\mathscr{H}$是一个$N\times N$矩阵
>$$\mathscr{H}_{nm}=\bra{n}H\ket{m}  $$
>$H$是整个系统的哈密顿量。


能量表示为
$$E=\frac{\bra{\psi}H\ket{\psi}}{\bra{\psi}\ket{\psi}  }  $$
接下来我们用变分的做法来证明方程正确性，首先E展开为
$$E=\frac{\bra{\psi}H\ket{\psi}}{\bra{\psi}\ket{\psi}  }=\frac{\sum_{n,m}\phi^*_{n}\mathscr{H}_{nm}\phi_{m}}{\sum_{n}|\phi_{n}|^2}\tag{12}$$
对每一个$\phi_{n}^*$求偏导取极值，注意：在求偏导时我们可以将$\phi_{n},\phi_{n}^*$当作不同的变量处理，所以有
$$0=\frac{\partial E}{\partial \phi^*_{n}}=\frac{\sum_{m}\mathscr{H}_{nm}\phi_{m}}{\sum_{p}|\phi_{p}|^2}-\left( \frac{\sum_{n,m}\phi^*_{n}\mathscr{H}_{nm}\phi_{m}}{\sum_{n}|\phi_{n}|^2} \right) \frac{\phi_{n}}{\sum_{p}|\phi_{p}|^2}$$
RHS第二项来源于对分母中的$\phi_{n}^*$求导。
$$\Rightarrow \sum_{m}\mathscr{H}_{nm}\phi_{m}-E\phi_{m}=0$$
得证。

(b) Two-orbital covalent bond
让我们回到基底中只有两个原子轨道的情形，这适用于有两个相同原子核和一个电子的情形（电子被共享形成共价键），整体哈密顿量为
$$H=\frac{\vec{p}^2}{2m}+V(\vec{r}-\vec{R_{1}})+V(\vec{r}-\vec{R_{2}})=K+V_{1}+V_{2}$$
每个原子轨道的基态能量为$\epsilon:(K+V_{1})\ket{1}=\epsilon \ket{1}$，cross energy为$V_{cross}=\bra{1}V_{2}\ket{1}=\bra{2}V_{1}\ket{2}$，hopping term为$t=-\bra{1}V_{2}\ket{2}=-\bra{1}V_{1}\ket{2}$。
我们总可以令$t$为实数通过改变其中一个态的相位因子。

### LCAO Done Right
我们现在放宽要求，不再规定原子轨道之间相互正交，我们可以定义重叠（overlap）矩阵$S$
$$S_{ij}=\bra{i}\ket{j}  $$
此时我们并不需要重叠矩阵是对角阵，态函数写作
$$\ket{\psi}=\sum_{i=1}^N\phi_{i} \ket{i} $$
类似于上文，我们可以得到“薛定谔方程”
>[!note] 非正交假设的约化薛定谔方程
>$$\mathscr{H}\phi=ES\phi$$
>定义和之前相同。

相同的我们还是通过变分取极值的方法
$$0=\frac{\partial E}{\partial \phi_{n}^*}=\frac{\sum_{m}\mathscr{H}_{nm}\phi_{m}}{\sum_{nm}\phi_{n}^*S_{nm}\phi_{m}}-\left( \frac{\sum_{nm}\phi^*_{n}\mathscr{H}_{nm}\phi_{m}}{\sum_{nm}\phi_{n}^*S_{nm}\phi_{m}} \right) \frac{\sum_{nm}S_{nm}\phi_{m}}{\sum_{nm}\phi_{n}^*S_{nm}\phi_{m}}$$
$$\Rightarrow \sum_{m}\mathscr{H}_{nm}\phi_{m}-E\sum_{m}S_{nm}\phi_{m}=0$$

其中$S$矩阵与分子轨道的形态有关系，例如$s$轨道没有nodes，所以对应的S矩阵都一定是正定的。

## Tight-Bonding chain
现在我们来考虑多粒子系统，也就是由一系列原子轨道形成的链状结构。我们称$n$原子的原子轨道为$\ket{n}$，并且轨道之间彼此正交
$$\bra{n}\ket{m}=\delta_{nm}\tag{13}  $$
总的波函数写作
$$\ket{\Psi}=\sum_{n}\phi_{n}\ket{n}   $$
之前我们讨论过约化薛定谔方程可以写作
$$\sum_{m}H_{nm}\phi_{m}=E\phi_{m}\tag{14}$$
其中$H_{nm}$表示哈密顿量的矩阵分量。
我们之前就说过，这并没有找到excat的基态，而是通过变分的方法，找到了最可能的由原子轨道组成的基态轨道。我们可以通过加入更多的原子轨道的方法来优化变分的方法。比如我们对于给定位置，不仅仅考虑$\ket{n}$轨道，还可以考虑$\ket{n,\alpha},\alpha=1,2,\cdots,p$，随着$p$增大，该方法越来越准确，找到的gs越来越准确。

我们计算的模型暂时只考虑每个位置一个轨道的情形：
$$H=K+\sum_{j}V_{j}$$
定义和之前一样。我们记
$$(K+V_{m})\ket{m}=\epsilon_{atomic}\ket{m}  $$
那么我们将矩阵元$H_{nm}$写作
$$H_{nm}=\bra{n}H\ket{m}=\epsilon_{atomic}\delta_{nm}+\sum_{j\neq m}\bra{n}V_{j}\ket{m}    $$
上式最后一项表示位于$m$原子位置的电子通过与非$m$位置原子相互作用可以被转移到$n$原子位置，我们规定这种转移只对于非常相近的两个原子之间可能发生
$$\sum_{j\neq m}\bra{n}V_{j}\ket{m}=\begin{cases}
&V_{0}\quad n=m \\
&-t\quad n=m+1 \\
&0\quad \text{ otherwise}
\end{cases}  \tag{15}$$
所以我们可以得到
$$H_{nm}=\epsilon_{0}\delta_{nm}-t(\delta_{n+1,m}+\delta_{n-1,m})\tag{16}$$
其中我们定义
$$\epsilon_{0}=\epsilon_{atomic}+V_{0}$$

### 方程通解
我们可以假设一个reasonable的通解形式：
$$\phi_{n}=\frac{e^{-ikna}}{\sqrt{ N }}\tag{17}$$
（其实这是根据Bloch Theorem可以得到的推论）这里带上了N原子模型的归一化系数。相比于之前的一维原子链振动模型，解形式中不含有频率指数项，是因为这是不含时薛定谔方程，如果考虑时间演化关系我们仍然需要$e^{iwt}$项。
将假设解带回原方程(14)，LHS可以写作
$$\sum_{m}H_{nm}\phi_{m}=\epsilon_{0} \frac{e^{-ikna}}{\sqrt{ N }}-t\left( \frac{e^{-k(n+1)a}}{\sqrt{ N }}+\frac{e^{-ik(n-1)a}}{\sqrt{ N }} \right)$$
RHS可以写作
$$E\phi_{n}=E \frac{e^{-ikna}}{\sqrt{ N }}$$
解得能谱
$$E=\epsilon_{0}-2t\cos(ka)\tag{18}$$
![[tightBinding1.png|300]]

类似于声子模型的色散关系，对于单原子链，我们可以写出
$$w^2=2 \frac{\kappa}{m}-2 \frac{\kappa}{m}\cos(ka)$$
但是，对于声子模型我们得到频率的平方，但是对于电子我们得到能量。
能谱也给出了tight bing chain的色散关系，色散关系有周期性$k\rightarrow k+2\pi/a$，并且在Brillouin zone boundary处群速度为0（$k=n\pi/a$）。
此时的电子不同于自由电子，存在一个允许的最小和最大能量值，我们将这段允许的能量本征态区间称为“能带（band）”。能带的宽度（4t）取决于原子核之间的距离。
![[tightBinding.png|300]]
对于上图右边，是N种态，每个对应一个原子轨道$\ket{n}$。由于Hilbert空间保持不变，所以左侧的band也被分为N个states，总能量的平均值还是保持$\epsilon_{0}$。

在能带的底端，色散关系是抛物线的，对其小量展开有
$$E(k)=\text{Constant}+ta^2k^2$$
这类似于自由电子的能量关系（色散关系）：
$$E_{free}(k)=\frac{\hbar^2k^2}{2m}$$
所以我们可以将能带底端的电子看作自由电子，规定有效电子质量（effective mass）：
$$\frac{\hbar^2k^2}{2m^*}=ta^2k^2\Rightarrow\quad m^*=\frac{\hbar^2}{2ta^2}$$
这里的$k$是crystal momentum而非电子的动量。

## 多能带结构
![[tightBinding2.png|300]]
电子优先填充低能级$\epsilon_{atomic}^2$，随着原子间间距减小，$\epsilon_{atomic}^2,\epsilon_{atomic}^1$能带之间开始出现重叠，会优先开始从下往上填充，然后填充重叠部分再到低能级能带充满。

多能带的来源可能是由于：
1.单原子per unit cell，但是每个原子有多个轨道
2.有复数个原子per unit cell

对于多能带情形，每个$k$对应多个可能能量值，我们称之间的差值为gap。

### Diatomic Tight Binding Chain
我们假设有如下结构的双原子链结构
$$-A-B-A-B-A-B-$$
对于A和B的轨道能量分别是$\epsilon_{A},\epsilon_{B}$，但hopping term都保持相同。
我们写出薛定谔方程
$$E\phi_{n}^A=\epsilon_{A}\phi_{n}^A-t(\phi_{n}^B+\phi_{n-1}^B)$$
$$E\phi_{n}^B=\epsilon_{B}\phi_{n}^B-t(\phi_{n}^A+\phi_{n+1}^A)$$
假设$$\phi_{n}^A=Ae^{ikna},\quad \phi_{n}^B=Be^{ikna}$$
那么
$$EA=\epsilon_{A}A-t(1+e^{-ika})B$$
$$EB=\epsilon_{B}B-t(1+e^{ika})A$$
特征方程写作
$$0=E^2-E(\epsilon_{A}+\epsilon_{B})+(\epsilon_{A}\epsilon_{B}-t^2(2+2\cos(ka)))$$
>[!note] 双原子色散关系
>$$ E_{\pm}(k)=\frac{1}{2}\Big(\epsilon_{A}+\epsilon_{B}\pm \sqrt{ (\epsilon_{A}-\epsilon_{B})^2+4t^2(2+2\cos(ka)) } \  \Big)$$

在极限$\epsilon_{A}=\epsilon_{B}$的条件下我们有
$$E=\epsilon\pm 2|t|\cos(ka)$$
在最小值附近展开能谱可得
$$E=\text{constant}+\frac{2t^2(ka)^2}{\sqrt{ (\epsilon_{A}-\epsilon_{B})^2+16t^2 }}$$
我们可以计算得到有效质量$m^*$为
$$m^*=\frac{\hbar^2\sqrt{ (\epsilon_{A}-\epsilon_{B})^2+16t^2 }}{4t^2a^2}$$

### Two Orbitals per Atom
假设一个原子有$\epsilon_{atomic}^A,\epsilon_{atomic}^B$两个轨道，我们有一条该种原子形成的链状结构，并且轨道之间保持正交。我们假设$t_{AA}$允许在给定原子轨道A的电子跳迁到相邻原子的A轨道。类似地定义$t_{BB}$。假设$V_{0}=0$。
此时两个轨道之间相互独立，是decoupled，所以可以直接写出两者的色散关系
$$E=\epsilon_{A}-2t_{AA}\cos (ka)$$
$$E=\epsilon_{B}-2t_{BB}\cos(ka)$$
若存在$t_{AB}$项允许位于一个原子的A轨道上的电子跳迁到相邻原子的B轨道上，那A，B之间产生耦合，原本的色散关系不再适用。
此时的薛定谔方程写作
$$E\phi_{n}^A=\epsilon_{A}\phi_{n}^A-t_{AA}\phi_{n+1}^A-t_{AA}^*\phi_{n-1}^A-t_{AB}\phi_{n+1}^B-t_{AB}^*\phi_{n-1}^B$$
$$E\phi_{n}^B=\epsilon_{B}\phi_{n}^B-t_{BB}\phi_{n+1}^B-t_{BB}^*\phi_{n+1}^B-t_{AB}\phi_{n+1}^A-t_{AB}^*\phi_{n-1}^A$$
带入假设解
$$\phi_{n}^A=Ae^{ikna}$$
$$\phi_{n}^B=Be^{ikna}$$
可得
$$EA=(\epsilon_{A}-t_{AA}e^{ika}-t_{AA}^*e^{-ika})A+(-t_{AB}e^{ika}-t_{AB}^*e^{-ika})B$$
$$EB=(\epsilon_{B}-t_{BB}e^{ika}-t_{BB}^*e^{-ika})B+(-t_{AB}e^{ika}-t_{AB}^*e^{-ika})A$$
我们规定
$$\begin{cases}
T_{AA}=t_{AA}e^{ika}+t_{AA}^*e^{-ika}=2\mathrm{Re}[t_{AA}e^{ika}] \\
T_{BB}=t_{BB}e^{ika}+t_{BB}e^{-ika}=2\mathrm{Re}[t_{BB}e^{ika}] \\
T_{AB}=t_{AB}e^{ika}+t_{AB}e^{-ika}=2\mathrm{Re}[t_{AB}e^{ika}]
\end{cases}$$
那么特征方程写作
$$0=E^2+E(T_{AA}+T_{BB}-\epsilon_{A}-\epsilon_{B})+(\epsilon_{A}-T_{AA})(\epsilon_{B}-T_{BB})-T^2_{AB}$$
所以能量写作
$$E=\frac{1}{2}(\epsilon_{A}+\epsilon_{B}-T_{AA}-T_{BB}\pm \sqrt{ (\epsilon_{A}-\epsilon_{B}-T_{AA}-T_{BB})^2-4T_{AB}^2 })$$