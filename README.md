# PINNs on flat manifolds
Flat manifold is a manifold with zero Riemann-Christoffel tensor, which physically means that geometry on this manifold locally is the same as in Euclidean space. In the two-dimensional case, the existence of five flat manifolds is possible: a plane, a flat cylinder, a flat torus, a flat Mobius strip and a flat Klein bottle.
To solve differential equations on a flat manifold, we represent it as a rectangular plane, the edges of which are glued together in a particular way. Accordingly, the solution must satisfy the resulting conditions at the edges and this is achieved by adding an additional term to the loss function:
$$Loss_e = \frac{1}{K} \sum_{i=1}^{K}(NN(\textbf{x}^e_i) - NN(\textbf{x}^e_{k(i)}))^2,\ where\ \textbf{x}^e_{k(i)}\ -\ corresponding\ point\ for\ \textbf{x}^e_i$$
For example, in case of flat Mobius strip let rectangular plane has Cartesian coordinates $x,y$ where $x \in [0,2\pi],\ y \in [-1,+1]$. Edges $(0,y)$ and $(2\pi,y)$ must be glued together so that points $(0,-1)$ and $(2\pi,1)$ were the same. This makes the $Loss_e$ look like:
$$Loss_e = \frac{1}{N} \sum_{i=1}^{N}(NN(0,y) - NN(2\pi,-y))^2$$
In cases with other manifolds there will be other $Loss_e$ outlooks, which is very simple to obtain according to the scheme below:  

<p align="center"><img src="https://github.com/mikhakuv/PINNs-on-flat-manifolds/blob/main/scheme.png"><br><caption>(same arrows should be glued with direction taken into account)</caption></p>  


In this repository some examples with heat equation on flat Mobius strip can be found. The equation has the form:  
$$\frac{\partial u}{\partial t} = (\frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2}) + f(x,y,t)$$
$$where\ x\in [0,2\pi]\ y\in [-1,+1]\ t\in [0,1]$$
with given initial condition:  
$$u(x,y,0) = u_0(x,y)$$
Notable examples:  
* $u_0(x,y)=5\cdot exp(-\frac{8}{10}(x-\frac{3\pi}{2})^2 - 8(y+1)^2),\ f(x,y,t)=0$

initial condition:
<p align="center"><img src="https://github.com/mikhakuv/PINNs-on-flat-manifolds/blob/main/conditions/u_0_exp1.png"></p>  

solution:
<p align="center"><img src="https://github.com/mikhakuv/PINNs-on-flat-manifolds/blob/main/results/u_pred_exp1.gif"></p>  

same solution on the flat manifold:
<p align="center"><img src="https://github.com/mikhakuv/PINNs-on-flat-manifolds/blob/main/results/u_pred_surface_exp1.gif"></p>  

* $u_0(x,y)=0,\ f(x,y,t)=5\cdot exp(-\frac{3}{10}(x-\frac{3\pi}{2})^2 - (y+1)^2)\cdot sin(2\pi t)$

initial condition:
<p align="center"><img src="https://github.com/mikhakuv/PINNs-on-flat-manifolds/blob/main/conditions/u_0_exp2.png"></p>  

solution:
<p align="center"><img src="https://github.com/mikhakuv/PINNs-on-flat-manifolds/blob/main/results/u_pred_exp2.gif"></p>  

same solution on the flat manifold:
<p align="center"><img src="https://github.com/mikhakuv/PINNs-on-flat-manifolds/blob/main/results/u_pred_surface_exp2.gif"></p>  

* $u_0(x,y)=0,\ f(x,y,t)=5\cdot exp(-3(x-1-2(\pi-1)t)^2-5(y+1-2t)^2)$

initial condition:
<p align="center"><img src="https://github.com/mikhakuv/PINNs-on-flat-manifolds/blob/main/conditions/u_0_exp4.png"></p>  

solution:
<p align="center"><img src="https://github.com/mikhakuv/PINNs-on-flat-manifolds/blob/main/results/u_pred_exp4.gif"></p>  

same solution on the flat manifold:
<p align="center"><img src="https://github.com/mikhakuv/PINNs-on-flat-manifolds/blob/main/results/u_pred_surface_exp4.gif"></p>  

* $u_0(x,y)=0,\ f(x,y,t)=5\cdot sin(\frac{3x}{2}+2\pi t)\cdot sin(\pi y)$

initial condition:
<p align="center"><img src="https://github.com/mikhakuv/PINNs-on-flat-manifolds/blob/main/conditions/u_0_exp5.png"></p>  

solution:
<p align="center"><img src="https://github.com/mikhakuv/PINNs-on-flat-manifolds/blob/main/results/u_pred_exp5.gif"></p>  

same solution on the flat manifold:
<p align="center"><img src="https://github.com/mikhakuv/PINNs-on-flat-manifolds/blob/main/results/u_pred_surface_exp5.gif"></p>  
