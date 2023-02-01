# Hasse-Weil Theorem

$p$ prime, $q = pⁿ$
$$ \Phi : \bar{𝔽}_q → \bar{𝔽}_q = \bar{𝔽}_p = \bigcup_n 𝔽_{pⁿ} $$
$$ \Phi(x) = x^q $$
it is a field homomorphism.
Induces a map for $E/𝔽_q$
$$ \Phi: E(\bar{𝔽}_q) → E(\bar{𝔽}_q) $$
$$ \Phi(x, y) = (x^q, y^q) $$
Frobenius is compatible wih group structure on $E(\bar{𝔽}_q)$.

## Definition: Isogeny

$E, E'$ are EC on $K$. An isogeny $α : E → E'$ is a rational map
such that the induced map
$$ E(\bar{K}) -> E'(\bar{K}) $$
is a group homomorphism

## Example: Frobenius

## Isogeny $α : E → E$ is an endomorphism.

If $α : E/K → E'/K$ is an isogeny then
$$ α : E(L) → E'(L) $$
for $K ⊆ L ⊆ \bar{K}$ is an isogeny.
$$ E(L) ⊆ E(\bar{K}) $$

## Example

Let $E/K$ be any EC, for all $n$ multiplication by $n$
is an endomorphism.
$$ [n] : E → E $$
$$ P → nP $$
Everything we do is polynomials and it preserves group structure.

## Recall:

An isogeny $α : E → E'$ viewed as a rational map, has a canonical form.
$$ α(x, y) = (r₁(x), yr₂(x)) $$
where $rِ₁(x) = \frac{p(x)}{q(x)}, r₂(x) = \frac{u(x)}{v(x)}$
and each quotient is reduced, so no common factors over $\bar{K}$.

If $q(x) = 0$ for some $x, y ∈ E(\bar{K})$, then we set $α(x, y) = 0_{E'}$
and otherwise we showed $v(x) ≠ 0$ and hence $α$ is well defined.

## Def

Let $α : E/K → E'/K$ be an isogeny.

1. The degree of $α$ is $\deg(α) = \textrm{max}\{ \deg(p), \deg(q) \}$.
2. $α$ is called separable if the formal derivative $r₁'(x)$ is not identically
   zero ⇔  $p(x) q'(x) - p'(x) q(x) ≠ 0$

$$ \Phi_q = α : E(\bar{𝔽}_q) → E(\bar{𝔽}_q) $$
$$ ∞ → ∞ $$
$$ (x, y) → (x^q, y^q) ∈ E(\bar{𝔽}_q) $$
$$ (y^q)² = (x^q)³ + Ax^q + B $$
$$ (y²)^q = (x³ + Ax + B)^q $$

Is $\Phi_q$ separable?
$$ (x^q)' = qx^{q - 1} = 0 \textrm{ in } 𝔽_q $$
so it is not separable.

## Prop

Let $α : E → E'$ be a nonzero isogeny.
If $α$ is separable then
$$ \# \textrm{ker}(α : E(\bar{K}) → E'(\bar{K})) = \deg(α) $$
and otherwise $\#\textrm{ker}(α) < \deg(α)$

### Observe $\# E(𝔽_q) = \# \ker(α)$

For $E/𝔽_q$
$$ α : \Phi^n_q - \textrm{id} : E → E $$
$$ P → \Phi_q^n(P) - P $$
$$ \ker(α : E(\bar{𝔽}_q) → E(\bar{𝔽}_q)) = \# E(𝔽_{q^n}) $$

(or without $n$ easier)

For $E/𝔽_q$
$$ α : \Phi_q - \textrm{id} : E → E $$
$$ P → \Phi_q(P) - P $$
$$ \ker(α : E(\bar{𝔽}_q) → E(\bar{𝔽}_q)) = \# E(𝔽_{q}) $$
$$P ∈ \ker(α) ⇔ \Phi_q(P) -P = ∞ $$
$$ ⇔ \Phi_q(P) = P $$
we saw that these points $P$ are exactly $E(𝔽_q)$

The only points frobenius acts as identity is those in $𝔽_q$,
so only unchanged points are in the kernel.
In higher extensions, frobenius doesn't act as the identity.

## Proof

Since $α ≠ 0$ and is a group homomorphism on $E(\bar{K}) → E'(\bar{K})$
it is non-constant.

Thus $α : E(\bar{K}) → E'(\bar{K})$ is surjective. Let $Q = (a, b) ∈ E'(\bar{K})$
and $P = (x₀, y₀) ∈ E(\bar{K})$.

## Exercise: Show the prop on surjectivity generalizes to the case of $E → E'$

Since $E'(\bar{K})$ is infinite we can choose $Q$ st

1. $a, b ≠ 0$
2. $\deg(p - qa) = \max\{\deg(p), \deg(q) \} = \deg(α)$

the only case in which $\deg(p - qa) < \deg(α)$ is when
$\deg(p) = \deg(q)$ and their leading coefficients $λ, δ$ respectively
satisfy
$$ λ - aδ = 0 ⇔ a = \frac{λ}{δ} $$
so we choose $Q$ such that $a ≠ \frac{λ}{δ}$.

Since $\deg(p - aq) = \deg(α)$,
$p(x) - aq(x)$ has exactly $\deg(α)$ roots over $\bar{K}$
(possibly repeated roots).

We claim that the number of distinct roots of $p - aq$ is exactly the
number of sources $P$ of $Q$ (under $α$).

Since $(a, b) ≠ (∞, ∞)$, then
$$r₁(x₀) ≠ 0 ⇔ q(x₀) ≠ 0$$
since $b ≠ 0$ and we have
$$y₀ r₂(x) = b$$
we have $y₀ = b / r₂(x₀)$, so $y₀$ is completely determined by $x₀$.

So it is enough to count the $x₀$'s which in turn must satisfy
$\frac{p(x₀)}{q(x₀)} = a$
$$ ⇔ p(x₀) - aq(x₀) = 0 $$
i.e the roots of $p - aq$

Since $α$ is a group homomorphism on $E(\bar{K}) → E'(\bar{K})$,
then $\# \ker(α)$ is the same as the number of sources of any given
point $Q ∈ E'(\bar{K})$

Which is enough to analyze the number of distinct roots $x₀$ of $p - aq$.

$x₀$ is a repeated root of $p - aq ⇔  p(x₀) - aq(x₀) = 0$
and also $p'(x₀) - aq'(x₀) = 0$.
Multiply both equations to get
$$ap(x₀)q'(x₀) = ap'(x₀)q(x₀)$$
Since $a ≠ 0$
$$p(x₀)q'(x₀) - p'(x₀)q(x₀) = 0$$
$$r₁'(x₀) = 0 $$
by the quotient rule applied to $r₁'$.

If $α$ is not separable
$$ r₁'(x) = 0 $$
which means $p - aq$ has repeated roots
and $\# \ker(α) < \deg(α)$.

If $α$ is separable
$$ r₁'(x) ≠ 0 $$
and hence has a finite number of roots $S$.
We may add a constraint on the choice of $Q$
saying that $a ∉ r₁(S)$. Then since
$r₁(x₀) = a$
$$x₀ ∉ S$$
so $p - aq$ will not have repeated roots,
i.e. $\# \ker(α) \deg(α)$.

