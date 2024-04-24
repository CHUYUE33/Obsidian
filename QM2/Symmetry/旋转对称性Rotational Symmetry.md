#QuantumMechanics 

## 关于z轴的旋转
我们记关于z轴旋转$\varphi$角度的算符为$\hat{R}_{z}(\varphi)$，有
$$\hat{R}_{z}(\varphi)\psi(r,\theta,\phi)=\psi'(r,\theta,\phi)=\psi(r,\theta,\phi-\varphi)$$
我们假设小角转动，再对转动后的态进行泰勒展开，最后可以将旋转算符化为（Stone 定理）：
$$\hat{R}_{z}(\varphi)=\exp{\left[ - \frac{i\varphi}{\hbar}\hat{L}_{z} \right]},$$
我们称$\hat{L}_{z}$为z轴转动的生成元。

接下来我们考察在转动变换下$\hat{x},\hat{p}$的变换关系。假设无限小转动
$$\hat{R}_{z}(\delta)\approx_{1}-\frac{i\delta}{\hbar }\hat{L}_{z}$$
那么$\hat{x}$变换为
$$\begin{align}
\hat{x'}&=\hat{R}^{\dagger} \ \hat{x} \ \hat{R}\approx\left( 1+\frac{i\delta}{\hbar}\hat{L}_{z} \right)\hat{x}\left( 1-\frac{i\delta}{\hbar}\hat{L}_{z} \right) \\
&=\hat{x}+\frac{i\delta}{\hbar}[\hat{L}_{z},\hat{x}]\approx \hat{x}-\delta \hat{y}
\end{align}$$
类似的我们可以得到$\hat{y'}=\hat{y}+\delta \hat{x},\hat{z'}=\hat{z}$，写成矩阵形式
$$\begin{pmatrix}
\hat{x'}\\\hat{y'}\\\hat{z'}
\end{pmatrix}=\begin{pmatrix}
1&-\delta&0 \\
\delta&1&0 \\
0&0&1
\end{pmatrix}\begin{pmatrix}
\hat{x}\\\hat{y}\\\hat{z}
\end{pmatrix}$$

## 三维空间中的旋转
关于$\vec{n}$方向的旋转可以写作
$$\hat{R}_{n}(\varphi)=\exp{\left[ -\frac{i\varphi}{\hbar}\vec{n}\cdot\hat{L} \right]}$$
任意在旋转变换后变换规则类似于位置算符的矢量称为“vector operator”，其数学定义式写作
$$[\hat{L}_{i},\hat{V}_{j}]=i\hbar \epsilon_{ijk}\hat{V}_{k}$$
例如我们直到的三个vector operator：$\hat{r},\hat{p},\hat{L}$
$$[\hat{L}_{i},\hat{r}_{j}]=i\epsilon_{ijk}\hat{r}_{k},\quad [\hat{L}_{i},\hat{p}_{j}]=i\epsilon_{ijk}\hat{p}_{k},\quad [\hat{L}_{i},\hat{L}_{j}]=i\epsilon_{ijk}\hat{L}_{k}$$

而"Scalar operator“表示单一的关于旋转变换保持不变的量，定义为
$$[\hat{L}_{i},\hat{f}]=0$$

根据是否与$\hat{L}$对易，可以定义vector和scalar。
是否与$\hat{\Pi}$对易，定义关系true/pseudo vector（scalar）。
![[Pseudo.png]]

>[!note] 大D系数
>考虑能量本征态$\psi_{nlm}$关于$\vec{n}$为轴的无限小转动，并将其写作
>$$\hat{R}_{\vec{n}}(\delta)\psi_{nlm}=\sum_{m'}D_{m'm}\psi_{nlm'}$$
>其中$$\begin{align}
D_{m'm}=&(1-i\delta m)\delta_{m',m} \\
&-i\delta \frac{n_{x}-in_{y}}{1}\sqrt{ l(l+1)-m(m+1) }\delta_{m',m+1} \\
&-i\delta\frac{ n_{x}+in_{y}}{2}\sqrt{ l(l+1)-m(m-1) }\delta_{{m',m-1}}
\end{align}$$

考虑无限小转动
$$\begin{align}
\hat{R}_{\vec{n}}(\delta)\psi_{nlm}&=\left( 1-\frac{i\delta}{\hbar}\vec{n}\cdot \hat{L} \right)\psi_{nlm} \\
&=\psi_{nlm}-\frac{i\delta}{\hbar}(n_{x}L_{x}+n_{y}L_{y}+n_{z}L_{z})\psi_{nlm} \\
&=\psi_{nlm}-\frac{i\delta}{\hbar}\left( \frac{n_{x}-in_{y}}{2}L_{+}+\frac{n_{x}+in_{y}}{2}L_{-}+n_{z}L_{z} \right)
\end{align}$$
带入升降算符的系数关系
$$\begin{align}
\hat{R}_{\vec{n}}\psi_{nlm}=&(1-i\delta m)\psi_{nlm} \\
&-i\delta \frac{n_{x}-in_{y}}{1}\sqrt{ l(l+1)-m(m+1) }\psi_{nlm+1} \\
&-i\delta\frac{ n_{x}+in_{y}}{2}\sqrt{ l(l+1)-m(m-1) }\psi_{nlm-1} \\
\equiv&\sum_{m'}D_{m'm}\psi_{nlm'}
\end{align}$$

高量中有更加general的大D系数表达式，上述的case非常的简单（甚至trivial）

## 简并Degeneracy
在量子力学中简并的主要来源是对称性，由于$[\hat{H},\hat{Q}]=0$，导致能量本征态在被$\hat{Q}$变换后保持静止：
$$\ket{\psi_{n}'}=\hat{Q}\ket{\psi_{n}},\quad \hat{H}\ket{\psi_{n}'}=\hat{H}\hat{Q}\ket{\psi_{n}}=\hat{Q}E_{n}\ket{\psi_{n}}=\mathbf{E}_{n}\ket{\psi_{n}}      $$
这就是说在存在对称性的系统中，原本能量的本征态被有对称性的算符作用后仍然是对应的能量本征态，此时再用能量描述系统就会出现简并。
但并不是所有的对称性都会导致简并的出现，如宇称算符作用后只会给对应态前加上正负号，不会改变态本身。
不出现简并的情况：只有single symmetry operator，或者multiplied symmetry operators that all commute。
如我们考虑有两个与$\hat{H}$对易的算符$\hat{Q},\hat{\Lambda}$，这两者之间彼此不对易，验证：
我们首先给出
$$\ket{g}=\hat{\Lambda}\ket{\psi}  $$
这也是$\hat{H}$的一个本征值为$E_{n}$的本征态。由于$\hat{Q},\hat{\Lambda}$之间不对易，所以不存在三个算符共同的完备本征基，所以一定会存在$\ket{\psi}$与$\hat{\Lambda}\ket{\psi}$不同的情形。
最典型的例子就是中心势场中的角动量，哈密顿量与绕任意轴的旋转（$\hat{L_{x}},\hat{L_{y}},\hat{L_{z}}$）对易，但三个旋转之间彼此不对易，所以单粒子中心势场谱中存在简并。
>[!note] 中心势场简并
>利用升降算符$\hat{L}_{\pm}$我们可知：$\psi_{nlm\pm_{1}}$也是$\hat{H}$的本征值为$E_{n}$的本征态
>$$(\hat{H}\hat{L_{\pm}}-\hat{L}_{\pm}\hat{H})\psi_{nlm}=0$$
>$$\Rightarrow \hat{H}\psi_{nlm\pm 1}=E_{n}\psi_{nlm\pm 1}$$
>我们可以看到，在有旋转对称性的条件下，态$\psi_{nlm}$的简并度为$2l+1$。

我们可以类比氢原子模型中的电子，能量本征态$\psi_{nlm}$的简并度为$d(n)=\sum_{l=0}^{n-1}(2l+1)=n^2$，简并度远大于只有旋转对称性的系统，额外的简并度是由库仑力的$\frac{1}{r}$带来的。详见Prob 6.34（346）。


## 旋转选择定则

### scalar operator选择定则
scalar operator$\hat{f}$与角动量算符的对易关系我们可以写作
$$[\hat{L_{z}},\hat{f}]=0,\quad [\hat{L_{\pm}},\hat{f}]=0,\quad [\hat{L}^2,\hat{f}]=0$$
接下来我们讨论本征态$\ket{n'l'm'},\ket{nlm}$之间的选择定则。（$\ket{nlm}$不一定需要时能量的本征态，这里我们只需要这个态最低限度满足是$\hat{L}^2,\hat{L_{z}}$的有量子数$l,m$的本征态即可，n的意义可以随便）
插入对易关系
$$\braket{ n'l'm'}[\hat{L_{z}},\hat{f}]\ket{nlm}=0  $$
$$\Rightarrow (m'-m)\bra{n'l'm'}\hat{f}\ket{nlm}=0  $$
类似的我们还有
$$\bra{n'l'm'}[\hat{L}^2,\hat{f}]\ket{nlm}=0  $$
$$\Rightarrow\quad[l'(l'+1)-l(l+1)]\bra{n'l'm'}\hat{f}\ket{nlm}=0  $$
这两个关系给出只有在$\Delta l=l'-l=0,\Delta m=m'-m=0$矩阵元$\bra{n'l'm'}\hat{f}\ket{nlm}$才不是0。
现在考虑升降算符带来的关系：
$$\bra{n'l'm'}[\hat{L_{+}},\hat{f}]\ket{nlm}=0  $$
$$\Rightarrow\quad B_{l'}^{m'}\bra{n' \ l' \ (m'-1)}\hat{f}\ket{n \ l \ m}-A_{l}^m\bra{n' \ l' \ m'}\hat{f}\ket{n \ l \ (m+1)}=0    $$
$$A_{l}^m=\hbar \sqrt{ l(l+1)-m(m+1) },\quad B_{l}^m=\hbar \sqrt{ l(l+1)-m(m-1) }$$
由前两条给出的限制关系，首先需要满足$m'=m+1,l'=l$，此时两个系数满足$B_{l}^{m+1}=A_{l}^m$，方程化简为
$$\bra{n'lm}\hat{f}\ket{nlm}=\bra{n'l(m+1)}\hat{f}\ket{nl(m+1)}    $$
由此我们可得，scalar operator矩阵元的取值与角标$m$无关。

>[!note] Scalar Operator选择定则
>$$\boxed{\bra{n'l'm'}  \hat{f}\ket{nlm}=\delta_{ll'}\delta_{mm'}\bra{n'l}\hat{f}\ket{nl}  } $$


###  Vector Operators选择定则
类似的我们先对vector operators定义升降算符：
$$\hat{V_{\pm}}\equiv \hat{V_{x}}\pm i \hat{V_{y}}$$
并且我们写出以下方程：
$$[\hat{L_{z}},\hat{V_{z}}]=0\tag{0}$$
$$[\hat{L_{z}},\hat{V_{\pm}}]=\pm \hbar\hat{V_{\pm}}\tag{1}$$
$$[\hat{L_{\pm}},\hat{V_{\pm}}]=0\tag{2}$$
$$[\hat{L_{\pm}},\hat{V_{z}}]=\mp \hbar  \hat{V_{\pm}}\tag{3}$$
$$[\hat{L_{\pm}},\hat{V_{\mp}}]=\pm 2\hbar  \hat{V_{z}}\tag{4}$$
我们通过将对易关系在两个不同基底下展开，来得到矩阵元不为0的条件和有不同角标m，V值矩阵元之间的关系。
对于$(1)$，可得
$$\bra{n'l'm'}\hat{L_{z}}\hat{V_{\pm}}\ket{nlm}-\bra{n'l'm'}\hat{V_{\pm}}\hat{L_{z}}\ket{nlm}=\pm \hbar \bra{n'l'm'}\hat{V_{\pm}}\ket{nlm}$$
$$\Rightarrow [m'-(m\pm 1)]\bra{n'l'm'}\hat{V_{\pm}}\ket{nlm}=0  \tag{5}$$
由（5）式可以得出，除非$m'=m+1$，否则$\hat{V_{\pm}}$矩阵元为0 。再带入（0）式可得以下关系
$$\bra{n'l'm'}\hat{V_{+}}\ket{nlm}=0\quad \text{unless m'=m+1}\tag{6}  $$
$$\bra{n'l'm'}\hat{V_{z}}\ket{nlm}=0\quad \text{unless m'=m}\tag{7}  $$
$$\bra{n'l'm'}\hat{V_{-}}\ket{nlm}=0\quad \text{unless m'=m-1}\tag{8}  $$
我们可以通过升降算符的定义式写出$\hat{V_{x}},\hat{V_{y}}$选择定则：
$$\bra{n'l'm'}\hat{V_{x}}\ket{nlm}=\frac{1}{2}\Big[\bra{n'l'm'}\hat{V_{-}}\ket{nlm}+\bra{n'l'm'}\hat{V_{+}}\ket{nlm}    \Big]  $$
$$\bra{n'l'm'}\hat{V_{y}}\ket{nlm}=\frac{i}{2}\Big[\bra{n'l'm'}\hat{V_{-}}\ket{nlm}-\bra{n'l'm'}\hat{V_{+}}\ket{nlm}    \Big]$$
剩下的对易关系$(2)-(4)$给出了关于量子数$l$的选择定则和非零矩阵元之间的关系，我们这里先直接给出
$$\bra{n'l'm'}\hat{V_{+}}\ket{nlm}=-\sqrt{ 2 }C_{m  1  m'}^{l \ 1 \ l'}\bra{nl'}\hat{V}\ket{nl}    \tag{9}$$
$$\bra{n'l'm'}\hat{V_{-}}\ket{nlm}=\sqrt{ 2 }C_{m -1  m'}^{l \ 1 \ l'}\bra{nl'}\hat{V}\ket{nl}    \tag{10}$$
$$\bra{n'l'm'}\hat{V_{z}}\ket{nlm}=C_{m0m'}^{l \ 1 \ l'}\bra{nl'}\hat{V}\ket{nl}    \tag{11}$$
其中系数$C_{m_{1}m_{2}M}^{j_{1}j_{2}J}$是CG系数（[[多粒子角动量耦合]]），CG系数只在$M=m_{1}+m_{2}$，$J=j_{1}+j_{2},j_{1}+j_{2}-1,\cdots, |j_{1}-j_{2}|$的条件下不为0。任意vector operator分量的矩阵元$\bra{n'l'm'}\hat{V_{i}}\ket{nlm}$不为零的条件为
$$\boxed{\Delta l=0,\pm 1,\quad\Delta m=0,\pm 1 }\tag{12}$$
<font color=##33CCFF>因为矩阵元值与m无关，所以我们一般取m=0带入方便计算。</font>
