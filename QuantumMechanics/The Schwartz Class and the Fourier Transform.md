## The Schwartz Class and the Fourier Transform

Fourier transform은 harmonic analysis에서 가장 중요한 도구라고 할 수 있다. 일반적으로 Fourier transform은 $L^1$ function에 대한 operation으로 소개되는데, 이하의 논의에서는 먼저 이보다 더 작은 함수 class인 Schwartz function의 공간에 대하여 Fourier transform을 소개한다.

몇가지 기본적인 개념 및 notation을 아래와 같이 소개한다.

* Given $x = (x_1, ... , x_n) \in \mathbb R^n$, we set $\vert x\vert = (x_1^2 + \cdots + x_n^2)^{1/2}$.

* The *partial derivative* of a function $f$ on $\mathbb R^n$ with respect to the $j$th variable $x_j$ : $\partial_j f$

* The *$m$th partial derivative* of a function $f$ on $\mathbb R^n$ with respect to the $j$th variable $x_j$ : $\partial_j^m f$

* The *gradient* of a function $f$ : $\nabla f = (\partial_1 f , ... , \partial_n f)$

* A *multi-index* $\alpha$ is an ordered $n$-tuple of nonnegative integers.

  * For a multi-index $\alpha = (\alpha_1, ... , \alpha_n)$, 
    $$
    \partial^\alpha f = \partial_1^{\alpha_1} \cdots \partial_n^{\alpha_n} f
    $$

  * The size of a multi-index $\alpha$ : $\vert \alpha \vert = \alpha_1 + \cdots + \alpha_n$

  * The product of the factorials of the entries of a multi-index : $\alpha ! = \alpha_1 ! \cdots \alpha_n!$

  * The number $\vert \alpha \vert $ indicates the *total order of differentiation* of $\partial^\alpha f$

* The space of functions

  * $\mathscr C^N(\mathbb R^n)$ : The space of functions in $\mathbb R^n$ all of whose derivatives of order at most $N \in \mathbb Z_+$ are continuous.
  * $\mathscr C^\infty(\mathbb R^n)$ : The space of all infinitely differentiable functions on $\mathbb R^n$.
  * $\mathscr C^\infty_0(\mathbb R^n)$ : The space of $\mathscr C^\infty$ with compact support on $\mathbb R^n$.

### 1. The Class of Schwartz Functions

The class of Schwartz function은 smooth하며, 모든 가능한 derivative가 그 어떠한 polynomial order보다도 빠르게 0으로 decay하는 함수의 모임을 의미한다. 정의는 다음과 같다.

> **[Definition 1]** A $\mathscr C^\infty$ complex-valued function $f$ on $\mathbb R^n$ is called a Schwartz function if for every pair of multi-indices $\alpha$ and $\beta$ there exists a positive constant $C_{\alpha, \beta}$ such that
> $$
> \rho_{\alpha, \beta}(f) = \sup_{x \in \mathbb R^n} \left\vert x^\alpha \partial^\beta f(x)\right\vert = C_{\alpha, \beta} < \infty
> $$
> The quantities $\rho_{\alpha, \beta}(f)$ are called the *Schwartz seminorms* of $f$. The set of all Schwartz functions on $\mathbb R^n$ is denoted by $\mathscr S(\mathbb R^n)$.

**[Example 2]** Schwartz function과 관련된 몇가지 실제 예시들은 다음과 같다.

* $e^{-\vert x\vert^2}$는 $\mathscr S(\mathbb R^n)$에 속하지만, $e^{-\vert x\vert}$는 원점에서 미분불가능하므로 $\mathscr S(\mathbb R^n)$에 속하지 않는다.
* $\mathscr C^\infty$ function인 $g(x) = (1 + \vert x \vert^4)^{-a}, a> 0$는 고정된 $a$th polynomial의 속도로 decay하므로, $\mathscr S(\mathbb R^n)$의 원소가 아니다.
* Compact support를 갖는 smooth function의 모임인 $\mathscr C_0^\infty(\mathbb R^n)$은, 모든 원소 function이 compact support 밖에서는 strictly 0이므로 $\mathscr S(\mathbb R^n)$의 부분집합이다.

**[Remark 3]** 또한 Schwartz function과 관련된 몇가지 다음 Remark들을 살펴보자.

* $f_1 \in \mathscr S(\mathbb R^n)$, $f_2 \in \mathscr S(\mathbb R^m)$이라면, $m+n$개 variable에 대한 function $f_1(x_1, ..., x_n)f_2(x_{n+1}, ... , x_{n+m})$은 $\mathscr S(\mathbb R^{m+n})$의 원소이다.
* $f \in \mathscr S(\mathbb R^n)$이고, $P(x)$가 $n$개 variable에 대한 어떤 polynomial이면, $P(x)f(x) \in \mathscr S(\mathbb R^n)$이다.
* 임의의 multi-index $\alpha$와 $f \in \mathscr S(\mathbb R^n)$에 대하여, $\partial^\alpha f \in \mathscr S(\mathbb R^n)$이 만족한다.
* 























* 부등식 1
  $$
  \vert x^\alpha \vert \leq C_{n,\alpha} {\vert x \vert }^{{\vert \alpha \vert}}
  $$

  * 증명

    * 위 부등식의 좌변에 log를 씌운 것에서 시작하면 Jensen 부등식에 의해 다음을 얻을 수 있다.

    $$
    \begin{align*}
    \log \vert x^\alpha\vert &= \sum_i \alpha_i \log \vert x_i \vert = \vert \alpha \vert \sum_i \frac{\alpha_i}{\vert \alpha \vert} \log \vert x_i \vert \\
    &\leq \vert \alpha \vert\log\left( \sum_i \frac{\alpha_i}{\vert \alpha \vert} \vert x_i \vert\right) 
    \end{align*}
    $$

    * 따라서 다음과 같이 증명할 수 있다.

    $$
    \begin{align*}
    \vert x^\alpha\vert &\leq \left( \sum_i \frac{\alpha_i}{\vert \alpha \vert} \vert x_i \vert\right)^{\vert \alpha \vert} \\
    &\leq \left( \sum_i  \vert x_i \vert\right)^{\vert \alpha \vert} \enspace (\because \alpha_i \leq \vert \alpha \vert) \\
    &\leq \left( n^{1/2} \vert x \vert \right)^{\vert \alpha \vert} =  n^{\vert \alpha \vert/2} {\vert x \vert }^{{\vert \alpha \vert}} =  C_{n,\alpha} {\vert x \vert }^{{\vert \alpha \vert}}
    \end{align*}
    $$

    * 위 식의 마지막 부등식은 아래와 같이 Jensen 부등식을 이용해 도출할 수 있다. 사실 이는 의미를 생각해보면 원점으로부터 거리가 $\vert x \vert$인 점들에 대하여 각 entry의 합의 최댓값은 $n^{1/2} \vert x \vert$인 것이다.
      $$
      \left(\sum_i  \frac{\vert x_i \vert}{n} \right)^2 \leq  \sum_i  \frac{\vert x_i \vert^2}{n} \\
      \implies \sum_i  \vert x_i \vert \leq  n^{1/2} \left( \sum_i  \vert x_i \vert^2 \right)^{1/2} =  n^{1/2} \vert x \vert
      $$
      

* 




$$

$$
