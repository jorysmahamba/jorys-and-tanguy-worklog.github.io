---
layout: post
title: "Sheaf Cohomology & Spectral Sequences"
author: jorys
date: 2025-08-17 21:45:00 +0200
categories: [algebraic-geometry, cohomology]
tags: [schemes, sheaves, cohomology, spectral-sequences]
hours: 6.5
math: true
resources:
  - name: "Hartshorne Ch. III §5-7"
    url: "#"
  - name: "Vakil's Rising Sea §18"
    url: "https://math.stanford.edu/~vakil/216blog/FOAGnov1817public.pdf"
  - name: "Stacks Project - Cohomology"
    url: "https://stacks.math.columbia.edu/tag/01X8"
summary: "Finally understood the geometric interpretation of higher cohomology groups and worked through Serre duality."
---

## Today's Focus

Productive session working through Hartshorne Chapter III. Finally understood the geometric interpretation of higher cohomology groups!

## Key Insights

### Cohomological Dimension

For a coherent sheaf $\mathcal{F}$ on a projective scheme $X$, we have the fundamental vanishing theorem:

$$H^i(X, \mathcal{F}(n)) = 0 \text{ for } i > 0 \text{ and } n \gg 0$$

This has deep implications for understanding the global sections functor. The twist by $\mathcal{O}(n)$ essentially "kills" higher cohomology for sufficiently positive $n$.

### Serre Duality

The pairing between $H^i(X, \mathcal{F})$ and $H^{n-i}(X, \omega_X \otimes \mathcal{F}^∨)$ is starting to make sense. The key observation:

$$H^n(X, \omega_X) \cong k$$

This gives us a perfect pairing:

$$H^i(X, \mathcal{F}) \times H^{n-i}(X, \omega_X \otimes \mathcal{F}^∨) \to H^n(X, \omega_X) \cong k$$

## Technical Details

Worked through the spectral sequence:

$$E_2^{p,q} = H^p(X, \mathcal{H}^q(\mathcal{F}^•)) \Rightarrow H^{p+q}(X, \mathcal{F}^•)$$

The convergence is subtle - need to be careful about the filtration.

## Computational Example

Computed $H^1(\mathbb{P}^2, \mathcal{O}(-3))$ using Čech cohomology:
- Cover $\mathbb{P}^2$ with standard affine opens $U_i = \{x_i \neq 0\}$
- The Čech complex gives us the vanishing directly
- Result: $H^1(\mathbb{P}^2, \mathcal{O}(-3)) = 0$

## Questions/Stuck Points

1. Still struggling with the derived category perspective - when is it really necessary?
2. How does this connect to deformation theory? The tangent space $T^1$ should be $H^1$ of something...
3. Need to understand the computational tools better - when to use Čech vs. spectral sequences?

## Tomorrow's Plan

- [ ] Read about relative cohomology and base change
- [ ] Work through exercises in Hartshorne III.8
- [ ] Start looking at coherent duality (the generalization of Serre duality)

## Code/Computations

```python
# SageMath computation for line bundle cohomology
P2 = ProjectiveSpace(2, QQ)
O = P2.structure_sheaf()
L = O(-3)  # Line bundle O(-3)

# Compute cohomology dimensions
for i in range(3):
    h_i = P2.cohomology(L, i)
    print(f"h^{i}(O(-3)) = {h_i}")
```

## Related to Previous Work

This builds on last week's work on:
- [2025-08-10: Introduction to Schemes](../08/10/schemes-basics)
- [2025-08-12: Coherent Sheaves](../08/12/coherent-sheaves)

## Notes for Weekly Review

**Key takeaway**: Cohomology is the "obstruction theory" for extending local to global. When $H^1 = 0$, local sections glue uniquely to global sections.---
layout: post
title: "Sheaf Cohomology & Spectral Sequences"
author: jorys
date: 2025-08-17 21:45:00 +0200
categories: [algebraic-geometry, cohomology]
tags: [schemes, sheaves, cohomology, spectral-sequences]
hours: 6.5
math: true
resources:
  - name: "Hartshorne Ch. III §5-7"
    url: "#"
  - name: "Vakil's Rising Sea §18"
    url: "https://math.stanford.edu/~vakil/216blog/FOAGnov1817public.pdf"
  - name: "Stacks Project - Cohomology"
    url: "https://stacks.math.columbia.edu/tag/01X8"
summary: "Finally understood the geometric interpretation of higher cohomology groups and worked through Serre duality."
---

## Today's Focus

Productive session working through Hartshorne Chapter III. Finally understood the geometric interpretation of higher cohomology groups!

## Key Insights

### Cohomological Dimension

For a coherent sheaf $\mathcal{F}$ on a projective scheme $X$, we have the fundamental vanishing theorem:

$$H^i(X, \mathcal{F}(n)) = 0 \text{ for } i > 0 \text{ and } n \gg 0$$

This has deep implications for understanding the global sections functor. The twist by $\mathcal{O}(n)$ essentially "kills" higher cohomology for sufficiently positive $n$.

### Serre Duality

The pairing between $H^i(X, \mathcal{F})$ and $H^{n-i}(X, \omega_X \otimes \mathcal{F}^∨)$ is starting to make sense. The key observation:

$$H^n(X, \omega_X) \cong k$$

This gives us a perfect pairing:

$$H^i(X, \mathcal{F}) \times H^{n-i}(X, \omega_X \otimes \mathcal{F}^∨) \to H^n(X, \omega_X) \cong k$$

## Technical Details

Worked through the spectral sequence:

$$E_2^{p,q} = H^p(X, \mathcal{H}^q(\mathcal{F}^•)) \Rightarrow H^{p+q}(X, \mathcal{F}^•)$$

The convergence is subtle - need to be careful about the filtration.

## Computational Example

Computed $H^1(\mathbb{P}^2, \mathcal{O}(-3))$ using Čech cohomology:
- Cover $\mathbb{P}^2$ with standard affine opens $U_i = \{x_i \neq 0\}$
- The Čech complex gives us the vanishing directly
- Result: $H^1(\mathbb{P}^2, \mathcal{O}(-3)) = 0$

## Questions/Stuck Points

1. Still struggling with the derived category perspective - when is it really necessary?
2. How does this connect to deformation theory? The tangent space $T^1$ should be $H^1$ of something...
3. Need to understand the computational tools better - when to use Čech vs. spectral sequences?

## Tomorrow's Plan

- [ ] Read about relative cohomology and base change
- [ ] Work through exercises in Hartshorne III.8
- [ ] Start looking at coherent duality (the generalization of Serre duality)

## Code/Computations

```python
# SageMath computation for line bundle cohomology
P2 = ProjectiveSpace(2, QQ)
O = P2.structure_sheaf()
L = O(-3)  # Line bundle O(-3)

# Compute cohomology dimensions
for i in range(3):
    h_i = P2.cohomology(L, i)
    print(f"h^{i}(O(-3)) = {h_i}")
```

## Related to Previous Work

This builds on last week's work on:
- [2025-08-10: Introduction to Schemes](../08/10/schemes-basics)
- [2025-08-12: Coherent Sheaves](../08/12/coherent-sheaves)

## Notes for Weekly Review

**Key takeaway**: Cohomology is the "obstruction theory" for extending local to global. When $H^1 = 0$, local sections glue uniquely to global sections.
