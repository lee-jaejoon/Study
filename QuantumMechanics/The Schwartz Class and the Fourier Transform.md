## The Schwartz Class and the Fourier Transform



### 1. The Class of Schwartz Functions

The class of Schwartz function은 smooth하며, 모든 가능한 derivative가 그 어떠한 polynomial order보다도 빠르게 0으로 decay하는 함수의 모임을 의미한다. 정의는 다음과 같다.

> **[Definition 1]** A $\mathscr C^\infty$ complex-valued function $f$ on $\mathbb R^n$ is called a Schwartz function if for every pair of multi-indices $\alpha$ and $\beta$ there exists a positive constant $C_{\alpha, \beta}$ such that
> $$
> \rho_{\alpha, \beta}(f) = \sup_{x \in \mathbb R^n} \left\vert x^\alpha \partial^\beta f(x)\right\vert = C_{\alpha, \beta} < \infty
> $$
> The quantities $\rho_{\alpha, \beta}(f)$ are called the *Schwartz seminorms* of $f$. The set of all Schwartz functions on $\mathbb R^n$ is denoted by $\mathscr S(\mathbb R^n)$.

























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
