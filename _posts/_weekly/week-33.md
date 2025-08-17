---
layout: weekly
title: "Week 33 Review: Cohomology meets Optimization"
week_number: 33
date: 2025-08-18
authors: [jorys, tanguy]
jorys_hours: 28.5
tanguy_hours: 31
highlight: "Found unexpected connections between optimization on manifolds and differential geometry"
---

## 📊 Week Overview

### Statistics
- **Total Hours**: 59.5 hours
- **Posts**: 12 (Jorys: 6, Tanguy: 6)
- **Streak Maintained**: ✅ Yes

## 🎯 Jorys's Progress

### Main Achievements
- Completed Hartshorne Chapter III on Cohomology
- Finally understood Serre duality and its applications
- Started exploring derived categories and triangulated categories

### Key Insights
1. **Cohomology as obstruction theory**: $H^1$ measures the failure of local-to-global principles
2. **Computational techniques**: When to use Čech vs. spectral sequences vs. derived functors
3. **Connection to deformation theory**: $\text{Ext}^1(\mathcal{F}, \mathcal{G})$ classifies extensions

### Challenges Faced
- Derived categories still feel abstract - need more concrete examples
- Spectral sequences convergence issues in non-proper cases

### Resources Discovered
- Huybrechts' "Fourier-Mukai Transforms" - excellent for derived category intuition
- Daniel Murfet's YouTube lectures on homological algebra

## 🎯 Tanguy's Progress

### Main Achievements
- Implemented proximal gradient methods with proven convergence rates
- Explored ADMM for distributed optimization
- Started investigating optimization on Riemannian manifolds

### Key Insights
1. **Splitting methods**: Decomposing problems into simpler subproblems (proximal operator)
2. **Acceleration**: Nesterov momentum gives $O(1/k^2)$ vs. $O(1/k)$ convergence
3. **Geometric optimization**: Natural gradient descent respects manifold structure

### Challenges Faced
- ADMM convergence for non-convex problems is subtle
- Implementing efficient proximal operators for complex regularizers

### Code Developed
```python
# Accelerated proximal gradient (FISTA)
def fista(f_grad, prox_g, x0, L, max_iter=1000):
    x, x_old = x0.copy(), x0.copy()
    t = 1
    for k in range(max_iter):
        y = x + (t - 1) / (t + 1) * (x - x_old)
        x_new = prox_g(y - (1/L) * f_grad(y), 1/L)
        t_new = (1 + np.sqrt(1 + 4*t**2)) / 2
        x_old, x, t = x, x_new, t_new
    return x
```

## 🔄 Cross-Pollination

### Joint Discoveries

**Optimization on Manifolds ↔ Differential Geometry**

Tanguy's work on Riemannian optimization connects directly to Jorys's differential geometry:
- The natural gradient uses the Fisher information metric (Tanguy)
- This is precisely the metric on statistical manifolds studied in information geometry (Jorys)
- Both involve parallel transport and geodesics!

**Proximal Operators ↔ Resolvent Operators**

Found a beautiful connection:
- Proximal operator: $(I + \lambda \partial f)^{-1}$ (Tanguy's optimization)
- Resolvent in functional analysis: $(I - \lambda A)^{-1}$ (related to Jorys's spectral theory)

## 📚 Joint Reading

Started reading together:
- **"Optimization Algorithms on Matrix Manifolds"** by Absil, Mahony, and Sepulchre
- Combines differential geometry with practical optimization
- Great bridge between our interests!

## 💡 Ideas for Collaboration

1. **Project**: Implementing sheaf cohomology computations using optimization techniques
   - Jorys provides the mathematical framework
   - Tanguy optimizes the computational algorithms

2. **Paper Review**: "Neural Networks and Topos Theory"
   - Combines category theory with machine learning
   - Schedule for next week

## 📝 Memorable Quotes

> "Cohomology is just the failure of exactness - but that failure contains all the interesting information!" - Jorys

> "Every optimization problem is secretly a projection onto a manifold" - Tanguy

## 🎯 Next Week's Goals

### Jorys
- [ ] Start Hartshorne Chapter IV (Curves)
- [ ] Understand the Riemann-Roch theorem
- [ ] Implement cohomology computations in SageMath

### Tanguy
- [ ] Deep dive into mirror descent and Bregman divergences
- [ ] Implement distributed ADMM
- [ ] Explore connections to game theory (minimax optimization)

### Joint
- [ ] Tuesday 3pm: Discuss optimization on Grassmannians
- [ ] Thursday 5pm: Work through Absil book Chapter 3
- [ ] Friday: Prepare for department seminar

## 🔗 Interesting Links

- [Tai-Danae Bradley's blog on Category Theory](https://www.math3ma.com/)
- [Distill.pub on optimization visualizations](https://distill.pub/)
- [nLab entry on cohomology](https://ncatlab.org/nlab/show/cohomology)

## 📈 Motivation Check

**Energy Level**: 8/10

Both feeling energized by the connections we're finding. The PhD application deadlines are approaching (December/January), but having this daily structure keeps us focused and productive. The mutual accountability is working perfectly!

**Quote for next week**:
> "Mathematics is not about numbers, equations, computations, or algorithms: it is about understanding." - William Paul Thurston

---

*See you next week for Week 34! 🚀*
