#QuantumMechanics 

## Time independent perturbation
我们首先可以解出某种特定势函数下的薛定谔方程（无限深势阱）并得到一组完备基：$\{\ket{n^{(0)}}\}$，现在我们对这个势函数进行微扰，并研究在势函数微扰后的本征态将如何变化。
我们把一个含有扰动的势函数以如下形式进行描述，我们称$\hat{H}'$为扰动修正项，$\hat{H}^{(0)}$是选取的标准势场哈密顿量。
$$\hat{H}=\hat{H}^{(0)}+\lambda  \hat{H}'\tag{1}$$
其中$H_{0}$是我们已知的规范场的哈密顿量：
$$\hat{H_{0}}\ket{n^{(0)}}=E_{n}^{(0)}\ket{n^{(0)}}  \tag{2}$$

于此同时，我们将真实的本征能量和本征态以级数展开的形式书写（假设能写出这种形式），其中$E_{n}^{(1)}$表示一阶修正，以此类推
>[!note] 微扰展开通解
>$$\Rightarrow E_{n}=E_{n}^{(0)}+\lambda E_{n}^{(1)}+\lambda^2E_{n}^{(2)}+\cdots\tag{3}$$
>$$\Rightarrow\ket{n}=\ket{n^{(0)}}+\lambda \ket{n^{(1)}}+\lambda^2\ket{n^{(2)}} +\cdots  \tag{4}$$
并且任意阶的扰动态可以由无扰动时的本征基张成：
$$\ket{n^{(1)}}=\sum_{m}C_{nm}\ket{m^{(0)}}  \tag{5}$$


现在我们将general的能量本征方程展开
$$\begin{align}
(\hat{H}^{(0)}+\lambda  \hat{H}')&(\ket{n^{(0)}}+\lambda \ket{n^{(1)}}  +\cdots)\\
&=(E_{n}^{(0)}+\lambda E_{n}^{(1)}+\lambda^2E_{n^{(2)}}+\cdots)(\ket{n^{(0)}}+\lambda \ket{n^{(1)}}+\lambda^2\ket{n^{(2)}}+\cdots   )
\end{align}$$
上式两边展开并合并同类项得
$$\begin{align}
H^{(0)}\psi_{n}^{(0)}&+\lambda(H^{(0)}\psi_{n}^{(1)}+H'\psi_{n}^{(0)})+\lambda^2(H^{(0)}\psi_{n}^{(2)}+H'\psi_{n}^{(1)})+\cdots \\=&E^{(0)}_{n}\psi_{n}^{(0)}+\lambda(E_{n}^{(0)}\psi_{n}^{(1)}+E_{n}^{(1)}\psi_{n}^{(0)})+\lambda^2(E_{n}^{(0)}\psi_{n}^{(2)}+E_{n}^{(1)}\psi_{n}^{(1)}+E_{n}^{(2)}\psi_{n}^{(0)})+\cdots
\end{align}\tag{6}$$
观察上式，我们提取左右两边$\lambda,\lambda^2$项，一阶项：
$$H^{(0)}\psi_{n}^{(1)}+H'\psi_{n}^{(0)}=E_{n}^{(0)}\psi_{n}^{(1)}+E_{n}^{(1)}\psi_{n}^{(0)}\tag{7}$$
二阶项：
$$H^{(0)}\psi_{n}^{(2)}+H'\psi_{n}^{(1)}=E_{n}^{(0)}\psi_{n}^{(2)}+E_{n}^{(1)}\psi_{n}^{(1)}+E_{n}^{(2)}\psi_{n}^{(0)}\tag{8}$$
## 一阶展开项
我们已知
$$\hat{H}^{(0)}\ket{n^{(0)}}=E_{n}^{(0)}\ket{n^{(0)}}  $$
对于本征方程的展开式，我们提出$\lambda$一阶项：
$$\hat{H}^{(0)}\ket{n^{(1)}}+\hat{H}'\ket{n^{(0)}}=E_{n}^{(0)}\ket{n^{(1)}}+E_{n}^{(1)}\ket{n^{(0)}}    \tag{7}$$
上式左右两边同时乘以$\braket{ n^{(0)}}$有
$$\begin{align}
\braket{ n^{(0)}}\hat{H}^{(0)}\ket{n^{(1)}}+\bra{n^{(0)}}\hat{H}'\ket{n^{(0)}}=\bra{n^{(0)}}E_{n}^{(0)}\ket{n^{(1)}}+\bra{n^{(0)}}E_{n}^{(1)}\ket{n^{(0)}}        
\end{align}$$
对于RHS第一项，我们有$$$\bra{n^{(0)}}\hat{H}^{(0)}\ket{n^{(1)}}=\bra{\hat{H}^{(0)}n^{(0)}}\ket{n^{(1)}}=E_{n}^{(0)}\bra{n^{(0)}}\ket{n^{(1)}}$$，所以继续化简得到
>[!note] 一阶微扰能量表达式
$$\boxed{E_{n}^{(1)}=\bra{n^{(0)}}\hat{H'}\ket{n^{(0)}}  \tag{9}}$$

之前我们提到，任意微扰态$\ket{n^{(1)}}$都可以用无微扰时的本征态展开，现在我们让（7）式乘以左矢$\bra{m^{(0)}}$
先讨论$m\neq n$的情形：
$$\bra{m^{(0)}}\hat{H}^{(0)}\ket{n^{(1)}} +\bra{m^{(0)}}\hat{H}'\ket{n^{(0)}}=\bra{m^{(0)}}E_{n}^{(0)}\ket{n^{(1)}}+0=E_{n}^{(0)}\bra{m^{(0)}}\ket{n^{(1)}}   $$
因为我们有
$$\bra{m^{(0)}}\ket{n^{(1)}}=\bra{m^{(0)}}\sum_{p}C_{np}\ket{p^{(0)}}=C_{nm}    $$
所以
$$E_{m}^{(0)}\bra{m^{(0)}}\ket{n^{(1)}}+\bra{m^{(0)}}\hat{H}'\ket{n^{(0)}}=E_{n}^{(0)}C_{nm}    $$
$$\boxed{C_{nm}=\frac{\bra{m^{(0)}}\hat{H}'\ket{n^{(0)}}}{E_{n}^{(0)}-E_{m}^{(0)}}  }\tag{10}$$




$$\ket{n}=\ket{n^{(0)}}+\lambda \ket{n^{(1)}}    $$
$$\begin{align}
\bra{n}\ket{n}&=(\bra{n^{(0)}}+\lambda \bra{n^{(1)}}  )(\ket{n^{(0)}}+\lambda\ket{n^{(1)}}  )  \\
1&=\bra{n^{(0)}}\ket{n^{(0)}}+\lambda(\bra{n^{(0)}}\ket{n^{(1)}}+\bra{n^{(1)}}\ket{n^{(0)}}+O(\lambda^2)    )  
\end{align} $$
令$C_{nn}=i\delta$，那么
$$\begin{align}
\ket{n}&=\ket{n^{(0)}}+\lambda \sum_{m}C_{nm}\ket{m^{(0)}}  \\
&=(1+i\delta \lambda)\ket{n^{(0)}}+\lambda \sum_{m\neq n}C_{nm}\ket{m^{(0)}}  
\end{align}  $$
对于$+i\delta \lambda$，我们可以将其写作$e^{i\delta \lambda}$。（现在看来我也不知道这段话的意义是什么）
对于一阶微扰态$\ket{n^{(1)}}$，我们通过左右同时乘以$\bra{n^{(0)}}$的方法求出了具体系数的表达式：
>[!note] 一阶微扰态表达式
>$$\ket{n^{(1)}}=\sum_{m\neq n}C_{nm}\ket{m^{(0)}},\quad C_{nm}=\frac{H_{mn}'}{E_{n}^{(0)}-E_{m}^{(0)}}=,\quad H_{mn}'=\bra{m^{(0)}}\hat{H}'\ket{n^{(0)}}$$

## 二阶微扰
类似于一阶微扰时的操作，我们对（8）式乘以$\bra{n^{(0)}}$可得
$$\bra{n^{(0)}}H^{(0)}\ket{n^{(2)}}+\bra{n^{(0)}}H'\ket{n^{(1)}}=E_{n}^{(0)}\bra{n^{(0)}}\ket{n^{(2)}}+E_{n}^{(1)}\bra{n^{(0)}\ket{n^{(1)}} }+E_{n}^{(2)}\bra{n^{(0)}}\ket{n^{(0)}}         $$
由于$\bra{n^{(0)}}H^{(0)}\ket{n^{(2)}}=E_{n}^{(2)}\bra{n^{(0)}}\ket{n^{(2)}}$，所以LHS第一项与RHS第一项相等，所以上式化简为
$$E_{n}^{(2)}=\bra{n^{(0)}}H'\ket{n^{(1)}}-E_{n}^{(1)}\bra{n^{(0)}}\ket{n^{(1)}}\tag{11}    $$
我们有关系
$$\bra{n^{(0)}}\ket{n^{(1)}}=\sum_{m\neq n}C_{nm}\bra{n^{(0)}}\ket{m^{(0)}}=0    $$
所以
>[!note] 二阶微扰能量
>$$E_{n}^{(2)}=\bra{n^{(0)}}H'\ket{n^{(1)}}=\sum_{m\neq n}C_{nm}\bra{n^{(0)}}H'\ket{n^{(1)}}=\sum_{m\neq n}\frac{\bra{m^{(0)}}H'\ket{n^{(0)}}\bra{n^{(0)}}H'\ket{m^{(0)}}}{E_{n}^{(0)}-E_{m}^{(0)}}$$
>$$\boxed{E_{n}^{(2)}=\sum_{m\neq n} \frac{ | H_{mn}'|^2}{E_{n}^{(0)}-E_{m}^{(0)}} ,\quad H_{mn}'=\bra{m^{(0)}}H'\ket {n^{(0)}}  }\tag{12}$$