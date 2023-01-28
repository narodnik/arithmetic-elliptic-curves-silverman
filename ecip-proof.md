---
header-includes: |
    - \newcommand{\div}{\operatorname{div}}
---

# Weil Reciprocity

$$ f(\div(g)) = g(\div(f)) $$

NOTE: cannot find proof

# Divisor Construction

We can either use the Miller loop, or Mumford polynomial representation.
Both are trivial.

We end up with a polynomial $f$ that represents our divisor.

# Proving Interpolation

Let $f ∈ K(C)^×$, with roots $P₁, …, P_n$. Then the norm

$$ f(P) f(-P) = (x(P) - x(P₁)) ⋯ (x(P) - x(P_n)) $$

Canonical form is $f(x, y) = v(x) + yw(x)$.
The conjugate of $f$ is $\bar{f} = v(x) - yw(x)$ and the norm is

$$ N_f = f·\bar{f} = v(x)² - (x³ + Ax + B)w(x)² $$

For $r = \frac{f}{g} ∈ K(C)$
$$ \frac{f}{g} = \frac{fg̅}{gg̅} = \frac{fg̅}{N_g} $$

But this norm also counts $-P$ which we want to disallow.
We instead use the resultant.

