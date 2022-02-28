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
   
3. *If $f$ and $g$ are complex measurable functions on $X$, then so are $f + g$ and $fg$.*
   
   * Real measurable function $f,g$에 대해서는 $\Phi(s,t) = s+t$, $\Phi(s,t) = st$로 Theorem 1.8 적용하여 확인 가능.
   * Complex measurable function $f, g$에 대해서는 Corollary 1.9.2에 의해 실수부와 허수부 각각 measurable.
   * 각각 따로 Corollary 1.9.1 적용. 그 후 Theorem 1.8 적용
   
4. *If $E$ is a measurable set in $X$ and if*
   $$
   \chi_E(x) = \begin{cases}
   1 & \text{if }x \in E\\
   0 & \text{if }x \notin E\\
   \end{cases}
   $$
   *then $\chi_E$ is a measurable function.*

   * 이와 같이 정의된 $\chi_E$를 *characteristic* function of the set $E$라고 부른다.

   * 임의의 open set $A \in \mathbb R$에 대하여, $\chi_E$의 inverse image의 case를 나누어 확인해보면 된다.
     $$
     \chi_E^{-1}(A) = \begin{cases}
     X & \text{if } 0 \in A,1 \in A\\
     E & \text{if } 0 \notin A,1 \in A\\
     E^c &\text{if } 0 \in A,1 \notin A\\
     \emptyset &\text{otherwise}\\
     \end{cases}
     $$

   * $X,E,E^c,\emptyset$ 모두 measurable, 즉 characteristic function $\chi_E$는 measurable function.

5. *If $f$ is a complex measurable function on $X$, there is a complex measurable function $\alpha$ on $X$ such that $\vert \alpha \vert = 1$ and $f = \alpha \vert f \vert$.*

   * $E = \{ x : f(x) = 0\}$, $Y = \mathbb C \backslash \{ 0\}$

   * $\varphi(z) = z/\vert z \vert$ for $z \in Y$

   * 아래와 같이 $X$ 위의 함수 $\alpha$를 정의하자.
     $$
     \alpha(x) = \varphi( f(x) + \chi_E(x))
     $$

     * Standard topology와 그에 대한 Borel $\sigma$-algebra (혹은 더 큰 $\sigma$-algebra) 가정 시, $E$는 measurable set.
       * Borel set : 어떤 topology의 open set을 countable union/intersection, relative complement하여 얻을 수 있는 set.
       * Borel $\sigma$-algebra : 어떤 topology의 모든 Borel set을 다 모은 collection. 이는 $\sigma$-algebra가 된다.
     * 따라서 $\chi_E$는 measurable.
     * $\varphi$는 continuous function이므로, 마찬가지로 Standard topology와 그에 대한 Borel $\sigma$-algebra 가정 시 measurable function.
       * open set에 대한 $\varphi$의 inverse image는 항상 open이 될텐데, 이는 Borel $\sigma$-algebra의 원소이고, 그에 따라 measurable.
     * 따라서 $\alpha$는 measurable function on $X$



### 1.10 Theorem (A $\sigma$-algebra Generated By $\mathscr F$)

*If $\mathscr F$ is any collection of subsets of $X$, there exists a smallest $\sigma$-algebra $\mathfrak M^\ast$ in $X$ such that $\mathscr F \subset \mathfrak M^\ast$.*



#### Proof

* $\Omega$ : $\mathscr F$를 포함하는 $X$의 모든 $\sigma$-algebra의 family
  * $X$의 모든 부분집합의 collection은 $\sigma$-algebra이며, $\Omega$의 원소가 됨.
  * 따라서 $\Omega$는 nonempty.
* $\mathfrak M^\ast$ : 모든 $\mathfrak M \in \Omega$의 intersection으로 정의한다.
  * $\Omega$의 정의에 의해 $\mathscr F \subset \mathfrak M^\ast$

* $\mathfrak M^\ast$가 $\sigma$-algebra라는 것만 확인하면 증명 끝.
  * 만약 $A_n \in \mathfrak M^\ast, n=1,2,...$이면, $\forall \mathfrak M \in \Omega, A_n \in \mathfrak M, n=1,2,...$이 된다.
  * 각 $\mathfrak M$은 모두 $\sigma$-algebra이므로, $\forall \mathfrak M \in \Omega, \cup_n A_n \in \mathfrak M$
  * 따라서 $\cup_n A_n \in \mathfrak M^\ast = \cap_{\mathfrak M \in \Omega} \mathfrak M$
* 나머지 성질도 유사하게 증명 가능



### 1.11 Definition (Borel Sets, Borel $\sigma$-algebra, Borel function)

* Let $X$ be a topological space. 

* Theorem 1.10에 의해, $X$의 모든 open set이 포함된 smallest $\sigma$-algebra $\mathscr B$ in $X$가 존재한다. 

* 이 $\mathscr B$의 원소를 **Borel sets of $X$**라고 한다.

  * Open set의 countable union/intersection, relative complement로 나타낼 수 있는 set들

  * Open set의 complement인 closed set도 Borel set이다.

  * Closed set의 countable union을 $F_\sigma$, open set의 countable intersection을 $G_\delta$라고 한다.

    *cf)* $F, G$는 closed, open set을 의미하고, $\sigma, \delta$는 union(summe), intersection(Durchschnitt)를 의미한다.

* $\mathscr B$는 $\sigma$-algebra이므로, Borel set이 measurable set의 역할을 하여 $X$를 measurable space로 볼 수 있다.

  * 보다 정확한 표현으로는, measurable space $(X, \mathscr B)$로 나타낼 수 있다.

* 만약 $f:X \to Y$가 continuous mapping of $X$이고, $Y$가 어떤 topological space라면,
  * Continuity의 정의에 의해, 모든 open set $V \subset Y$에 대해, $f^{-1}(V)$도 open set이 된다.
  * 즉 $f^{-1}(V) \in \mathscr B$가 성립한다.
  * 따라서 모든 continuous mapping of $X$는 *Borel measurable*이다.

* Borel measurable한 mapping을 **Borel mappings**, 혹은 **Borel functions**로 부른다.



### 1.12 Theorem

* Theorem 1.12.1의 $\Omega$는 어떤 함수 $f$의 measurability를 판정하기 위한 도구가 된다.

  * 단, 1.1에서 언급했던 것처럼 $\sigma$-algebra를 measurable set의 collection으로 본다는 가정 하에.

  $$
  \Omega = \left\{ E \subset Y : f^{-1}(E) \in \mathfrak M \right\}
  $$

  * 다음 두 statement는 동치
    * $\Omega$가 모든 open set을 포함한다.
    * $f$ is a measurable function.

* Theorem 1.12.3은 real-valued function의 measurability를 확인하는 criterion으로 흔히 사용된다.
* 또한 Theorem 1.12.4는 Theorem 1.7.2를 일반화한 정리이다.
  * Theorem 1.7.2 : *If $X$ is a measurable space, if $f: X \rightarrow Y$ is measurable, and if $h=g \circ f$, then $h: X \to Z$ is measurable.*

*Suppose $\mathfrak M $ is a $\sigma$-algebra in $X$, and $Y$ is a topological space. Let $f$ map $X$ into $Y$.*

1. *If $\Omega$ is the collection of all sets $E \subset Y$ such that $f^{-1}(E) \in \mathfrak M$, then $\Omega$ is a $\sigma$-algebra in $Y$.*
2. *If $f$ is measurable and $E$ is a Borel set in $Y$, then $f^{-1}(E) \in \mathfrak M$.*
3. *If $Y = [-\infty , \infty]$ and $f^{-1}((\alpha, \infty]) \in \mathfrak M$ for every real $\alpha$, then $f$ is measurable.*
4. *If $f$ is measurable, if $Z$ is a topological space, if $g : Y \to Z$ is a Borel mapping, and if $h = g \circ f$, then $h: X \to Z$ is measurable.*



#### Proof

**1.**

* $f^{-1}(Y) = X$이므로 $Y \in \Omega$

* $E \in \Omega$라고 하면, $f^{-1}(E) \in \mathfrak M$.
  $$
  \begin{align*}
  f^{-1}(E^c) &= \left\{ x \in X : f(x) \notin E \right\} \\
  &= \left\{ x \in X : f(x) \in E \right\}^c \\
  &= f^{-1}(E)^c \in \mathfrak M\\
  \implies E^c &\in \mathfrak M
  \end{align*}
  $$

* $\Omega$의 sigma-additivity는 아래와 같이 보일 수 있다.

  * $E_i \in \Omega, i=1,2,...$라고 하면, $\Omega$의 정의에 따라 다음이 만족한다.

    * $f^{-1}(E_i) \in \mathfrak M, i=1,2,...$

  * 아래 성질에 의해 $\cup_i E_i$도 $\Omega$의 원소가 된다.
    $$
    \begin{align*}
    f^{-1}\left( \bigcup_i E_i \right) &= \left\{ x \in X : f(x) \in \bigcup_i E_i \right\} \\
    &= \bigcup_i \left\{ x \in X : f(x) \in E_i \right\} \\
    &= \bigcup_i f^{-1}(E_i) \enspace \in \mathfrak M \\
    \implies \bigcup_i E_i  &\in \Omega
    \end{align*}
    $$

**2.**

* 1.에서와 같이 $\Omega$를 정의한다.
* $f$는 measurable $\iff$ $f^{-1}(E) \in \mathfrak M$ for all open $E \subset Y$
* 따라서 $\Omega$는 모든 open set in $Y$을 포함한다.
* 1.에 의해 $\Omega$는 $\sigma$-algebra이므로, 모든 Borel set은 $\Omega$에 속한다.

**3.**

* 1.에서와 같이 $\Omega$를 정의한다.
* Extended real line의 open set은 다음 세 형태 중 하나
  * $(\alpha, \infty ], [-\infty, \alpha), (\alpha, \beta)$
* Theorem의 조건에 의해, $\forall \alpha \in \mathbb R, f^{-1}((\alpha,\infty]) \in \mathfrak M \implies \forall \alpha \in \mathbb R, (\alpha,\infty] \in \Omega$ 

* $[-\infty, \alpha)$
  $$
  [-\infty, \alpha) = \bigcup_{n=1}^\infty \left[-\infty, \alpha-\frac{1}{n}\right]= \bigcup_{n=1}^\infty \left(\alpha-\frac{1}{n}, \infty \right]^c \in \Omega
  $$

* $(\alpha, \beta)$
  $$
  (\alpha, \beta) = [-\infty, \beta)\cap(\alpha, \infty] \in \Omega
  $$

* 임의의 open set in $[-\infty, \infty]$은 위 세 type의 segment의 countable union이고, $\Omega$는 $\sigma$-algebra이기 때문에, $\Omega$는 모든 open set in $Y$를 포함한다.

  * 즉 $f$ is measurable.

**4.**

* Let $V \subset Z$ be open. $g$는 Borel mapping이므로, $g^{-1}(V)$는 Borel set of $Y$.

* $f$가 measurable이고, $g^{-1}(V)$는 Borel set of $Y$이므로, Theorem 1.12.2에 의해
  $$
  h^{-1}(V) = f^{-1}(g^{-1}(V)) \in \mathfrak M \implies h \text{ measurable}
  $$





### 1.13 Definition ($\limsup$, $\liminf$)

*Let $\{ a_n \}$ be a sequence in $[-\infty, \infty]$, and put*
$$
b_k = \sup_{k \le \ell} a_\ell , \quad k=1,2,\cdots \\
\limsup_{n \to \infty} a_n := \inf_k b_k  = \inf_k   \sup_{k \le \ell} a_\ell
$$
*We call $\limsup_{n\to \infty}a_n$ the **upper limit** of $\{ a_n \}$. The **lower limit** is defined analogously: simply interchange $\sup$ and $\inf$ in the above definition.*
$$
\liminf_{n \to \infty} a_n := \sup_k b_k  = \sup_k \inf_{k \le \ell} a_\ell
$$
*Suppose $\{f_n\}$ is a sequence of extended-real functions on a set $X$. Then $\sup_n f_n$ and $\limsup_{n\to\infty}f_n$ are the functions defined on $X$ by*
$$
\left( \sup_n f_n\right)(x) = \sup_n (f_n(x)) \\
\left( \limsup_{n\to\infty} f_n\right)(x) = \limsup_{n\to\infty} (f_n(x)) \\
$$
*If $f(x) = \lim_{n\to\infty}f_n(x)$, the limit being assumed to exist at every $x \in X$, then we call $f$ the **pointwise limit** of the sequence $\{f_n\}$*



#### Properties

1. $b_1 \ge b_2 \ge b_3 \ge \cdots$로 decreasing이므로, 이 $\inf$로 $\{b_k\}$가 수렴하게 된다.

$$
b_k \to \limsup_{n\to \infty}a_n \enspace \text{ as }k \to \infty
$$

2. 이 $\limsup$ 값으로 수렴하는 $\{ a_n\}$의 subsequence $\{a_{n_i}\}$가 존재한다.
   $$
   \exists \{ n_i \} \text{ such that }a_{n_i} \to \limsup_{n\to \infty}a_n \enspace \text{ as }i \to \infty
   $$

   * $\limsup a_n$은 $\{ a_n\}$의 limit point

     * Let $\varepsilon > 0$ be given.

     * $b_k \to \limsup a_n$이므로
       $$
       \exists K \text{ such that } k\ge K \implies \left\vert b_k - \limsup_{n\to\infty} a_n\right\vert < \frac{\varepsilon}{2}
       $$

     * 모든 $k$에 대하여, $b_k = \sup_{k \le \ell} a_\ell$이므로, $b_k$로 수렴하는 subsequence $\{a_{n_i}\}$ 존재.
       $$
       \exists I \text{ such that } i \ge I \implies \left\vert a_{n_i} - b_k \right\vert < \frac{\varepsilon}{2}
       $$

     * $k \ge K , i \ge I$이면
       $$
       \left\vert a_{n_i} -\limsup_{n\to\infty} a_n\right\vert < \left\vert a_{n_i} - b_k \right\vert + \left\vert b_k - \limsup_{n\to\infty} a_n\right\vert< \varepsilon
       $$

   * 그러므로 $\limsup$ 값으로 수렴하는 $\{ a_n\}$의 subsequence $\{a_{n_i}\}$가 존재.

3. $\liminf a_n = - \limsup (-a_n)$

4. If $\{ a_n \}$ converges,
   $$
   \limsup_{n\to\infty}a_n = \liminf_{n\to\infty}a_n = \lim_{n\to\infty}a_n
   $$



### 1.14 Theorem 

*If $f_n:X\to [-\infty, \infty]$ is measurable, for $n=1,2,...$, and* 
$$
g = \sup_{n \ge 1}f_n, \quad h = \limsup_{n\to\infty}f_n,
$$
*then $g$ and $h$ are measurable.*



#### Proof

* $g$ is measurable

  * 다음이 만족하는 것을 확인.
    $$
    \begin{align*}
    g^{-1}((\alpha,\infty]) &= \left\{ x\in X : \sup_{n \ge 1} f_n(x) \in (\alpha, \infty] \right\} \\
    &= \bigcup_{n=1}^\infty \left\{ x\in X :  f_n(x) \in (\alpha, \infty] \right\} \\
    &= \bigcup_{n=1}^\infty f_n^{-1}((\alpha,\infty]) 
    \end{align*}
    $$

  * $(\alpha,\infty]$는 Borel set이고 $f$ measurable이므로, Theorem 1.12.2에 의해 $f_n^{-1}((\alpha,\infty])$는 measurable set

  * 따라서 $g^{-1}((\alpha,\infty]) $도 measurable set이 되고, Thorem 1.12.3에 의해 $g$는 measurable function.

* $h$ is measurable

  * $\sup$ 뿐만 아니라 $\inf$에 대해서도 위 증명이 성립한다.
  * $h = \inf_{k\ge 1}\sup_{\ell \ge k}f_\ell$이므로 Theorem 1.12.4에 의해 $h$는 measurable function.



#### Corollaries

1. *The limit of every pointwise convergent sequence of complex measurable functions is measurable.*

2. *If $f$ and $g$ are measurable (with range in $[-\infty, \infty]$), then so are $\max\{ f, g \}$ and $\min\{ f, g \}$. In particular, this is true of the functions*
   $$
   f^+ = \max \{ f, 0\} \quad \text{ and }\quad f^-= -\min\{f,0\}
   $$
   

### 1.15 Definition (Positive and Negative Parts)

*The above functions $f^+$ and $f^-$ are called the **positive** and **negative parts** of $f$. We have $\vert f \vert = f^+ + f^-$ and $f = f^+ - f^-$, a standard representation of $f$ as a difference of two nonnegative functions, with a certain minimality property as follows:*

#### Proposition

*If $f = g - h , g \ge 0$, and $h\ge 0$, then$f^+ \le g$ and $f^- \le h$*

* $f = g-h \le g$, $0 \le g$이므로, $f^+ = \max\{f, 0\} \le g$
* $f = g - h \ge -h$, $0 \ge -h$이므로, $\min \{f , 0\} \ge -h \implies f^- = -\min \{f , 0\} \le h$ 



### 1.16 Definition (Simple Functions)

*A complex function $s$ on a measurable space $X$ whose range consists of only finitely many points will be called a **simple function**. Among these are the nonnegative simple functions, whose range is a finite subset of $[0, \infty)$. Note that we explicitly exclude $\infty$ from the values of a simple function.*

*If $\alpha_1, ... , \alpha_n$ are the distinct values of a simple function $s$, and if we set $A_i = \{ x : s(x) = \alpha_i \}$, then clearly*
$$
s = \sum_{i=1}^{n} \alpha_i \chi_{A_i},
$$
*where $\chi_{A_i}$ is the characteristic function of $A_i$, as defined in Section 1.9.4.*

*It is also clear that $s$ is measurable if and only if each of the sets $A_i$ is measurable.*



### 1.17 Theorem (Approximation by Simple Function)

*Let $f : X \to [0, \infty]$ be measurable. There exist simple measurable functions $s_n$ on $X$ such that*

1. *$0 \le s_1 \le s_2 \le \cdots \le f$*
2. *$s_n(x) \to f(x) \text{ as }n \to \infty$, for every $x \in X$*



#### Proof

* 양의 정수 $n$과 실수 $t$에 대하여, 아래 조건을 만족하는 정수 $k = k_n(t)$가 unique하게 존재한다.
  $$
  \frac{k}{2^n} \le t < \frac{k+1}{2^n} \quad \text{ or }\quad t - \frac{1}{2^n}< \frac{k}{2^n}\le t
  $$

* 아래와 같이 $\varphi_n(t)$를 정의한다.
  $$
  \varphi_n(t) = \begin{cases}
  {k_n(t)}/{2^n} & \text{if }0 \le t < n\\
  n & \text{if }n \le t \le \infty
  \end{cases}
  $$

* $\varphi_n(t)$는 다음 성질을 맍고한다.

  * $0 \le \varphi_1\le \varphi_2 \le  \cdots \le t$
  * $\varphi_n(t) \to t $ as $n \to \infty$, for every $t \in [0, \infty]$.

  $$
  \because \enspace t - \frac{1}{2^n}< \frac{k_n(t)}{2^n}\le t \quad \text{if }0 \le t \le n
  $$

  * $\varphi_n$ is a Borel function on $[0,\infty]$

    * 풀어서 써보면 $\varphi_n$은 아래와 같으므로, $\varphi_n$의 preimage가 Borel set이 됨을 알 수 있다.
      $$
      \varphi_n(t) = \begin{cases}
      0 & \text{if }0 \le t < 1/2^n\\
      {1}/{2^n} & \text{if }1/2^n \le t < 2/2^n\\
      &\vdots \\
      {(n2^n -1)}/{2^n} & \text{if }{(n2^n -1)}/{2^n} \le t < n\\
      n & \text{if }n \le t \le \infty
      \end{cases}
      $$

* $f$의 simple function approximation $s_n$을 아래와 같이 정의한다.
  $$
  s_n = \varphi_n \circ f
  $$

  * $f : X \to [0,\infty]$는 measurable이고, $\varphi_n$은 Borel function이므로, Theorem 1.12.4에 의해 $s_n$은 measurable.



### 1.18 Definition (Elementary Properties of Measures)

1. *A **positive measure** is a function $\mu$, defined on a $\sigma$-algebra $\mathfrak M$, whose range is in $[0,\infty]$ and which is **countably additive**. This means that if $\{A_i\}$ is a disjoint countable collection of members of $\mathfrak M$, then*
   $$
   \mu \left( \bigcup_{i=1}^\infty A_i \right) = \sum_{i=1}^\infty \mu(A_i)
   $$
   *To avoid trivialities, we shall also assume that $\mu(A) < \infty$ for at least one $A \in \mathfrak M$.*

2. *A **measure space** is a measurable space which has a positive measure defined on the $\sigma$-algebra of its measurable sets.*

3. *A **complex measure** is a complex-valued countably additive function defined on a $\sigma$-algebra.*



### 1.19 Theorem

*Let $\mu$ be a positive measure on a $\sigma$-algebra $\mathfrak M$. Then*

1. *$\mu(\emptyset) = 0$*
2. *$\mu(A_1 \cup \cdots \cup A_n) = \mu(A_1) + \cdots + \mu(A_n)$ if $A_1, ... , A_n$ are pairwise disjoint members of $\mathfrak M$*

3. *$A \subset B$ implies $\mu(A)\le \mu(B)$ if $A \in \mathfrak M$, $B \in \mathfrak M$*

4. *$\mu(A_n) \to \mu(A)$ as $n \to \infty$ if $A = \cup_{n=1}^\infty A_n$, $A_n \in \mathfrak M$,*
   $$
   A_1 \subset A_2 \subset A_3 \subset \cdots
   $$

5. *$\mu(A_n) \to \mu(A)$ as $n \to \infty$ if $A = \cap_{n=1}^\infty A_n$, $A_n \in \mathfrak M$,*
   $$
   A_1 \supset A_2 \supset A_3 \supset \cdots
   $$
   *and $\mu(A_1)$ is finite.*



#### Proof

**1.**

* $\mu(A) < \infty$인 $A \in \mathfrak M$을 하나 고른다.

* $A_1 = A, A_2 = A_3 = \cdots = \emptyset$를 Definition 1.18.1에 대입하면
  $$
  \mu \left( \bigcup_{i=1}^\infty A_i \right) = \mu(A) = \mu(A) + \sum_{i=2}^\infty \mu(\emptyset)
  $$

* 따라서 $\mu(\emptyset) = 0$

**2.**

* $A_{n+1} = A_{n+2} = \cdots = \emptyset$으로 Definition 1.18.1 식 사용.

**3.**

* $B = A \cup (B- A)$이고, $A \cap (B-A) = \emptyset$이므로, 
  $$
  \mu(B) = \mu(A) + \mu(B-A) \ge \mu(A)
  $$

* 

**4.**

* $B_1 = A_1, B_n = A_n - A_{n-1}$ for $n \ge 2$ 로 두면, 다음이 만족한다.
  * $B_n \in \mathfrak M$
  * $B_i \cap B_j = \emptyset$ if $i \neq j$
  * $A_n = \cup_{i=1}^n B_i$, $A = \cup_{i=1}^\infty A_i = \cup_{i=1}^\infty B_i$
* 따라서 $\mu(A_n) = \sum_{i=1}^{n}\mu(B_i)$, $\mu(A) = \sum_{i=1}^{\infty}\mu(B_i)$이 만족한다.
* 그러므로 $\mu(A_n) \to \mu(A)$ as $n \to \infty$

**5.**

* $C_n = A_1 - A_n$ for $n \ge 2$.
  * $C_1 \subset C_2 \subset C_3 \subset \cdots$
  * $A_n \subset A_1$이므로, $\mu(C_n) = \mu(A_1) - \mu(A_n)$ 
  * $C_n \in \mathfrak M$

* 아래 사항이 만족한다.
  $$
  \begin{align*}
  C&= \bigcup_{i=1}^\infty C_i \\
  &= \bigcup_{i=1}^\infty (A_1 \cap A_i^c) \\
  &= \left(\bigcup_{i=1}^\infty A_1 \right) \cap \left( \bigcup_{i=1}^\infty A_i^c \right)\\
  &= A_1 \cap \left( \bigcap_{i=1}^\infty A_i \right)^c\\
  &= A_1 \cap A^c\\
  &= A_1 - A\\
  \end{align*}
  $$

* Theorem 1.19.4를 적용하면 아래와 같다.
  $$
  \mu(C_n) =\mu(A_1 - A_n) = \mu(A_1) - \mu(A_n) \\
  \to \mu(C) = \mu(A_1 - A)= \mu(A_1) - \mu(A)
  $$

* 따라서 $\mu(A_n) \to \mu(A)$ as $n\to\infty$



### 1.20 Examples

* Measure space를 construct하는 것은 이론적으로 여러 수고로움을 필요로 하지만, 다음과 같이 몇가지 간단한 measure space의 예시를 생각해볼 수 있다.

1. **Counting measure**

   * For any $E \subset X$, where $X$ is any set, define $\mu(E) = \infty$ if $E$ is an infinite set, and let $\mu(E)$ be the number of points in $E$ if $E$ is finite. This $\mu$ is called the **counting measure** on $X$.
   * 자연수의 집합 $\mathbb N$ 위에서의 counting measure를 생각해보자.
     * Let $A_n = \{ n, n+1, n+2, ...\}$.
     * Then $A = \cap A_n = \emptyset$ but $\mu(A_n) = \infty$ for all $n \in \mathbb N$.
     * $\infty = \mu(A_n) \nrightarrow \mu(A) = 0$
     * 즉, Theorem 1.19.5의 "$\mu(A_1)$ is finite" 조건은 불필요한 조건이 아님.

2. **Unit mass concentrated at $x_0$**

   * 어떤 $x_0 \in X$에 대해, 아래와 같이 $\mu$를 정의한다.
     $$
     \mu(E) = \begin{cases}
     1 & \text{ if }x_0 \in E \\
     0 & \text{ if }x_0 \notin E 
     \end{cases}
     $$



### 1.21 A Comment on Terminology

#### Measure theory의 terminology에 대한 Walter Rudin의 생각

* 흔히 "ordered triple" $(X,\mathfrak M , \mu)$의 형태로 measure space를 정의한다.
  * $X$는 set, $\mathfrak M$는 $\sigma$-algebra in $X$, $\mu$는 $\mathfrak M$ 위에서 정의된 measure.
* 마찬가지로, measurable space는 "ordered pair" $(X, \mathfrak M)$의 형태로 나타낸다.

* 논리적으로 틀린 점이 없고 편리하지만, 다소 redundant한 점이 있는 표현이다.
  * $(X, \mathfrak M)$에서 $X$는 $\mathfrak M$의 가장 큰 원소일 뿐이므로, $\mathfrak M$을 알면 $X$를 알게 된다.
  * 모든 measure는 그 domain으로 $\sigma$-algebra를 가지므로, $(X, \mathfrak M, \mu)$에서 $\mu$를 알면 $\mu$가 정의된 $\sigma$-algebra인 $\mathfrak M$를 알 수 있고, $X$도 알 수 있다.

* 따라서 아래와 같이 표현하는 것도 전혀 문제가 없다.
  * *"Let $\mu$ be a measure."*
  * $\sigma$-algebra나 measure가 정의된 공간을 강조하고 싶다면, *"Let $\mu$ be a measure on $\mathfrak M$"* 혹은 *"Let $\mu$ be a measure on $X$".*

*  



### 1.22 Arithmetic in $[0, \infty]$

* 



### 1.23 Definition (Integration of Positive Functions)

*If $s : X \to [0,\infty)$ is a measurable simple function, of the form*
$$
s = \sum_{i=1}^n \alpha_i \chi_{A_i},
$$
 *where $\alpha_1, ..., \alpha_n$ are the distinct values of $s$, and if $E \in \mathfrak M$, we define*
$$
\int_E s d\mu = \sum_{i=1}^n \alpha_i \mu(A_i \cap E).
$$
*The convention $0\cdot \infty = 0$ is used here; it may happen that $\alpha_i = 0$ for some $i$ and that $\mu(A_i \cap E) = \infty$.*



*If $f : X \to [0,\infty]$ is measurable, and $E \in \mathfrak M$, we define*
$$
\int_E f d\mu = \sup \int_E s d\mu,
$$
*the supremum being taken over all simple measurable functions $s$ such that $0 \le s \le f$.* 

* 이 식의 좌변을 **Lebesgue integral of $f$ over $E$, with respect to the measure $\mu$**라고 부른다.
  * 그 값은 $[0,\infty]$에 속한다.

* Simple function의 경우와 그렇지 않은 경우에 대해 두 가지 방법으로 정의를 한 것 같지만, 아래 정의는 $f$가 simple function일 때도 적용된다.
  * 이 때는 $0 \le s \le f$의 $s$ 중 supremum을 취하면 $s=f$이 된다.

* 위 정의에서 왜 $f$가 measurable function이어야 할까?
  * $f$가 measurable이어야 $f$의 preimage $f^{-1}(A)$이 measurable하고, simple function에 대한 integration을 정의할 수 있기 때문이다. 
    * $\mu(f^{-1}(A))$가 정의되어야함.

### 1.24 Proposition

*The functions and sets occurring in the following are assumed to be measurable:*

1. *If $0\le f \le g$, then $\int_E f d\mu \le \int_E g d\mu$.*

2. *If $A \subset B$ and $f \ge 0$, then $\int_A f d\mu \le \int_B f d\mu$.*

3. *If $f \ge 0$ and $c$ is a constant, $0 \le c < \infty$, then*
   $$
   \int_E cf d\mu = c \int_E f d\mu
   $$

4. *If $f(x)=0$ for all $x \in E$, then $\int_E f d\mu = 0$, even if $\mu(E) = \infty$.*

5. *If $\mu(E) = 0$, then $\int_E f d\mu = 0$, even if $f(x) = \infty$ for every $x \in E$.*

6. *If $f \ge 0$, then $\int_E f d\mu = \int_X \chi_E f d\mu$.*



#### Proof

**1.**
$$
\begin{align*}
&f\le g \\
\implies &\{ s : 0\le s\le f\} \subset \{ s : 0\le s\le g\} \\
\implies &\int_E f d\mu = \sup_{0 \le s \le f, s \text{ : simple}} \int_E s d\mu \le
\sup_{0 \le s \le g, s \text{ : simple}} \int_E s d\mu = \int_E g d\mu
\end{align*}
$$
**2.**
$$
\begin{align*}
\int_B f d\mu &= \sup_{\sum_{i=1}^n \alpha_i \chi_{A_i} \le f} \left\{ \sum_{i=1}^{n} \alpha_i\mu(A_i \cap B) \right\} \\
&=\sup_{\sum_{i=1}^n \alpha_i \chi_{A_i} \le f} \left\{ \sum_{i=1}^{n} \alpha_i[\mu(A_i \cap A)+\mu(A_i \cap (B-A))] \right\}\\
&\ge\sup_{\sum_{i=1}^n \alpha_i \chi_{A_i} \le f} \left\{ \sum_{i=1}^{n} \alpha_i\mu(A_i \cap A) \right\} = \int_A f d\mu
\end{align*}
$$
**3.**
$$
\begin{align*}
c\int_E f d\mu &= \sup_{ s : 0\le s\le f} c\int_E s d\mu\\
&= \sup_{\sum_{i=1}^n \alpha_i \chi_{A_i} \le f} \left\{ c\sum_{i=1}^{n} \alpha_i\mu(A_i \cap E) \right\} \\
&= \sup_{\sum_{i=1}^n \beta_i \chi_{A_i} \le cf} \left\{ \sum_{i=1}^{n} \beta_i\mu(A_i \cap E) \right\} \enspace(\beta_i = c \alpha_i)\\
&= \sup_{ s : 0\le s\le cf} \int_E s d\mu \\
&= \int_E cf d\mu
\end{align*}
$$
**4.**

* 상수함수 $f = 0$에 대해, $0 \le s \le f = 0$을 만족하는 simple function $s$는 $s=0$ 밖에 없으므로,
  $$
  \int_E f d\mu = \sup_{ s : 0\le s\le f} \int_E s d\mu =   \int_E 0 d\mu = \sum_{i=1}^{n} 0 \cdot \mu(A_i \cap E) = 0
  $$

  * $0\cdot \infty= 0$의 convention을 사용하고 있으므로, 이는 $\mu(A_i \cap E) = \infty$의 경우에도 성립.

**5.**

* $A_i \cap E \subset E \implies 0\le \mu(A_i \cap E) \le \mu(E)=0$이므로,

$$
\int_E f d\mu = \sup_{ s : 0\le s\le f} \int_E s d\mu = \sup_{\sum_{i=1}^n \alpha_i \chi_{A_i} \le f}  \sum_{i=1}^{n} \alpha_i \cdot \mu(A_i \cap E) = \sup_{\sum_{i=1}^n \alpha_i \chi_{A_i} \le f}  \sum_{i=1}^{n} \alpha_i \cdot 0= 0
$$

**6.**
$$
\int_X \chi_E f d\mu =\sup_{\sum_{i=1}^n \alpha_i \chi_{A_i} \le \chi_Ef}  \sum_{i=1}^{n} \alpha_i \cdot \mu(A_i) \\
= \sup_{\sum_{i=1}^n \alpha_i \chi_{A_i} \le \chi_Ef}  \sum_{i=1}^{n} \alpha_i \cdot \mu(A_i \cap E)
$$


### 1.25 Proposition

*Let $s$ and $t$ be nonnegative measurable simple functions on $X$. For $E \in \mathfrak M$, define*
$$
\varphi(E) = \int_E s d\mu.
$$
*Then $\varphi$ is a measure on $\mathfrak M$. Also*
$$
\int_X (s+t) d\mu = \int_X s d\mu + \int_X t d\mu.
$$


#### Proof

* 



### 1.26 Theorem (Lebesgue's Monotone Convergence Theorem)

*Let $\{ f_n \}$ be a sequence of measurable functions on $X$, and suppose that*

1. *$0 \le f_1(x) \le f_2(x)\le \cdots \le \infty$ for every $x \in X$,*
2. *$f_n(x) \to f(x)$ as $n \to \infty$, for every $x \in X$.*

*Then $f$ is measurable, and*
$$
\int_X f_n d\mu \to \int_X f d\mu \quad \text{ as }n \to \infty.
$$


#### Proof

* 



### 1.27 Theorem

