---
title: Oráculos quânticos
description: Aprenda a trabalhar e definir oráculos quânticos, operações de caixa preta que são usadas como entrada para outro algoritmo.
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
ms.openlocfilehash: 1d1d0b0903db8e994166c3e8a5798f70742a1c7e
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904932"
---
# <a name="quantum-oracles"></a>Oráculos Quânticos

Um oráculo $O$ é uma operação de "caixa preta" que é usada como entrada para outro algoritmo.
Muitas vezes, tais operações são definidas usando uma função clássica $f : \\{0, 1\\}^n \para \\{0, 1\\^m$ que leva uma entrada binária de $n$bit e produz uma saída binária de $m$bit.
Para tal, considere uma entrada binária específica $x = (x_{0}, x_{1}, \pontos, x_{n-1})$.
Podemos rotular os estados qubit como $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket {x_{1}x_ } \otimes \otimes \otimes \ket{x_{n-1}}$.

Podemos primeiro tentar definir $O$ para que $O\ket{x} = \ket{f(x)}$, mas isto tem alguns problemas.
Em primeiro lugar, $f$ pode ter um tamanho diferente de entrada e saída ($n \ne m$), de modo que a aplicação $O$ alteraria o número de qubits no registo.
Segundo, mesmo $n = m$, a função pode não ser invertível: se $f(x) = f(y)$ para algumas $x \ne y$, então $O\ket{x} = O\ket{y}$ mas $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.
Isto significa que não seremos capazes de construir a operação adjoint $O^\dagger$, e os oráculos têm que ter um adjoint definido para eles.

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>Definição de um oráculo pelo seu efeito nos estados de base computacional
Podemos lidar com ambos estes problemas introduzindo um segundo registo de qubits de $m$ para manter a nossa resposta.
Em seguida, definiremos o efeito do oráculo em todos os estados computacionais: para todos os $x \in \\{0, 1\\}^n$ e $y \in \\{0, 1\\}^m$,

$$ \begin{align} O (\ket{x} \otimes \ket {y}) = \ket{x} \otimes \ket {y \oplus f(x)}.
\end{align} $$

Agora $O = O^\dagger$ por construção, assim resolvemos ambos os problemas anteriores.

> [!TIP]
> Para ver que $O = O^{\dagger}$, note que $O^2 = \boldone$ desde $a \oplus b \oplus b = a$ para todos os $a, b \in \{0, 1\}$.
> Como resultado, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y\oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.

Importante, definir um oráculo desta forma para cada estado de base computacional $\ket{x}\ket{y}$ também define como $O$ atua para qualquer outro estado.
Isto decorre imediatamente do facto de $O$, como todas as operações quânticas, ser linear no estado em que age.
Considere a operação Hadamard, por exemplo, que é definida por $H \ket{0} = \ket{+}$ e $H \ket{1} = \ket{-}$.
Se quisermos saber como $H$ atua em $\ket{+}$, podemos usar esse $H$ é linear,

$$ \start{align} H\ket{+} & = \frac{1}{\sqrt{2}} H (\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}{0}.
\end{align} $$

No caso de definir o nosso oráculo $O$, podemos usar da mesma forma que qualquer estado $\ket{\psi}$ em $n + qubits m$ pode ser escrito como

$$ \begin{align} \ket{\psi} & = \sum_{x \in \\{0, 1\\^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \end{align} $$

onde $\alfa: \\{0, 1\\}^n \vezes \\{0, 1\\}^m \para \mathbb{C}$ representa os coeficientes do estado $\ket{\psi}$. Assim,

$$ \start{align} O \ket{\psi} & O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_ {x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket {y} \\\\ &amp\\\\sum_; , y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket {y \oplus f(x)}.
\end{align} $$

## <a name="phase-oracles"></a>Oráculos de fase
Em alternativa, podemos codificar $f$ num oráculo $O$ aplicando uma _fase_ baseada na entrada para $O$.
Por exemplo, podemos definir $O$ de tal forma que $$ \begin{align} O \ket{x} = (-1)^{f(x)} \ket{x}.
\end{align} $$ Se um oráculo de fase agir num registo inicialmente numa base computacional estado $\ket{x}$, então esta fase é uma fase global e, portanto, não observável.
Mas tal oráculo pode ser um recurso muito poderoso se aplicado a uma superposição ou como uma operação controlada.
Por exemplo, considere uma fase orcale $O_f$ para uma função de um único qubit $f$.
Em seguida, $$ \begin{align} O_f \ket{+} & = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.
\end{align} $$

De um modo mais geral, ambas as visões dos oráculos podem ser alargadas para representar funções clássicas que devolvem números reais em vez de apenas um bit.

Escolher a melhor maneira de implementar um oráculo depende muito de como este oráculo será usado dentro de um determinado algoritmo.
Por exemplo, o [algoritmo Deutsch-Jozsa baseia-se](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) no oráculo implementado da primeira forma, enquanto o [algoritmo de Grover](https://en.wikipedia.org/wiki/Grover's_algorithm) depende do oráculo implementado na segunda forma.


Para mais detalhes, sugerimos a discussão em [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).
