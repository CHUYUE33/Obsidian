#SolidStates #BookNote 
我们假设电子散射时间为$\tau$，在时间间隔$dt$内散射的概率为$dt/\tau$，被散射后的电子动量为$\vec{p}=0$。（对于所有末态动量平均之后为0）
所以我么你可以写出单个电子在$dt$时间内的变化：
$$\langle \vec{p}(t+dt)\rangle=(1-dt/\tau)(\vec{p}(t)+\vec{F}dt)+0\cdot (dt/\tau)$$
$$\Rightarrow\quad \frac{d\vec{p}}{dt}=\vec{F}-\frac{\vec{p}}{\tau}$$
$$\vec{F}=-e(\vec{E}+\vec{v}\times\vec{B})$$
$$\vec{p}(t)=\vec{p}_{initial}e^{-t/\tau}$$

## 外加电场
在稳态时有$d\vec{p}/dt=0$，所以
$$m\vec{v}=\vec{p}=-e\tau\vec{E}$$
电子移动产生的电流密度为
$$\vec{j}=-en\vec{v}=\frac{e^2\tau n}{m}\vec{E}$$
对于较为简单的情形我们可以通过$j=\sigma E$写出电导率：
$$\sigma=\frac{e^\tau n}{m}$$

## 外加磁场
额外添加磁场后最大的改变在于外力多了洛伦兹力项：
$$\frac{d\vec{p}}{dt}=-e(\vec{E}+\vec{v}\times\vec{B})-\frac{\vec{p}}{\tau}$$
稳态电流方程写作：
$$0=-e\vec{E}+\frac{\vec{j}\times \vec{B}}{n}+\frac{m}{ne\tau}\vec{j}$$
$$\Rightarrow \vec{E}=\hat{\rho}\vec{j},\quad\begin{cases}
&E_{x}=\frac{m}{ne^2\tau}j_{x}+ \frac{B_{z}}{ne}j_{y}+\left( -\frac{B_{y}}{ne} \right)j_{z} \\
&E_{y}=\left( -\frac{B_{z}}{ne} \right)j_{x}+\frac{m}{ne^2\tau}j_{y}+\frac{B_{x}}{ne}j_{z}  \\
&E_{z}=\frac{B_{y}}{ne}j_{x}+\left( -\frac{B_{x}}{ne} \right)j_{y}+\frac{m}{ne^2\tau}j_{z}
\end{cases}$$
通常情况下只有$B_{z}$方向不为零，其余磁场均为0，所以有
$$\hat{\rho}=\begin{pmatrix}
\frac{m}{ne^2\tau}& \frac{B}{ne}&0 \\
- \frac{B}{ne}& \frac{m}{ne^2\tau}&0 \\
0&0& \frac{m}{ne^2\tau}
\end{pmatrix}$$
与此同时，通过取逆我们即可得到电导率张量$\vec{J}=\hat{\sigma}\vec{E}$
$$\hat{\sigma}=\begin{pmatrix}\frac{ne^2\tau/m}{1+(eB\tau/m)^2} & -\frac{ne^2B\tau^2/m^2}{1+(eB\tau/m)^2} & 0 \\\frac{ne^2B\tau^2/m^2}{1+(eB\tau/m)^2}&\frac{ne^2\tau/m}{1+(eB\tau/m)^2}&0\\0&0&\frac{ne^2\tau}{m}\end{pmatrix}$$
