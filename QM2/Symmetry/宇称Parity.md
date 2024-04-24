#QuantumMechanics 

## 一维宇称
我们将一维的宇称定义为空间的逆变换（spatial inversion）：
$$\hat{\Pi}\psi(x)=\psi'(x)=\psi(-x)$$
接下来我们给出宇称算符的三个性质
>[!note] $\hat{\Pi}$性质
>1. Unitary
>$$\hat{\Pi}\ket{\vec{r}}=\ket{-\vec{r}},\braket{ \vec{r}}\hat{\Pi}^{\dagger}=\braket{ -\vec{r}} \Rightarrow \bra{\vec{r'}}\hat{\Pi}^{\dagger}\hat{\Pi}\ket{\vec{r}}=\bra{-\vec{r'}}\ket{-\vec{r}}=\delta(\vec{r}-\vec{r'})=\bra{\vec{r'}}   \ket{\vec{r}}      $$
>$$\Rightarrow \boxed{\hat{\Pi}^{\dagger}\hat{\Pi}=\hat{I}}$$
>2. $\boxed{(\hat{\Pi})^2=\hat{I}}$
>$$(\hat{\Pi})^2\ket{\vec{r}}=\hat{\Pi}\ket{-\vec{r}}=\ket{\vec{r}},\quad \Rightarrow \hat{\Pi}^{-1}=\hat{{\Pi}}   $$
>3. Hermitian $\hat{\Pi}^{\dagger}=\hat{\Pi}$
>$$(\hat{\Pi})^2=\hat{I}=\hat{\Pi}^{\dagger}\hat{\Pi},\text{proofed}$$

算符在spatial inversion变换下为
$$\hat{Q'}=\hat{\Pi}^{\dagger}\hat{Q}\hat{\Pi}$$
所以位置、动量算符均为“奇宇称”（odd under parity）
$$\hat{x'}=\hat{\Pi}^{\dagger}\hat{x}\hat{\Pi}=-\hat{x},$$
$$\hat{{p'}}=\hat{\Pi}^{\dagger}\hat{p}\hat{\Pi}=-\hat{p},$$
也就是说，位置/动量算符与宇称算符满足反对易关系。
这也给出了任意算符如何变换
$$\hat{Q'}(\hat{x},\hat{p})=\hat{\Pi}^{\dagger}\hat{Q}(\hat{x},\hat{p})\hat{\Pi}=\hat{Q}(-\hat{x},-\hat{p})$$
我们称系统有倒转对称性（inversion symmetry）如果哈密顿量保持不变：
$$\hat{H'}=\hat{\Pi}^{\dagger}\hat{H}\hat{\Pi}=\hat{H}\Rightarrow [\hat{H},\hat{\Pi}]$$

如果哈密顿量描述质量为m的粒子处于一维势能$V(x)$，那么倒转对称性意味着势能是关于位置的偶函数
$V(x)=V(-x)$

接下来我们考察由inversion symmetry生发的两个性质。
我们会考虑关于宇称算符$\hat{\Pi}$的本征值和本征态，很容易证明，有如下本征关系
$\hat{\Pi}\psi_{n}(x)=\psi_{n}(-x)=\pm \psi_{n}(x)$
$\hat{\Pi}$的本征值为$\pm1$，我们可以由此将能量本征态分为两类
$\hat{\Pi}\ket{E_{i}}=\ket{E_{i}},\quad \hat{\Pi}\ket{E_{\alpha}}=-\ket{E_{\alpha}}    $

自然而然地，我们可以引申到对于宇称这个物理量守恒的讨论，在满足inversion symmetry时，自然有
$$\frac{d}{dt}\langle\hat{\Pi}\rangle=\frac{i}{\hbar}\langle [\hat{H},\hat{\Pi}]\rangle=0$$
所以宇称这个量在inversion symmetry的系统中应该为守恒量。
我们可以以谐振子为例，在$t=0$时刻为偶函数的谐振模式随时间演化会一直偶函数形式。
接下来我们采用宇称算符本征态的视角来看守恒性：
任意一个波函数我们写作
$$\psi(t)=\sum_{i}C_{i}\ket{E_{i}}+\sum_{\alpha}C_{\alpha}\ket{E_{\alpha}}  $$
那么
$$\begin{align}
&\bra{\psi(t)}\hat{\Pi}\ket{\psi(t)}   \\
=&\left[ \sum_{j} C_{j}^*e^{iE_{j}t/\hbar}\bra{E_{j}}+\sum_{\beta}C_{\beta}^*e^{iE_{\beta}t/\hbar}\bra{E_{\beta}}  \right]\cdot\left[ \sum_{i} C_{i}^*e^{iE_{i}t/\hbar}\ket{E_{i}}+\sum_{\alpha}C_{\alpha}^*e^{iE_{\alpha}t/\hbar}\ket{E_{\alpha}}  \right] \\
=&\sum_{i} |C_{i}|^2-\sum_{\alpha}|C_{\alpha}|^2  
\end{align}$$
可以看到对于时间的平均不含时，概率分布也不随时间改变。


## 三维宇称
类似的我们将inversion symmetry推广到三维
$$\hat{\Pi}\psi(\vec{r})=\psi'(\vec{r})=\psi(-\vec{r})$$
算符$\hat{}{r},\hat{p}$变为
$$\hat{r'}=\hat{\Pi}^{\dagger}\hat{r}\hat{\Pi}=-\hat{r},$$
$$\hat{p'}=\hat{\Pi}^{\dagger}\hat{p}\hat{\Pi}=-\hat{p}.$$
任意算符变换为
$$\hat{Q'}(\hat{r},\hat{p})=\hat{\Pi}^{\dagger}\hat{Q}(\hat{r},\hat{p})\hat{\Pi}=\hat{Q}(-\hat{r},-\hat{p})$$
>[!note] 举例
>找到角动量算符$\hat{L}$的宇称变换形式。
>根据上式，我们已有$\hat{L}=\hat{r}\hat{\times}p$，那么
>$$\hat{L'}=\hat{\Pi}^{\dagger}\hat{L}\hat{\Pi}=\hat{r'}\times \hat{p'}=(-\hat{r})\times(-\hat{p})=\hat{r}\times\hat{p}=\hat{L}$$
>我们把类似于角动量算符这样的在宇称变换下保持不变的矢量称为“赝矢量（pseudovector）”。以此区别于在宇称变换下改变符号的“true vector”。
>类似的我们将那些odd under parity的scalar定义为“赝标量（pseudoscalar）”，而那些even under parity的例如$\hat{r}\hat{\cdot}r$则是“true scalar”。
><font color=orange>注意这里赝矢量和赝标量的定义是刚刚好相反的！！！</font>
>$$\text{Scalar}\begin{cases}
\Big\{\hat{\Pi},\hat{f}\Big\}=0,\quad \text{pseudoscalar}  \\
\Big[\hat{\Pi},\hat{f}\Big]=0,\quad \text{ture scalar}
\end{cases}\quad \text{Vector}\begin{cases}
\Big\{\hat{\Pi},\hat{V}\Big\}=0,\quad \text{true vector} \\
\Big[\hat{\Pi},\hat{V}\Big]=0,\quad \text{pseudovector}
\end{cases}$$

在三维空间中我们可以将inversion symmetry描述为
$$V(\vec{r})=V(-\vec{r})$$
我们这里不加证明的给出，处于中心势场中的单电子的本征态波函数$\psi_{nlm}(r,\theta,\phi)=R_{nl}(r)Y_{l}^m(\theta,\phi)$也是宇称算符的本征态：
>[!note] 氢原子本征态的宇称变换
>$$\hat{\Pi}\psi_{nlm}(r,\theta,\phi)=(-1)^l\psi_{nlm}(r,\theta,\phi)$$

（其实证明很简单，先找出$\hat{\Pi}$在球坐标下对于函数的变换关系，然后将这个关系带入本征函数中去硬算）

## 宇称选择定则
选择定则告诉我们那些矩阵元在某种特定对称性下为零。对于宇称我们考虑电偶极子算符
$$\hat{P}_{e}=q\hat{r}$$
这个算符是odd under parity的：
$$\hat{\Pi}^{\dagger}\hat{P}_{e}\hat{\Pi}=-\hat{P}_{e}$$
现在考察处于$\psi_{n'l'm'}$和$\psi_{nlm}$之间的电偶极子算符矩阵元
$$\begin{align}
\bra{n'l'm'}\hat{P}_{e}\ket{nlm}&=-\bra{n'l'm'}\hat{\Pi}^{\dagger}\hat{P}_{e}\hat{\Pi}\ket{nlm} \\
&=  -\bra{n'l'm'}(-1)^{l'}\hat{P}_{e}(-1)^{l}\ket{nlm} \\
&=(-1)^{l'+l+1}\bra{n'l'm'}\hat{P}_{e}\ket{nlm}       
\end{align}$$
所以我们可以给出
>[!note] Laporte's rule
>$$\bra{n'l'm'}\hat{P}_{e}\ket{nlm}=0\quad \text{if} \ l+l' \ \text{is even}  $$
>这说明两个相同parity的态之间的电偶极子会消失。
>对于任意的odd under parity的算符，Laporte’s rule都是用。
>而对于even under parity的算符，规律刚好相反。



