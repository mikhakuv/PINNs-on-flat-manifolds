# PINNs-on-surfaces
To solve differential equations on a surface, we represent it as a rectangular plane, the edges of which are glued together so that the resulting surface is homeomorphic to the desired surface. Accordingly, the solution must satisfy the resulting conditions at the edges and this is achieved by adding an additional term to the loss function:
$$Loss_e = \frac{1}{N} \sum_{i=1}^{N}(NN(\textbf{x}^e_i) - NN(\textbf{x}^e_{k(i)}))^2,\ where\ \textbf{x}^e_{k(i)}\ -\ corresponding\ point\ for\ \textbf{x}^e_i$$
For example, in case of Mobius strip let rectangular plane has Cartesian coordinates $x,y$ where $x \in [0,2\pi],\ y \in [-1,+1]$. Edges $(0,y)$ and $(2\pi,y)$ must be glued together so that points $(0,-1)$ and $(2\pi,1)$ were the same. This makes the $Losse_e$ look like this:
$$Loss_e = \frac{1}{N} \sum_{i=1}^{N}(NN(0,y) - NN(2\pi,-y))^2$$
In this repository some examples with heat equation on Mobius strip can be found. In cases with other surfaces there will be other $Loss_e$ outlooks(which is very simple to obtain) and possibly equations may take another form according to differential geometry.
