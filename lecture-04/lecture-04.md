---
title: Math 555E
author: Atabey Kaygun
date: Tuesday, March 15, 2022
incremental: true
---

# Model Building via Optimization

---

## Fit, Cost and Penalty

- Larger the fit, larger the similarity, smaller the penalty
- Larger the cost, smaller the similarity, larger the penalty
  
~~~ {.ditaa}

   Least Similar                      Most Similar
   Worst Fit ------------------------ Best Fit
 Highest Penalty                     Least Penalty 
 Highest Cost                        Least Cost

~~~

## Distance measures

+ $L^p$-distance for points in $\mathbb{R}^n$
<div class="fragment">
$$\sum_x\|f(x)-g(x)\|_p$$
</div>

+ Kullback-Leibler-divergence for distributions
<div class="fragment">
$$ \sum_x p(x) \log (p(x)/q(x)) $$
</div>

## Similarity measures

+ Cosine similarity
<div class="fragment">
$$Sim(x,y) = (x\cdot y)/\|x\|\|y\|$$
</div>

---

## Demo

---

# Supervised Learning

---

## Data and model

+ Data set $D$ consists of $(x,y)$
  - $x$ input
  - $y$ expected output
  
+ Model is a function $f(x,\theta)$
<div class="fragment">
$$  Cost(\theta) =  \sum_x dist(f(x,\theta),y) $$
</div>

+ Best model is one where Cost is minimized.

## Optimization

Gradient descent 

+ $F\colon \mathbb{R}^m\to \mathbb{R}$
  - We want $argmin_{\theta} F(\theta)$
  - We find it iteratively
    <div class="fragment">
    $$\theta_{n+1} = \theta_n + \gamma \nabla F(\theta_n)$$
    </div>
+ Optimal $\theta$ gives best fitting model.

## Regularization

+ In *Regularization* add a penalty term into the Cost function
<div class="fragment">
$$  Cost(\theta) =  \Psi(\theta) + \sum_x dist(f(x,\theta),y) $$
</div>
+ Occam's Razor = Optimal $\theta$ with minimal penalty

## Example

---

### Regression

+ Data: $X,y=(x_1^{(i)},\ldots,x_n^{(i)};y^{(i)})$
+ Cost: $\|y-\beta X\|$
+ $\ell_p$-regularization: $\|y-\beta X\| + \lambda \|\beta\|_p$ 
  - $p=1$: Lasso 
  - $p=2$: Ridge
  - $p=1$ and $p=2$: Elastic Net

---

### Demo

---

### K-means

+ Data: $X=(x_1^{(i)},\ldots,x_m^{(i)})\subseteq \mathbb{R}^m$
+ $p\colon X\to \{y_1,\ldots,y_k\}\subseteq \mathbb{R}^m$
<div class="fragment">
$$argmin_p \sum_x \|x-p(x)\|$$
</div>

---

### Demo

---
