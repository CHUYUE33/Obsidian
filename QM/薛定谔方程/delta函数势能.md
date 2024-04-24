#QuantumMechanics 
## 束缚态与散射态
我们已经遇到定态薛定鄂方程的两类非常不同的解：对无限深方势阱和谐振子它们是可归一 化的，解由分立的指标 n 标记；对自由粒子它们是不可归一化的，解用一个连续的变量 k 标 记。前者本身就代表物理上可实现的态，而后者不是；两种情况下含时薛定谔方程的一般解都是定态解的叠加。这种区别的本质在于对应的状态不同，分别为<font color=orange>束缚态</font>和<font color=orange>散射态</font>。
对于一个一维系统，如果$V(x)$在两边都比粒子总能量$E$高，则粒子被限制在势阱内，在两个拐点之间运动，不能逃逸，这种状态我们称之为<font color=orange>束缚态</font>。另一方面，如果$E$在某一侧（或两侧）超过$V(x)$，则从无限远的粒子经过势场的减速或加速，然后折返回无限远处，我们称这种状态为<font color=orange>散射态</font>。

## $V(x)=-\alpha\delta (X)$势阱的散射
对于$E>0$的态，TISE写作：
$$-\frac{\hbar^2}{2m}\frac{d^2\psi_E}{dx^2}-\alpha\delta(x)\psi_E=E\psi_E$$
$$-\frac{\hbar^2}{2m}\frac{d^2\psi_E}{dx^2}=E\psi_E,for \ x<0 \ and \ x>0$$
$$\Rightarrow \begin{cases}\psi_E=Ae^{ikx}+Be^{-ikx},\quad x<0\\\psi_E=fe^{ikx}+Ge^{-kx},\quad x>0\end{cases}$$
边界条件：
首先我们说明对于薛定谔方程的标准边界条件是什么：
$$\begin{cases}1.\psi 连续 \\2.\frac{d\psi}{dx}在势无穷点外连续\end{cases}$$
第二个限制条件对于$\delta(x)$类型的势能很难起到作用，所以我们需要转化一下，基本思想是对薛定谔方程进行积分并取$\epsilon\rightarrow0$的极限：
$$-\frac{\hbar^2}{2m}\int_{-\epsilon}^{\epsilon}\frac{d^2\psi}{dx^2}dx+\int_{-\epsilon}^{\epsilon}V(x)\psi(x) dx=E\int_{-\epsilon}^{\epsilon}\psi(x)dx$$
$$\Rightarrow \Delta\Big(\frac{d\psi}{dx}\Big)\equiv\frac{\partial\psi}{\partial x}|_{+\epsilon}-\frac{\partial\psi}{\partial x}|_{-\epsilon}=\frac{2m}{\hbar^2}\int_{-\epsilon}^{\epsilon}V(x)\psi(x) dx=-\frac{2m\alpha}{\hbar^2}\psi(0)$$
接下来进行计算：
>1. $\psi_E(0^+)=\psi_E(0^-)$ $$\Rightarrow A+B=F+G$$
>2. $\psi_E'(0^+)-\psi_E'(0^-)=-\frac{2mx}{\hbar^2}\psi_E(0)$$$ \Rightarrow ik(F-G)-ik(A-B)=-\frac{2m\alpha}{\hbar}(A+B)$$$$F-G=A(1+2i\beta)-B(1-2i\beta),\quad \beta\equiv\frac{m\alpha}{\hbar^2k}$$

在一般的散射实验中， 若粒子从左侧入射，那么$\delta (x)$左侧会有向左的反射和向右的入射，右侧则只有向右的透射，所以$G=0$

联立上述B.C，可以写出
$$\begin{cases}B=\frac{i\beta A}{1-i\beta}\\F=\frac{A}{1-i\beta}\end{cases}$$
A是入射波振幅，B是反射波振幅，F是透射波振幅。

尽管平面波解在通常情况下（in the context of scattering）不能被归一化（normalized），但是我们对于粒子的反射与透射概率更加感兴趣，因为概率与概率幅的平方相关$|\psi|^2$，所以可以定义反射系数$R$：
$$R\equiv\frac{|\psi_R|^2}{|\psi_I|^2}=\frac{|Be^{-ikx}|^2}{|Ae^{ikx}|^2}=\frac{|B|^2}{|A|^2}=\frac{\beta^2}{1+\beta^2}$$
透射系数（Transmition coefficient）$T$：
$$T\equiv\frac{|\psi_T|^2}{|\psi_I|^2}=\frac{|Fe^{ikx}|^2}{|Ae^{ikx}|^2}=\frac{1}{1+\beta^2},\quad T+R=1$$
$$\boxed{R=\frac{1}{1+(2\hbar^2E/2m\alpha^2)},\quad T=\frac{1}{1+(m\alpha^2/2\hbar^2E)}}$$

由于分离变量法得出的散射定态薛定谔方程解是无法归一化的，所以和自由粒子的定态薛定谔方程分离变量解相同，只是给出了一个完备的数学基，真实粒子的状态应该是这些基的线性叠加，也就是说是多个平面波叠加形成的波包，也再次说明对于散射粒子和自由粒子，不存在定态。