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

# Finite Field Extension Containing Nth Roots of Unity

$$ μ_N = ⟨ω⟩, |𝔽_{p^N}^×| = p^N - 1 $$
$$ \textrm{ord}(ω) = n | p^N - 1 $$
but $𝔽_{p^N}^×$ is cyclic.

For all $d | p^N - 1$, there exists $x ∈ 𝔽_{p^N}^×$
with ord$(x) = d$.

Finding $n | p^N - 1$ is sufficient for $ω ∈ 𝔽_{p^N}$
$$ n | p^N - 1 ⇔ \textrm{ord}(p) = (ℤ / nℤ)^× $$

# FFT Algorithm Recursive Compute

We recurse to a depth of $\log n$. Since each recursion uses $ω^i$, then
in the final step $ω^i = 1$, and we simply return $f^T$.

We only need to prove a single step of the algorithm produces the desired
result, and then the correctness is inductively proven.

\begin{align*}
f(X)    &= a_0 + a_1 X + a_2 X^2 + ⋯ + a_{n - 1} X^{n - 1} \\
        &= g(X) + X^{n/2} h(X)
\end{align*}

## Algorithm

\begin{algorithm}[H]
    \caption{Discrete Fourier Transform}
    \label{dft}
    \begin{algorithmic}[1] % The number tells where the line numbering should start
        \Function{DFT}{$n = 2^d, f(X)$}
            \If {$n = 1$}
                \State \textbf{return} $f(X)$
            \EndIf
            \State $f(X) = g(X) + X^{n/2} h(X)$             \Comment{Write $f(X)$ as the sum of two polynomials with equal degree}
            \State Let $\mathbf{g}, \mathbf{h}$ be the vector representations of $g(X), h(X)$
            \State
            \State $\mathbf{r} = \mathbf{g} + \mathbf{h}$
            \State $\mathbf{s} = (\mathbf{g} - \mathbf{h})·(ω^0, …, ω^{n/2 - 1})$
            \State Let $r(X), s(X)$ be the polynomials represented by the vectors $\mathbf{r}, \mathbf{s}$
            \State
            \State Compute $(r(ω^0), …, r(ω^{n/2})) = \textrm{DFT}_{ω^2}(n/2, r(X))$
            \State Compute $(s(ω^0), …, s(ω^{n/2})) = \textrm{DFT}_{ω^2}(n/2, s(X))$
            \State
            \State \textbf{return} $(r(ω^0), s(ω^0), r(ω^2), s(ω^2), …, r(ω^{n/2}), s(ω^{n/2}))$
        \EndFunction
    \end{algorithmic}
\end{algorithm}

## Even Values

\begin{align*}
r(X)        &= g(X) + h(X) \\
\\
f(ω^{2i})   &= g(ω^{2i}) + (ω^{2i})^{n/2} h(ω^{2i}) \\
            &= g(ω^{2i}) +                h(ω^{2i}) \\
            &= (g + h)(ω^{2i}) \\
\end{align*}

So then we can now compute $DFT_ω(f)_{k=2i} = DFT_{ω^2}(r)$
for the even powers of $f(ω^{2i})$.

## Odd Values

For odd values $k = 2i + 1$

\begin{align*}
s(X)        &= (g(X) + h(X))·(ω^0, …, ω^{n/2 - 1}) \\
\\
f(X)          &= a_0 + a_1 X + a_2 X^2 + ⋯ + a_{n - 1} X^{n - 1} \\
              &= g(X) + X^{n/2} h(X) \\
f(ω^{2i + 1}) &= g(ω^{2i + 1}) + (ω^{2i + 1})^{n/2} h(ω^{2i + 1}) \\
\end{align*}
But observe that for any $n$th root of unity $ω^n = 1$ and $ω^{n/2} = -1$
$$ (ω^{2i + 1})^{n/2} = ω^{in} ω^{n/2} = ω^{n/2} = -1 $$
\begin{align*}
⇒ f(ω^{2i + 1}) &= g(ω^{2i + 1}) - h(ω^{2i + 1}) \\
                &= (g - h)(ω^{2i + 1})
\end{align*}

Let $\mathbf{s} = (\mathbf{g} - \mathbf{h})·(ω^0, …, ω^{n/2 - 1})$ be the
representation for $s(X)$. Then we can see that $s(ω^{2i}) = (g - h)(ω^{2i + 1})$
as desired.

So then we can now compute $DFT_ω(f)_{k=2i + 1} = DFT_{ω^2}(s)$
for the odd powers of $f(ω^{2i + 1})$.

# Example

TODO

