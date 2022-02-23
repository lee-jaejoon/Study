# 1. Abstract Integration

* 구간 $[a,b]$ 위에서의 함수 $f$의 Riemann integral은 아래와 같이 근사될 수 있다.
  $$
  \sum_{i=1}^{n} f(t_i)m(E_i)
  $$

  * $E_1, ...,E_n$은 union이 $[a,b]$인 disjoint interval들이다.
  * $m(E_i)$는 $E_i$의 길이이고, $t_i \in E_i, i=1,...,n$이다.

* Lebesgue는 위 식의 적분구간의 부분집합 $E_i$가 interval이 아닌 더 넓은 class의 부분집합이 되도록 하면 이론적으로 더 좋은 성질을 갖는 적분을 정의할 수 있다는 것을 발견하였다.
  * 이를 **measurable set**이라고 한다.
  * 그에 따라 적분 가능한 함수의 class도 더 넓어졌는데 이를 **measurable function**이라고 한다.
* 이를 위해 필요한 주요 set-theoretic property는 아래와 같다.
  * Measurable set의 countable union/intersection은 measurable이다.
  * Measurable set의 complement는 measurable이다.
  * (countable additivity) 또한 disjoint measurable set의 countable union의 measure는 각 measure의 합과 같다.
    * measure은 위 Riemann integral 식에서 "각 구간의 길이"에 대응되는 개념이다.
* 위 Riemann integral의 확장에서 등장한 measure (Lebesgue measure) $m$은 실수의 geometry와 깊이 연관되어있다.
  * 이 장에서는 실수의 적분에 대응되는 Lebesgue measure 뿐만 아니라, 모든 countably additive한 measure에 대해 적용되는 general한 Lebesgue integral의 이론에 대해 다룬다.
  * 그렇다고 해서 실수에 대해 정의된 적분보다 특별히 더 어려운 것은 아니다.
  * 이 Lebesgue 적분의 이론이 적분을 정의하고자 하는 특정 공간의 geometry나 topology에 국한되지 않는 것.



### 1.1 Topology and Measure Theory

* Measurable function의 class는 continuous function의 class와 유사한 방식으로 정의된 부분이 많다.
  * Topology
    * A *topological space* $(X,\tau)$ is a set $X$ endowed with a topology $\tau$
    * A set $O \subseteq X$ is *open* if $O \in \tau$
    * A function $f : (X, \tau_X) \rightarrow (Y, \tau_Y)$ is *continuous* if $f^{-1}(O) \in \tau_X$ for every $O \in \tau_Y$
  * Measure theory
    * A *measurable space* $(X, \mathcal A)$ is a set $X$ endowed with a $\sigma$-algebra $\mathcal A$
    * A set $A \subseteq X$ is *measurable* if $A \in \mathcal A$
    * A function $f : (X, \mathcal A_X) \rightarrow (Y, \mathcal A_Y)$ is *measurable* if $f^{-1}(A) \in \mathcal A_X$ for every $A \in \mathcal A_Y$
* 사실 엄밀히 이야기하면 measurable set의 정의는 '$\sigma$-algebra의 원소'가 아니며, 이 부분을 일부 뭉개서 비교한 것이다.
  * Caratheodory의 measurability criterion에 의하면 $\sigma$-algebra 외의 set에도 measure가 정의된다.
  * 하지만 $\sigma$-algebra 위에서는 $\sigma$-additivity가 성립하고 이는 measure theory 관점에서 매우 좋은 이론적 성질이기 때문에, 대부분의 경우 $\sigma$-algebra를 measure의 domain으로 본다.
  * 즉 $\sigma$-algebra는 우리가 measure를 정의할 수 있고, 또 measure를 정의하고자 하는 set들을 포함한다.



### 1.2 Definition (Topology, Topological Space, Continuous Function)

1. *A collection $\tau$ of subsets of a set $X$ is said to be **a topology in $X$** if $\tau$ has the following three properties:*
   * *$\emptyset \in \tau$ and $X \in \tau$*
   * *If $V_i \in \tau $ for $i=1,..., n$, then $V_1 \cap \cdots \cap V_n \in \tau$*
   * *If $\{ V_\alpha \}$ is an arbitrary collection of members of $\tau$ (finite, countable, or uncountable), then $\bigcup_\alpha V_\alpha \in \tau$*
2. *If $\tau$ is a topology in $X$, then $X$ is called a **topological space**, and the members of $\tau$ are called the **open sets in $X$**.*
3. *If $X$ and $Y$ are topological spaces and if $f$ is a mapping of $X$ into $Y$, then $f$ is said to be **continuous** provided that $f^{-1}(V)$ is an open set in $X$ for every open set in $Y$.*



### 1.3 Definition ($\sigma$-algebra, Measurable Space, Measurable Function)

1. *A collection $\mathfrak M$ of subsets of a set $X$ is said to be a **$\sigma$-algebra in $X$** if $\mathfrak M$ has the following properties:*
   * *$X \in \mathfrak M$*
   * *If $A \in \mathfrak M$, then $A^c \in \mathfrak M$, where $A^c$ is the complement of $A$ relative to $X$*
   * *If $A = \bigcup^\infty_{n=1}A_n$ and if $A_n \in \mathfrak M$ for $n=1,2,...$, then $A \in \mathfrak M$*

2. *If $\mathfrak M$ is a $\sigma$-algebra in $X$, then $X$ is called a **measurable space**, and the members of $\mathfrak M$ are called the **measurable sets in $X$**.*
3. *If $X$ is a measurable space, $Y$ is a topological space, and $f$ is a mapping of $X$ into $Y$, then $f$ is said to be **measurable** provided that $f^{-1}(V)$ is a measurable set in $X$ for every open set $V$ in $Y$.*



### 1.4 Comments on Definition 1.2

* Topological space 중 가장 친숙한 space는 *metric space*일 것이다.

  * If $x \in X$ and $r \geq 0$, the *open ball with center at $x$ and radius $r$* is the set
    $$
    \{ y \in X : \rho(x,y) < r \}
    $$

* 만약 $X$가 metric space이고 $\tau$가 open ball들의 arbitrary union인 모든 $E \subset X$의 collection일 때, $\tau$는 $X$의 topology가 된다.

  * Real line $\mathbb R$에서, 어떤 set이 open인 것은 그 set이 open segment $(a,b)$의 union이라는 것과 동치이다.
  * Plane $\mathbb R^2$에서, open set은 open circular disc의 union이다.

* Extended real line $[-\infty, \infty]$ 역시 topological space의 한 예이다.

  * $(a,b), [-\infty, a), (a,\infty]$, 그리고 이 세 type의 segment의 union이 open set으로 정의된다.

* 1.2에서 제시된 continuity의 정의는 $X$ 전체에 대한 global한 정의이고, continuity를 local하게 정의하는 것이 유용한 경우가 많다.

  * A mapping $f$ of $X$ into $Y$ is said to be continuous at the point $x_0 \in X$ if to every neighborhood $V$ of $f(x_0)$ there corresponds a neighborhood $W$ of $x_0$ such that $f(W) \subset V$
  * $X$, $Y$가 metric space라면, 이와 같은 local definition은 일반적인 epsilon-delta 정의와 같다.

* 아래 proposition은 continuity의 local, global 정의를 이어준다.



### 1.5 Proposition (Local, Global Continuity의 동치)

*Let $X$ and $Y$ be topological spaces. A mapping $f$ of $X$ into $Y$ is continuous if and only if $f$ is continuous at every point of $X$.*



#### Proof

$\Rightarrow$

* Neighborhood of $x$는 "$x$를 포함하는 open set"이라는 의미.

* 만약 $f$가 continuous function이고 $x_0 \in X$라면, $f(x_0)$의 임의의 neighborhood $V$에 대하여, $f^{-1}(V)$는 open set이 된다. 
* 근데 $f(x_0) \in V$이므로 당연히 $x_0 \in f^{-1}(V)$이 됨.
* 따라서 $f^{-1}(V)$는 neighborhood of $x_0$이다.
* $f(f^{-1}(V)) \subset V$이므로 $f$는 continuous at $x_0$

$\Leftarrow$

* $f$이 $X$의 모든 point에서 continuous하고, $V$가 open in $Y$이라고 하자.
* Local continuity의 정의에 의해, $f^{-1}(V)$ 안의 모든 $x$에 대해, 각각 다음을 만족하는 neighborhood $W_x$를 잡을 수 있다.
  * $f(W_x) \subset V$
* $W_x \subset f^{-1}(V)$이 되고, $\cup_{x \in f^{-1}(V)} W_x \subset f^{-1}(V)$가 성립.
* $f^{-1}(V) \subset \cup_{x \in f^{-1}(V)} W_x$는 당연히 성립.
* 따라서 $f^{-1}(V) = \cup_{x \in f^{-1}(V)} W_x$이다.
* $f^{-1}(V)$는 open set의 union이므로 역시 open이 되고, 이에 따라 global continuity 조건 만족.



### 1.6 Comments on Definition 1.3

* $\mathfrak M$를 어떤 set $X$의 한 $\sigma$-algebra라고 하자.

* 이때 Definition 1.3.1의 세 성질에 의해 아래 성질들이 만족한다.

  * $\emptyset = X^c$이므로, $\emptyset \in \mathfrak M$

  * 어떤 정수 $n$ 이후의 $A_{n+1} = A_{n+2} = \cdots = \emptyset$으로 둘 수 있으므로, $A_i \in \mathfrak M$이라면, finite union $A_1 \cup \cdots \cup A_n \in \mathfrak M$

  * $\mathfrak M$은 countable (혹은 finite) intersection에도 closed이다.
    $$
    \bigcap_{n=1}^\infty A_n = \left( \bigcup_{n=1}^\infty A_n^c\right)^c
    $$

  * $A-B = A\cap B^c$이므로, $A, B\in \mathfrak M$이면 $A-B \in \mathfrak M$이다.

* $\sigma$-algebra의 $\sigma$는 $\mathfrak M$ countable union에 대해 closed인 것을 의미한다.
  * finite union에 대해서만 closed인 경우, 이 collection은 **algebra**라고 부른다.



### 1.7 Theorem

*Let $Y$ and $Z$ be topological spaces, and let $g: Y \rightarrow Z$ be continuous.*

1. *If $X$ is a topological space, if $f: X \rightarrow Y$ is continuous, and if $h=g \circ f$, then $h: X \to Z$ is continuous.*
2. *If $X$ is a measurable space, if $f: X \rightarrow Y$ is measurable, and if $h=g \circ f$, then $h: X \to Z$ is measurable.*



#### Proof

* 만약 $V$가 $Z$의 open set이라면, $g^{-1}(V)$는 $Y$의 open set이다.
* $h^{-1}(V) = f^{-1}(g^{-1}(V))$



### 1.8 Theorem

*Let $u$ and $v$ be real measurable functions on a measurable space $X$, let $\Phi$ be a continuous mapping of the plane into a topological space $Y$, and define*
$$
h(x) = \Phi(u(x), v(x))
$$
*for $x \in X$. Then $h : X \to Y$ is measurable.*



#### Proof

* $f(x) = (u(x), v(x))$, $h= (\Phi \circ f)(x)$라고 하자.

* $f$가 measurable function이라는 것을 보이면, Theorem 1.7에 의해 $h$도 measurable이다.

  * $R$을 $\mathbb R^2$ 상의 임의의 open rectangle $I_1 \times I_2$이라고 하면 다음이 만족한다.
    $$
    f^{-1}(R) = u^{-1}(I_1)\cap v^{-1}(I_2)
    $$

  * $u,v$는 measurable real function이므로, $u^{-1}(I_1), v^{-1}(I_2)$는 measurable set in $X$이 된다.

  * Measurable set의 intersection은 measurable set이므로, $f^{-1}(R)$ 역시 measurable set in $X$이다.

  * $V$ 안의 모든 open set은 open rectangle의 countable union이므로, 
    $$
    f^{-1}(V)= f^{-1}\left( \bigcup_{i=1}^\infty R_i \right) = \bigcup_{i=1}^\infty f^{-1}\left( R_i \right) \\
    \begin{align*}
    \because \enspace f^{-1}\left( \bigcup_{i=1}^\infty R_i \right) &= \{ \mathbf x \in \mathbb R^2 : f(\mathbf x) \in R_i \text{ for some }i\} \\
    &= \bigcup_{i=1}^\infty \{ \mathbf x \in \mathbb R^2 : f(\mathbf x) \in R_i \} \\
    &= \bigcup_{i=1}^\infty f^{-1}\left( R_i \right) \\
    
    \end{align*}
    $$

  * 따라서 $f^{-1}(V)$는 measurable set이 되고, $f$는 measurable function.



### 1.9 Corollary

1. *If $f=u+iv$, where $u$ and $v$ are real measurable functions on $X$, then $f$ is a complex measurable function on $X$.*
   * $\Phi(z) = z$로 Theorem 1.8 적용
2. *If $f = u+iv$ is a complex measurable function on $X$, then $u$, $v$, and $\vert f \vert$ are real measurable functions on $X$.*
   * $g(z) = \text{Re}(z), \text{Im}(z), \vert z\vert$로 Theorem 1.7 적용
3. If $f$ and $g$ are complex measurable functions on $X$, then so are $f + g$ and $fg$.
   * Real measurable function $f,g$에 대해서는 $\Phi(s,t) = s+t$, $\Phi(s,t) = st$로 Theorem 1.8 적용하여 확인 가능.
   * ㄴ
4. 



