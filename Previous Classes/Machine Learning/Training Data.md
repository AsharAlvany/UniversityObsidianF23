**Training Data:** list of scenarios or list of examples, in excel a list of rows where a row represents an instance or a scenario

$X_{train}$ \[("...10m$ dollars...", +1] ("...CS4375 exam1...", -1))
-partial specification of behavior
$X_{train}$ $\rightarrow$ Learner (learning algorithm) $\rightarrow$ f (predictor)
**Modeling:** the question of what types of predictors we should consider
**Inference:** is about how to compute y given x
**Learning:** how do you take data and produce a predictor to create an inference
**Target:** the characteristic that you are training for

#### Example
"abc@mail.com" $\rightarrow\rightarrow\rightarrow\rightarrow$ \[length>10 : 1, fracOfAlpha : 0.85, contain_@ : 1, endsWith_.com : 1, endsWith_.org : 0]
feature vector: \[1 0.85 1 1 0]
Definition: $\Phi(X) \ \ \epsilon \ \  R$  
For an input X, its feature vector is:
$\Phi(X) = [\Phi_1(x), ..., \Phi_d(x)]$

Linear Predictors
 
| Weight Vector w | Feature Vector $\Phi(x)$ |
| -------- | -------- |
| length>10 : -1.2 | length>10 : 1 | 
| fracOfAlpha : 0.6 | fracOfAlpha : 0.85 |
| contain_@ : 3 |  contain_@ : 1 |
| endsWith_.com : 2.2 | endsWith_.com : 1 |
| endsWith_.org : 1.4 | endsWith_.org : 0 |

w $\cdot$ $\Phi$(x) = $\Sigma_{i=1}^d w_i\Phi_i(x)$ 

weight: direction (neg or pos), magnitude (strong or weak)

$f_w(x) = sign(w\cdot \Phi(x)) = + 1$ if  $w\cdot \Phi(x) > 0$ $ -1 if $w\cdot \Phi(x) < 0$
w = \[2 , -1]
$\Phi(x)$ $\epsilon$ {(2, 0), (0, 2), (2, 4)}

