**Polynomials** are functions of type $$P(n) = \Sigma _ {i=0} ^d a_i n^i$$
**Exponentials** are functions that have the time constant (n) in the exponents place$$a^n \ | \ a \ \epsilon \ N$$
Exponential FUNCTIONS grow faster than polynomial FUNCTIONS; this means that polynomial FUNCTIONS are more efficient for PROGRAMS

**Logarithm**$$a^{log_bc} = c^{log_ba}$$
$$log_ba=\frac{log_ca}{log_cb}$$
No matter what base that a logarithmic function is, log base any real number is equivalent to log base 2 in terms of asymptotic notation

**Polylogarithmically Bounded**
f(n) is Polylogarithmically bounzded if $f(n) = O()$

**Series**
Geometric series commonly used in [[Binary Trees]]
$$\Sigma _{i=0}^n A^i = \frac{A^{n+1}}{A-1}$$
Converging geometric series:$$\Sigma_{i=0}^\inf A^i = \frac{1}{1-A} \ | \ 0 < A < 1$$
Harmonic series:$$H_n = \Sigma_{k=1}^n\frac{1}{k}\geq \int^{n+1}
_1\frac{1}{x}$$
**Factorial**
Recurrence function
$$n! = \sqrt{2\pi n}\ \ (\frac{n}{e})^n$$
**Function Iteration**
Recurrence relation$$f^{(i)}(n) = f(f^{(i-1)}(n))$$
**Log * Function**
$$lg*n=min[i\geq 0 : lg^{(i)}(n)\leq1]$$
	In plain English, log * functions basically ask "how many times do I have to apply lg to this number so that it can become 1?"

**Fibonacci Numbers**
$$F_i = \frac{\phi^i - \phi ^i}{\sqrt{5}}$$