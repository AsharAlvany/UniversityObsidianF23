$$f_w(x) = w \cdot \Phi(x)$$
$$y = mx + b$$
Where $f_w$ is the predictor and $w$ is the weight and $\Phi(x)$
**Residual:** The residual is $(w\cdot \Phi(x)) - y$ the amount by which prediction $f_w(x) = w \cdot \phi(x)$ overshoots the target
* Square loss: $Loss^2 (x, y, w) = (f_w(x) - y) ^2$
**Example:**
w = \[2, -1], $\Phi(x)$ \[2, 0], y = -1
Loss (x, y, z) = 25