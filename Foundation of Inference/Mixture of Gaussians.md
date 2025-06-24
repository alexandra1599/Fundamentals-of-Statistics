# Mixture Of Gaussians

Family of probability distributions for modeling in cases where we have subpopulations; heterogeneous subpopulations.
So we will have different peaks for the different subpopulations and all of them are Gaussians.

Assume each subpopulation is Gaussian and we have 2 subpopulations for simplicity here : $N(\mu_1,\sigma_{1}^2), N(\mu_2,\sigma_{2}^2)$

Also need to specify the **size/proportion** of each subpopulation :
- $\pi \in (0,1)$ : proportion of first subpopulation (here $\pi$ is a ***parameter*** and not 3.14)
- $1 - \pi$ : proportion of the second subpopulation

**Mixture of Gaussians** is a continous distribution. PDF of a mixture of Gaussians (Unimodal/Multimodal) :

$f(x) = \pi \frac{1}{\sigma_1 \sqrt{2\pi}} e^{\frac{-(x-\mu_1)^2}{2\sigma_1^2}} + (1-\pi) \frac{1}{\sigma_2 \sqrt{2\pi}}e^{\frac{-(x-\mu_2)^2}{2\sigma_2^2}}$

$f(x) = \pi f_1(x) + (1-\pi) f_2(x)$

$f(x) \geq 0$ and $\int f(x)dx = 1$

So we have 5 parameters : $\mu_1, \mu_2, \sigma_1, \sigma_2, \pi$

A simple way to understand mixture of Gaussians has 2 steps : 
1) Sample the **latent** (don't get to observe) variable Z ~ Ber($\pi$)
2) Sample $X_1$ ~ $N(\mu_1, \sigma_1^2)$ and $X_2$ ~ $N(\mu_2, \sigma_2^2)$. They should both be **independent of Z**.
3) Define $X = ZX_1 + (1-Z)X_2$ with $Z \in {0,1}$ so when $Z = 1, X = X_1$ and when $Z = 0, X = X_2$

  $E(X) = E(ZX_1 + (1-Z)X_2) = E(Z)E(X_1) + E(1-Z)E(X_2)$

  $Var(X) = E(Var(X|Z)) + Var(E(X|Z))$

  $E(X|Z) = ZE(X|Z=1) + (1-Z)E(X|Z=0)$

  $Var(Z) = Var(1-Z)$

### Example 

$X = ZX_1 + (1-Z)X_2$

Z ~ Ber(0.25) so we have E(Z) = p = 0.25 and Var(Z) = $\frac{3}{16}$

$X_1$ ~ N(0,1) so we have E($X_1$) = 0 and Var($X_1$) = 1

$X_2$ ~ N(1,1) so we have E($X_2$) = 1 and Var($X_2$) = 1

a) Find E(X) and Var(X)

E(X) = E($ZX_1 + (1-Z)X_2$) = E(Z)E($X_1$) + E($X_2$) - E(Z)E($X_2$) = $0.25 * 0 + 1 - 0.25 * 1$ = 0.75

Var(X) = E(Var(X|Z)) + Var(E(X|Z)) with :
- E(X|Z=1) = E($X_1$) = 0
- E(X|Z=0) = E($X_2$) = 1
- E(X|Z) = ZE(X|Z=1) + (1-Z)E(X|Z=0) = 1 - Z
- **Var(E(X|Z)) = Var(1-Z) = Var(Z) = p(1-p) = $\frac{3}{16}$**
- Var(X|Z=1) = Var($X_1$) = 1
- Var(X|Z=0) = Var($X_2$) = 1
- **E(Var(X|Z)) = 1**
    
So we get Var(X) = 1 + $\frac{3}{16}$ = 1.1875
     
b) What is E($e^{Xt}$) for t=-1 ?

E($e^{-X}$) = E($e^{-X}$|Z=1) P(Z=1) + E($e^{-X}$|Z=0) P(Z=0)
            = pE($e^{-X_1}$) + (1-p)E($e^{-X_2}$)
            = 0.25E($e^{-X_1}$) + 0.75E($e^{-X_2}$)

E($e^{-X_1}$) = $e^{\frac{t^{2}\sigma^2}{2}} = e^{0.5}$

E($e^{-X_2}$) = $e^{-1 + 0.5} = e^{-0.5}$ 

E($e^{-X}$) = $0.25e^{0.5} + 0.75e^{-0.5}$ 


## Moment Generating Function of a normal Gaussian

$M_X(t) = E(e^{tX}) = e^{t\mu+\frac{t^2\sigma^2}{2}}$
