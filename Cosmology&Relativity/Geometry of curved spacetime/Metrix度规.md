#cosmology
首先，我们需要明确，在实际空间中，各个坐标并不一定有实际意义，而只是一种“label”，表示不同的时空位置。在不同的度规框架下，事件与事件之间的距离有不同的定义方式。
## 欧几里得度规
这是最简单最符合直觉的度规定义，坐标之间的差值表示了距离：
$$dl^2=dx^2+dy^2+dz^2$$

接下来我们考虑一些各向同性但是有着不同度规定义的模型：二维球面和二维马鞍面。
在球面上，圆的周长不再满足$C=2\pi R$（想象一个球冠）。
为了表示一个二维的球面，我们可以在三维平整欧几里得空间中约束得到一个球面，此时的度规仍然满足
$$dl^2=dx^2+dy^2+dz^2$$
球面方程
$$x^2+y^2+z^2=a^2$$
将直角坐标系转化为球坐标系，度规方程简化为
$$dl^2=dr^2+r^2d\phi^2+dz^2$$
带入球面方程的约束可得
$$dl^2=\frac{dr^2}{1-r^2/a^2}+r^2d\phi^2$$
>[!note] detail：
>$$x^2+y^2+z^2=a^2\Rightarrow dz=\frac{xdx+ydy}{-z},$$
>$$\begin{align}
dz^2&=\frac{1}{z^2}(x^2dx^2+y^2dy^2+2xydxdy) \\
&=\frac{1}{a^2-(x^2+y^2)}\Big[r^2\cos^2 \phi(\cos\phi dr-r\sin\phi d\phi)^2+r^2\sin^2\phi(\sin \phi dr+r\cos \phi d\phi)^2 \\
&\quad+2r^2\sin \phi\cos \phi(\cos \phi dr-r\sin \phi d\phi)(\sin \phi dr+r\cos \phi d\phi)\Big] \\
&=\frac{r^2}{a^2-r^2}\Big[\cos^2\phi(\cos^2\phi dr^2+r^2\sin^2\phi d\phi^2-2r\cos \phi\sin \phi d\phi dr) \\
& \quad +\sin^2\phi(\sin^2\phi dr^2+r^2\cos^2\phi d\phi^2+2r\sin \phi\cos \phi drd\phi) \\
&\quad+2\sin \phi\cos \phi(\sin\phi \cos \phi dr^2+r\cos^2\phi\cos \phi drd\phi-r\sin^2\phi drd\phi-r^2\sin \phi\cos \phi d\phi^2)\Big] \\
&=\frac{r^2}{a^2-r^2}dr^2
\end{align}$$


## 固有时间（proper time）
固有时间定义为在固定的位置进行的测量（即$dx=dy=dz=0$的条件下）
$$d\tau=\sqrt{ -\frac{ds^2}{c} }$$
对于不同的度规中$ds$表达式不同对应的固有时表达式也不同
>[!note] Example
>Minkowski Metric:
>$$ds^2=-c^2dt^2+dx^2,\quad d\tau^2=dt^2-\frac{dx^2}{c^2},\quad \tau=\int  \, dt\sqrt{ 1-\frac{1}{c^2}\left( \frac{dx}{dt} \right)^2 } $$


类似的我们可以定义固有距离（proper distance）的概念，即要求测量的两个事件需要在某一个参考系下同时发生，在该参考系下测得的距离为固有距离（即$dt=0$时得到的距离）。
## Schwarzchlid Metric
施瓦西度规是对于中心质量恒定为M的天体体系附近的重力场分布（最简单的Einstein场方程的解）的描述：
$$ds^2=-\left( 1- \frac{r_{s}}{r} \right)c^2dt^2+\frac{dr^2}{\left( 1-\frac{r_{s}}{r} \right)}+r^2(d\theta^2+\sin^2\theta d\phi^2),\quad r_{s}=\frac{2GM}{c^2}$$
为了计算径向的距离，我们需要$d\theta=d\phi=dt=0$，所以
$$\text{距离}=\int_{r_{1}}^{r_{2}}  \frac{dr}{\sqrt{ 1-\frac{rs}{r} }}$$