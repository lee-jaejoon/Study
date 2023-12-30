# 4. Free Schrödinger Equation

이 장에서는 1차원 공간 하에서의 free Schrodinger equation을 푸는 다양한 방법을 다룬다. 이때 "free"라는 말의 의미는 입자에 작용하는 힘이 없다는 것을 의미하며, 따라서 potential $V$가 모든 위치 $x$에 대하여 zero가 된다. 따라서 Schrodinger equation은 다음과 같다.
$$
\frac{\partial \psi}{\partial t} = \frac{i\hbar}{2m}\frac{\partial^2 \psi}{\partial x^2}, \enspace \psi(x, 0) = \psi_0(x)
$$
이 장에서는 이 Schrodinger equation의 solution에 대한 몇 가지 중요한 feature를 다룰 것이다.

* wave packet의 spread
* phase velocity / group velocity

Free Schrodinger equation을 풀기 전에, 먼저 position과 momentum의 기댓값의 time-evolution에 대한 관계식을 살펴보자. Proposition 3.19의 관계식에 zero potential을 적용하면 다음과 같다.
$$
\begin{align*}
\frac{d}{dt}\langle X\rangle_{\psi(t)} &= \frac{1}{m}\langle P \rangle_{\psi(t)}\\
\frac{d}{dt}\langle P\rangle_{\psi(t)} &= 0
\end{align*}
$$
Momentum operator $P$의 기댓값은 시간에 대해 constant이며, position operator $X$는 아래와 같이 시간 $t$에 linear 하다.
$$
\begin{align*}
\langle X\rangle_{\psi(t)} &= \langle X\rangle_{\psi_0} + \frac{t}{m}\langle P \rangle_{\psi_0}\\
\langle P\rangle_{\psi(t)} &= \langle P\rangle_{\psi_0}
\end{align*}
$$
따라서 free Schrodinger equation은 position과 momentum의 기댓값이 정확히 classical trajectory를 따르는 special case 중 하나이다.

## 4.1. Solution by Means of the Fourier Transform

위와 같은 $\mathbb R^1$ 상의 free Schrodinger equation에 대하여 다음과 같은 형태의 solution을 얻고자 한다.
$$
\psi(x, t) = e^{i(kx - \omega t)}
$$
이때 $k$는 공간에 대한 frequency고 $\omega$는 시간에 대한 frequency이다. 이를 위 free Schrodinger equation에 대입하면 time frequency $\omega$에 대한 함수식을 다음과 같이 얻을 수 있다.
$$
\frac{\partial }{\partial t}e^{i(kx - \omega t)} = -i \omega e^{i(kx - \omega t)}\\
\frac{i\hbar}{2m}\left[\frac{\partial^2 }{\partial x^2}e^{i(kx - \omega t)}\right] = \frac{i\hbar}{2m}[-k^2e^{i(kx - \omega t)}]\\
\implies \enspace \omega  = \omega(k) = \frac{\hbar k^2}{2m}
$$
즉 temporal frequency $\omega$가 spatial frequency $k$에 대한 함수임을 알 수 있는데, 어떤 편미분방정식의 solution에서 이와 같은 관계가 만족하는 것을 *dispersion relation*이라고 한다.

free Schrodinger equation에 대한 solution 식은 아래와 같이도 나타낼 수 있다.
$$
\psi(x, t) = \exp \left[ik\left(x - \frac{\omega(k)}{k} t\right)\right]= \exp \left[ik\left(x -  \frac{\hbar k}{2m}t\right)\right]
$$
어떤 함수 $f(x)$를 $f(x-a)$로 바꾸는 transformation은 $f$를 $x$축 방향으로 $a$만큼 shift 시키는 것이므로, time-evolution에 의해 시간이 $t$만큼 흘렀을 때, initial function은 $(\omega(k)/k)t $ 만큼 shift 된다는 것을 알 수 있다. 다시 말해서, $\psi(x,t)$는 $x$축 방향으로 $\omega(k)/k = \hbar k/2m $의 speed로 이동하는데, 이 speed를 *phase velocity*라고 부른다.

따라서 phase velocity는 free Schrodinger equation의 exponential 형태의 solution이 시간이 지남에 따라 나아가는 speed를 의미한다. 그런데 앞서 3장에서 $e^{ikx}$ 형태의 exponential wave function은 momentum $\hbar k$를 갖는 입자를 나타낸다는 것을 확인하였다.
$$
P e^{ikx} =  -i \hbar \frac{d}{dx}e^{ikx} =  -(i \hbar) (ik)e^{ikx} = (\hbar k) e^{ikx}
$$
따라서 다음과 같은 다소 이해할 수 없는 결론에 도달한다.

> **[Proposition 4.1]** The phase velocity of a particle with momentum $p = \hbar k$ is
> $$
> \text{phase velocity} = \frac{\omega (k)}{k} = \frac{\hbar k}{2m} = \frac{p}{2m}
> $$
> This velocity is **half** the velocity of a classical particle of momentum $p$.

왜 wave function의 *phase velocity*는 momentum operator $P$로 구한 momentum의 결과와 $1/2$배만큼 차이가 나는 것일까? 뒤에서 확인하겠지만, pure exponential solution의 velocity로 구했던 *phase velocity* $p/2m$은 momentum $p$를 갖는 입자의 "진짜" velocity는 아니다. "진짜" velocity는 *group velocity*라고 하는데 이는 우리가 기대했던 것처럼 $p/m$이 된다.

이와 같은 velocity 개념에 대한 의문은 잠시 제쳐두고, free Schrodinger equation에 대한 general solution을 도출하는 과정을 살펴보자. 그 과정에서 Fourier transform의 개념을 사용할 것이며, 적당히 nice한 initial condition하에서, pure exponential solution의 "superposition" (혹은 linear combination) 형태로 free Schrodinger equation에 대한 solution을 나타낼 수 있다.

>**[Proposition 4.2]** Suppose that $\psi_0$ is a “nice” function, for example, a Schwartz function (Definition A.15). Let $\hat\psi_0$ denote the Fourier transform of $\psi_0$ and define $\psi(x, t)$ by
>$$
>\psi(x,t) = \frac{1}{\sqrt{2\pi}} \int^\infty_{-\infty} \hat\psi_0(k) e^{i(kx-\omega(k)t)}dk,
>$$
>where $\omega(k)$ is defined as follows
>$$
>\omega(k) = \frac{\hbar k^2}{2m}.
>$$
>Then $\psi(x, t)$ solves the free Schrodinger equation with initial condition $\psi_0$.

