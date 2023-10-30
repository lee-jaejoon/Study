# 3. A First Approach to Quantum Mechanics

이 챕터는 양자역학의 주된 아이디어들을 이해하는 것을 목표로 한다. 양자역학에서 어떤 측정의 결과는 사전에 예측될 수 없고 (even in principle), 오직 측정 결과에 대한 *확률*만이 예측 가능하다. 이 *확률*은 *wave function*이라고 하는 위치 변수 $\mathbf x \in \mathbb R^n$에 대한 함수로 encode되어 있고, 입자의 위치에 대한 확률은 이 wave function을 제곱하여 얻을 수 있다. 또한 입자의 운동량(momentum)에 대한 확률은 wave function의 진동 주파수에 그 정보가 encode되어 있다. 이처럼 입자의 정보가 wave function, 즉 함수에 encode되어 있기 때문에, 입자의 위치와 운동량에 대한 확률은 함수 공간 상 정의된 연산자(operator), *position operator*와 *momentum operator*를 이용하여 기술된다. 또한 wave function의 시간 변화(time-evolution)은 Hamiltonian operator에 의해 기술되며, 이는 고전역학의 Hamilton 방정식의 Hamiltonian 함수(혹은 에너지 함수)와 대응되는 개념이다.

## 3.1. Waves, Particles, and Probabilities

양자이론에는 크게 두 가지의 주된 내용이 있고, 이는 모두 어떤 실험 결과로부터 착안한 것이다.

첫 번째 내용은 *파동-입자 이중성(wave-particle duality)*이다. 이는 어떤 물체가 입자의 성질과 파동의 성질을 동시에 보이는 것을 의미하는데, 빛을 예로 들면, 빛은 19세기 후반까지 파동으로 여겨졌으나, 20세기 초반 이후 입자의 성질도 갖는다는 사실이 확인되었다. 반대로 전자는 원래는 입자인 것으로 여겨졌으나 이후 파동의 성질을 갖는다는 것이 밝혀졌다.

두 번째 주된 내용은 물체가 갖는 확률적인 성질이다. 이중 슬릿 실험을 예로 들면, 동일하게 준비된 전자들은 스크린 상 같은 위치에 도달하지 않는다. 양자이론은 Randomness가 자연이 움직이는 방식의 근간을 이루고 있다고 가정한다. 양자역학에 의하면, 어떤 실험의 결과를 사전에 예측하는 것은 실험적으로도, 심지어 이론적으로도 불가능하며, 오직 실험 결과에 대한 확률을 예측할 수 있을 뿐이다.

Wave function, 즉 파동함수는 이 두 가지 양자이론의 주된 내용을 모두 포함하고 있는 개념이다. Wave function은 위치 변수 $\mathbf x \in \mathbb R^n$에 대한 함수이며, 시간이 지남에 따라 파동과 같은 방정식(Schrödinger equation)을 따라 진행(evolve)한다. Wave function과 wave function의 time-evolution은 양자이론의 파동적 측면을 설명하며, 입자적인 측면은 이 wave function을 해석하는 방식에서 나온다. 

혹자는 wave function을 어떤 종류의 구름과 같이, 어떤 전자의 구름의 일부는 여기 있고 또 다른 일부는 저기 있는 것과 같이 해석하고 싶을 수도 있지만, 이와 같은 wave function의 해석은 실제 실험에서 얻어지는 결과와는 매우 다르다. 실제로 측정했을 때, 어떤 한 전자의 위치는 항상 특정 한 지점에 있는 것으로 측정된다. 이중 슬릿 실험에서조차 어떤 한 전자의 위치는 하나의 지점에 있는 것으로 측정되지, wave function과 같이 여러 위치에 동시에 퍼져서 존재하는 것으로 측정되지 않는다. 따라서 wave function은 어떤 한 입자에서 직접 관측한 양상을 기술하는 것이 아니라, 해당 입자와 동일한 입자가 충분히 많이 있을 때 그 입자들이 통계적으로 어떤 움직임 양상을 보일지에 대한 정보를 기술하는 것으로 해석해야 한다.

이중 슬릿 실험에서, 우리는 Schrödinger 방정식의 해를 구함으로써 wave function이 시간에 대하여 어떻게 변화하는지는 완전히 알 수 있다. 하지만 어떤 한 전자에 대한 wave function의 정보로부터, 우리는 실제로 그 전자가 스크린의 어느 위치에 도달할지는 알 수 없다. Wave function은 전자가 도달할 위치에 대한 확률 분포를 알려줄 뿐이며, 이는 전자 한 개가 아니라 동일한 전자를 충분히 많이 쏘아보고 나서야 확인할 수 있다.

양자이론의 wave-particle duality를 설명하는 데 있어, 앞서 언급한 것처럼 전자(혹은 광자나 다른 어떤 물체도) 한 개는 입자와 같이 행동하지만, 많은 수의 전자의 집합 전체는 파동과 같이 행동한다는 설명은,   과도한 simplification이지만 굉장히 유용하다. 

또다른 흥미로운 사실은, 빛과 전자는 모두 실제로는 wave function에 의해 확률적으로 그 운동이 기술되는 wave-particle hybrid이지만, (양자 효과가 눈에 띄지 않는) 거시적인 scale에서는, 빛은 파동과 같이 보이고 전자는 입자와 같이 보인다는 점이다. 차이점은 광자는 질량을 갖지 않지만 전자는 질량을 갖는다는 점이다. 이는 광자는 낮은 에너지 하에서도 쉽게 발생하고 사라질 수 있으나, 전자는 그렇지 않다는 것을 의미하는데, 이로 인해 빛이 갖는 이산적인(discrete) 양상, 다시 말해 빛의 에너지는 항상 어떤 이산적인 quanta(quantum의 복수형; quantum은 "더 이상 나눌 수 없는 에너지의 최소 단위"를 의미함)의 값만 가질 수 있다는 점은, 전자가 갖는 동일한 양상에 비해서는 잘 눈에 띄지 않는다. 

## 3.2. A Few Words About Operators and Their Adjoints
양자역학에서, 위치, 운동량, 에너지 등 모든 물리적 양(physical quantities)들은 어떤 Hilbert space $\mathbf H$ 상의 operator로 나타내어진다. 또한 고전역학에서 물리적 양이 고전적 phase space 상의 unbounded function으로 나타내어지듯이, 이는 unbounded operator이다. 이 절에서는 unbounded operator와 그 adjoint와 관련된 기술적인 이슈들에 대한 내용을 간략히 다루고, 보다 자세하고 완전한 기술적인 내용들은 양자역학의 기본적인 개념들을 다루고 난 후 소개한다(Chap. 9).

이 절 이후로, $\mathbf H$는 Hilbert space over $\mathbb C$를 의미하며, separable한 것(countable dense subset 존재)으로 가정한다. 또한 물리학의 관습을 따라, inner product의 input factor 중 두 번째 factor가 linear한 것으로 둔다.
$$
\langle \phi , \lambda \psi \rangle =\lambda  \langle \phi , \psi \rangle; \enspace \langle \lambda \phi ,  \psi \rangle =\bar\lambda  \langle \phi , \psi \rangle \enspace \text{for all }\phi, \psi \in \mathbf H, \lambda \in \mathbb C
$$
어떤 linear operator $A : \mathbf H \to  \mathbf H$ 가 *bounded*라는 것은, 임의의 $\psi \in \mathbf H$에 대하여 $\Vert A \psi \Vert \leq  C \Vert \psi \Vert$를 만족하는 상수 $C$가 존재함을 의미한다. 또한 임의의 bounded operator $A$에 대하여, 다음을 만족하는 linear bounded operator $A^\ast$가 unique하게 존재하는데, 이를 $A$의 *adjoint*라고 한다.
$$
\langle \phi , A \psi \rangle =  \langle A^\ast \phi , \psi \rangle \enspace \text{for all }\phi, \psi \in \mathbf H
$$
이러한 $A^\ast$의 존재성은 다음과 같이 보일 수 있다.

* $A$는 bounded operator이므로, 임의의 fixed $\phi$에 대하여 map $L_\phi : \psi \mapsto \langle \phi, A\psi \rangle$는 bounded linear functional.
  * By Cauchy-Bunyakowsky-Schwarz, $ \vert \langle \phi, A\psi \rangle \vert^2  \leq \Vert \phi \Vert \Vert A\psi \Vert \leq C \Vert \phi \Vert \Vert \psi \Vert $ for some constant $C$.
* Riesz 정리에 의해 $L_\phi(\psi) = \langle \phi, A\psi \rangle = \langle \chi, \psi \rangle$ 만족하는 $\chi \in \mathbf H$가 unique하게 존재함.
* 임의의 각 fixed $\phi$에 대하여, $A^\ast \phi = \chi$로 operator $A^\ast$를 정의할 수 있음.

또한 이 $A^\ast$는 linear operator이며, $\Vert A^\ast \Vert = \Vert A \Vert $를 만족하여 즉 bounded operator이다.

* Linearity
  $$
  \begin{align*}
  \langle A^\ast(\alpha \phi + \xi), \psi \rangle &= \langle \alpha \phi + \xi, A\psi \rangle\\
  &= \bar\alpha \langle \phi, A\psi \rangle + \langle \xi, A\psi \rangle \\
  &= \bar\alpha \langle A^\ast \phi, \psi \rangle + \langle A^\ast \xi, \psi \rangle \\
  &= \langle \alpha A^\ast \phi + A^\ast\xi, \psi \rangle , \enspace\text{ for all }\phi,\psi,\xi \in \mathbf H, \alpha \in \mathbb C
  \end{align*}
  $$

* Boundedness

  * 참고로 어떤 operator $A : \mathbf H \to \mathbf H$에 대하여, norm $\Vert A \Vert$는 다음과 같이 정의된다.
    $$
    \begin{align*}
    \Vert A \Vert &= \sup \{ \Vert A\phi \Vert : \phi \in \mathbf H, \Vert \phi \Vert \leq 1 \} \\
    &= \sup \{ \Vert A\phi \Vert : \phi \in \mathbf H, \Vert \phi \Vert = 1 \} \\
    &= \sup \{ \Vert A\phi \Vert / \Vert \phi \Vert : \phi \in \mathbf H, \Vert \phi \Vert \neq 0 \} \\
    &= \inf \{ c > 0 : \Vert A\phi \Vert \leq c\Vert \phi \Vert, \phi \in \mathbf H\} \\
    \end{align*}
    $$

  * 임의의 operator $A$와 $\phi \in \mathbf H, \Vert\phi\Vert \leq 1$에 대하여 다음이 만족하므로, 
    $$
    \begin{align*}
    \Vert A \phi \Vert^2 &= \langle A \phi , A \phi \rangle = \langle A^\ast A \phi ,  \phi \rangle \\
    &\leq \Vert A^\ast A \phi \Vert \Vert \phi \Vert \leq \Vert A^\ast A \Vert \Vert \phi \Vert \Vert \phi \Vert \\
    &\leq \Vert A^\ast\Vert \Vert A\Vert \Vert \phi \Vert^2 \leq \Vert A^\ast\Vert \Vert A\Vert \\
    \end{align*}
    $$

  * operator norm의 정의에 의하여 $\Vert A \Vert \leq \Vert A^\ast\Vert^{1/2} \Vert A\Vert^{1/2}
    \iff \Vert A \Vert^{1/2} \leq \Vert A^\ast\Vert^{1/2}$ 이 만족한다.

  * 이는 $A^\ast$에 대해서도 만족하므로, $\Vert A^\ast \Vert^{1/2} \leq \Vert A^{\ast\ast}\Vert^{1/2}$도 만족.

  * $A^{\ast\ast} = A$ 이므로, $\Vert A^\ast \Vert = \Vert A \Vert = \Vert A^\ast A \Vert^{1/2}$.

  * 즉 $A^\ast$ 역시 bounded.

물리적인 그리고 수학적인 다양한 이유로, 양자역학에서 등장하는 operator는 self-adjoint, 즉 $A^\ast = A$여야 한다. 하지만 앞서 언급한 adjoint operator는 bounded operator에 대한 내용이나, 실제 우리가 맞닥뜨릴 operator는 bounded가 아니라는 기술적인 문제가 있다. 

만약 어떤 linear operator $A$가 Hilbert space $\mathbf H$ 전체에서 정의되고, 임의의 $\phi,\psi$에 대하여 $\langle \phi,A \psi \rangle = \langle A \phi,\psi \rangle$이 만족한다면, $A$는 bounded일 수 밖에 없게 된다. (이후 Corollary 9.9에서 증명함) 따라서 이를 다시 말하면, unbounded self-adjoint operator는 Hilbert space 전체에서 정의될 수 없다는 것을 의미한다. 따라서 양자역학에서 등장하는 unbounded operator들을 다루기 위해서는, Hilbert space의 적절한 subspace 내에서만 정의된 operator들을 다룰 필요가 있고, 그 subspace를 operator의 *domain*이라고 부른다.

> **[Definition 3.1]** An unbounded operator $A$ on $\mathbf H$ is a linear map from a dense subspace $\text{Dom}(A) \subset \mathbf H$ into $\mathbf H$.

위 정의 상에서 $\text{Dom}(A) = \mathbf H$로 두고 $A$가 bounded여도 문제가 없기 때문에, 보다 정확하게는 operator $A$가 "bounded일 필요는 없다"는 것을 의미한다 (not necessarily bounded).

어떤 unbounded operator의 adjoint를 정의할 때, 우리는 다음과 같은 문제를 겪는다. 

* 임의의 $\phi \in \mathbf H$에 대하여, linear functional $L_\phi(\cdot) = \langle \phi, A \cdot\rangle$이 bounded가 아닐 수도 있기 때문에, $A^\ast \phi$를 정의할 때, 위의 bounded operator의 예시에서와 같이 Riesz 정리를 바로 사용할 수 없음.

따라서 unbounded operator $A$가 $\mathbf H$ 전체가 아닌 어떤 subspace $\text{Dom}(A)$에서만 정의된 것처럼, $A^\ast$ 역시 $\mathbf H$의 어떤 subspace에서만 정의가 되어야 한다.

> **[Definition 3.2]** For an unbounded operator $A$ on $\mathbf H$, the adjoint $A^\ast$ of $A$ is defined as follows. A vector $\phi \in \mathbf H$ belongs to the domain $\text{Dom}(A^\ast)$ of $A^\ast$ if the linear functional
> $$
> L_\phi(\cdot) = \langle \phi, A \cdot\rangle,
> $$
> defined on $\text{Dom}(A)$, is bounded. For $\phi \in \text{Dom}(A^\ast)$, let $A^\ast \phi$ be the unique vector $\chi$ such that
> $$
> \langle \chi, \psi \rangle = L_\phi(\psi) = \langle \phi, A \psi \rangle
> $$
> for all $\psi \in \text{Dom}(A)$.

$L_\phi (\cdot) : \text{Dom}(A)\to \mathbf H $이 linear, bounded functional이 되도록 하는 $\phi$들만 모아놓고, 그 collection을 $\text{Dom}(A^\ast)$라고 하고 거기서만 $A^\ast$를 정의하고자 하는 것이다. 이렇게 하면 unbounded operator $A$에 대해서도 adjoint $A^\ast$를 정의할 수 있게 된다.

여기서는 Riesz 정리를 사용하기 위해, 아래와 같은 정리를 사용한다.

> **[Bounded Linear Transformation Theorem]** Let $V_1$ be a normed space and $V_2$ be a Banach space. Suppose $W$ is a dense subspace of $V_1$ and $T: W \to V_2$ is a bounded linear map. Then there exists a unique bounded linear map $T : V_1 \to V_2$ such that $\tilde T \vert_W = T$. Furthermore, the norm of $\tilde T$ equals the norm of $T$.

* Banach space는 complete normed vector space를 의미하므로, inner product로부터 induce된 norm을 갖는 Hilbert space $\mathbf H$는 Banach space이기도 하다.

* 위 정리는, 어떤 normed space $V_1$로부터 Banach space $V_2$로 가는 bounded linear map을 정의할 때, $V_1$의 어떤 dense subspace $W$에서 $V_2$로 가는 bounded linear map을 먼저 정의하고 이를 $V_1$ 전체로 확장하여도 된다는 것을 의미한다.

  * 또한, 그 extended된 bounded linear map은 항상 unique하게 정의되고, extension 전후의 operator norm도 보존된다.

  * 임의의 bounded & linear operator는 항상 continous하므로, 이와 같은 과정을 *continous linear extension*이라고도 부른다.

    * For any $\epsilon > 0$, choose $\delta = \epsilon/2C$, then we have
      $$
      \Vert x-y\Vert < \delta \implies \Vert Ax - Ay\Vert  = \Vert A(x - y)\Vert\leq C \Vert x-y\Vert < C \delta = C\frac{\epsilon}{2C} < \epsilon
      $$

* 즉 $\text{Dom}(A) \subset \mathbf H$에서만 정의된 bounded linear functional을 $\mathbf H$ 전체에서 정의된 bounded linear functional로 확장하는데 BLT 정리를 사용한다.

Definition 3.1에서 subspace $\text{Dom}(A)$가 dense in $\mathbf H$라고 했고, 임의의 $\phi \in \text{Dom}(A^\ast)$에 대하여 $L_\phi : \text{Dom}(A) \to \mathbf H$가 bounded linear functional이므로, BLT 정리에 의해, $L_\phi=\langle \phi, A \cdot \rangle$은 $\mathbf H$ 전체에 대하여 unique linear bounded extension을 갖는다. Riesz 정리를 이용하면 $L_\phi(\psi) = \langle \phi, A\psi \rangle = \langle \chi, \psi \rangle$ 만족하는 $\chi \in \mathbf H$가 unique하게 존재하고,  이를 $A^\ast \phi = \chi$로 정의하여, unbounded operator $A$의 adjoint $A^\ast$를 정의할 수 있다.

> **[Definition 3.3]** An unbounded operator $A$ on $\mathbf H$ is **symmetric** if
> $$
> \langle \phi, A \psi \rangle = \langle A \phi,  \psi \rangle
> $$
> for all $\phi, \psi \in \text{Dom}(A)$. The operator $A$ is **self-adjoint** if $\text{Dom}(A^\ast) = \text{Dom}(A)$ and $A^\ast \phi = A \phi$ for all $\phi \in \text{Dom}(A)$. Finally $A$ is **essentially self-adjoint** if the closure in $\mathbf H \times \mathbf H$ of the graph of $A$ is the graph of a self-adjoint operator.

이 개념들의 의미를 살펴보면, $A^\ast$와 $A$가 같은 operator이고 같은 domain을 가지면 $A$는 self-adjoint하다. 모든 self-adjoint 혹은 essentially self-adjoint operator는 symmetric이나, symmetric operator는 essentially self-adjoint하지 않을 수 있다. 임의의 symmetric operator에 대하여, $\text{Dom}(A^\ast) \supset \text{Dom}(A) $는 항상 만족하며, $A^\ast$는 $\text{Dom}(A)$ 위에서는 $A$와 일치한다. Symmetric operator이면서 self-adjoint이 아닌 반례가 있는 경우는 $\text{Dom}(A^\ast)$이 $ \text{Dom}(A) $보다 strict하게 큰 경우 발생한다.

* symmetric operator $A$에 대하여 다음 사실이 항상 만족함을 증명해보자.
  * $\text{Dom}(A^\ast) \supset \text{Dom}(A) $
  
    * 주어진 unbounded, symmetric operator $A$에 대하여, 어떤 $\phi \in \text{Dom}(A)$를 고려해보자.
  
    * 아래와 같이 linear functional $L_\phi (\psi) $ on $\text{Dom}(A^\ast)$ 을 정의하면
      $$
      L_\phi(\cdot) = \langle \phi, A \cdot\rangle
      $$
  
    * 임의의 $\psi \in \text{Dom}(A^\ast )$에 대하여, 다음이 성립한다.
      $$
      L_\phi(\psi) = \langle \phi, A \psi\rangle= \langle A\phi,  \psi\rangle \leq \Vert A \phi \Vert \Vert \psi \Vert
      $$
  
    * 즉 linear functional $L_\phi (\psi) $ on $\text{Dom}(A^\ast)$는 bounded이고, $\text{Dom}(A^\ast)$의 정의에 따라 $\phi \in \text{Dom}(A^\ast)$. 
  
  * $A^\ast$는 $\text{Dom}(A)$ 위에서는 $A$와 일치
  
    * $\text{Dom}(A^\ast) \supset \text{Dom}(A) $이므로, 임의의 $\phi \in \text{Dom}(A) \subset \text{Dom}(A^\ast)$이며, $A^\ast$는 Riesz 정리에 의해 다음과 같이 정의했다.
      $$
      L_\phi(\psi) = \langle \phi, A \psi \rangle = \langle \chi,  \psi \rangle = \langle A^\ast \phi,  \psi \rangle \text{ , for all }\psi \in \text{Dom}(A)
      $$
  
    * 그런데 $A$는 symmetric이므로,
      $$
      \begin{align*}
      &L_\phi(\psi) = \langle \phi, A \psi \rangle = \langle A^\ast \phi,  \psi \rangle =  \langle A \phi,  \psi \rangle \text{ , for all }\psi \in \text{Dom}(A) \\
      &\implies \langle A^\ast \phi - A \phi,  \psi \rangle =  \mathbf 0 \text{ , for all }\psi \in \text{Dom}(A)\\
      &\implies A^\ast \phi = A \phi
      \end{align*}
      $$

따라서 어떤 symmetric operator $A$가 self-adjoint가 아니라면, 이는 $\text{Dom}(A^\ast)$이 $\text{Dom}(A) $보다 strict하게 더 큰 set인 경우임을 의미한다. 사실 self-adjoint보다는 symmetric의 조건이 이해하기도, 또 만족하는지 확인하기도 더 쉽지만, self-adjoint가 양자역학에서 사용하기에 더 "올바른" 조건이다. 구체적으로는, spectral theorem을 적용하기 위한 필요조건이 operator의 self-adjointness이기 때문이다. 또한 만약 operator $A$가 essentially self-adjoint라면, $A$의 graph에 closure를 취해 self-adjoint operator를 유도할 수 있다. (이거 무슨 뜻?) 따라서 이후에 다룰 operator는 많은 technical한 이유때문에, symmetric이나 self-adjoint가 아니라 essentially self-adjoint한 것으로 가정한다.

Position, momentum 등 이후에 다룰 양자역학의 operator들이 적절한 domain 상에서 symmetric하다는 것을 보이는 것은 쉽다. 하지만 essentially self-adjoint하다는 것을 실제로 보이기는 기술적으로 어려운 경우가 많은데, 처음 양자역학을 배우는 입장에서 크게 걱정하지 않는 것이 좋다. 따라서 이 Chapter에서는 essential self-adjointness 혹은 domain을 설정하는 방법과 같은 기술적인 detail에 집중하지 않고 (이는 Chapter 9에서 깊이 다루자), self-adjoint operator의 기본적인 성질들을 유도하는 것으로 만족하기로 한다. 

> **[Proposition 3.4]** Suppose $A$ is a symmetric operator on $\mathbf H$.
>
> 1. For all $\psi \in \text{Dom}(A)$, the quantity $\langle \psi, A\psi \rangle$ is real. More generally, if $\psi$, $A\psi$, ... , $A^{m-1}\psi$ all belong to $\text{Dom}(A)$, then $\langle \psi, A^m \psi \rangle$ is real.
> 2. Suppose $\lambda$ is an eigenvalue for $A$, meaning that $A \psi = \lambda \psi$ for some nonzero $\psi \in \text{Dom}(A)$. Then $\lambda \in \mathbb R$.

이는 아래와 같이 쉽게 증명할 수 있다.


* 1.
  $$
  \langle \psi, A \psi \rangle = \langle A \psi, \psi \rangle = \overline{ \langle \psi, A \psi \rangle} \implies \langle  \psi, A \psi \rangle \text{ is real.}
  $$

  $$
  \langle \psi, A^m \psi \rangle = \langle A \psi, A^{m-1}\psi \rangle = \cdots = \langle  A^m \psi, \psi \rangle = \overline{ \langle \psi, A^m \psi \rangle } \implies \langle \psi, A^m \psi \rangle\text{ is real.}
  $$

* 2.
  $$
  \lambda \langle \psi, \psi \rangle = \langle \psi, \lambda \psi \rangle = \langle \psi, A \psi \rangle = \langle A \psi, \psi \rangle = \langle \lambda \psi, \psi \rangle = \bar \lambda \langle  \psi, \psi \rangle
  $$


  * $\psi$는 nonzero vector in $\text{Dom}(A)$이므로, inner product의 정의에 의해 $\langle \psi, \psi \rangle > 0$.
  * 따라서 $\lambda = \bar \lambda$, $\lambda$ is real.

이후에 살펴보겠지만, 물리적으로 $\langle \psi, A \psi \rangle$는 quantum state $\psi$에서 $A$라는 물리량을 측정했을 때 기댓값을 의미하고, eigenvalue $\lambda$는 측정 시 얻을 수 있는 가능한 값들 중 하나를 의미한다. 어떤 물리량을 측정했을 때 예상되는 기댓값과, 또 측정 시 얻어지는 값들은 모두 실수여야 하기 때문에, 우리는 $A$를 symmetric한 operator로 한정하고자 하는 것이다. 또한 다시 한 번 말하지만, 이후 spectral theorem을 이용해 각 state $\psi \in \mathbf H$에 probability measure를 부여하고, 이를 이용해 state $\psi$에서 $A$라는 물리량을 측정했을 때의 확률을 나타낼 것이기 때문에 symmetric에서 더 나아간 self-adjoint operator로 물리량을 정의한다.



## 3.3. Position and the Position Operator

1차원 real line 위를 움직이는 하나의 입자를 생각해보자. 이러한 입자에 대한 wave function은 $\psi : \mathbb R \to \mathbb C$와 같은 형태의 map이다. 실제로는 이 map은 시간이 지남에 따라 evolve, 변화하지만, 우선 여기서는 시간에 대해 고정인 것으로 생각해보자. 이 wave function $\psi$에 대하여, $\vert \psi (x)\vert^2$는 입자의 위치에 대한 확률 밀도를 나타낸다. 다시 말해서, 이 입자의 위치가 $E \subset \mathbb R^1$ 내에 있을 확률은 다음과 같다.
$$
\int_E \vert \psi (x)\vert^2 dx
$$
이를 위해서는, 전체 집합에 대한 확률은 1이므로, $\psi$가 다음과 같이 normalize될 필요가 있다.
$$
1 = \int_{\mathbb R} \vert \psi (x)\vert^2 dx = \int_{\mathbb R}  \overline {\psi (x)} \psi (x) dx = \langle \psi, \psi \rangle = \Vert \psi \Vert^2
$$
즉 wave function $\psi$는 Hilbert space $L^2(\mathbb R)$ 내의 unit vector여야 한다.

$\vert \psi (x)\vert^2$가 입자의 위치에 대한 확률 밀도를 나타내므로, 아래 적분이 absolutely convergent하기만 하면, 위치에 대한 **기댓값(expectation)**은 다음과 같다.
$$
E(x) = \int_{\mathbb R} x \vert \psi (x)\vert^2 dx
$$
또한 더 일반적으로, 마찬가지로 아래 적분이 잘 정의되기만 한다면, 위치의 **m차 moment**도 다음과 같이 정의할 수 있다.
$$
E(x^m) = \int_{\mathbb R} x^m \vert \psi (x)\vert^2 dx
$$
양자역학의 주된 아이디어는, 다양한 물리량에 대한 기댓값을 Hilbert space에서 정의된 operator와 inner product로 나타낼 수 있다는 점이다. 1차원 real line 내의 입자를 고려하는 위 예시 경우에서는 그 Hilbert space가 $L^2(\mathbb R)$이다. '위치'라는 물리량을 대변하는 operator, position operator $X$를 다음과 같이 정의할 수 있다.
$$
(X\psi)(x) = x \psi(x)
$$
즉 $X$는 어떤 함수에 "$x$를 곱하는" operator이다. 이를 이용하여 위에서 정의한 position의 기댓값을 다시 쓰면
$$
E(x) = \langle \psi, X \psi \rangle
$$
이때 inner product는 아래와 같이, $L^2(\mathbb R)$에서 정의된 일반적인 inner product의 형태이다.
$$
\langle \phi, \psi \rangle = \int_{\mathbb R}  \overline {\phi (x)} \psi (x) dx
$$
이후의 장에서는, state $\psi$에서의 operator $X$의 기댓값은 다음과 같이 표시한다.
$$
\langle X \rangle_\psi := \langle \psi, X \psi \rangle
$$
Position의 **m차 moment**도 다음과 같이 operator와 inner product를 이용해 나타낼 수 있다.
$$
E(x^m) =  \langle \psi, X^m \psi \rangle
$$
지금 단계에서는 표현 방법만 달라진 것이지, 기댓값이나 moment를 적분 기호가 아닌 operator와 inner product로 나타내는 것으로 얻은 것이 아무것도 없다. 하지만, 이후 장에서 입자의 momentum, energy, angular momentum 등을 각각에 맞는 operator를 이용해 정의할 때 operator와 inner product로 물리량과 그 기댓값을 나타내는 방식의 장점이 드러나게 될 것이다.

사실 수학적으로, 어떤 $\psi \in L^2 (\mathbb R)$에 대하여, $X \psi$가 $ L^2 (\mathbb R)$의 원소가 되리라는 보장은 없다. 이는 $X$가 unbounded operator이고, Hilbert space 전체에서 $X$를 정의할 수 없게 되는, 앞서 3.2.절에서 self-adjoint operator를 정의할 때 겪었던 문제이다. 또한 $X \psi \in L^2 (\mathbb R)$라고 하더라도 어떤 $m$에 대하여 $X^m \psi$가 $L^2(\mathbb R)$의 원소가 아닐 수도 있다. 그럼에도 불구하고, 임의의 unit vector $\psi \in L^2 (\mathbb R)$에 대하여, 확률 밀도 on real line $\vert \psi (x) \vert^2$는 **항상** 잘 정의된다.

## 3.4. Momentum and the Momentum Operator

고정된 시간 하에서, (Schrodinger가 제시한 wave theory를 따르는) 어떤 입자의 wave function $\psi (x)$는 "위치" 변수 $x$만을 input으로 갖는 함수이다. 따라서 wave function $\psi$는 입자의 위치에 대한 정보는 확률 밀도 $\vert \psi (x) \vert^2$를 통해 직접적으로 encoding하고 있는데, 입자의 momentum과 관련된 정보가 wave function에 어떻게 encoding되어 있는지는 직관적으로 바로 보이지는 않는다. 알고 보니 momentum에 대한 정보는 wave function의 *oscillations*, 즉 진동 양상에 encoding되어 있는데, 이와 관련된 양자 역학의 중요한 개념이 바로 *de Broglie hypothesis*이다. The de Broglie hypothesis는 wave function이, 고정된 시간 하에서 위치에 대한 함수가, 진동하는 주파수와 입자의 momentum 간의 관계식을 기술한다.

> **[Proposition 3.5] (de Broglie hypothesis)** If the wave function of a particle has spatial frequency $k$, then the momentum $p$ of the particle is
> $$
> p = \hbar k
> $$
> where $\hbar$ is Planck's constant.

Statement만 보았을 때는 Proposition 3.5는 다소 애매한 부분이 있는데, 보다 정확히 이야기하면, **$\psi(x) = e^{ikx}$의 형태를 갖는 wave function은 $p=\hbar k$의 momentum을 갖는 입자를 나타낸다**는 것이다. 그런데 함수 $e^{ikx}$는 square integrable한 함수가 아니므로, 아래 성질을 만족할 수 없고, 따라서 $e^{ikx}$이 바로 wave funciton이 될 수는 없다. 
$$
1 = \int_{\mathbb R} \vert \psi (x)\vert^2 dx
$$


#### Case 1 : Unit Circle($0 \sim 2\pi$) 위를 따라 움직이는 입자

따라서 우선은 technical한 어려움을 피하기 위해, real line이 아닌 어떤 원($0 \sim 2\pi$) 위를 따라 움직이는 입자를 생각해보자. 그러면 우리의 wave function $\psi$은 $2\pi$-periodic function on $\mathbb R$이 되고, 아래와 같이 normalization condition을 나타낼 수 있다.
$$
\int_0^{2\pi} \vert \psi (x)\vert^2 dx = \int_0^{2\pi} \vert Ce^{ikx}\vert^2 dx= C^2\int_0^{2\pi}\overline{e^{ikx}}e^{ikx} dx= C^2\int_0^{2\pi}e^{-ikx}e^{ikx} dx = 2\pi C^2 = 1 \\
\implies\psi(x) = \frac{1}{\sqrt{2\pi}}e^{ikx}
$$
Normalization condition이 만족하므로, 이제 임의의 정수 $k$에 대하여 $\psi(x) = e^{ikx}/{\sqrt{2\pi}}$가 $p=\hbar k$의 momentum을 갖는 입자의 wave function을 나타낸다고 할 수 있다. 이는 입자의 momentum을 정해진 것으로, definite, nonrandom한 것으로 보는 것이다. 만약 어떤 입자의 wave function이 $e^{ikx}/{\sqrt{2\pi}}$라면, 그 입자의 momentum을 쟀을 때의 측정값은 $\hbar k$이 될 것이다 (with probability 1).

특정 $k$가 아니라, 모든 $k\in \mathbb Z$에 대한 함수 $e^{ikx}/{\sqrt{2\pi}}$들의 collection을 생각해보면, 이는 $2\pi$-periodic, square-integrable한 함수들로 이루어진 Hilbert space, 즉 $L^2([0,2\pi])$의 orthonormal basis가 된다. 

* orthonormality

  * For $\phi_1 = e^{ik_1x}/{\sqrt{2\pi}}$ and $\psi_2 = e^{ik_2x}/{\sqrt{2\pi}}$, 
    $$
    \begin{align*}
    \langle \phi_1, \phi_2 \rangle &= \frac{1}{2\pi}\int_0^{2\pi}  \overline{e^{ik_1x}}e^{ik_2x}dx = \frac{1}{2\pi}\int_0^{2\pi}  e^{i(k_2 - k_1)x}dx \\
    &= \frac{1}{2\pi}\int_0^{2\pi} \cos ((k_2 - k_1)x)dx + \frac{i }{2\pi}\int_0^{2\pi} \sin ((k_2 - k_1)x)dx\\
    &=
    \begin{cases} 
    1 & k_1 = k_2\\
    0 & k_1 \ne k_2
    \end{cases}
    \end{align*}
    $$

* The space of finite linear combinations of $\{ e^{ikx}/{\sqrt{2\pi}} : k \in \mathbb Z\}$ is dense in $L^2([0,2\pi])$

  * 보충 필요
  * ***Stone-Weierstrass theorem?***
    https://math.stackexchange.com/questions/2720188/showing-that-the-sequence-big-fraceint-sqrt2-pi-big-n-1-infty

따라서 원 위를 따라 움직이는 어떤 입자의 일반적인 wave function은 아래와 같이 이 orthonormal basis를 이용하여 나타낼 수 있다.
$$
\psi(x) = \sum_{k=-\infty}^{\infty} a_k \frac{e^{ikx}}{\sqrt{2\pi}}
$$
참고로 위 infinite sum은 $L^2([0,2\pi])$ 내에서 convergent하다고 하자. 만약 $\psi$가 unit vector로 normalize되었다면 아래 식이 만족할 것이다.
$$
\sum_{k=-\infty }^{\infty } {\vert a_k \vert^2} = \Vert \psi \Vert_{L^2([0,2\pi])}= 1
$$

* 이는 다음과 같이 확인할 수 있다. 
  $$
  \begin{align*}
  1 &= \Vert \psi \Vert_{L^2([0,2\pi])} = \langle \psi, \psi\rangle \\
  &= \left\langle \sum_{k=-\infty}^{\infty} a_k \frac{e^{ikx}}{\sqrt{2\pi}}, \sum_{\ell=-\infty}^{\infty} a_\ell \frac{e^{i\ell x}}{\sqrt{2\pi}} \right\rangle \\
  &=\left\langle \lim_{m \to \infty }\sum_{k=-m}^{m} a_k \frac{e^{ikx}}{\sqrt{2\pi}}, \lim_{n \to \infty }\sum_{\ell=-n}^{n} a_\ell \frac{e^{i\ell x}}{\sqrt{2\pi}} \right\rangle \\
  &=\lim_{m \to \infty }\lim_{n \to \infty }\left\langle \sum_{k=-m}^{m} a_k \frac{e^{ikx}}{\sqrt{2\pi}}, \sum_{\ell=-n}^{n} a_\ell \frac{e^{i\ell x}}{\sqrt{2\pi}} \right\rangle &\because \text{ continuity of inner product} \\
  &=\lim_{m \to \infty }\lim_{n \to \infty }\sum_{k=-m}^{m}\sum_{\ell=-n}^{n} \overline{a_k} a_\ell \left\langle   \frac{e^{ikx}}{\sqrt{2\pi}},  \frac{e^{i\ell x}}{\sqrt{2\pi}} \right\rangle  &\because \text{ linearity of inner product} \\
  &=\lim_{m \to \infty }\lim_{n \to \infty }\sum_{k=-\min(m,n)}^{\min(m,n)} {\vert a_k\vert^2} 
  \\&=\sum_{k=-\infty }^{\infty } {\vert a_k \vert^2}
  \end{align*}
  $$

* 참고로 inner product가 continuous한 function이라는 것은 Cauchy-Schwartz에 의해 쉽게 확인할 수 있다.
  $$
  \langle \phi_n, \psi \rangle - \langle \phi, \psi \rangle = \langle \phi_n - \phi, \psi \rangle \leq \Vert\phi_n - \phi\Vert \Vert\psi\Vert \\
  \langle \phi, \psi_n \rangle - \langle \phi, \psi \rangle = \langle \phi, \psi_n - \psi \rangle \leq \Vert\phi\Vert \Vert\psi_n - \psi\Vert
  $$

이렇게 orthonormal basis의 infinite linear combination 형태로 나타난 wave function $\psi$는 더이상 특정 momentum 값을 확정적으로 갖지 않는다. 그 대신 어떤 한 정수 $k$에 대하여 $\hbar k$의 momentum 값을 갖게 되며, 측정했을 때 입자의 momentum 값이 $\hbar k$일 확률은 $\vert a_k \vert^2$이다. 따라서 확률론의 개념을 이용하면, momentum의 기댓값 및 m차 moment는 다음과 같다. (아래 infinite sum의 absolute convergence는 보장된다고 가정.)
$$
E(p)= \sum_{k = -\infty}^\infty \hbar k \vert a_k \vert^2, \enspace E(p^m)= \sum_{k = -\infty}^\infty (\hbar k)^m \vert a_k \vert^2
$$
우리는 물리량을 operator로 나타내기로 했고, 기댓값과 m차 moment를 operator와 inner product를 이용해 정의했으므로, momentum에 대한 operator $P$는 다음을 만족해야한다.
$$
E(p)= \langle \psi , P \psi \rangle = \sum_{k = -\infty}^\infty \hbar k \vert a_k \vert^2 , \enspace
E(p^m) = \langle \psi , P^m \psi \rangle= \sum_{k = -\infty}^\infty (\hbar k)^m \vert a_k \vert^2 
$$
이를 만족하는 operator $P$의 형태는 다음과 같다.
$$
P = -i \hbar \frac{d}{dx}
$$

#### Case 2 : Real line 위의 입자

다시 1차원 real line 위를 움직이는 입자의 상황으로 돌아오자. Real line 위에서도 unit circle 위에서와 마찬가지로 momentum operator $P$가 $P = -i \hbar \text{ }{d}/{dx}$의 형태를 가질 것으로 추측해볼 수 있다. 이 형태의 operator $P$는 아래 관계식을 만족하므로, *"wave function $e^{ikx}$가 momentum $\hbar k$에 대응된다"*는 **Proposition 3.5 (de Broglie hypothesis)**의 내용과도 일맥상통한다.
$$
P e^{ikx} =  -i \hbar \frac{d}{dx}e^{ikx} =  -(i \hbar) (ik)e^{ikx} = (\hbar k) e^{ikx}
$$
비록 real line 위에서는 $e^{ikx}$가 $x$에 대하여 square-integrable하지 않으나, Fourier transform은 임의의 square-integrable function (in $L^2(\mathbb R)$)을 $e^{ikx}$ 형태 함수의 "superposition"으로 나타낼 수 있게 해준다. 여기서 *superposition*이라는 용어는 물리학자들이 linear combination 혹은 linear combination의 continuous version, 즉 integral을 부르는 말이다. 따라서 Fourier transform을 이용하면 아래와 같이 $e^{ikx}$의 (continuous) linear combination 형태이면서 square-integrable한 함수 $\psi$를 만들 수 있다.
$$
\psi(x) = \int_{-\infty}^\infty \hat\psi(k) \frac{e^{ikx}}{\sqrt{2\pi}} dk
$$
이때 앞선 예시의 $a_k$에 대응되는 $\hat\psi(k)$는 Fourier transform of $\psi$이며, 다음과 같이 정의된다.
$$
\hat \psi(k) = \int_{-\infty}^\infty \psi(x) \frac{e^{-ikx}}{\sqrt{2\pi}} dx
$$
Plancherel theorem에 의해 Fourier transform은 $L^2(\mathbb R)$에서 $L^2(\mathbb R)$로 가는 unitary map이며, surjective map(onto)이다. 따라서 임의의 unit vector $\psi \in L^2 (\mathbb R )$에 대하여 다음이 만족한다.
$$
\int_{-\infty}^\infty \vert \psi(x)\vert^2 dx = \int_{-\infty}^\infty \left\vert \hat\psi(k)\right\vert^2 dk = 1
$$
Unit circle 상 입자 예시에서 $\vert a_k \vert^2$가 momentum에 대한 확률값이었던 것처럼, $\vert \hat\psi(k)\vert^2$가 입자의 momentum에 대한 (보다 정확히는 $p/\hbar$에 대한) 확률 밀도가 될 것으로 추측해볼 수 있다. 

이제 $e^{ikx}$가 square-integrable하지 않은 점에 구애받지 않고, momentum operator의 성질(wave function $e^{ikx}$가 momentum $p=\hbar k$에 대응)을 만족하는 wave function $\psi$를 Hilbert space $L^2(\mathbb R )$에서 정의할 수 있다.

> **[Proposition 3.6]** Define the momentum operator $P$ by
> $$
> P = -i\hbar \frac{d}{dx}
> $$
> Then for all sufficiently nice unit vectors $\psi$ in $L^2(\mathbb R)$, we have
> $$
> \langle \psi, P^m \psi \rangle = \int_{-\infty}^\infty (\hbar k)^m \left\vert \hat\psi (k) \right\vert^2dk
> $$
> for all positive integers $m$. The quantity is interpreted as the expectation value of the $m$th power of the momentum, $E(p^m)$.

Proposition 3.6은 앞서 소개한 내용으로 도출한 momentum operator $P$의 식 형태를 정의하고, 그리고 (Fourier transform을 이용해 $e^{ikx}$의 superposition 형태를 갖는) 적절한 함수 형태의 $\psi$에 대해서는 momentum의 기댓값과 m차 moment가 잘 정의된다는 사실을 소개한다.

* ***Fourier analysis 기반 증명 (내용 공부하고 돌아오자.)***
* 



3.4절의 내용을 정리하면 다음과 같다. 

* Proposition 3.5 (de Broglie hypothesis)에 따르면, $\psi(x) = e^{ikx}$의 형태를 갖는 wave function은 $p=\hbar k$의 momentum을 갖는 입자를 나타낸다. 

* 하지만 $e^{ikx}$는 $x$를 실수 전체 범위로 두면 square-integrable하지 않은 함수이다.

  * 이로 인해 $\vert \psi \vert = 1$의 normalization condition을 만족시킬 수 없고, wave function의 square 형태로 입자의 위치에 대한 확률 밀도가 정의가 되지 않는 문제가 발생한다.

* $x \in [0,2\pi]$의 unit circle 상황 하에서는 그러한 문제가 없으므로, $e^{ikx}/{\sqrt{2\pi}}$를 wave function으로 둘 수 있었다.

  * $\{ e^{ikx}/{\sqrt{2\pi}} : k \in \mathbb Z \}$가 the Hilbert space of $2\pi$-periodic, square-integrable functions, 즉 $L^2([0,2\pi])$의 orthonormal basis가 되므로, $e^{ikx}/{\sqrt{2\pi}}$의 (infinite) linear combination 형태로 wave function을 정의할 수 있었다.
    $$
    \psi(x) = \sum_{k=-\infty}^{\infty} a_k \frac{e^{ikx}}{\sqrt{2\pi}}
    $$

    * 계수 $a_k$에 대하여 $\vert a_k \vert^2$는 관측가능한 각 momentum 값 $p=\hbar k$에 대한 확률을 나타냄.

  * 또한 momentum operator $P$가 다음과 같은 형태를 가질 것으로 추론할 수 있었다.

  $$
  P = -i \hbar \frac{d}{dx}
  $$

* $x$를 실수 전체 범위로 둔 경우에서는, Fourier transform을 이용하여, 관측가능한 각 momentum $p = \hbar k$와 각각의 관측 확률에 대한 정보가 encoding된 wave function $\psi$를 아래 형태와 같이 정의할 수 있다.
  $$
  \psi(x) = \int_{-\infty}^\infty \hat\psi(k) \frac{e^{ikx}}{\sqrt{2\pi}} dk, \enspace \text{ where }\hat \psi(k) = \int_{-\infty}^\infty \psi(x) \frac{e^{-ikx}}{\sqrt{2\pi}} dx.
  $$
  



## 3.5. The Position and Momentum Operators

앞선 두 절에서 배경 내용을 설명했던 position operator와 momentum operator의 정의는 아래와 같다.

> **[Definition 3.7]** For a particle moving in $\mathbb R^1$, let the quantum Hilbert space be $L^2(\mathbb R)$ and define the **position** and **momentum operators** $X$ and $P$ by
> $$
> X \psi(x) = x \psi (x) \\
> P \psi(x) = -i \hbar \frac{d\psi}{dx}
> $$

두 operator 모두 Hilbert space $L^2(\mathbb R)$ 전체에서 정의된 mapping이 아니다. 이는 다시 말하면 어떤 $\psi \in L^2(\mathbb R)$에 대하여, 아래와 같은 경우가 있을 수 있음을 의미한다.

* $X\psi(x) = x \psi(x) \notin L^2(\mathbb R)$
* $\psi$ not differentiable.
* $P\psi(x) = -i \hbar \text{ }{d\psi}/{dx} \notin L^2(\mathbb R)$

이는 3.2절에서 언급했던 것과 같이 $X$와 $P$가 unbounded operator임을 의미하며, 각자에게 적합한 $L^2(\mathbb R)$의 dense subspace $\text{Dom}(X)$와 $\text{Dom}(P)$ 위에서 정의하게 된다. 이러한 operator의 domain에 대한 심도있는 내용은 이후 9장에서 다루도록 하자.

어떤 두 operator가 있을 때 굉장히 중요한 성질은, 많은 경우 두 operator가 **commutative하지 않다**는 점이다.

> **[Proposition 3.8]** The position and momentum operator $X$ and $P$ do not commute, but satisfy the relation
> $$
> XP - PX = i \hbar I,
> $$
> This relation is known as the *canonical commutation relation*.

* 증명
  $$
  \begin{align*}
  PX \psi &= -i\hbar \frac{d}{dx}(x\psi(x)) \\
  &= -i\hbar \psi(x) -i\hbar x\frac{d\psi}{dx} \\
  &= -i\hbar \psi(x) + XP\psi
  \end{align*}
  $$

* 

이 "non-commutativity"에 의하여 양자역학의 다양한 중요한 개념들이 다뤄지는데 이는 11-14장에서 다룬다. 지금 단계에서는 고전 역학에서의 Poisson bracket 관계식과 위 식 간 연관이 있다는 점만 알아두자.

> **[Proposition 3.9]** For all sufficiently nice functions $\phi$ and $\psi$ in $L^2 (\mathbb R)$, we have
> $$
> \langle \phi, X \psi \rangle = \langle  X \phi,\psi \rangle
> $$
> and
> $$
> \langle \phi, P \psi \rangle = \langle  P \phi,\psi \rangle.
> $$

* Position operator에 대한 symmetricity 증명

  * $\phi$와 $\psi$가 $L^2 (\mathbb R)$의 원소이고, domain을 적절하게 선택하여 $x\phi(x)$와 $\psi(x)$ 역시 $L^2 (\mathbb R)$의 원소가 된다고 가정해보자. 그러면 $x$는 실수이므로 다음이 만족한다.
    $$
    \langle \phi, X \psi \rangle = \int^\infty_{-\infty} \overline{\phi(x)} x\psi(x) dx \int^\infty_{-\infty} \overline{x\phi(x)} \psi(x) dx = \langle X\phi, \psi \rangle
    $$

* Momentum operator에 대한 symmetricity 증명

  * $\phi$와 $\psi$가 continuously differentiable하고, $x$가 $\pm \infty$로 갈 때 0으로 수렴한다고 가정하자.

    * Schwartz function은 위 조건을 만족.

  * 또한 $\phi$, $\psi$, $d\phi/dx$, $d\psi/dx$가 모두 $L^2 (\mathbb R)$의 원소라고 가정하면 다음이 만족한다.
    $$
    \begin{align*}
    \langle \phi, P \psi \rangle &= \int^\infty_{-\infty} \overline{ \phi(x)} (P\psi)(x)dx \\
    &= -i\hbar \int^\infty_{-\infty} \overline{\phi(x)} \frac{d \psi}{dx}dx \\
    &= -i\hbar \overline{\phi(x)}  \psi(x) \Bigg\vert^\infty_{-\infty} + i\hbar \int^\infty_{-\infty} \overline{\frac{d \phi}{dx}} \psi(x)dx \\
    &= 0 + \int^\infty_{-\infty} \overline{ -i\hbar\frac{d \phi}{dx}} \psi(x)dx \\
    &= \int^\infty_{-\infty} \overline{ P\phi(x)} \psi(x)dx \\
    &= \langle P\phi,  \psi \rangle
    \end{align*}
    $$



## 3.6. Axioms of Quantum Mechanics: Operators and Measurements

이 절에서는 양자역학의 일반적인 axiom, 즉 공리에 대해 다룬다. 다만 이는 수학적인 sense로 이 공리로부터 다른 결과들이 엄밀하게 논리적으로 도출되는 것이 아니라, 양자역학이 어떻게 작동하는가에 대한 주된 원칙을 나타낸 것이라는 관점에서 이해하는 것이 바람직하다. 이 절에서는 고정된 시점에 대해 적용되는 "kinematic"한 axiom에 대해 다루며, system의 time-evolution에 대한 axiom은 다음 절에서 다룬다.

> **[Axiom 1]** The state of the system is represented by a unit vector $\psi$ in an appropriate Hilbert space $\mathbf H$. If $\psi_1$ and $\psi_2$ are two unit vectors in $\mathbf H$ with $\psi_2 = c\psi_1$ for some constant $c \in \mathbb C$, then $\psi_1$ and $\psi_2$ represent the same physical state.

Hilbert space $\mathbf H$는 보통 "quantum Hilbert space"라고 불린다. 그러나 이것이 $\mathbf H$가 Hilbert space의 개념에서 벗어난 어떤 variant라는 것을 의미하는 것은 아니며, "어떤 주어진 quantum system과 관련된 Hilbert space"로 이해하면 된다.

$\mathbf H$의 unit vector는 "pure state"만을 나타내는데, 보다 일반적인 개념인 "Mixed state"에 대한 내용은 19장에서 다룬다. 대부분의 물리 교과서에서 처음에는 pure state의 내용만을 다루는 것과 같이, 본 교재도 전반부에서는 pure state만을 고려하기로 한다.

> **[Axiom 2]** To each real-valued function $f$ on the classical phase space there is associated a self-adjoint operator $\hat f$ on the quantum Hilbert space.

거의 모든 경우, observable $f$에 대한 operator $\hat f$는 unbounded operator이며, position operator나 momentum operator와 같이 가장 기본적인 operator조차도 unbounded이다. 이러한 unbounded case에서 self-adjointness의 개념을 정의하는 데에는 다소 technical한 작업이 필요한데, 이에 대한 예시를 앞서 살펴보았다. 대부분의 application에서, classical phase space의 모든 observable에 대하여 $\hat f$를 정의하는 것까지는 필요가 없고, 보통은 position, momentum, energy, angular momentum과 같이 몇가지 중요한 observable에 대해서만 operator $\hat f$를 정의하면 충분하다. 이 기본적인 operator에 대한 내용은 이 3장의 후반부에서 다루게 될 것이다. (몇 가지 조건을 만족하는) 임의의 observable $f$에 대하여 operator $\hat f$를 정의하기 위해서는 Weyl quantization scheme이라는 방법을 사용해야 하는데, 이는 13장에서 소개한다.

$\mathbb R^1$ 위를 움직이는 입자에 대하여, classical phase space에서는 입자의 위치 $x$와 momentum $p$의 pair $ (x,p) \in \mathbb R^2$로 입자의 위치와 운동을 기술한다. 양자역학의 경우 $\mathbb R^1$ 위를 움직이는 입자에 대한 quantum Hilbert space는 $L^2 (\mathbb R)$이다 ($L^2 (\mathbb R^2)$이 아니라!). Observable $f$가 입자의 위치를 나타내는 position function $f(x,p) = x$라면, 이에 대한 operator $\hat f$는 position operator $X$이다. Observable $f$가 입자의 운동량을 나타내는 momentum function $f(x,p) = p$라면, 이에 대한 operator $\hat f$는 momentum operator $P = -i \hbar \text{ }d/dx$이다.

앞에서도 이미 사용한 표현이지만, 물리학에서는 classical phase space에서 정의된 function $f$를 **observable**, 혹은 **classical observable**이라고 한다. 이는 해당 system에서 어떤 측정을 함으로써 관측될 수 있는 물리량이라는 뜻이다. 그리고 이에 대한 operator $\hat f$를 **quantum observable**이라고 한다.

> **[Axiom 3]** If a quantum system is in a state described by a unit vector $\psi \in \mathbf H$, the probability distribution for the measurement of some observable $f$ satisfies
> $$
> E(f^m) = \left\langle \psi, (\hat f )^m \psi \right\rangle.
> $$
> In particular, the expectation value for a measurement of $f$ is given by
> $$
> E(f) = \left\langle \psi, \hat f  \psi \right\rangle.
> $$

양자역학에서는 classical observable $f$는 더이상 특정 definite value를 갖는 것이 아니라, 여러 관측 가능한 값들에 대한 어떤 확률 분포를 갖게 된다. 그리고 이 정보는 quantum observable $\hat f$ 와 vector $\psi \in \mathbf H$ 안에 encoding되어있다.

만약 위 정의에서 vector $\psi \in \mathbf H$가 unit vector가 아니라고 한다면, 식은 다음과 같이 normalized된 $\tilde \psi = \psi/\Vert \psi\Vert$에 대한 식으로 수정되어야 한다. 기댓값을 구할 때마다 normalization factor $\langle  \psi ,  \psi \rangle$를 곱해주는 것은 번거롭기 때문에, 보통은 $\psi \in \mathbf H$를 unit vector로 가정한다.
$$
E(f) = \frac{\left\langle \psi, \hat f  \psi \right\rangle}{\langle  \psi ,  \psi \rangle} = \frac{\left\langle \psi, \hat f  \psi \right\rangle}{\Vert  \psi  \Vert^2} = \left\langle \tilde \psi, \hat f  \tilde \psi \right\rangle
$$
Axiom 2에서 $\hat f$는 self-adjoint한 operator임을 가정했고, 모든 self-adjoint operator는 symmetric하므로, Proposition 3.4에 의하여 Axiom 3의 기댓값 $E(f)$와 $m$차 moment $E(f^m)$이 항상 실수값을 갖는다는 사실을 알 수 있다. 또한 $\hat f$가 symmetric일 뿐만 아니라 self-adjoint한 것으로 가정했으므로, **spectral theorem**에 의해 $\mathbb R^1$ 위의 probability measure $\mu_{A, \psi}$를 잘 정의할 수 있게 되고, 이 probability measure는 state $\psi$에서 $A$라는 값이 관측하는 확률 분포를 의미한다.

또한 Axiom 3으로부터 (complex) 상수배 차이나는 두 unit vector가 같은 physical state를 나타낸다는 점을 확인할 수 있다. 만약 $\vert c \vert = 1$인 $c \in \mathbb C$에 대하여 $\psi_2 = c\psi_1$이 만족한다면, 임의의 operator $A$에 대하여 다음와 같이 쓸 수 있다.
$$
\langle \psi_2 , A \psi_2\rangle = \langle c\psi_1 , A c\psi_1\rangle = c\bar c\langle \psi_1 , A \psi_1\rangle = \vert c\vert \langle \psi_1 , A \psi_1\rangle = \langle \psi_1 , A \psi_1\rangle
$$
이는 임의의 quantum observable에 대하여 state $\psi_1$와 state $\psi_2$에서 그 기댓값이 같다는 것, 즉 두 state가 같은 physical state임을 의미한다.

> **[Notation 3.10]** If $A$ is a self-adjoint operator on $\mathbf H$ and $\psi \in \mathbf H$ is a unit vector, the expectation value of $A$ in the state $\psi$ is denoted $\langle A \rangle_\psi$ and is defined (in light of Axiom 3) to be
> $$
> \langle A \rangle_\psi = \left\langle \psi, A  \psi \right\rangle .
> $$

> **[Proposition 3.11] (Eigenvectors)** If a quantum system is in a state described by a unit vector $\psi \in \mathbf H$ and for some quantum observable $\hat f$ we have $\hat f \psi = \lambda \psi$ for some $\lambda \in \mathbb R$, then
> $$
> E(f^m)= \left\langle (\hat f)^m \right\rangle_\psi = \lambda^m
> $$
> for all positive integers $m$. The unique probability measure consistent with this condition is the one in which $f$ has the definite value $\lambda$, with probability one.

이 Proposition이 의미하는 바는, $\psi$가 $\hat f$의 eigenvector라면 state $\psi$에 있는 입자에 대하여 $f$를 관측했을 때는 항상 그 결과값이 $\lambda$가 나온다는 것이다.  또한 $\hat f$는 self-adjoint, 즉 symmetric하므로 quantum observable $\hat f$의 eigenvalue는 항상 real이다.

만약 $\hat f \psi = \lambda \psi$가 만족한다면, $m$차 moment $\langle \psi, (\hat f)^m \psi \rangle = \langle \psi, \lambda^m \psi \rangle = \lambda^m$이다. 따라서 우리는 임의의 non-negative integer $m$에 대하여 다음을 만족하는 probability measure $\mu$ on $\mathbb R$를 찾아야 한다.
$$
\int_\mathbb R x^m d\mu = \lambda^m
$$
Proposition 3.11은 그러한 probability measure가 유일하게 존재하고, 그것이 point $\lambda$에서 degenerate하게 모든 probability mass를 갖는 $\delta$-measure라는 것을 말한다.

* 증명

  * quantum observable $\hat f$의 eigenvalue가 real이라는 것, $m$차 moment $E(f^m)$이 $\lambda^m$라는 것은 앞선 내용에서 이미 보였다.

  * Non-negative integer $m$에 대하여 다음을 만족하는 probability measure $\mu$ on $\mathbb R$가 point $\lambda$에서 degenerate하게 모든 probability mass를 갖는 $\delta$-measure라는 것을 보여야 한다.
    $$
    \int_\mathbb R x^m d\mu = \lambda^m
    $$

    * $\mu$가 $\delta$-measure at $\lambda$라면 당연히 위 관계식이 만족한다.
    * 위 관계식이 만족하면 $\mu$가 $\delta$-measure at $\lambda$라는 부분은, 



































































