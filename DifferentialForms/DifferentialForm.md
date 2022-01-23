# 1. Integration on Chains

## 1.1. Algebraic Preliminaries

* $\mathbb R$ 위에서 정의된 vector space $V$ 에 대하여, $V$의 $k$-fold product $V \times \cdots \times V$를 $V^k$로 나타낸다.

* 함수 $T : V^k \rightarrow \mathbb{R}$가 다음을 만족한다면 $T$는 **multilinear**하다고 한다.

  For each $i$ with $1 \le i \le k$, we have
  $$
  T(\cdots, v_i + v_i^\prime, \cdots) = T(\cdots, v_i, \cdots) + T(\cdots, v_i^\prime, \cdots) \\
  T(\cdots, av_i, \cdots) = a\cdot T(\cdots, v_i, \cdots)
  $$

* Multilinear function $T : V^k \rightarrow \mathbb R$를 **$k$-tensor on $V$** 라고 부르며, 모든 $k$-tensor의 모임을 $\mathscr T^k(V)$라고 한다.

  * $\mathscr T^k(V)$는 vector space over $\mathbb R$이다.

  $$
  (S+T)(v_1, \cdots, v_k) = S(v_1, \cdots, v_k) + T(v_1, \cdots, v_k)\\
  (aS)(v_1, \cdots, v_k) = a\times S(v_1, \cdots, v_k)
  $$

* $S \in \mathscr T^k(V), T\in \mathscr T^l(V)$에 대하여, $S,T$의 tensor product $S\otimes T \in \mathscr T^{k+l}(v)$를 다음과 같이 정의한다.
  $$
  S\otimes T (v_1, \cdots, v_k, v_{k+1}, \cdots, v_{k+l}) = S(v_1, \cdots, v_k) \cdot T( v_{k+1}, \cdots, v_{k+l})
  $$

  *  Tensor product 연산 $\otimes$는 다음과 같은 성질을 만족한다.
    $$
    (S_1 + S_2) \otimes T = S_1 \otimes T + S_2 \otimes T \\
    S \otimes (T_1 + T_2) = S \otimes T_1 + S\otimes T_2 \\
    (aS) \otimes T = S \otimes (aT) = a(S\otimes T) \\
    (S \otimes T) \otimes U = S \otimes (T \otimes U)
    $$

  * 결합법칙이 만족하는 네 번째 성질로 인해 higher-order products $T_1 \otimes \cdots \otimes T_r$를 괄호 없이 나타낸다.

* $\mathscr T^1(V)$는 linear function $T : V \rightarrow \mathbb R$들의 모임이므로, $V$의 dual space $V^\ast$와 같다.

  * Tensor product 연산 $\otimes$는 $\mathscr T^k(V)$를 $\mathscr T^1 (V)$로 나타낼 수 있게 해주는 역할을 한다.



### Theorem 4.1

> Let $v_1, \cdots, v_n$ be a basis for $V$, and let $\varphi_1, \cdots, \varphi_n$ be the dual basis, $\varphi_i(v_j) = \delta_{ij}$. Then the set of all $k$-fold tensor products
> $$
> \varphi_{i_1} \otimes \cdots \otimes \varphi_{i_k}, \enspace \enspace 1\le i_1, \cdots, i_k \le n
> $$
> is a basis for $\mathscr T^k (V)$, which therefore has dimension $n^k$.

#### Proof

$$
\begin{align*}
\varphi_{i_1} \otimes \cdots \otimes \varphi_{i_k} (v_{j_1}, \cdots , v_{j_k}) &= \delta_{i_1 j_1} \cdots \delta_{i_k j_k} \\
&= \begin{cases}
1 \quad \text{if } i_1 = j_1, \cdots, i_k = j_k ,\\
0 \quad \text{otherwise.}
\end{cases}
\end{align*}
$$

* 먼저 $\text{span} \{\varphi_{j_1} \otimes \cdots \otimes \varphi_{j_k}\} = \mathscr T^k(V)$를 보인다.
* $w_1, \cdots, w_k$가 $w_i = \sum_{j=1}^n a_{ij} v_j$이고 $T \in \mathscr T^k (V)$라면,

$$
\begin{align*}
T(w_1, \cdots, w_k) &= \sum_{j_1=1}^{n}\cdots \sum_{j_k=1}^{n} a_{1j_1}\cdots a_{kj_k} T(v_{j_1}, \cdots ,v_{j_k}) \\
&= \sum_{j_1=1}^{n}\cdots \sum_{j_k=1}^{n} \varphi_{j_1}(w_1)\cdots \varphi_{j_k}(w_k) T(v_{j_1}, \cdots ,v_{j_k}) \\
&= \sum_{j_1=1}^{n}\cdots \sum_{j_k=1}^{n} T(v_{j_1}, \cdots ,v_{j_k}) \varphi_{j_1} \otimes \cdots \otimes \varphi_{j_k}(w_1, \cdots, w_k)\\
\therefore \quad T &= \sum_{j_1=1}^{n}\cdots \sum_{j_k=1}^{n} T(v_{j_1}, \cdots ,v_{j_k}) \varphi_{j_1} \otimes \cdots \otimes \varphi_{j_k}\\
\end{align*}
$$

* 이제 $\{\varphi_{j_1} \otimes \cdots \otimes \varphi_{j_k}\}$가 linearly independent임을 보인다.
* 다음을 만족하는 수들 $a_{i_1, \cdots, i_k}$가 있다고 한다면,

$$
\sum_{i_1=1}^{n}\cdots \sum_{i_k=1}^{n} a_{i_1, \cdots, i_k} \varphi_{i_1} \otimes \cdots \otimes \varphi_{i_k} = \mathbf 0 \enspace \text{(zero function)}
$$

* 양변에 $(v_{j_1}, \cdots, v_{j_k})$를 대입하면 $a_{j_1, \cdots, j_k} = 0$을 얻는다.



### Pullback

* Linear transformation $f : V\rightarrow W$에 대하여, 다음과 같이 또다른 linear transformation $f^\ast : \mathscr T^k(W) \rightarrow \mathscr T^k(V)$을 정의할 수 있다.
  $$
  f^\ast T(v_1, \cdots ,v_k) = T(f(v_1), \cdots, f(v_k))
  $$
  for $T \in \mathscr T^k(W)$ and $v_1, \cdots, v_k \in V$.
  * 이와 같이 정의된 $f^\ast T$를 **a pullback of $T$ by $f$**라고 한다.
  * 다음 성질이 만족함을 간단히 확인할 수 있다.

  $$
  f^\ast (S\otimes T) = f^\ast S \otimes f^\ast T \\
  (f \circ g)^\ast T = g^\ast(f^\ast T)
  $$


### Inner product

* $\mathbb R^n$의 Inner product를 $\langle \cdot , \cdot \rangle$라고 하자.
* $\langle \cdot , \cdot \rangle$는 $\mathscr T^2(\mathbb R^n)$의 원소이다.



### Theorem 4.2

> If $T$ is an inner product on $V$, there is a basis $v_1, \cdots, v_n$ for $V$ such that $T(v_i, v_j) = \delta_{ij}$. (Such a basis is called **orthonormal** with respect to the inner product $T$.) Consequently, there is an isomorphism $f : \mathbb R^n \rightarrow V$ such that $T(f(x), f(y)) = \langle x , y \rangle$ for $x,y \in \mathbb R^n$. In other words $f^\ast T = \langle \cdot , \cdot \rangle$ .

* $n$차원 vector space $V$에서 inner product $T$가 정의된다면,

  * $V$는 orthonormal basis가 존재한다.
  * 또한, $V$의 내적 $T \in \mathscr T^2(V)$를 $\mathbb R^n$으로 pullback 했을 때 $\mathbb R^n$의 내적 $\langle \cdot , \cdot \rangle \in \mathscr T^2(\mathbb R^n)$이 되는 isomorphism $f : \mathbb R^n \rightarrow V$가 존재한다.

  $$
  f^\ast T = \langle \cdot , \cdot \rangle \in \mathscr T^2(\mathbb R^n)
  $$



#### Proof

* $w_1, \cdots, w_n$을 $V$의 a basis라고 한다면, 다음과 같이 projection을 이용해 orthogonal basis $w_1^\prime, \cdots, w_n^\prime$을 얻을 수 있다.

$$
\begin{align*}
w_1^\prime &= w_1 \\
w_2^\prime &= w_2  - \frac{T(w_1^\prime, w_2)}{T(w_1^\prime, w_1^\prime)} w_1^\prime\\
w_3^\prime &= w_3  - \frac{T(w_1^\prime, w_3)}{T(w_1^\prime, w_1^\prime)} w_1^\prime - \frac{T(w_2^\prime, w_3)}{T(w_2^\prime, w_2^\prime)} w_2^\prime\\
&\vdots
\end{align*}
$$

* 이를 normalize하면 다음과 같이 orthonormal basis $v_1, \cdots, v_n$을 얻는다.

$$
v_i = T(w_i^\prime, w_i^\prime)^{-1/2} w_i^\prime
$$

* $f(e_i) = v_i, \enspace i = 1, \cdots, n$으로 정의하면, $V$에서의 내적 $T$를 $f$로 pullback한 $f^\ast T$는 $\mathbb R^n$에서의 내적이 된다.
  * 임의의 $\mathbf a = (a_1, \cdots, a_n)^T, \mathbf b = (b_1, \cdots, b_n)^T \in \mathbb R^n$에 대하여, 다음이 만족한다.

  $$
  \langle \mathbf a, \mathbf b \rangle = \sum_{i=1}^n a_i b_i
  $$

  $$
  \begin{align*}
  f^\ast T(\mathbf a, \mathbf b) &= T(f(\mathbf a), f(\mathbf b)) \\
  &= \sum_{i=1}^n\sum_{j=1}^n a_i b_j T(f(e_i),f(e_j)) \\
  &= \sum_{i=1}^n\sum_{j=1}^n a_i b_j T(v_i, v_j) \\
  &= \sum_{i=1}^n a_i b_i \quad \because v_1, \cdots, v_n : \text{an orthonormal basis} \\
  &= \langle \mathbf a, \mathbf b \rangle
  \end{align*}
  $$



### Alternating Tensor, Wedge Product

* Determinant : $\text{det} \in \mathscr T^n(\mathbb R^n)$.

* 임의의 $i, j \in \{1, \cdots, k\}, i \neq j$에 대해 다음을 만족하는 $k$-tensor $\omega \in \mathscr T^k(V)$를 **alternating**, 혹은 **antisymmetric**이라고 한다.
  $$
  \omega(\cdots, v_i, \cdots, v_j, \cdots) = -\omega(\cdots, v_j, \cdots, v_i, \cdots)
  $$

* 모든 alternating $k$-tensor의 모임을 $\Lambda^k(V)^\ast$라고 한다.

  * $\Lambda^k(V)^\ast \subset \mathscr T^k(V)$

* 다음과 같이 함수 $\mathscr A : \mathscr T^k(V) \rightarrow \Lambda^k(V)^\ast$를 정의한다.
  $$
  \mathscr A(T)(v_1, \cdots, v_k) = \frac{1}{k!}\sum_{\sigma \in S_k} \text{sign}(\sigma) \cdot T(v_{\sigma(1)}, \cdots, v_{\sigma(k)})
  $$

  * $\mathscr A$는 임의의 $k$-tensor $T$를 alternating tensor $\mathscr A(T)$로 mapping하는 함수이다.
  * $S_k$는 $1, \cdots, k$의 모든 permuation의 모임이며, $\text{sign}$은 permutation의 sign 함수이다.
  * 임의의 $T\in \mathscr T^k(V)$에 대하여 $\mathscr A(T)$가 alternating 성질을 만족하는 것은 아래와 같이 확인할 수 있다.

  $$
  \begin{align*}
  \mathscr A(T)(\cdots, v_j, \cdots, v_i , \cdots) &= \frac{1}{k!}\sum_{\sigma \in S_k} \text{sign}(\sigma) \cdot T(\cdots, v_{\sigma(j)}, \cdots, v_{\sigma(i)} , \cdots) \\
  &= \frac{1}{k!}\sum_{\sigma \in S_k} \text{sign}(\sigma) \cdot \text{sign}(\tau_{ij})^2 \cdot T(\cdots, v_{\sigma\tau_{ij}(i)}, \cdots, v_{\sigma\tau_{ij}(j)} , \cdots) \\
  &= \text{sign}(\tau_{ij})\frac{1}{k!}\sum_{\sigma^\prime \in S_k} \text{sign}(\sigma^\prime) \cdot T(\cdots, v_{\sigma^\prime(i)}, \cdots, v_{\sigma^\prime(j)} , \cdots) \\
  &= \text{sign}(\tau_{ij}) \cdot \mathscr A(T)(\cdots, v_i, \cdots, v_j , \cdots)
  \end{align*}
  $$

  * 이때 $\tau_{ij}$는 $i$번째와 $j$번째를 바꾸는 permutation이며, $\text{sign}(\tau_{ij}) = -1$이다.

* Alternating tensor는 다음과 같은 성질을 만족한다.
  $$
  \omega \in \Lambda^k(V)^\ast \implies \mathscr A(\omega) = \omega \\
  T \in \mathscr T^k(V) \implies \mathscr A (\mathscr A(T)) = \mathscr A(T)
  $$

  * 첫 번째 성질은 다음과 같이 확인할 수 있다.

  $$
  \begin{align*}
  \mathscr A(\omega)(v_1, \cdots, v_k) &= \frac{1}{k!}\sum_{\sigma \in S_k} \text{sign}(\sigma) \cdot \omega( v_{\sigma(1)}, \cdots, v_{\sigma(k)}) \\
  &= \frac{1}{k!}\sum_{\sigma \in S_k} \text{sign}(\sigma)^2 \cdot \omega( v_1, \cdots, v_k) \\
   &=  \omega( v_1, \cdots, v_k) \\
  \end{align*}
  $$

  * 두 번째 성질은 첫 번째 성질에 의해 바로 만족.

* 앞서 $\mathscr T^k(V)$의 차원을 밝히기 위해, $V$의 dual basis의 tensor product를 고려했다.
* $\Lambda^k (V)^\ast$의 차원을 알아보기 위해 아래와 같이 새 product 연산, **wedge product**를 정의한다.

* $\omega \in \Lambda^k(V)^\ast, \eta \in \Lambda^l(V)^\ast$에 대하여, 다음과 같이 $\omega \wedge \eta \in \Lambda^{k+l}(V)^\ast$를 정의한다.
  $$
  \omega \wedge \eta = \frac{(k+l)!}{k!l!}\mathscr A(\omega \otimes \eta)
  $$

* Wedge product는 다음과 같은 성질을 만족한다.
  $$
  (\omega_1 + \omega_2)\wedge\eta = \omega_1 \wedge \eta + \omega_2 \wedge \eta \\
  \omega \wedge (\eta_1 + \eta_2) = \omega \wedge \eta_1 + \omega \wedge \eta_2 \\
  a(\omega \wedge \eta) = a\omega \wedge \eta = \omega \wedge a \eta \\
  \omega \wedge \eta = (-1)^{kl} \eta \wedge \omega \\
  f^\ast(\omega \wedge \eta) = f^\ast\omega \wedge f^\ast \eta
  $$

  * 대부분의 성질은 tensor product $\otimes$에 의해 만족한다는 사실이 간단히 확인 가능하다.

  * 네 번째 성질은 다음과 같이 확인할 수 있다.
    $$
    \begin{align*}
    proof
     
    \end{align*}
    $$



### Theorem 4.4

> If $\omega \in \Lambda^k(V)^\ast$, $\eta \in \Lambda^l(V)^\ast$, $\theta \in \Lambda^m(V)^\ast$, then
> $$
> (\omega \wedge \eta) \wedge \theta = \omega \wedge (\eta \wedge \theta) = \frac{(k+l+m)!}{k!l!m!}\mathscr A(\omega \otimes \eta \otimes \theta)
> $$

* 따라서 tensor product $\otimes$와 같이 higher-order wedge product  $\omega_1 \wedge \cdots \wedge \omega_r$를 괄호 없이 나타낼 수 있다.

#### Proof

* 다음 lemma를 이용하여 증명한다.
  * 아래 Lemma 1은 Lemma 2를 증명하는 데 쓰이며, Lemma 2는 아래 증명의 마지막 등호를 보이는 데 사용된다.

> 1. If $S \in \mathscr T^k (V)$ and $T \in \mathscr T^l(V)$ and $\mathscr A(S) = \mathbf 0$, then $\mathscr A(S \otimes T) = \mathscr A (T \otimes S) = \mathbf 0$.
> 2. $\mathscr A(\mathscr A(\omega \otimes \eta) \otimes \theta) = \mathscr A(\omega \otimes \eta \otimes \theta)= \mathscr A(\omega \otimes \mathscr A(\eta \otimes \theta))$

$$
\begin{align*}
(\omega \wedge \eta) \wedge \theta &=\frac{(k+l+m)!}{(k+l)!m!} \mathscr A((\omega \wedge \eta) \otimes \theta) \\
&=\frac{(k+l+m)!}{(k+l)!m!} \mathscr A\left( \frac{(k+l)!}{k!l!}\mathscr A(\omega \wedge \eta) \otimes \theta\right) \\
&= \frac{(k+l+m)!}{(k+l)!m!} \frac{(k+l)!}{k!l!} \mathscr A(\mathscr A(\omega \otimes \eta) \otimes \theta) \\
&= \frac{(k+l+m)!}{(k+l)!m!} \frac{(k+l)!}{k!l!} \mathscr A(\omega \otimes \eta \otimes \theta) 
\end{align*}
$$

#### Proof of the Lemma 1

> If $S \in \mathscr T^k (V)$ and $T \in \mathscr T^l(V)$ and $\mathscr A(S) = \mathbf 0$, then $\mathscr A(S \otimes T) = \mathscr A (T \otimes S) = \mathbf 0$.



#### Proof of the Lemma 2

> $\mathscr A(\mathscr A(\omega \otimes \eta) \otimes \theta) = \mathscr A(\omega \otimes \eta \otimes \theta)= \mathscr A(\omega \otimes \mathscr A(\eta \otimes \theta))$

$$
\begin{align*}
\mathscr A(\mathscr A(\eta \otimes \theta) - \eta \otimes \theta) &= \mathscr A(\mathscr A(\eta \otimes \theta)) -  \mathscr A(\eta \otimes \theta) \\ 
&=\mathscr A(\eta \otimes \theta)-  \mathscr A(\eta \otimes \theta) \enspace = \mathbf 0
\end{align*}
$$

* Lemma 1을 사용하면 다음과 같다.

$$
\begin{align*}
\mathbf 0 &= \mathscr A(\omega \otimes [\mathscr A(\eta \otimes \theta) - \eta \otimes \theta]) \\
&=\mathscr A(\omega \otimes \mathscr A(\eta \otimes \theta))) -  \mathscr A(\omega \otimes  \eta \otimes \theta)\\
\therefore \quad \mathscr A(\omega \otimes  \eta \otimes \theta) &=   \mathscr A(\omega \otimes \mathscr A(\eta \otimes \theta)))
\end{align*}
$$



### Theorem 4.5

> The set of all
> $$
> \varphi_{i_1} \wedge \cdots \wedge \varphi_{i_k}, \enspace \enspace 1\le i_1 < \cdots < i_k \le n
> $$
> is a basis for $\Lambda^k(V)^\ast$, which therefore has dimension
> $$
> {n\choose k} =\frac{n!}{k!(n-k)!}.
> $$

* Dual basis를 $k$ 번 wedge product한 form들의 모임은 $\Lambda^k(V)^\ast$의 basis가 된다.



#### Proof

* 임의의 $\omega \in \Lambda^k (V)^\ast \subset \mathscr T^k(V)$는 다음과 같이 나타낼 수 있다.

$$
\omega = \sum_{i_1=1}^{n}\cdots \sum_{i_k=1}^{n} a_{i_1, \cdots, i_k} \varphi_{i_1} \otimes \cdots \otimes \varphi_{i_k}\\
\omega = \mathscr A(\omega) = \sum_{i_1=1}^{n}\cdots \sum_{i_k=1}^{n} a_{i_1, \cdots, i_k} \mathscr A( \varphi_{i_1} \otimes \cdots \otimes \varphi_{i_k})\\
$$

* $\mathscr A( \varphi_{i_1} \otimes \cdots \otimes \varphi_{i_k})$는 $\varphi_{i_1} \wedge \cdots \wedge \varphi_{i_k}$와 상수배 차이 나므로, 위 모임은 $\Lambda^k (V)^\ast $를 span한다.

* Linear independence는 아래와 같이 보일 수 있다.

  * 다음을 만족하는 수들 $a_{i_1, \cdots, i_k}$를 생각해보자.

  $$
  \sum_{1\le i_1 < \cdots < i_k \le n} a_{i_1, \cdots, i_k} \varphi_{i_1} \wedge \cdots \wedge \varphi_{i_k} = \mathbf 0
  $$

  * 양변에 $(v_{j_1}, \cdots, v_{j_k})$를 대입하면 $a_{j_1, \cdots, j_k} = 0$을 얻는다.



### Theorem 4.6

