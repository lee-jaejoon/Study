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









