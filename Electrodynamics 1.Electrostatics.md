# 2. Electrostatics

* 정전기학
* the study of electromagnetic phenomena that occur when there are **no moving charges**—i.e., after a static equilibrium has been established.

## 2.1. The Electric Field

### 2.1.1. Introduction

* Electrodynamics의 근본적인 목표는 다음 문제를 해결하는 것.
  * 전하 $q_1, q_2, \cdots$가 있을 때, 이들이 다른 전하 $Q$에 가하는 힘이 무엇인가?
    ![image-20220122083855908](\images\ED_1.png)
  * $q_1, q_2, \cdots $를 source charge, $Q$를 test charge라고 함.
  * Source charge의 위치는 시간에 대한 함수로 주어지고, 그에 따른 test particle의 궤적은 계산되어야 함.
* 이 문제에 대한 solution은 **"중첩(superposition)의 원리"**에 의해 얻을 수 있다.
  * The interaction between any two charges is completely unaffected by the presence of others.
  * 두 전하 간의 상호작용은 서로의 존재에 의해서는 영향을 전혀 받지 않는다.
  * 따라서 최종적인 결과는 각 전하가 미치는 영향을 각각 따로 계산해준 뒤 이를 합친 것과 같다.
    * 다른 $q_2, q_3, \cdots$를 무시하고, $q_1$이 가하는 힘 $F_1$를 구한다.
    * 마찬가지로 $q_1,q_3, \cdots$를 무시하고, $q_2$가 가하는 힘 $F_2$를 구한다.
  * 각 힘의 vector sum을 취하면 source charge $q$가 $Q$에 가하는 힘 $F = F_1+ F_2 + \cdots$을 구할 수 있다.

* $q$로부터 $Q$에 가해지는 힘을 구할 때, 왜 처음부터 그냥 $q$에 대한 함수로 공식을 사용하지 않는가?

  * 질문의 statement는 간단히 보이지만 많은 요소를 고려해야 한다.

    * Q에 가해지는 힘은 전하 간 separation distance $r$에 영향을 받는다.

    ![image-20220122083926284](\images\ED_2.png)

    * $q$의 속도와 가속도에 영향을 받음.
    * 가해지는 전자기적 영향은 빛의 속도로 이동하므로, $Q$에 영향을 끼치는 것은 아주 조금 더 과거의 $q$의 위치, 속도, 가속도임.
      * 교재는 electromagnetic "news"가 전해지는 데 시간이 걸리는 것으로 표현.

  * 이 요소들의 영향을 하나하나 배워나갈 것.





### 2.1.2. Coulomb's Law

