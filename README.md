# PINNs on flat manifolds
Flat manifold is a manifold with zero Riemann-Christoffel tensor, which physically means that geometry on this manifold locally is the same as in Euclidean space. In the two-dimensional case, the existence of five flat manifolds is possible: a plane, a flat cylinder, a flat torus, a flat Mobius strip and a flat Klein bottle.
To solve differential equations on a flat manifold, we represent it as a rectangular plane, the edges of which are glued together in a particular way. Accordingly, the solution must satisfy the resulting conditions at the edges and this is achieved by adding an additional term to the loss function:
$$Loss_e = \frac{1}{K} \sum_{i=1}^{K}(NN(\textbf{x}^e_i) - NN(\textbf{x}^e_{k(i)}))^2,\ where\ \textbf{x}^e_{k(i)}\ -\ corresponding\ point\ for\ \textbf{x}^e_i$$
For example, in case of flat Mobius strip let rectangular plane has Cartesian coordinates $x,y$ where $x \in [0,2\pi],\ y \in [-1,+1]$. Edges $(0,y)$ and $(2\pi,y)$ must be glued together so that points $(0,-1)$ and $(2\pi,1)$ were the same. This makes the $Loss_e$ look like:
$$Loss_e = \frac{1}{N} \sum_{i=1}^{N}(NN(0,y) - NN(2\pi,-y))^2$$
In this repository some examples with heat equation on flat Mobius strip can be found. In cases with other manifolds there will be other $Loss_e$ outlooks, which is very simple to obtain.
