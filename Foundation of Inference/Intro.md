# Foundation of Inference

When you have data, the main 3 things you want are : 

1) Estimation : Estimator is a r.v
2) Confidence Interval
3) Hypothesis testing : find statistical evidence or not


## Statistical Model

Let the observed outcome of a statistical experiment (what generates the data) be a sample $X_1, ..., X_n$ of n iid random variables in some measurable space E ($E \in R$),
and denote by P their **common distribution**. A **statistical model** associated to that statistical experiment is a **PAIR** (E,($P_\theta)_{\theta \in O}$), where O is the parameter set.

Assume statistical model is **well specified** i.e. $\exists \theta$ s.t $P = P_{theta}$. Here, this particular theta is the **true parameter**. It is unknown. The aim of a statistical experiment
is to estimate $\theta$ or check it's properties.

Assume $O \subseteq \mathbb{R}^d, d \geq 1$. Here, the model is called **parametric**.

If O is infinite dimensional, the model is called **non-parametric**. This doesn't mean no parameter !

If O = $O_1 + O_2$ with $O_1$ finite dimensional (what we want to estimate) and $O_2$ infinite dimensional (called nuisance parameter), the model is called **semi-parametric**.

## Parametric Models 

1) 
