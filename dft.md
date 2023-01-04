---
header-includes: |
    - \usepackage{mathtools}
    - \newcommand{\DFT}{\textrm{DFT}}
---

$$ f(x)g(x) ∈ 𝔽_{<2n}[x] $$
$$ fg = \sum_{i + j < 2n - 2} a_i b_j x^{i + j} $$
Complexity: $O(n^2)$

Suppose $ω ∈ 𝔽$ is an nth root of unity.

Recall: if $𝔽 = 𝔽_{p^k}$ then $∃N : 𝔽_{p^N}$
contains all nth roots of unity.

$$ \DFT_ω : 𝔽^n → 𝔽^n $$
$$ \DFT_ω(f) = (f(ω^0), f(ω^1), …, f(ω^{n - 1})) $$

$$ V_ω =
\begin{pmatrix}
1 & 1   & 1   & \hdots & 1 \\
1 & ω^1 & ω^2 & \hdots & ω^{n - 1} \\
1 & ω^2 & ω^4 & \hdots & ω^{2(n - 1)} \\
\vdots \\
1 & ω^{n - 1} & ω^{2(n - 1)} & \hdots & ω^{(n - 1)^2} \\
\end{pmatrix}
$$

$$ \DFT_ω(f) = V_ω · f^T $$
since vandermonde multiplication is simply evaluation of a polynomial.

# Lemma: $V_ω^{-1} = \frac{1}{n} V_{ω^{-1}}$

Use $1 + ω + ⋯ + ω^{n - 1}$ and compute $V_ω V_{ω^{-1}}$

Corollary: $\DFT_ω$ is invertible.

# Definitions

1. Convolution $f * g = fg \mod (x^n - 1)$
2. Pointwise product
   $$(a_0, …, a_{n - 1})·(b_0, …, b_{n - 1}) =
         (a_0 b_0, …, a_{n - 1} b_{n - 1}) ∈ 𝔽^n → 𝔽_{<n}[x]$$

# Theorem: $\DFT_ω(f*g) = \DFT_ω(f)·\DFT_ω(g)$

$$ fg = q'(x^n - 1) + f*g  $$
$$ ⇒ f*g = fg + q(x^n - 1) $$
$$ \deg fg ≤ 2n - 2        $$

\begin{align*}
(f*g)(ω^i) &= f(ω^i)g(ω^i) + q(ω^i)(ω^{in} - 1) \\
           &= f(ω^i)g(ω^i)
\end{align*}

# Result

$$ f, g ∈ 𝔽_{<n/2}[x] $$
$$ fg = f*g $$
$$ \DFT_ω(f*g) = \DFT_ω(f)·\DFT_ω(g) $$
$$ fg = \frac{1}{n} \DFT_{ω^{-1}} (\DFT_ω(f) · \DFT_ω(g)) $$

