# Uniform Distribution 

X ~ U[a,b]

1) $E[X] = \frac{a+b}{2}$
2) $Var(X) = \frac{(b-a)^2}{12}$
3) $P(X > c) = \frac{b-c}{b-a}$ with $c \in [a,b]$
4) $P(X \leq c) = \frac{c-a}{b-a}$ with $c \in [a,b]$

Let U,V be iid U ~ [0,1]

$E[|U-V|] = \int_0^1 \int_0^u (u-v)\ dvdu + \int_0^1 \int_u^1 (v-u)\ dvdu$

X ~ U[0,1]
 - **PDF :** $f_X(x) = 1$ for $x \in [0,1]$

X,Y ~ U[0,1]
 - **PDF of X+Y :** $f_{X+Y}(z) = \int_0^1 f_X(x)f_Y(z-x)dx$
