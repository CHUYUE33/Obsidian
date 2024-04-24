
--- 
title:Unitory Operator酉(幺正）算符
date::2023-09-1919:32
categories:
tags:

---
#QuantumMechanics  #Basic_Def  #Math
幺正算符$\hat{U}$的定义：
$$\hat{U}\hat{U}^\dagger=\hat{I}$$
满足这个性质的算符我们称之为幺正算符。
## 幺正算符的性质
>1.$\hat{U}$保证了希尔伯特空间上内积的一致性，即：$$<Ux,Uy>=<x,y>$$
>2.$\hat{U}$是满射的。（或者说$\hat{U}$是一个[[稠密集]]，这个定义等价但是较弱）
>3.两个幺正算符的乘积也是幺正算符。$$(UV)^\dagger(UV)=V^{\dagger}U^{\dagger}UV=\hat{I}$$

二维空间的旋转就是一个典型的幺正算符，这种旋转不改变向量之间的夹角和大小。



## 哈密顿Generator
我们可以将一个unitory operator写成哈密顿算符$\hat{G}$的形式：
$$\hat{U}=e^{-i\theta\hat{G}}=\sum\limits_n\frac{1}{n!}(-i\theta\hat{G})^n$$
如果有$\hat{G}^{\dagger}=\hat{G}$，那么$\hat{U}=\sum\limits_n\frac{1}{n!}(+i\theta\hat{U}^{\dagger})=e^{i\theta\hat{G}}$
所以有：$$\hat{U}^{\dagger}\hat{U}=\hat{I}$$
Queastion：（但是可以说明这种构造和$\hat{U}$之间是满射的吗，所有$\hat{U}$都可以找到对应的$\theta,\hat{G}$吗？）

当我们的变换参数$\theta$很小时，我们可以进行展开：
$$\hat{U}=\hat{I}-i\theta\hat{G}+\cdots$$
我们可以看到，这个第二项导致了$\hat{U}$对于右矢原本量的一些小改变
我们称$\hat{G}$为generator of $\hat{U}$。
Question：感觉这个$\theta$的意义不是很明确，或者说$\theta$的意义是什么？
关于比较数学本质的探讨可以看看这个：
https://www.zhihu.com/question/473993868/answer/2021501592

## 幺正算符与基变化
1.
${\ket{v_i}}$为态空间中的离散归一正交基，我们将受到$\hat{U}$作用后产生的新基记作：$\ket{\tilde{v_i}}$
由于幺正保内积，所以产生的新向量组还是一个正交归一的：
$$\bra{\tilde{v_i}}\ket{\tilde{v_j}}=\bra{v_i}\ket{v_j}=\delta_{ij}$$
要证明这个向量组是一个基，可以这样做：
$$U^\dagger\ket{\psi}=\sum\limits_ic_i\ket{v_i}$$
同时乘$\hat{U}$可得：
$$UU^\dagger\ket{\psi}=\sum\limits_ic_iU\ket{v_i}\Rightarrow\ket{\psi}=\sum\limits_ic_i\ket{\tilde{v_i}}$$
2.反过来，这个条件也是充分的，也就是说：
>若有：$$\begin{align}&\ket{\tilde{v_i}}=U\ket{v_i}\\&\bra{\tilde{v_i}}\ket{\tilde{v_j}}=\delta_{ij}\\&\sum\limits_i\ket{\tilde{v_i}}\bra{\tilde{v_j}}=\boldsymbol{I}\\&\bra{\upsilon_j}\boldsymbol{U}^{\dagger}=\bra{\tilde{\upsilon}}_{j}\end{align}$$

则会有：
$$\begin{align}\boldsymbol{U}\boldsymbol{U}^{\dagger}\ket{\upsilon_i}&=\sum\limits_{j}\boldsymbol{U}\ket{\upsilon_j}\bra{\tilde{\upsilon}_j}\ket{\upsilon_i}\\
&=\sum\limits_{j}\ket{\tilde{\upsilon}_j}\bra{\tilde{\upsilon}_j}\ket{\upsilon_i}\\
&=\ket{\upsilon}
\end{align}$$
（在$U$、$U^\dagger$之间插入原本基中”神奇的1”即可）

## 幺正矩阵
判断一个矩阵是否为幺正矩阵，我们可以考虑单位矩阵用幺正来表示：
$$\bra{\upsilon_i}\boldsymbol{U}\boldsymbol{U}^{\dagger}\ket{\upsilon_j}=\sum\limits_{k}\bra{\upsilon_i}\boldsymbol{U}\ket{\upsilon_k}\bra{\upsilon_k}\boldsymbol{U}^{\dagger}\ket{\upsilon_j}$$
$$\Rightarrow\sum\limits_{k}\boldsymbol{U}^{*}_{ki}\boldsymbol{U}_{kj}=\delta_{ij}$$
也就是说，一列元素与另一列元素的乘积之和（两列向量的内积）应该是个$\delta$
举个例子：在自旋为$\frac{1}{2}$的粒子态空间中的旋转矩阵：
$$R^{(1/2)}(\alpha,\beta,\gamma)=\begin{pmatrix}e^{-\frac{i}{2}(\alpha+\gamma)}\cos{\frac{\beta}{2}}&-e^{\frac{i}{2}(\gamma-\alpha)}\sin{\frac{\beta}{2}}\\e^{\frac{i}{2}(\alpha-\gamma)}\sin{\frac{\beta}{2}}&e^{\frac{i}{2}(\alpha+\gamma)}\cos{\frac{\beta}{2}}\end{pmatrix}$$

## 算符的幺正变换
现在我们来定义一种并非施行在矢量上的变换，而是对于算符的一种变换。
我们定义这样一种算符$A$的变换$\tilde{A}$是这样一个算符：它在基$\{\ket{\tilde{\upsilon_i}}\}$中的矩阵元等于算符$A$在基$\{\ket{\upsilon_i}\}$中对应的矩阵元（也就是说在不同基下使用相同坐标的矩阵），即：
$$\bra{\tilde{\upsilon}_i}\tilde{A}\ket{\tilde{\upsilon}_j}=\bra{\upsilon_i}A\ket{\upsilon_j}$$
带入新基的变换关系$\ket{\tilde{\upsilon}_i}=U\ket{\upsilon_i}$:
$$\bra{\upsilon_i}U^{\dagger}\tilde{A}U\ket{\upsilon_j}=\bra{v_i}A\ket{v_j}$$
$$\Rightarrow U^{\dagger}\tilde{A}U=A \quad or \quad \tilde{A}=UAU^{\dagger}$$

考虑算符幺正变换后对于本征矢的影响：
$$A\ket{\psi_a}=a\ket{\psi_a}$$
假设由于算符$U$作用$\ket{\psi_a}$变为$\ket{\tilde{\psi}_a}$，那么有：
$$\begin{align}\tilde{A}\ket{\tilde{\psi}_a}&=(UAU^{\dagger})\ket{\psi_a}=UA\ket{\psi_a}\\
&=aU\ket{\psi_a}\\&=a\ket{\tilde{\psi}_a}\end{align}$$
所以我们有关系：A的本征矢$\ket{\psi}$对应$\tilde{A}$的本征矢$\ket{\tilde{\psi}}$，本征值都为a。

我们有关系：$\tilde{F}(A)=F(\tilde{A})$