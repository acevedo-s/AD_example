Autodiff guide: https://www.tensorflow.org/guide/autodiff

In the notebook I take the second example from the tf guide and I compute the result both by hand and by automatic differentiation, using simple values for the variables involved.  

Definitions and concepts:

Let $x$ be a row vector that represents data, set to $[1,2,3]$. Let $W$ and $b$ be a weight matrix and a bias row vector filled with ones for simplicity.

With $x$, $W$ and $b$ we construct the new row vector

$$y = x . W + b.$$

The target function chosen by the tf autodiff guide  is 

$$\text{loss}(x,W,b) = 
\frac{\big(x_1 W_{11} + x_2 W_{21} + x_3 W_{31} + b_1 \big)^2 + 
\big(x_1 W_{12} + x_2 W_{22} + x_3 W_{32} + b_2 \big)^2}
{2}.$$

To check, we calculate here simbolically the partial derivative $\frac{\partial\text{loss}}{\partial{b_1}}$, which is 

$$\frac{\partial\text{loss}(x,W,b)}{\partial{b_1}} = 
x_1 W_{11} + x_2 W_{21} + x_3 W_{31} + b_1.
$$

PS: To understand the use of tf.GradientTape, read the cited guide. 
