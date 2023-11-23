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



