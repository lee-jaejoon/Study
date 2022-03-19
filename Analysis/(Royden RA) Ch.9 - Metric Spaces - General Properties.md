# 9. Metric Spaces: General Properties

## 9.1 EXAMPLES OF METRIC SPACES

* Let $X$ be a nonempty set. A function $\rho : X \times X \to \mathbb R$ is called a **metric** provided for all $x, y,$ and $z$ in $X,$
  1. $\rho(x,y) \ge 0$
  2. $\rho(x,y) = 0$ if and only if $x =y$
  3. $\rho(x, y) = \rho(y,x)$
  4. $\rho(x,y) \le \rho(x,z) + \rho(z, y)$ : **the triangle inequality**

* A nonempty set together with a metric on the set is called a **metric space**.

* A nonnegative real-valued function $\Vert \cdot \Vert$ on a linear space $X$ is called a **norm** provided for each $u,v \in X$ and real number $\alpha$,
  1. $\Vert u \Vert = 0$ if and only if $u=0$
  2. $\Vert u + v \Vert \le \Vert u \Vert + \Vert v \Vert$
  3. $\Vert \alpha u \Vert = \vert \alpha \vert \Vert u \Vert$

* A linear space with a norm is called a **normed linear space**.

  * *Linear space는 vector space와 같은 의미이다.*

  * A norm $\Vert \cdot \Vert$ on a linear space $X$ induces a metric $\rho$ on $X $ by defining
    $$
    \rho(x, y) = \Vert x - y \Vert
    $$

  * Example

    * $\mathbb R^n : \Vert x \Vert = [x_1^2 + \cdots + x_n^2]^{1/2}$

    * $L^p(E)$
      $$
      \Vert f \Vert_p = \left( \int \vert f \vert^p \right)^{1/p}
      $$

    * $C[a,b] : \Vert f \Vert_{\max}= \max \{ \vert f(x) \vert : x \in [a,b] \} $

* For any nonempty set $X$, the **discrete metric** $\rho$ is defined by setting $\rho(x,y) = 0$ if $x = y$ and $\rho(x,y) = 1$ if $x \neq y$.

* For a metric space $(X, \rho )$, let $Y$ be a nonempty subset of $X$. Then the restriction of $\rho$ to $Y \times Y$ defines a metric on $Y$ and we call such a metric space a **metric subspace**. Therefore every nonempty subset of Euclidean space, of an $L^p(E)$ space, $1 \le p \le \infty$, and of $C[a, b]$ is a metric space.

* For metric spaces $(X_1, \rho_1)$ and $(X_2, \rho_2)$, we define the **product metric** $\tau$ on the *Cartesian product* $X_1 \times X_2$ by setting, for $(x_1, x_2)$ and $(y_1, y_2)$ in $X_1 \times X_2$,
  $$
  \tau( (x_1, x_2), (y_1, y_2) ) = \Big\{ [\rho_1(x_1, y_1)]^2 + [\rho_2(x_2, y_2)]^2 \Big\}^{1/2}
  $$

  * This construction extends to countable products.

* Two metrics $\rho$ and $\sigma$ on a set $X$ are said to be **equivalent** provided there are positive numbers $c_1$ and $c_2$ such that for all $x_1, x_2 \in X$,
  $$
  c_1 \sigma(x_1, x_2) \le \rho(x_1, x_2) \le c_2 \sigma(x_1,x_2)
  $$

* A mapping $f$ from a metric space $(X, p)$ to a metric space $(Y, \sigma)$ is said to be an **isometry** provided it maps $X$ onto $Y$ and for all $x_1, x_2 \in X$,
  $$
  \sigma( f(x_1), f(x_2) )  = \rho(x_1, x_2)
  $$

* Two metric spaces are called **isometric** provided there is an isometry from one onto the other.
  * *To be isometric is an equivalence relation among metric spaces.*

* If we relax the condition that $\rho(x,y) = 0$ and allow the possibility that $\rho(x,y) = 0$ for some $x \neq y$ in the definition of a metric $\rho$, we call $\rho$ a **pseudometric** and $(X,\rho)$ a **pseudometric space**.
  * The relation $x \cong y$ is defined for $\rho(x,y) = 0$.
    * This is an equivalence relation that separates $X$ into a disjoint collection of equivalence classes $X/\cong$.
    * For equivalence classes $[x], [y]$, define $\tilde \rho([x], [y]) = \rho(x, y)$ which is a metric on $X / \cong$.
  * Similar considerations apply when we allow the possibility, in the definition of a norm, that $\Vert u \Vert = 0$ for $u \neq 0$.



## 9.2 OPEN SETS, CLOSED SETS, AND CONVERGENT SEQUENCES

* Let $(X,\rho)$ be a metric space. For a point $x$ in $X$ and $r > 0$, the set
  $$
  B(x , r) = \{ x^\prime \in X : \rho(x^\prime, x ) < r \}
  $$
  is called the **open ball** centered at $x$ of radius $r$. A subset $\mathcal O$ of $X$ is said to be **open** provided for every point $x \in \mathcal O$, there is an open ball centered at $x$ that is contained in $\mathcal O$. For a point $x \in X$, an open set that contains $x$ is called a **neighborhood** of $x$.

### Proposition 1

Let $X$ be a metric space. The whole set $X$ and the empty-set $\empty$ are open; the intersection of any two open subsets of $X$ is open; and the union of any collection of open subsets of $X$ is open.

### Proposition 2

Let $X $ be a subspace of the metric space $Y$ and $E$ a subset of $X$. Then $E$ is open in $X$ if and only if $E = X \cap \mathcal O$, where $\mathcal O$ is open in $Y$

* Let $B_X(x,r), B_Y(x,r)$ be an open ball centered at $x$ of radius $r$ in $X, Y$, respectively.
  * It is clear that $B_X(x,r) = X \cap B_Y(x,r) $.

* $\Rightarrow$

  * For all $x \in E$, $\exists r > 0$ with $B_X(x,r) \subseteq E$.

  * Then we have the following:
    $$
    E = \bigcup_{x \in E} B_X(x,r)  =  \bigcup_{x \in E} \left(B_Y(x,r)\cap X\right)= \left( \bigcup_{x \in E} B_Y(x,r)\right)\cap X
    $$

  * Let $\mathcal O = \bigcup_{x \in E} B_Y(x,r)$. $\mathcal O$ is open in $Y$.
    * A countable union of open sets is open.

* $\Leftarrow$
  * Let $x \in E$.
    * $x \in E \subseteq \mathcal O \implies \exists r > 0$ with $B_Y(x,r) \subseteq \mathcal O$.
  * $\exists r > 0$ such that $B_X(x,r)= X \cap B_Y(x,r)  \subseteq X \cap \mathcal O = E$.
  * Then $E$ is open in $X$.

### Definition

* For a subset $E$ of a metric space $X$, a point $x \in X$ is called a **point of closure** of $E$ provided every neighborhood of $x$ contains a point in $E$. The collection of points of closure of $E$ is called the **closure** of $E$ and is denoted by $\bar E$.

  * It is clear that $E \subseteq \bar E$.

* If $E$ contains all of its points of closure, that is, $E = \bar E$, then the set $E$ is said to be **closed**.

* For a point $x$ in the metric space $(X, \rho)$ and $r > 0$, the set $\bar B(x,r)$ is called the **closed ball** centered at $x$ of radius $r$.
  $$
  \bar B(x,r) = \{ x^\prime \in X : \rho(x^\prime, x ) \le r \}
  $$

### Proposition 3

For $E$, a subset of a metric space $X$, its closure $\bar E$ is closed. Moreover, $\bar E$ is the smallest closed subset of $X$ containing $E$ in the sense that if $F$ is closed and $E \subseteq F$, then $\bar E \subseteq F$.

* $\bar E$ is closed 

  $\iff$ ( $x$ is a point of closure of $\bar E \implies x \in \bar E$ )

  $\iff$ ( $x$ is a point of closure of $\bar E \implies x $ is a point of closure of $E$ )

  * Let $x$ be a point of closure of $\bar E$, and $\mathcal U_x$ be a neighborhood of $x$.
  * Then there is a point $x^\prime \in \bar E \cap \mathcal U_x$.
    * $x^\prime \in \bar E \implies x^\prime $ is a point of closure of $E$.
    * $\mathcal U_x$ is a neighborhood of $x^\prime$.
  * Then there is a point $x^{\prime\prime} \in E \cap \mathcal U_x$
    * Thus every neighborhood $\mathcal U_x$ of $x$ contains a point $x^{\prime\prime} \in E$
    * $x$ is a point of closure of $E$.

### Proposition 4

A subset of a metric space $X$ is open if and only if its complement in $X$ is closed.

* $\Rightarrow$
  * Suppose $E$ is open in $X$.
  * Let $x$ be a point of closure of $X \backslash E$. Then $x \notin E$ and $x \in X \backslash E$
    * (open) If $x \in E$, there exists a neighborhood of $x$, $B(x,r) \subseteq E$.
    * (a point of closure) All neighborhood of $x$ contains a point $x^\prime \in X \backslash E$.
    * Contradiction.
  * Thus $X \backslash E$ is closed.
* $\Leftarrow$
  * Suppose $X \backslash E$ is closed. Let $x \in E$.
  * Then $x$ is not a point of closure of $X \backslash E$.
    * Since $X \backslash E$ is closed, thus contains all of its points of closure within it.
  * Then there exists a neighborhood of $x$, $B(x,r)$ that does not contain a point of $X \backslash E$.
    * In other words, $B(x,r) \subseteq  X \backslash (X\backslash E ) = E$.
  * Thus $E$ is open.

### Proposition 5

Let $X$ be a metric space. The empty-set $\emptyset$ and the whole set $X$ are closed; the union of any two closed subsets of $X$ is closed; and the intersection of any collection of closed subsets of $X$ is closed.

* Straightforward results of Proposition 1 along with Proposition 4.

### Definition

A sequence $\{ x_n\}$ in a metric space $(X, \rho)$ is said to **converge** to the point $x \in X$ provided
$$
 \lim_{n \to \infty} \rho(x_n , x) = 0,
$$
that is, for each $\epsilon > 0$, there is an index $N$ such that for every $n \ge N$, $\rho(x_n, x) < \epsilon$. The point to which the sequence converges is called the **limit** of the sequence and we often write $\{ x_n \} \to x$ to denote the convergence of $\{x_n \}$ to $x$.

* Convergence can be rephrased as follows: a sequence $\{x_n \}$ converges to the limit $x$ provided that for any neighborhood $\mathcal O$ of $X$, **all but at most finitely many** terms of the sequence belong to $\mathcal O$.

### Proposition 6

For a subset $E$ of a metric space $X$, a point $x \in X$ is a point of closure of $E$ if and only if $x$ is the limit of a sequence in $E$. Therefore, $E$ is closed if and only if whenever a sequence in $E$ converges to a limit $x \in X$, the limit $x$ belongs to $E$.

* $\Rightarrow$

  * Let $\epsilon > 0$. Let $x \in X$ be a point of closure of $E$.

    * Then every neighborhood of $x$ contains a point of $E$.

  * For $n=1,2,\cdots$, Let $r_n = 1/n$.

  * (a point of closure) $B(r_n, x)$ contains a point of $E$. Denote the point $x_n \in B(r_n, x)$.

    * $\rho(x_n , x ) < 1/n$ for all $n = 1,2, \cdots$.

  * Choose $N \ge 1/\epsilon$, then for $n \ge N$,
    $$
    \rho(x_n , x ) < r_n = \frac{1}{n} \le \frac{1}{N} < \epsilon
    $$

* $\Leftarrow$

  * Let $\{x_n \}$ be a sequence in $E$ such that $\{x_n \} \to x$.
  * Then every ball centered at $x$ contains infinitely many points in $E$.
  * Then $x$ is a point of closure of $E$.

### Proposition 7

Let $\rho$ and $\sigma$ be equivalent metrics on a nonempty set $X$. Then a subset of $X$ is open in the metric space $(X, \rho)$ if and only if it is open in the metric space $(X, \sigma)$.

* The equivalence of metric $\rho, \sigma$ implies that there exist $c_1, c_2 \ge 0$ such that, for all $x, y \in X$,
  $$
  c_1 \sigma(x, y) \le \rho(x,y) \le c_2 \sigma(x,y) \\
  \frac{1}{c_2} \rho(x, y) \le \sigma(x,y) \le \frac{1}{c_1} \rho(x,y) \\
  $$

* $\Rightarrow$

  * Let $E$ be an open set in $(X, \rho)$.
    $$
    \iff \forall x \in E, \exists r>0 \text{ s.t. } \{ y \in X : \rho(x, y) < r \} \subseteq E.
    $$

  * Note that $\rho(x,y) \le c_2 \sigma(x,y)$ implies the following.
    $$
    \{ y \in X : c_2 \sigma(x, y) < r \} \subseteq  \{ y \in X : \rho(x, y) < r \} \subseteq E.
    $$

  * Then for all $x \in E$, there exists an open ball of $x$ with respect to metric $\sigma$ which is a subset of $E$.

  * $E$ is open in $(X, \sigma)$.

* $\Leftarrow$

  * vice versa.
    * $\sigma(x,y) \le  \rho(x,y)/{c_1}$



## 9.3 CONTINUOUS MAPPINGS BETWEEN METRIC SPACES

### Definition

A mapping $f$ from a metric space $X$ to a metric space $Y$ is said to be **continuous at the point** $x \in X$ provided for any sequence $\{ x_n \}$ in $X$,
$$
\text{if }\{x_n\} \to x, \text{ then } \{ f(x_n)\} \to f(x).
$$
The mapping $f$ is said to be **continuous** at every point in $X$.

### The $\epsilon - \delta$ Criterion for Continuity

A mapping $f$ from a metric space $(X, \rho)$ to a metric space $(Y, \sigma)$ is continuous at the point $x \in X$ if and only if for every $\epsilon > 0$, there is a $\delta > 0$ for which if $\rho(x, x^\prime) < \delta$, then $\sigma(f (x), f(x^\prime))< \epsilon$, that is,
$$
f( B(x,\delta) ) \subseteq B(f(x), \epsilon).
$$

* s

### Proposition 8































