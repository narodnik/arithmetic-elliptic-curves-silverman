# Constructing the Algebraic Closure

Let $p$ be prime and
$$\mathbb{F}_p \subseteq \mathbb{F}_{p^2} \subseteq \cdots \subseteq \mathbb{F}_{p^n} \subseteq \cdots \subseteq \bar{\mathbb{F}}_p$$

$$\bar{\mathbb{F}}_p = \bigcup \mathbb{F}_{p^n}$$

Find a prime poly $f(x) \in \mathbb{F}_p[x]$ (i.e cannot be non-trivially factored such that deg $(f) = n$)

$$\mathbb{F}_p \subseteq \{\mathbb{F}_p[x] \textrm{ mod } f(x) \} \subseteq \mathbb{F}_p$$

# Balasubramanian-Koblitz Theorem

$n$ is prime st. $n \mid \#E(\mathbb{F}_p)$ and gcd$(n, p - 1) = 1$.
Then
$$ E[n] \subseteq E(\mathbb{F}_{p^k}) \iff n \mid p^k - 1$$
The embedding degree of $(E, n)$ is the minimal $k$ st. $n \mid p^k - 1$.

## Corollary

$k$ is embedding degree of $E$, then $\mu_n \subseteq \mathbb{F}_{p^k}$.

# Reduced Tate

$$\tau_n(P, Q) = f_{nD_P}(D_Q)^{\frac{p^k - 1}{n}}$$

# Equivalent Tate Pairing

Let $Q_0$ be such that $nQ_0 = Q$. Such a point is guaranteed to exist by the surjectivity
of multiplication by $n$ map.

\begin{tikzcd}
    Q_0 \arrow[r] \arrow[d]                     & E(\mathbb{F}_{p^k}) \ni Q \arrow[d] \\
    n: E(\overline{\mathbb{F}_{p^k}}) \arrow[r] & E(\overline{\mathbb{F}_{p^k}})    
\end{tikzcd}

Then let $Q_1 = (\Phi^k - 1)(Q_0)$ where $Q_0 \in E[n]$ and $\Phi$ is the frobenius automorphism.
Then $Q_1 \in E[n]$.

\begin{align*}
e_n(P, Q_1) &= \frac{g_P(S + Q_1)}{g_P(S)} \\
            &= \tau_n(P, Q)
\end{align*}

