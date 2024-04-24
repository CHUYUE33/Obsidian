shankar chap10.

## 两粒子情形
对于一个两粒子的系统，我们可以这样表示一个系统的态：
$$\ket{\psi_1}\otimes\ket{\psi_2}$$
其中$\ket{\psi_1},\ket{\psi_2}$分别表示粒子1，粒子2的态。
这个“$\otimes$”可以看作是tensor product表示系统拥有双线性，或者看作直积。

我们假设一个粒子处于两个定态的叠加态：$\ket{\psi_1}=\alpha\ket{w_1^{(1)}}+\beta\ket{w_2^{(1)}}$
另一个粒子处于定态：$\ket{\psi_2}=\ket{\lambda_1^{(2)}}$
$$\begin{align}\Rightarrow \ket{\psi_1}\otimes\ket{\psi_2}&=(\alpha\ket{w_1^{(1)}}+\beta\ket{w_2^{(0)}})\otimes\ket{\lambda_1^{(2)}}\\
&=\alpha\ket{w_1^{(1)}}\otimes\ket{\lambda_1^{(1)}}+\beta\ket{w_2^{(1)}}\otimes\ket{\lambda_1^{(2)}} \end{align}$$
所以当我们对粒子1测量$\hat{\Omega}$，粒子2测量$\hat{\Lambda}$时，结果粒子1的$\Omega=w_1$，粒子2的$\Lambda=\lambda_1$的概率为$|\alpha|^2$；粒子1的$\Omega=w_2$，粒子2的$\Lambda=\lambda_1$的概率为$|\beta|^2$。
>[!note] 
>有两个粒子系统的量子态空间是由两个粒子自己的量子态空间$V_1,V_2$张成的：$V=V_1\otimes V_2$
>这意味着，如果$\{\ket{w_1^{(1)}},\ket{w_2^{(1)}},\cdots \}$是$V_1$空间的基，$\{\ket{\lambda_1^{(2)}},\lambda_2^{(2)},\cdots \}$是$V_2$空间的基，所以整个系统的基为：$$\{\ket{w_i^{(1)}}\otimes\ket{\lambda_j^{(2)}},\cdots \},\quad V=V_1\otimes V_2$$
>$\operatorname{dim}\Big(V_1\otimes V_2\Big)=\operatorname{dim}(V_1)\otimes\operatorname{dim}(V_2)$

说白了也就是告诉你双线性空间怎么凑新的基。
在这个规则下，一个只作用于$V_1$空间的算符$\hat{\Omega}^{(1)}$作用于直积基时可以写作：
$$\begin{align}\hat{\Omega^{(1)}}\Big(\ket{\psi_1^{(1)}}\otimes\ket{\psi_2^{(2)}}\Big)&=\hat{\Omega^{(1)}}\otimes\hat{I^{(2)}}\Big(\ket{\psi_1^{(1)}}\otimes\ket{\psi_2^{(2)}}\Big)\\
&=\Big(\hat{\Omega_1^{(1)}}\ket{\psi_1^{(1)}}\Big)\otimes\Big(\hat{I^{(2)}}\ket{\psi_2^{(2)}}\Big)\end{align}$$


### 两个在quadratic potential中的粒子
我们可以写出经典的哈密顿量表达式：
$$\hat{H}=\frac{P_1^2}{2m}+\frac{P_2^2}{2m}+\frac{1}{2}mw^2x^2_1+\frac{1}{2}mw^2x_2^2$$
由于量子化，不考虑相互作用，有：
$$\hat{H}^{(1)\otimes(2)}=\frac{(\hat{P}_1^{(1)}\otimes\hat{I}^{(2)})^2}{2m}+\frac{(\hat{I}^{(1)}\otimes\hat{P}_2^{(2)})^2}{2m}+\frac{1}{2}mw^2(\hat{X}_1^{(1)}\otimes\hat{I}^{(2)})^2+\frac{1}{2}mw^2(\hat{I}^{(1)}\otimes\hat{X}_2^{(2)})^2$$
其中和$\hat{P}_1,\hat{X}_1$相关的项我们可以合并写成$\hat{H}^{(1)}=\frac{(\hat{P}_1^{(1)})^2}{2m}+\frac{1}{2}mw^2(\hat{X}_1^{(1)})^2$，也就是单个粒子的哈密顿量。
我们可以验证，形如$\ket{n_1}\otimes\ket{n_2}$的态是上述$\hat{H}^{(1)\otimes(2)}$的本征态，对应能量本征值为$(N+1)\hbar w$

$$\begin{align} \hat{H}^{(1)\otimes(2)}\Big(\ket{n_1}\otimes\ket{n_2}\Big)&=(\hat{H}^{(1)}\otimes\hat{I}^{(2)}+\hat{I}^{(1)}\otimes\hat{H}^{(2)})\ket{n_1}\otimes\ket{n_2}\\ 
&=(\hat{H}^{(1)}\ket{n_1}\otimes\ket{n_2})+\ket{n_1}\otimes(\hat{H}^{(2)}\ket{n_2}) \\
&=\Big[(n_1+\frac{1}{2})\hbar w\Big]\ket{n_1}\otimes\ket{n_2}+\ket{n_1}\otimes\Big[(n_2+\frac{1}{2})\hbar w\Big]\ket{n_2} \\
&=(n_1+n_2+1)\hbar w\ket{n_1}\otimes\ket{n_2} \\
&=(N+1)\hbar w\ket{n_1}\otimes\ket{n_2}
\end{align}$$
其中$N=n_1+n_2,E_{tol}=E_1+E_2$
注意$\hat{H}^{(1)\otimes(2)}$是作用在空间$V_1\otimes V_2$上的哈密顿量，
所以$\{\ket{N}\}$给出了$V_1\otimes V_2$空间的一个完备基，有别于$\{\ket{n_1}\otimes\ket{n_2}\}$
其中$\{\ket{N}\}$是一个简并的基，有关系例如：
$$\ket{N=3}=\alpha\ket{n_1=1}\otimes\ket{n_2=2}+\beta\ket{n_1=2}\otimes\ket{n_2=1}$$
所以我们在只测量$\hat{H}^{(1)\otimes(2)}$之后大概率不能给出对于$\hat{H}^{(1)}\otimes\hat{I}^{(2)}$的准确预测。

出于更加真实的图景（考虑粒子间相互作用），两个粒子的哈密顿量会写作：
$$\hat{H}^{(1)\otimes(2)}=\hat{H}_1^{(1)}\otimes\hat{I}^{(2)}+\hat{I}^{(1)}\otimes\hat{H}^{(2)}+\hat{\Omega}^{(1)}\otimes\hat{\Lambda}^{(2)}$$
在这种情形$\ket{E_1}\otimes\ket{E_2}$就不再是$\hat{H}^{(1)\otimes(2)}$的特征根$\ket{E_{tol}}$




## 全同粒子的统计规律：Fermions和Bosons
因为在量子力学中我们无法追踪粒子的全部过程，所以两个相同粒子相互作用时，我们无法分辨哪个粒子是哪个。
假设粒子之间无相互作用，$\ket{E_1}\otimes\ket{E_2}$是$\hat{H}^{(1)\otimes(2)}$的本征态。
但是由于我们无法distinguish这些粒子，我们能做到的只能是测量total energy，也就是测量$E_{tol}=\alpha+\beta$，这意味着我们无法区分下列两种情形：
$$\begin{cases}E_1=\alpha,E_2=\beta\\ 
E_1=\beta,E_2=\alpha\end{cases}$$

更加详细表达，对于两例子系统的量子态应该有以下形式：
$$\ket{\alpha,\beta}=a\ket{E_1=\alpha}\otimes\ket{E_2=\beta}+b\ket{E_1}\ket{E_1=\beta}\otimes\ket{E_2=\alpha}$$
并且交换两个粒子的位置后仍然是线性相关的：
$$\ket{\beta,\alpha}=C\ket{\alpha,\beta}$$
这个条件要求：
$$\begin{cases}a=Cb\\b=Ca\end{cases}\Rightarrow C^2=1,C=\pm1$$

$$\Rightarrow \ket{\beta,\alpha}=\pm\ket{\alpha,\beta}$$
所以量子态要么是symmetric，要么是anti-symmetric的
由于电子是费米子，所以两个电子的能量不可能相同。

在两个粒子的情形，如果我们对$\hat{\Omega}$进行测量并用其本征态展开，可以将两全同粒子系统写作：
$$\ket{w_1,w_2}=\frac{1}{\sqrt{2}}(\ket{w_1}\otimes\ket{w_2}\pm\ket{w_2}\otimes\ket{w_1})$$


## 泡利不相容原理
对于费米子，如果两粒子有相同的本征态：
$$\Rightarrow \ket{w,w;A}=-\ket{w,w;A}=0$$
我们不可能拥有这种两个费米子相同的态。


## Spin-Statistic Theorem
在QFT中我们可以知道，有整数自旋$0,1,2,3,\cdots$的粒子是Bosons
(Higgs=0, photon=1, gravation=2)
有半自旋的粒子$\frac{1}{2},\frac{3}{2},\frac{5}{2},\cdots$是Fermions（如$e^-,p^+=\frac{1}{2}$, quarts,neutrians)