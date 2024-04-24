#SolidStates
晶体内部由ion，electrons，nucleus构成
nucleus+core electrons=+ZeV
valence electrons=-ZeV

Drude Theory:treat electrons as ideal gas,ion$\rightarrow$smaved out psotive background
$\Rightarrow$"electrons gas" or "jellium"
>[!note] $r_S$
>Linear density parameter, $r_S$ (AKA Wigner-Seitz radius)
>$$\frac{1}{n}=\frac{V}{N}=\frac{4}{3}\pi r_S^3$$
>Here $N$ is the number of electrons.
>$$r_S=\Big(\frac{3V}{4\pi N}\Big)^{1/3}$$
For typical metal,
$$2\le r_S\le 6 $$
in Bhor radius.

## Assumption of Drude model
>1. Neglect electron-ion interaction : <font color=orange>"free electron approximation"</font>
> Neglect electron-electron interactions : <font color=orange>"independent electron approximation"</font>
>2. Collisions are instantaneous and unspecified.(anything can e collise with)
>3. electrons  scatter with a probability$dt/\tau$,$\tau$ is scattering time,$dt$ is time interval
>4. average velocity after a collision is zero$<\vec{\Omega}>=0$,but $<|\vec{v}|>\neq0$.Collisions randomly scatter electrons
>5. Between collisions,electrons obey Newtow's law if there are external $\vec{B},\vec{E}$ field

>[!note] distribution of velocities, $g(\vec{v})$
>$g(\vec{v})=$ number of electrons/volume woth a velocity between $\vec{v}$ and $\vec{v}d+d\vec{v}$
>Total electron density $\Rightarrow \quad n=\int d\vec{v}g(\vec{v})$
>Maxwell Boltzmann:
>$$g(\vec{v})d\vec{v}=\Big(\frac{m}{2\pi k_BT}\Big)^{3/2}e^{-\frac{mv^2}{2k_BT}}d\vec{v}$$
>current density $\vec{J}=-ne\vec{v}=-e\int d\vec{v}g(\vec{v})\vec{v}$
>if $g(\vec{v})=g(|\vec{v}|)$, then $\vec{J}=0,\vec{E}=0$

## External constant field
Suppse there is an external field:$\vec{E}=E\hat{z}$
Newton's law:$$m\frac{d\vec{v}_i}{dt}=-e\vec{E}$$
$$\vec{v}_i(t)=\vec{v}_i(0)-(eE/m)t\Rightarrow\vec{v}_i(t)=\vec{v}_i-\frac{e\vec{E}}{m}(t-t_i)$$
Here $\vec{v}_i$ is velocity since most recent collisoin.
$$<\vec{v}_i(t)>=\frac{1}{N}\sum\limits_i\vec{v}_i-\frac{1}{N}\frac{e\vec{E}}{m}\sum\limits(t-t_i)$$
let's define mean scattering time $\tau=\sum\limits_i\frac{\tau_i}{N},\tau_i=t-t_i$,it is independet of $\vec{E},t,T$
$$<\vec{v}_i(t)>=\frac{-e\vec{E}}{m}\tau$$
We can figure out this one is <font color=orange>independent of velocity distribution</font>
current density will be:
$$\vec{J}=-ne<\vec{v}>=\frac{ne^2\tau}{m}\vec{E}$$
since Ohm's law $\vec{J}=\sigma\vec{E}$, so we have
$$conductivity\equiv \sigma=\frac{ne^2\tau}{m},\tau\sim10^{-14}s$$
This is called Drude conductivity.