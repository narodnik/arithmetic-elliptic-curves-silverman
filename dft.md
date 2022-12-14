---
header-includes: |
    - \usepackage{mathtools}
    - \newcommand{\DFT}{\textrm{DFT}}
---

$$ f(x)g(x) โ ๐ฝ_{<2n}[x] $$
$$ fg = \sum_{i + j < 2n - 2} a_i b_j x^{i + j} $$
Complexity: $O(n^2)$

Suppose $ฯ โ ๐ฝ$ is an nth root of unity.

Recall: if $๐ฝ = ๐ฝ_{p^k}$ then $โN : ๐ฝ_{p^N}$
contains all nth roots of unity.

$$ \DFT_ฯ : ๐ฝ^n โ ๐ฝ^n $$
$$ \DFT_ฯ(f) = (f(ฯ^0), f(ฯ^1), โฆ, f(ฯ^{n - 1})) $$

$$ V_ฯ =
\begin{pmatrix}
1 & 1   & 1   & \hdots & 1 \\
1 & ฯ^1 & ฯ^2 & \hdots & ฯ^{n - 1} \\
1 & ฯ^2 & ฯ^4 & \hdots & ฯ^{2(n - 1)} \\
\vdots \\
1 & ฯ^{n - 1} & ฯ^{2(n - 1)} & \hdots & ฯ^{(n - 1)^2} \\
\end{pmatrix}
$$

$$ \DFT_ฯ(f) = V_ฯ ยท f^T $$
since vandermonde multiplication is simply evaluation of a polynomial.

# Lemma: $V_ฯ^{-1} = \frac{1}{n} V_{ฯ^{-1}}$

Use $1 + ฯ + โฏ + ฯ^{n - 1}$ and compute $V_ฯ V_{ฯ^{-1}}$

Corollary: $\DFT_ฯ$ is invertible.

# Definitions

1. Convolution $f * g = fg \mod (x^n - 1)$
2. Pointwise product
   $$(a_0, โฆ, a_{n - 1})ยท(b_0, โฆ, b_{n - 1}) =
         (a_0 b_0, โฆ, a_{n - 1} b_{n - 1}) โ ๐ฝ^n โ ๐ฝ_{<n}[x]$$

# Theorem: $\DFT_ฯ(f*g) = \DFT_ฯ(f)ยท\DFT_ฯ(g)$

$$ fg = q'(x^n - 1) + f*g  $$
$$ โ f*g = fg + q(x^n - 1) $$
$$ \deg fg โค 2n - 2        $$

\begin{align*}
(f*g)(ฯ^i) &= f(ฯ^i)g(ฯ^i) + q(ฯ^i)(ฯ^{in} - 1) \\
           &= f(ฯ^i)g(ฯ^i)
\end{align*}

# Result

$$ f, g โ ๐ฝ_{<n/2}[x] $$
$$ fg = f*g $$
$$ \DFT_ฯ(f*g) = \DFT_ฯ(f)ยท\DFT_ฯ(g) $$
$$ fg = \frac{1}{n} \DFT_{ฯ^{-1}} (\DFT_ฯ(f) ยท \DFT_ฯ(g)) $$

