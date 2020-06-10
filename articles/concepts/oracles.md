---
title: Oráculos quânticos
description: Aprenda a trabalhar e a definir oráculos quânticos, operações de caixa preta que são usadas como entrada para outro algoritmo.
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
no-loc:
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
ms.openlocfilehash: 31e43940fc0607b15ccefcfae6be7122227b3d64
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630326"
---
# <a name="quantum-oracles"></a>Oráculos Quânticos

Um oráculo $O $ é uma operação de "caixa preta" que é usada como entrada para outro algoritmo.
Frequentemente, tais operações são definidas utilizando uma função clássica $f : \\ {0, 1 \\ }^n \a \\ {0, \\ 1}^m $ que leva uma entrada binária de $n $ -bit e produz uma saída binária de $ $m-bit.
Para tal, considere uma entrada binária específica $x = (x_{0 } , x_{1 } , \pontos, x_{n-1 } )$.
Podemos rotular os estados qubit como $\ket { \vec{x} } = \ket{x_{0} } \otimes \ket{x_{1 } } \otimes \otimes \ket{{x_{n-1 } }$.

Podemos primeiro tentar definir $O $ de modo que $O \ket {x = } \ket{f(x)}$,, mas isto tem alguns problemas.
Em primeiro lugar, $f $ podem ter um tamanho diferente de entrada e saída ($n \ne $ m), de tal forma que a aplicação de $O $ alteraria o número de qubits no registo.
Em segundo lugar, mesmo que $n = $ m, a função pode não ser invertível: se $f(x) = f(y)$ para algum $x \ne y $ , em seguida, $O \ket {x = O } \ket {y } $ mas $O^\dagger O \ket {x } \ne O^\dagger O \ket {y } $.
Isto significa que não seremos capazes de construir a operação adjacente $O^\dagger $ , e os oráculos têm de ter um adjacente definido para eles.

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>Definição de um oráculo pelo seu efeito em estados de base computacional
Podemos lidar com estes dois problemas introduzindo um segundo registo de $m $ qubits para manter a nossa resposta.
Em seguida, definiremos o efeito do oráculo em todos os estados de base computacional: para todos os $x \in \\ {0, \\ 1}^n $ e $y \in \\ {0, \\ 1}^m, $

$$ \start{align}
    O(\ket{x } \otimes \ket{y } ) = \ket{x } \otimes \ket{y \oplus f(x)}.
\end{align}
$$

Agora $O = O^\punhal $ por construção, assim resolvemos ambos os problemas anteriores.

> [!TIP]
> Para ver que $O = O^{\dagger } $, note que $O^2 = \boldone $ desde $a \oplus b \oplus b = a $ para todos os $a, b \in \{ 0, 1 \} $.
> Como resultado, $O \ket{x } \ket{y \oplus f(x)} = \ket{x } \ket{y \ket{y \oplus f(x) \oplus f(x)} = \ket{x } \ket{y } $.

Importante, definir um oráculo desta forma para cada estado de base computacional $\ket{x } \ket{y } $ também define como $O atua para qualquer outro $ estado.
Isto resulta imediatamente do facto de $O $ , como todas as operações quânticas, ser linear no estado em que atua.
Considere a operação Hadamard, por exemplo, que é definida por $H \ket{0 } = \ket { +}$ e $H \ket{1 } = \ket { -}$.
Se quisermos saber como $H $ atua em $\ket { +}$, podemos usar esse $H $ é linear,

$$ \start{align}
H \ket { +} & = \frac{1 } {\sqrt{2 } } H(\ket{0 } + \ket{1) } = \frac{1 } {\sqrt{2 } } (H \ket {0 } + H \ket {1 } ) & = \\ \\ \frac {1 } {\sqrt{2 } } (\ket { +} + \ket { -}) = \frac12 (\ket{0 } + \ket{1 } + \ket{0 } - \ket{1 } ) = \ket{0 } .
\end{align}
$$

No caso de definir o nosso oráculo $ $O, podemos igualmente usar que qualquer estado $\ket { \psi } $ em $n + m $ qubits pode ser escrito como

$$ \start{align}
\ket { \psi } & = \sum_{x \in \\ {0, \\ 1}^n, y \in \\ {0, \\ 1}^m } \alpha(x, y) \ket{x } \ket{y}
\end{align}
$$

onde $\alpha : \\ {0, 1 \\ }^n \times \\ {0, 1 \\ }^m \to \mathbb{C$ } representa os coeficientes do estado $\ket { \psi } $. Assim,

$$ \start{align}
O \ket { \psi } & = O \sum_{x \in \\ {0, \\ 1}^n, y \in \\ {0, \\ 1}^m } \alpha(x, y) \ket{x } \ket{y } \\ \\ & = \sum_{x \in \\ {0, \\ 1}^n, y \in \\ {0, \\ 1}^m } \alpha(x, y) O \ket{x } \ket{y } \\ \\ & = \sum_{x \in \\ {0, \\ 1}^n, y \in \\ {0, \\ 1}^m } \alpha(x, y) } \ket{\ket{y\y\y\y\ket{y\y\y\ket{y\y\ket{y\y\y\y\y\ket{y\y\y\y\y\ket{y\y\y\y\y\y\ket{y\y\ket{y\y\ket{y\y\ket{y\y\ket{y\y\y\ket{y\y\y\ket{y\y\ket{y\y\ket{y\y\ket{y\y\ket{y\y\y\ket{y\y\y\ket{y\y\y\
\end{align}
$$

## <a name="phase-oracles"></a>Oráculos de fase
Em alternativa, podemos codificar $f $ num $O oráculo $ aplicando uma _fase_ baseada na entrada para $O $ .
Por exemplo, podemos definir $O $ tal que $$ \start{align}
    O \ket{x } = (-1)^{f(x)} \ket{x } .
\end{align}
$$ Se um oráculo de fase agir num registo inicialmente numa base computacional estado $\ket{x } $, então esta fase é uma fase global e, portanto, não observável.
Mas tal oráculo pode ser um recurso muito poderoso se aplicado a uma superposição ou como uma operação controlada.
Por exemplo, considere uma fase orcale $O_f $ para uma função de um único qubit $f $ .
Então, $$ \start{align}
    O_f \ket { +} & = O_f (\ket{0 } + \ket{1 } ) / \sqrt{2 & = } \\ \\ ((-1)^{f(0)} \ket{0 + } (-1)^{f(1)} \ket{1) \ ket{1 } ) / \sqrt{2 } \\ \\ & = (-1)^{f(0)} (\ket{0 + } (-1)^{f(1) - f(0)} \ket{1 } ) / \sqrt{2 } \\ \\ & = (-1)^{f(0)} Z^{f(0) - f(1)} \ket { +}
\end{align}
$$

De uma forma mais geral, ambas as vistas dos oráculos podem ser alargadas para representar funções clássicas que devolvem números reais em vez de apenas um bit.

Escolher a melhor maneira de implementar um oráculo depende muito de como este oráculo será usado dentro de um determinado algoritmo.
Por exemplo, o [algoritmo Deutsch-Jozsa baseia-se](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) no oráculo implementado de primeira forma, enquanto o [algoritmo de Grover](https://en.wikipedia.org/wiki/Grover's_algorithm) depende do oráculo implementado da segunda forma.


Para mais detalhes, sugerimos a discussão em [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).
