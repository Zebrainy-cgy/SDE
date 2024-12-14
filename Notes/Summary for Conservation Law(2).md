## Theoretic Part: Conservation
### Scalar Conservation Law
First, we consider the simpliest conservation law: **scalar conservation law**. Its form shows:
$$
\frac{\partial \rho }{\partial t}+\nabla \cdot(\rho \mathbf{u})=0,
$$
where $\rho$ means the density of fluid, and $\mathbf{u}$ means its velocity. In fact, we can derive this equation from the mass conservation law.

> [!definition] Definition.[Flow Map]
> The **flow map** of particle $\mathbf{p}\in\mathbb{R}^{n}$ is a solution of the following odes:
$$
\begin{align}
\frac{\mathrm{d}\phi_{t_{0}}^{t}(\mathbf{p}) }{\mathrm{d}t}&=\mathbf{u}(\phi_{t_{0}}^{t}(\mathbf{p}),t_{0}+t ),\\ 
\phi_{t_{0}}^{0}(\mathbf{p})&=\mathbf{p}.
\end{align}
$$

Assume $\Omega\in \mathbb{R}^{n}$ and $\phi_{t_{0}}^{{k}}(\mathbf{x})$ be the flow map w.r.t $\mathbf{u}$, and 
$$
\Omega(t):=\phi_{t_{0}}^{{t}}(\Omega ),
$$
then by the conservation law:
$$
\int_{\Omega(t)}\rho(t,\mathbf{x})\mathrm{d}\mathbf{x}\equiv C.
$$
By Reynold's transport theorem, 
$$
\frac{\mathrm{d}}{\mathrm{d}t}\int_{\Omega(t)}\rho(t,\mathbf{x})\mathrm{d}\mathbf{x}=\int_{\Omega (t)}\frac{\partial \rho }{\partial t}\mathrm{d}\mathbf{x}+\int_{\partial \Omega(t)}\rho \mathbf{u}\cdot \mathbf{n}\mathrm{d}S= 0,
$$
then by the divergence theorem:
$$
\int_{\Omega (t)}\left( \frac{\partial \rho }{\partial t}+\nabla \cdot(\rho \mathbf{u}) \right)\mathrm{d}\mathbf{x}=0,\quad\forall \Omega (t).
$$
It means 
$$
\frac{\partial \rho }{\partial t}+\nabla \cdot(\rho \mathbf{u})=0.
$$
### Euler equations
If we neglect the viscosity of fluid, we get the **Euler equations** with the following form:
$$
\frac{\partial}{\partial t} \begin{bmatrix}
\rho  \\
\rho v \\
E \\
\end{bmatrix}+\nabla_{\mathbf{x}}\cdot \begin{bmatrix}
\rho v \\
\rho v \otimes v+p \\
v(E+p) \\
\end{bmatrix}=0.
$$



Where $\rho$ is the density, $v$ is the velocity, $\rho v$ is the momentum, $E$ is the energy and $p$ is the pressure. 
> [!theorem] Theorem.[Conservation of Momentum]
> The **conservation law of momentum** equals:
$$
(\rho v)_{t}+\nabla \cdot(\rho v \otimes v+p)=0.
$$

**proof:** For the ideal fluid, the force across a surface $S$ per area equals $p \mathbf{n}$. By the conservation of momentum,	
	$$
	\frac{\mathrm{d}}{\mathrm{d}t}\int_{\Omega(t)}(\rho v)\mathrm{d}\mathbf{x}+\int_{\partial \Omega (t)}p \mathbf{n}\mathrm{d}S=0,
	$$
Then by Reynold's transport theorem and divergent theorem, we have:
$$
\int_{\Omega(t)}\frac{\partial (\rho v)}{\partial t}+\int_{\partial \Omega(t)}(\rho v \otimes v)\cdot \mathbf{n}\mathrm{d}S+\int_{\partial \Omega (t)}p \mathbf{n}\mathrm{d}S=\int_{\Omega (t)}\frac{\partial (\rho v)}{\partial t}+\nabla \cdot(\rho v \otimes v+p)\mathrm{d} \mathbf{x}=0.
$$
So 
$$
(\rho v)_{t}+\nabla \cdot(\rho v \otimes v+p)=0.
$$
> [!theorem] Theorem.[Conservation of Energy]
> The **conservation law of energy** equals:
$$
(E)_{t}+\nabla \cdot(v(E+p))=0.
$$
where $E$ is the total energy of this system. Normally, $E=E_{\text{kinetic}}+E_{\text{internal}}$.

If we combine these three equations, we get the **Euler equations**.

### General Form
Assume the region $\Omega\in \mathbb{R}^{m}$, the general form of conservation law shows:
$$
\frac{\partial \mathbf{u}}{\partial t}+\nabla_{\mathbf{x}}\cdot(F(\mathbf{u}))=0,
$$
where $F:\mathbb{R}^{d}\rightarrow \mathbb{R}^{d}$, $\mathbf{u}:\mathbb{R}^{m}\times \mathbb{R}\rightarrow \mathbb{R}^{d}$. Its integration form: 
$$
\frac{\mathrm{d}}{\mathrm{d}t}\int_{\Omega}\mathbf{u}(\mathbf{x},t)\mathrm{d}\mathbf{x}=-\int_{\Omega}\nabla_{\mathbf{x}}\cdot(F(\mathbf{u}))\mathrm{d}\mathbf{x}=-\int_{\partial \Omega}F(\mathbf{u})\cdot \mathbf{n}\mathrm{d}S.
$$
We can derive the **Eulerian scheme** of conservation law by this form. To simplify the discussion, we show the case $m=d=1$ first. For the 1-dimensional case, we have 
$$
\frac{\partial u}{\partial t}+(f(u))_{x}= u_{t}+f'(u)u_{x}=0.
$$
### Characteristic Line 
For the system $$ u_{t}+f'(u)u_{x}=0, $$ the **characteristic line** satisfies: $$ x'(t)=f'(u(x(t),t)). $$We have: $$ \frac{\mathrm{d} u(x(t),t)}{\mathrm{d}t}=u_{x}x'(t)+u_{t}=f'(u)u_{x}+u_{t}=0. $$So $u(x(t),t) \equiv u(x(0),0)$, i.e., the solution along the characteristic line remains constant. We can derive the **Lagrangian scheme** of the conservation law by this form. If $m>1$ and $d=1$, i.e., $$ u_{t}+\nabla \cdot(f(u))=u_{t}+f'(u) \nabla\cdot u=0, $$the characteristic line satisfies: $$ \mathbf{x}'(t)=f'(u(\mathbf{x}(t),t)) \begin{bmatrix} 1 \\ 1 \\ \vdots \\ 1 \end{bmatrix}.$$
In the general case, $$ \mathbf{u}_{t}+\nabla\cdot (F(\mathbf{u}))=\mathbf{u}_{t}+J_{F}\nabla \cdot \mathbf{u}=0, $$ there are $d$ characteristic curves through each point. The curves 
$\mathbf{x}(t)$ in the $p$-th family satisfy: $$ \mathbf{x}'(t)=\lambda_{p}(\mathbf{u}(\mathbf{x}(t)),t)\begin{bmatrix} 1 \\ 1 \\ \vdots \\ 1 \\ \end{bmatrix}, $$ where $\lambda_{p}$ is the $p$-th eigenvalue of the matrix $J_{F}$. 
### One-dimensional conservation laws
Now, we give some examples about 1-dimensional conservation law.
#### Linear conservation law
If $f(u)=au$ with constant $a\in \mathbb{R}$, the equation shows:
$$
u_{t}+au_{x}=0,\quad u(x,0)=\varphi(x).
$$
The characteristic line $x(t;x_{0})=x_{0}+at$, it means that 
$$
u(x,t)=u(x-at,0)=\varphi(x-at).
$$
In this simple example, the characteristic lines are parallel with each other. So if $\varphi\in C^{k}(\mathbb{R})$, then $u\in C^{k}(\mathbb{R}^{2})$.
#### Burgers' equation
If $f(u)=\frac{1}{2}u^{2}$, the equation shows:
$$
u_{t}+uu_{x}=0,\quad u(x,0)=\varphi(x).
$$
It is **Burgers' equation**. The characteristic line $\phi(t;x_{0})$ satisfies:
$$
\frac{\mathrm{d}\phi }{\mathrm{d}t}=u(\phi(t;x_{0}),t),\quad \phi(0;x_{0})=x_{0}.
$$
By the definition of characteristic line, 
$$
u(\phi(t;x_{0}),t)\equiv u(\phi(0;x_{0}),0)=\varphi(x_{0}),
$$
it means 
$$
\phi(t;x_{0})=x_{0}+\varphi(x_{0})t.
$$
Then, for the equation $u$, we have:
$$
u(x,t)=u(x_{0},0)=\varphi(x_{0}),\quad x=x_{0}+\varphi(x_{0})t=x_{0}+ut.
$$
Now we can get the implicit form of solution:
$$
u(x,t)=\varphi(x-u(x,t)t).
$$
In this case, the characteristic lines **may intersect with each other.** So the classical solution $u$ doesn't exist even though $\varphi\in C^{\infty}(\Omega)$. In this case, we should consider the **shock wave** and **rarefraction.**
#### Traffic flow
Consider the flow of cars on a highway. Let $\rho$ denote the **density** of cars and $u$ the velocity. The mass conservation law shows 
$$
\rho_{t}+(\rho u)_{x}=0,
$$
but in this condition, $u$ is related to $\rho$. If there are few cars on the highway, the velocity $u$ can be large. On the contrary, in a traffic jam, vehicles move with slow speed. In the simplest model, we choose 
$$
u(\rho )=u_{\text{max}}\left( 1-\frac{\rho}{\rho_{\text{max}}} \right),
$$
it's also a **nonlinear conservation law**, and the characteristic lines may intersect as well. 

### Weak form and Entropy condition
In some condition, the nonlinear conservation law has no classical solutions. It means that we should consider the **discontinuous solutions,** then we should give the **weak form** of conservation law.

For the equation 
$$
u_{t}+\nabla_{\mathbf{x}}\cdot(f(u))=0,
$$
Consider **test functions** $\phi\in C_{c}^{\infty}(\mathbb{R}^{d}\times(0,+\infty))$, multiply the above function with $\phi$ and integrate over space and time, we have:
$$
\int_{0}^{\infty}\int_{\mathbb{R}^{d}}[\phi u_{t}+\phi 
\nabla_{{\mathbf{x}}}\cdot(f(u))]\mathrm{d}\mathbf{x}\mathrm{d}t=0,
$$
then by the Gauss-Green formula:
$$
\int_{0}^{\infty}\int_{\mathbb{R}^{d}}\phi u_{t}\mathrm{d}\mathbf{x}\mathrm{d}t=-\int_{\mathbb{R}^{d}}\phi(\mathbf{x},0)u(\mathbf{x},0)\mathrm{d}\mathbf{x}-\int_{0}^{\infty }\int_{\mathbb{R}^{d}}\phi_{t}u \mathrm{d}\mathbf{x}\mathrm{d}t,
$$
and 
$$
\int_{0}^{\infty}\int_{\mathbb{R}^{d}}[\phi \nabla_{\mathbf{x}}\cdot(f(u))]\mathrm{d}\mathbf{x}\mathrm{d}t=-\int_{0}^{\infty}\int_{\mathbb{R}^{d}}\nabla\cdot \phi f(u)\mathrm{d}\mathbf{x}\mathrm{d}t.
$$
So its weak form shows:
$$
\int_{0}^{\infty }\int_{\mathbb{R}^{d}}(f(u)\nabla \cdot \phi +u \phi _{t})\mathrm{d}\mathbf{x} \mathrm{d}t=-\int_{\mathbb{R}^{d}}\phi(\mathbf{x},0)u(\mathbf{x},0)\mathrm{d}\mathbf{x}.
$$
To garantee the uniqueness of weak solution, we should give the **entropy condition.** 
> [!definition] Definition.[Entropy Pair]
> If the $C^{1}$ functions $\psi$ and $\eta$ satisfies:
> $$
> \psi'(u)=\eta'(u)f'(u),
> $$
> then $(\psi,\eta)$ is called **entropy pair**, and $\eta$ is the entropy function and $\psi$ is the entropy flux.

> [!definition] Definition.[Entropy Condition]
> The function $u(\mathbf{x},t)$ is the **entropy solution** of the conservation law if, for all convex entropy functions and corresponding entropy fluxes, the inequality
> $$
> \eta(u)_{t}+\nabla \cdot \psi(u)\le 0
> $$
> is satisfied in the **weak sense**.

We can varify that all classical solutions satisfy the entropy condition.
Now we give an example about entropy solution:
> [!example] Example. 
> Consider the Riemann IVP of one-dimensional Burgers' equation 
> $$
> u_{t}+uu_{x}=0,\quad u(x,0)=\left\{
> \begin{align}  &u_{L},\quad x\le 0,\\
 & u_{R},\quad x>0.\\
> \end{align}
> \right.
> $$
> Take the entropy pair $\eta(u)=u^{2}$ and $\psi(u)=\frac{2}{3}u^{3}$, then the entropy condition reads 
> $$
> (u^{2})_{t}+\left( \frac{2}{3}u^{3} \right)_{x}\le 0.
> $$
> For smooth solutions of Burgers' equation this should hold with equality. If a discontinuity is present, we integrate $(u^{2})_{t}+\left( \frac{2}{3} u^{3}\right)_{x}$ over an infinitesmal rectangle near the discontinuous point, i.e. $[x_{1},x_{2}]\times[t_{1},t_{2}]$ and the discontinuity point $x_{0}$ lies in the interval $[x_{1},x_{2}]$, then:
> $$
> \begin{align} 
> &\int_{x_{1}}^{x_{2}}\int_{t_{1}}^{t_{2}}(u^{2})_{t}\mathrm{d}x \mathrm{d}t+\int_{x_{1}}^{x_{2}}\int_{t_{1}}^{t_{2}}\left( \frac{2}{3}u^{3} \right)_{x}\mathrm{d}x \mathrm{d}t \\ \\
=& (x_{2}-x_{1})(u_{L}^{2}-u_{R}^{2})+\frac{2}{3}\Delta t(u_{R}^{3}-u_{L}^{3})+O(\Delta t^{2}). \\
\end{align}
> $$
> Since the shock traving speed $s=\frac{\left[ \frac{1}{2}u^{2} \right]}{[u]}=\frac{1}{2}(u_{L}+u_{R})$, we have $x_{2}-x_{1}=\frac{1}{2}(u_{L}+u_{R})\Delta t$. Then the above integral shows:
> $$
> I=s \Delta t(u_{L}^{2}-u_{R}^{2})+\frac{2}{3}\Delta t(u_{R}^{3}-u_{L}^{3})+O(\Delta t^{2})=-\frac{1}{6}(u_{L}-u_{R})^{3}\Delta t+O(\Delta t^{2}).
> $$
> 
> 
The entropy condition satisfies iff $(u_{L}-u_{R})^{3}>0$, so the entropy shock wave exists iff $u_{L}>u_{R}$.
### Shock wave and Rarefraction
In this section, we discuss the **shock wave** and **rarefraction**. We take Burgers' equation with Riemann IVP for instance.

If $u_{L}>u_{R}$, there exists a unique weak solution 
$$
u(x,t)=\left\{
\begin{align}
u_{L},\quad & x<st \\
u_{R},\quad & x>st \\
\end{align}
\right.

$$
where $s=\frac{u_{R}+u_{L}}{2}$ is the **shock speed**, the speed at which the discontinuity travels. 
If there exists $l\subset \mathbb{R}^{2}$ which separates the plane to $\Omega_{1},\Omega_{2}$, and the solution is continuous on both $\Omega_{1}$ and $\Omega_{2}$, but discontinuous on $l$, this weak solution is called **shock wave**. The speed of the shock wave 
$$
s=\frac{f(u_{L})-f(u_{R})}{u_{L}-u_{R}}=\frac{[f]}{[u]}.
$$

If $u_{L}<u_{R}$, there are **infinitely many** weak solutions. One of these weak solutions is the **rarefraction wave**, it shows:
$$
u(x,t)=\left\{
\begin{align}
u_{L}\quad & x<u_{L}t, \\
\frac{x}{t}\quad & u_{L}t\le x\le u_{R}t, \\
u_{R}\quad & x>u_{R}t.
\end{align}
\right.
$$
This solution is **stable to perturbations** and is in fact the vanishing viscosity generalized solution.
## Numerical Part
### Linear Conservation Law
#### Discretization and Finite Difference Scheme
We start from the time-dependent Cauchy problem with **periodic boundary conditions** in one space dimension:
$$
\begin{align}
u_{t}+Au_{x}&=0,\quad x\in [0,1], t\ge 0, \\
u(x,0)&=u_{0}(x), \\
u(0,t)&=u(1,t),\quad \forall t\ge 0.
\end{align}
$$

And the mesh shows:
$$
h=\frac{1}{N},\quad x_{i}=ih(0\le i\le N), 
$$
with the time discretization 
$$
k\in \mathbb{R}^{+},\quad t_{n}=nk.
$$
It will also be useful to define $x_{j+\frac{1}{2}}:=\left( j+\frac{1}{2} \right)h$.
In the **finite difference(FD) scheme**, we mark $U_{j}^{n}\approx u(x_{j},t_{n})$, then approximate the derivative by differential scheme. The periodic boundary condition shows:
$$
U_{i+N}^{n}=U_{i}^{n}.
$$
Now we list some familiar FD methods for the linear problem:
- **Backward Euler:** $U_{j}^{n+1}=U_{j}^{n}-\frac{k}{2h}A(U_{j+1}^{n+1}-U_{j-1}^{n+1})$.
- **One-sided:** $U_{j}^{n+1}=U_{j}^{n}-\frac{k}{h}A(U_{j}^{n}-U_{j-1}^{n})$.
- **One-sided:** $U_{j}^{n+1}=U_{j}^{n}-\frac{k}{h}A(U_{j+1}^{n}-U_{j}^{n})$.
- **Lax-Friedriches:** $U_{j}^{n+1}=\frac{1}{2}(U_{j-1}^{n}+U_{j+1}^{n})-\frac{k}{2h}A(U_{j+1}^{n}-U_{j-1}^{n})$.
- **Leapfrog**: $U_{j}^{n+1}=U_{j}^{n-1}-\frac{k}{2h}A(U_{j+1}^{n}-U_{j-1}^{n})$.
- **Lax-Wendroff:** $U_{j}^{n+1}=U_{j}^{n}-\frac{k}{2h}A(U_{j+1}^{n}-U_{j-1}^{n})+\frac{k^{2}}{2h^{2}}A^{2}(U_{j+1}^{n}-2U_{j}^{n}+U_{j-1}^{n})$.
- **Beam-Warming:** $U_{j}^{n+1}=U_{j}^{n}-\frac{k}{2h}A(3U_{j}^{n}-4U_{j-1}^{n}+U_{j-2}^{n})+\frac{k^{2}}{2h^{2}}A^{2}(U_{j}^{n}-2U_{j-1}^{n}+U_{j-2}^{n})$.
We can write these form by:
$$
U^{n+1}=\mathcal{H}_{k}U^{n},
$$
where $\mathcal{H}_{k}$ is a $N\times N$ matrix. 
> [!remark] Remark. 
	 > Since the energy norm is conservative, a challenging topic is to design an energy stable numerical scheme for conservation law.
#### Local truncation error(LTE)
The **local truncation error** $L_{k}(x,t)$ is a measure of how well the difference equation models the differential equation locally. It is defined by replacing the approximate solution $U_{j}^{n}$ by the true solution $u(x_{j},t_{n})$. 
> [!definition] Definition.[Local truncation error]
> The **local truncation error(LTE)** is defined by:
> $$
> L_{k}(x,t):=\frac{1}{k}[u(x,t+k)-\mathcal{H}_{k}(u(\cdot,t);x)],
> $$
> where
> $$
> U_{k}(x,t+k)=\mathcal{H}_{k}(U_{k}(\cdot,t);x).
> $$

> [!definition] Definition.
> The method is of **order** $p$ if for all sufficiently smooth initial data with compact support, there is some constant $C_{L}$ such that 
> $$
> \|L_{k}(\cdot,t)\|\le C_{L}k^{p}.
> $$
> The method is **consistent** if 
> $$
> \lim\limits_{k\rightarrow 0} \left\|L_{k}(\cdot,t)\right\|=0.
> $$

> [!example] Example.
> Now we derive the LTE of Lax-Friedriches scheme:
> $$
> \begin{align}
> L_{k}(x,t)&=\frac{1}{k}\left[ u(x,t+k)-\frac{1}{2}(u(x-h),t)+u(x+h,t) \right] \\
&+\frac{1}{2h}A[u(x+h,t)-u(x-h,t)] \\
&=u_{t}+Au_{x}+\frac{1}{2}\left( ku_{tt}-\frac{h^{2}}{k}u_{xx} \right)+O(h^{2}).
> \end{align}
> $$
> Assume $\frac{k}{h}=O(1)$, then $L_{k}=O(k)$.
#### Stability
Now we can rewrite the definition of LTE by:
$$
u(x,t+k)=\mathcal{H}_{k}(u(\cdot,t);x)+kL_{k}(x,t).
$$
Define the **global error**
$$
E_{k}(x_{j},nk)=u(x_{j},nk)-U_{j}^{n},
$$
then since $\mathcal{H}_{k}$ is linear, we have:
$$
E_{k}(\cdot,t+k)=\mathcal{H}_{k}E_{k}(\cdot,t)-kL_{k}(\cdot,t).
$$
Then:
$$
E_{k}(\cdot,t_{n})=\mathcal{H}_{k}^{n}E_{k}(\cdot,0)-k\sum\limits_{i=1}^{n}\mathcal{H}_{k}^{n-i}L_{k}(\cdot,t_{i-1}).
$$
So:
> [!definition] Definition.
> The method is **stable** is for each time $T$ there is a constant $C_{S}$ and a value $k_{0}>0$ such that 
> $$
> \left\| \mathcal{H}_{k}^{n} \right\|\le C_{S}\quad \text{for all }nk\le T,\;k<k_{0}.
  $$

For linear difference methods, we have the following fundamental convergence theorem:

> [!theorem] Theorem.[Lax Equivalence Theorem]
> For a consistent linear method, stability is necessary and sufficient for convergence.

> [!example] Example.
> For the Lax-Friedriches method, the method is **stable** provided that
> $$
> \left| \frac{Ak}{h} \right|\le 1.
>  $$
>  And $C_{r}:=\frac{Ak}{h}$ is the **Courant number** of a numerical scheme.
#### The CFL condition
> [!definition] Definition.
> The **domain of dependence** $\mathcal{D}(\bar{x},\bar{t})$ is the collection of points $p$ that $u(\bar{x},\bar{t})$ depends on $u(p,0)$, and the **numerical domain of dependence** $\mathcal{D}_{k}(\bar{x},\bar{t})$ is the set of points $x$ for which initial data $u_{0}(x)$ could possibly affect the **numerical solution** at $(\bar{x},\bar{t})$.

> [!theorem] Theorem.[CFL condition]
> The CFL condition requires that 
> $$
> \mathcal{D}(\bar{x},\bar{t})\subset \mathcal{D}_{0}(\bar{x},\bar{t}),
> $$
> and the CFL condition is a **necessary condition** for stability.  

### Discontinuous Solution
In this section, we will talk about the **Riemann problem** for the scalar advection equation 
$$
\begin{align}
&u_{t}+au_{x}=0,\quad x\in \mathbb{R},\quad t\ge 0, \\
&u_{0}(x)=\left\{  
\begin{aligned} 
 &1\quad &x<0, \\
&0\quad &x>0.\\
\end{aligned}
\right.
\end{align}
$$
The exact solution is simply $u_{0}(x-at)$, but the analysis about the convergence of numerical methods fails because the LTE diverges near $x=at$. 
To apply the numerical schemes, we consider $\Omega=[-1,1]$ and the boundary value 
$$
u(-1,t)=u_{0}(-1-at),\quad u(1,t)=u_{0}(1-at),
$$
then set $a=1$, $\frac{k}{h}=0.5$, and apply the Lax-Friedriches scheme, Upwind scheme, Lax-Wendroff scheme and Beam-Warming scheme, respectively. It seems strange that for the Lax-Wendroff scheme and the Beam-Warming scheme, it shows high oscilliations near the discontinuous point. We should derive the concept of **modified equations** to explain this phenomenon.

#### Modified Equations
A useful technique to analyze these numerical schemes is to model these schemes by differential equations. It means that: there are other differential equations that are better models for the numerical scheme.
> [!example] Example.
> Consider Lax-Friedrichs scheme, its local truncation error(LTE) shows:
> $$
> L_{k}(x,t)=u_{t}+Au_{x}+\frac{1}{2}\left( ku_{tt}-\frac{h^{2}}{k}u_{xx} \right)+O(h^{2}),
> $$
> So for the equation 
> $$
> u_{t}+Au_{x}+\frac{1}{2}\left( ku_{tt}-\frac{h^{2}}{k}u_{xx} \right)=0,
> $$
> the LTE of this scheme comes $O(h^{2})$. To make the system easier to analyze, we use a manipulation such that 
> $$
> \begin{align} 
  u_{tt}&=-A u_{tx}-\frac{1}{2}\left( ku_{ttt}-\frac{h^{2}}{k}u_{xxt} \right) \\
 & = -A[-A u_{xx}+O(k)]+O(k) \\
 & =A^{2}u_{xx}+O(k).
> \end{align}
> $$
> Using $u_{tt}=Au_{xx}$, the modified equation shows:
> $$
> u_{t}+Au_{x}=\frac{h^{2}}{2k}\left( 1-\frac{k^{2}}{h^{2}}a^{2} \right)u_{xx}.
> $$

> [!exercise] Exercise.
> Show that the modified equation of Lax-Wendroff method is 
> $$
> u_{t}+Au_{x}=\frac{h^{2}}{6}a\left( \frac{a^{2}k^{2}}{h^{2}}-1 \right)u_{xxx}.
> $$
> 

#### Fourier Expansion and Wave Solutions
Now, we try to analyze the origin of highly oscillation solutions. First, we should consider the **wave solutions** with the form 
$$
u(x,t;\xi )=e^{i(\xi x-c(\xi )t)},
$$
while 
$$
u(x,t)=\int_{\mathbb{R}}\hat{u}(\xi ,0) u(x,t;\xi )\mathrm{d}\xi.
$$
Since 
$$
\hat{u}(\xi ,0)=\int_{\mathbb{R}}u_{0}(x)e^{-i \xi x}\mathrm{d}x,
$$
we have: for $| \xi| \rightarrow \infty$, $\hat{u}(\xi,0)=O\left( \frac{1}{| \xi|} \right)$.

#### Lax-Friedriches Scheme
First, we assume $\frac{ak}{h}<1$, i.e. the CFL condition is satisfied, the modified equation of Lax-Friedriches scheme is:
$$
u_{t}+Au_{x}=Du_{xx},
$$
while $D>0$. The wave solution $u(x,t;\xi)$ shows:
$$
u(x,t;\xi)=e^{i(\xi x-c(\xi )t)},\quad c(\xi )=A \xi -iD \xi ^{2}.
$$
In this condition, if $|\xi| \rightarrow \infty$, $|u(x,t; \xi)| \rightarrow 0$, i.e. the high frequency waves will eliminish.
#### Lax-Wendroff Scheme
Also, we assume $\frac{ak}{h}<1$ for the CFL condition. The modified equation of Lax-Wendroff scheme is:
$$
u_{t}+Au_{x}+Du_{xxx}=0,
$$
where $D>0$. The wave solution $u(x,t;\xi)$ shows:
$$
u(x,t;\xi)=e^{i(\xi x-c(\xi )t)},\quad c(\xi )=A \xi -D \xi ^{3}.
$$
Unfortunately, if $|\xi| \rightarrow \infty$, $|u(x,t; \xi)|=O(1)$. It means the high oscillations near the discontinuous point won't disappear.
Then we consider the velocity of the wave solutions. The **phase velocity** $c_{p}(\xi)$ shows the velocity of the wave, while the **group velocity** $c_{g}(\xi)$ shows the velocity of the envelope of the wave. The phase velocity of Lax-Wendroff scheme shows:
$$
c_{p}(\xi )=\frac{c(\xi )}{\xi }=A-D \xi ^{2}<A,
$$
while the group velocity shows:
$$
c_{g}(\xi )=\frac{\mathrm{d}c(\xi )}{\mathrm{d}\xi }=A-3D \xi ^{2}<A.
$$
It means that the high frequency waves will move slower than the original waves. So the oscillations will appear front of the discontinuous point.

### Nonlinear Problems and Conservative Methods
For nonlinear problems, we will face more troubles. For smooth solutions, the numerical method can be linearized, but for discontinuous solutions, the linearized method may not be a good model. For nonlinear problems, there are additional difficulties:
- The method might be **nonlinearly unstable**.
- The method might converge to a function that is not a weak solution of our original equation.
- The method may converge to the wrong weak solution, i.e., doesn't satisfy the entropy condition.
- The method may not converge at all.
> [!example] Example.
> Consider the **Burgers' equation** in the quasilinear form 
> $$
> u_{t}+uu_{x}=0,
> $$
> assume $U_{j}^{n}\ge 0$, then the **upwind scheme** shows:
> $$
> U_{j}^{n+1}=U_{j}^{n}-\frac{k}{h}U_{j}^{n}(U_{j}^{n}-U_{j-1}^{n}).
> $$
> This method is adequate for smooth solutions, but for discontinuous solutions, the numerical solution may totally wrong. For example, if the discrete form shows:
> $$
> U_{j}^{0}=\left\{
> \begin{aligned}
> 1\quad & j<0\\
> 0\quad & j\ge 0.\\
> \end{aligned}
> \right.
> $$
> It is easy to verify that $U_{j}^{n} \equiv U_{j}^{0}$. This solution is **obviously wrong**.
> So, we observe a **consistent** but **useless** scheme for nonlinear problems.
#### Conservative Methods
Luckily, there turns out to be a class of numerical methods that are **conservative** for nonlinear problems. If we choose forward Euler method for the time integral, we have:
$$
U_{j}^{n+1}=U_{j}^{n}-\frac{k}{h}[F(U^{n};j)-F(U^{n};j-1)].
$$
Where $F(U^{n};j)$ means the **numerical flux** at the point $x_{j}$.
The conservation form follows from the weak form of the conservation law, i.e.:
$$
\int_{x_{j-\frac{1}{2}}}^{x_{j+1/2}}u(x,t_{n+1})\mathrm{d}x=\int_{x_{j-\frac{1}{2}}}^{x_{j+1/2}}u(x,t_{n})\mathrm{d}x-\left[ \int_{t_{n}}^{t_{n+1}}f\left( u\left( x_{j+\frac{1}{2}},t \right) \right)\mathrm{d}t-\int_{t_{n}}^{t_{n+1}}f\left( u\left( x_{j-\frac{1}{2}} \right),t \right)\mathrm{d}t \right].
$$
Dividing by $h$ and using the definition of cell averages, this gives:
$$
\bar{u}_{j}^{n+1}=\bar{u}_{j}^{n}-\frac{1}{h}\left[ \int_{t_{n}}^{t_{n+1}}f\left( u\left( x_{j+\frac{1}{2}},t \right) \right)\mathrm{d}t-\int_{t_{n}}^{t_{n+1}}f\left( u\left( x_{j-\frac{1}{2}},t \right) \right)\mathrm{d}t \right].
$$
We should choose the numerical flux such that 
$$
F(U^{n};j)\sim \frac{1}{k}\int_{t_{n}}^{t_{n+1}}f\left( u\left( x_{j+\frac{1}{2}},t \right) \right)\mathrm{d}t.
$$
Assume $U_{j}^{n}\ge 0$, for Burgers' equation, the **upwind numerical flux** shows:
$$
F(U^{n};j):=\frac{1}{2}(U_{j}^{n})^{2}.
$$
The **Lax-Friedriches numerical flux** shows:
$$
F(U^{n};j):=\frac{h}{2k}(U_{j}^{n}-U_{j+1}^{n})+\frac{1}{2}(f(U_{j}^{n})+f(U_{j+1}^{n})).
$$
It's clear that the numerical flux plays an important role in the convergence and stability of the numerical method. We have the following demand for the numerical flux:
- Consistency: the numerical flux should converge to the true flux as the mesh size goes to zero. It means: 
$$
F(\bar{u},\bar{u},\ldots,\bar{u})=f(\bar{u}).
$$
- Lipschitz condition: the numerical flux should be **Lipschitz continuous** for each component of $U$.
- (optional) Monothonicity: the numerical flux should be **monotone** in the sense that if $U_{j}^{n}\le U_{j+1}^{n}$, then $F(U_{j}^{n})\le F(U_{j+1}^{n})$.
We can also derive the **two-step conservative procedure**, such as the **Richtmyer two-step Lax-Wendroff method**, which is:
$$
\begin{align} 
U_{j+\frac{1}{2}}^{n+\frac{1}{2}}&=\frac{1}{2}(U_{j}^{n}+U_{j+1}^{n})-\frac{k}{2h}[f(U_{j+1}^{n})-f(U_{j}^{n})], \\
U_{j}^{n+1}&=U_{j}^{n}-\frac{k}{h}\left[ f\left( U_{j+\frac{1}{2}}^{n+\frac{1}{2}}\right)-f\left( U_{j-\frac{1}{2}}^{n+\frac{1}{2}} \right) \right]. \\
\end{align}
$$
Set the numerical flux 
$$
F(U^{n};j):=f\left(\frac{1}{2}(U_{j}^{n}+U_{j+1}^{n})-\frac{k}{2h}[f(U_{j+1}^{n})-f(U_{j}^{n})]\right),
$$
it shows that the **Richtmyer two-step Lax-Wendroff method** is a conservative scheme. 

Assume that for $j<J$, $U_{j}^{n}\equiv u_{- \infty}$ and for $j\ge K$, $U_{j}^{n}\equiv u_{+ \infty}$, then a conservative scheme satisfies:
$$
h \sum\limits_{j=J}^{K}U_{j}^{N}=h \sum\limits_{j=J}^{K}U_{j}^{n}-(t_{N}-t_{n})[f(u_{+ \infty})-f(u_{- \infty})].
$$
This is the **discrete form** of conservation law.

If the initial value satisfies:
$$
h \sum\limits_{j=J}^{K}U_{j}^{0}=\int_{x_{J-\frac{1}{2}}}^{x_{K+\frac{1}{2}}}u_{0}(x)\mathrm{d}x,
$$
then we have 
$$
h \sum\limits_{j=J}^{K}U_{j}^{n}=\int_{x_{J-\frac{1}{2}}}^{x_{K+\frac{1}{2}}}u(x,t_{n})\mathrm{d}x.
$$
So this form guarantees the **conservation** of the numerical scheme.

#### Lax-Wendroff Theorem
Finally, we will introduce the **Lax-Wendroff Theorem**.
> [!theorem] Theorem.[Lax-Wendroff Theorem]
> Consider a sequence of grids indexed by $l=1,2,\ldots,$ with mesh parameters $k_{l},h_{l} \rightarrow 0$ as $l \rightarrow \infty$. Let $U_{l}(x,t)$ denote the numerical approximation computed with a consistent and conservative scheme on the $l$th grid. Suppose that $U_{l}$ converges to a function $u$ as $l \rightarrow \infty$, then $u$ is a weak solution of the conservation law.
## Reference
[1] Numerical Methods for Conservation Laws. Randall J.Leveque
[2] A Mathematical Introduction to Fluid Mechanics. Alexandre J.Chorin
