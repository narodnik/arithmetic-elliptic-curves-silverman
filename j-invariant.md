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

