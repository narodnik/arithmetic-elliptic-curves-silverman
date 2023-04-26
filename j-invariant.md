$$ t = q + 1 - \# E(𝔽_q) $$
So the characteristic polynomial of frobenius polynomial is
$x² - tx + q$.
$$ Φ_q² - [t]Φ_q + [q] = 0 $$

Let $α$ be that endomorphism so $α ∈$ End(E).

If $α ≠ 0$ then $\# \ker α ≤ \deg α$, so $\ker α$ is finite.

We now show that if $α ≠ 0$ then $\# \ker α = ∞$.

For any int $n$ such that $p \nmid n$,
$$ E[n] \cong ℤ_n × ℤ_n $$
and we represent
$$ Φ_q |_{E[n]} : E[n] → E[n] $$
since it's an endomorphism that is just restricted to $E[n]$ so we
can represent this as a matrix
$A = \begin{pmatrix}
a & b \\
c & d \\
\end{pmatrix}$

So by direct inspection
$$ A_n² - \textrm{tr}(A_n) · A_n + \det(A_n) I = 0 $$
We've shown that
$$ \det(A_n) = \deg Φ_q \mod{n} $$
Another calc shows
$$ \textrm{tr}(A_n) = 1 + \det(A_n) - \det(I - A_n) $$
so
$$ \textrm{tr}(A_n) = 1 + q - \deg(\textrm{id} - Φ_q) \mod{n} $$
since $\deg(\textrm{id} - Φ_q) = \# E(𝔽_q) = q + 1 - t$
so
$$A_n² - [1 + q - (q + 1 - t)]A_n + qI = 0 $$
for 2x2 matrices.
Remember that $A_n$ is a matrix in $E[n]$ so the matrix is defined over mod $n$.

$$ \underbrace{A_n² - [t] A_n + qI = 0}_{\textrm{representation of } α|_{E[n]}} $$

This means that for any $n$ such that $p \nmid n$ then for all
$P ∈ E[n]$
$$α(P) = 0 $$
since the set
$$ U_{p \nmid n} E[n] $$
is infinite (the U means union here),
$$ \# \ker(α) = ∞ $$
contradiction.

Note: $t = \textrm{tr}(A_n)$ $\forall p \nmid n$ so is called the
trace of Frobenius.

# $\deg(α \circ α') = \deg(α) \circ \deg(α')$

$$ E → E' → E'' $$
by the maps $α', α$.

For simplicity think $E = E' = E''$.

$$ α(x, y) = (R(x), yS(x)) $$
$$ α'(x, y) = (R'(x), yS'(x)) $$

Then $(α \circ α')(x, y)$ has repr:
$$ (R''(x), yS''(x)) = (R(R'(x)), S(R'(x))S'(x)y) $$

So this already satisfies the property of canonical form.
The other property is that both sides don't share a common root
over the algebraic closure.

If $R(R'(x)) = \frac{u''(x)}{v''(x)}$ is a reduced rational function, then
$$ \deg(α \circ α') = \max{\{ \deg u'', \deg v'' \}} $$

Reduced means no common roots over $\bar{K}$.

How do we prove $R(R'(x))$ is reduced? Lets write over $\bar{K}$
$$ R(x) = \frac{ \prod (x - α_i) }{ \prod (x - β_j) } $$
$$ R'(x) = \frac{ \prod (x - α_i') }{ \prod (x - β_j') } $$

$$ R(R'(x)) = \frac{ \prod (\frac{ \prod (x - α_i') }{ \prod (x - β_j') } - α_i) }{ \prod (\frac{ \prod (x - α_i') }{ \prod (x - β_j') } - β_j) } $$
if $x₀$ is such that
$$ R'(x₀) = α_i $$
for some $i$.

Then clearly since $a_i ≠ β_j$ for all $j$.
$$ R'(x₀) ≠ β_j $$

Finally, a direct calculation shows that if
$$ R''(x) = R(R'(x)) = \frac{ u''(x) } { v''(x) } $$
then
$$ \max{\{ \deg u'', \deg v'' \}} = \max{\{ \deg u, \deg v \}} \max{\{ \deg u', \deg v' \}} $$

$$ R = u/v, R'' = u' / v' $$
$$ R(R') = \frac{ u(u'/v') }{v(u'/v')} $$
as rational functions,
$$ \deg u(u'/v') = \deg u \max{ \{ \deg u', \deg v' \} } $$
$$ \deg v(u'/v') = \deg v \max{ \{ \deg u', \deg v' \} } $$
(remember we are doing composition not multiplication)
$$ R(R'(x)) = \frac{ u''(x) } {v''(x)} $$
and
\begin{align*}
\max\{ \deg u'', \deg v'' \} 
    &= \max\{ u \max \{ \deg u', \deg v' \}, v \max \{ \deg u', \deg v' \} \} \\
    &= \max\{ u, v \} \max\{ u', v' \} \\
    &= \deg α \deg α'
\end{align*}

# Isomorphic Isogeny

Isogeny $α : E → E'$ is called an isomorphism if $\exists$ an isogeny
$\bar{α}' : E' → E$ such that $α \circ α⁻¹ = \textrm{id}_E$ and
$α⁻¹ \circ α = \textrm{id}_E$.

## $\deg α = 1$ when $α$ is an isomorphism

$$ \deg α \circ \deg α⁻¹ = \deg(α \circ α⁻¹) = \deg(\textrm{id}_E) = 1 $$
$$ ⇒ \deg α = 1 $$

Remember $E$ and $E'$ might not be isomorphic over $K$ but they might be
isomorphic over an extension of $K$.

# j-invariant

EC should be non-singular means $Δ = 4A³ + 27B² ≠ 0$.

$$ j = 1728 \frac{4A³}{Δ} $$
determines $E$ up to isomorphism over $\bar{K}$.

A twist is you have two curves where $K ⊆ K'$
$$ E(K), \quad E'(K') $$
$$ E(K') \cong E'(K') $$

It also turns out $[K' : K]$ is only 2, 4 or 6 (quadratic, quartic, sextic twists).

For $E(K)$, you can calculate $\# \textrm{Aut}_{\bar{K}}(E) ≤ 24$.

Remark: if $A = 0$ then $j = 0$. If $B = 0$, then $j = 1728$.

## Proof of j invariant

If $j = 0$ or 1728, then take $E: y² = x³ + 1$ or $E: y² = x³ + x$, otherwise
$$ A = 3j₀(1728 - j₀), \; B = 2j₀(1728 - j₀)² $$
Then we see the j-invariants are consistent.

## We cannot use rational maps, only polynomials for isogenies

All well defined rational maps which map $R(x)$ or $S(x)$ to $∞$ must map to $(∞, ∞)$.
To observe this just look at $y² = x³ + Ax + B$.

Let $R(x) = \frac{p(x)}{q(x)}$, then there's a root of $q(x)$ which is $x₀$.
Then $R(x₀) = ∞$, but $α(∞) = ∞$ so we have a contradiction.

## Showing $A' = μ⁴A, B' = μ⁶B$

Since deg $α = 1$, $R(x) = ax + b$ by the definition of degree for a rational map.
$$ S²(x)(x³ + Ax + B) = (ax + b)³ + A'(ax + b) + B' $$
so comparing coefficients, we see $c² = a³$ so $μ = c/a ∈ K^×$ so $a = μ²$.
$$ μ⁶(x³ + Ax + B) = μ⁶x³ + A'μ²x + B' $$
$$ ⇒ A' = μ⁴A, B' = μ⁶B $$

## Converse

Let $A' = μ⁴A, B' = μ⁶B$, $α(x, y) = (μ²x, μ³y)$.
Then $α$ is a rational map that preserves $∞$, so $α$ is an isogeny.

Also $α$ has an inverse $α⁻¹(x, y) = (x/μ², y/μ³)$.

And then composing them clearly gives the identity.

# Tate Pairing Recap

$$ q = pⁿ, r | \#E(𝔽_q) $$
with $r$ prime.
$$ E[r] = \{ P ∈ E(\bar{𝔽}_{qᵏ}) : rP = ∞ \} $$
$$ E[r] ⊆ E(𝔽_{qᵏ}) $$
$$ τ : E[r] × E(𝔽_{qᵏ})/rE(𝔽_{qᵏ}) → μ_r $$
so this $k$ is the embedding degree.

## Embedding Degree

1. $r|\#E(𝔽_q)$
2. gcd$(r, q - 1)$

Embedding degree of $E$ wrt $r$ is the minimal $k$ such that
$$ r | qᵏ - 1 $$

Also we assume gcd($r, k) = 1$.

We want to extract a type II bilinear pairing
$$ G₁ × G₂ → G_T $$
$$ |G₁| = |G₂| = |G_T| = r $$

For $G₁$, recall that $E(𝔽_q)$ has the property that for any $r | \#E(𝔽_q)$ there is a subgroup of order $r$
with $|G₁| = r$.

Now we find the $k$ such that we have $G₂$.

# Balasubramanian-Koblitz

Theorem: $r | \#E(𝔽_q)$ and gcd$(r, q - 1) = 1$ then $E[r] ⊆ E(𝔽_{qᵏ})$
iff $r | qᵏ - 1$.

## $r | qᵏ - 1 ⇒ E[r] ⊆ E(𝔽_{qᵏ})$

Hasse-Weil states that in End$(E)$ then $Φ² - [t]Φ + [q] = 0$ where $t = q + 1 - \#E(𝔽_q)$.

**Lemma**: for $r$ as above
$$ (Φ - [1])(Φ - [q]) ≡ 0 \mod{r} $$

Denote $\#E(𝔽_q) = hr$. We usually call $h$ the cofactor, and $p(x) = x² - tx + q$.
\begin{align*}
p(x) &= x² - tx + q \\
    &= x² - (q + 1 - hr)x + q \\
    &≡ x² - (q + 1)x + q \mod{r} \\
    &≡ (x - 1)(x - q) \mod{r}
\end{align*}

**Def**: the lth eigenspace of $Φ$ is
$$ \textrm{Eig}_ℓ(Φ) = \{ P ∈ E(\bar{𝔽}_q) : Φ(P) = ℓP \} $$
so for example the 1th eigenspace is simply $E(\bar{𝔽}_q)$.

We set $H₁ = \textrm{Eig}₁(Φ) \cap E[r]$ and $H_q = \textrm{Eig}_q(Φ) \cap E[r]$.

**Corollary:**
\begin{align*}
E[r] &= \{ aP + bQ : P ∈ H₁, Q ∈ H_q \} \\
    &= H₁ × H_q
\end{align*}
(remembering E[r] contains points from the closure)

$$ E[r] ⊆ \{ R ∈ E(\bar{𝔽}_q) : (Φ - 1)(Φ - q)(R) = 0 \} $$
$H₁ =$ roots of $Φ - 1 \cap E[r]$, $H_q =$ roots of $Φ - q \cap E[r]$.

## Selecting $G₁$

$r$ is prime and $E[r] \cong H₁ × H_r$, so in practice a natural choice of $G₁$ is
$$ G₁ = H₁ = E(𝔽_q)[r] $$

**Def**: let $r$ be prime $r | \#E(𝔽_q)$ and gcd$(r, q - 1) = 1$ and $k$ the embedding degree
(minimal integer such that $r|qᵏ - 1$ and gcd$(k, r) = 1$).

The trace map is
$$ Tr : E(𝔽_{qᵏ}) → E(𝔽_q) $$
$$ Tr(P) = P + Φ(P) + Φ²(P) + ⋯ + Φ^{k - 1}(P) $$
(not to be confused with trace of Frobenius)

Note $Φᵏ$ is the $qᵏ$-Frobenius map hence the identity.

$$ Φ : E(\bar{𝔽}_q) → E(\bar{𝔽}_q) $$
$$ Φ : E(𝔽_q) → E(𝔽_q) $$
$$ Φᵏ : E(\bar{𝔽}_q) → E(\bar{𝔽}_q) $$
$$ Φᵏ : E(𝔽_{q^k}) → E(𝔽_{q^k}) $$
where 2nd and 4th lines are the identity.

\begin{align*}
Φ(Tr(P)) &= Φ(P + Φ(P) + Φ²(P) + ⋯ + Φ^{k - 1}(P)) \\
         &= Φ(P) + Φ²(P) + Φ³(P) + ⋯ + Φ^{k - 1}(P) + P \\
         &= Tr(P)
\end{align*}
so the trace image is fixed under action by $Φ$ and hence
$$ \textrm{Im}(Tr) ⊆ E(𝔽_q) $$
and not only in $E(𝔽_{qᵏ})$.

**Lemma:** the k-eigenspace of $Tr$ is $E(𝔽_q)[r] = H₁$.

If $R ∈ E(𝔽_q)[r]$ then $Φ(R) = R$ which means $Tr(R) = R + … + R = kR$.
So $R$ is a k eigenvector of the trace.

Likewise if $R ∈ E(𝔽_{qᵏ})$ such that $Tr(R) = kR$ then $Φ(Tr(R)) = Φ(kR) = kΦ(R)$,
and since $Φ(Tr(R)) = Tr(R)$ then $Φ(Tr(R)) = Tr(R)$.
Then $k(Φ(R) - R) = ∞ ⇒ Φ(R) = R$ since gcd$(k, r) = 1$ since then $kP = ∞$ otherwise.

So $Φ$ fixes all points $R ∈ E[r]$ such that $Tr(R) = kR$ hence such points must be in $E(𝔽_q)[r]$.

## Defining $G₂$

1. $H₁ = E(𝔽_q)[r]$
2. $H_q = \{ R ∈ E[r] : Tr(R) = ∞ \}$

We see (1) is immediate from before.

Let $R ∈ E[r]$ with $Tr(R) = ∞$. Write $R = aP + bQ$ for $P ∈ H₁, Q ∈ H_q$.

\begin{align*}
Φ(R) &= Φ(aP + bQ) \\
    &= aP + bqQ \\
Φ²(R) &= aP + bq² Q
\end{align*}

$$ ∞ = Tr(R) = kaP + b(1 + q + ⋯  + q^{k - 1}) Q $$
note that $1 + q + ⋯  + q^{k - 1} = \frac{qᵏ - 1}{q - 1}$.
$$ ⇒ ∞ = kaP + b\left(\frac{qᵏ - 1}{q - 1}\right) Q $$
so $a ≡ 0 \mod{r}$ since $H₁, H_q$ are subgroups with trivial intersections, and the order of $P$ is $r$.

Conversely, if $R = Q ∈ H_q$ then
$$ Tr(Q) = \frac{q^k - 1}{q - 1}Q $$
but $r | q^k - 1$ and $r \nmid q - 1$ so $r | \frac{q^k - 1}{q - 1}$
$$ ⇒ Tr(Q) = 0 $$

## <= of BR theorem

For $E, r, k, q$ as above
$$ E[r] ⊆ E(𝔽_{q^k}) $$

Let $R ∈ E[r]$, write $R = aP + bQ$ with $P ∈ H₁, Q ∈ H_q$, then
$Tr(Q) = ∞$ and
$$ Φᵏ(Q) = qᵏQ = Q $$
since $r | qᵏ - 1$.
Furthermore
$$ Φᵏ(P) = P $$
because $P ∈ E(𝔽_q)[r] ⊆ E(𝔽_q)$. Thus
\begin{align*}
Φᵏ(R) &= Φᵏ(aP + bQ) \\
    &= aP + bQ
\end{align*}
so $E[r]$ is fixed by $Φᵏ$ hence
$$ E[r] ⊆ E(𝔽_{qᵏ}) $$

