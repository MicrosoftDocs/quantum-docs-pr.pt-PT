---
title: Oracle Quantum | Microsoft Docs
description: Oracle Quantum
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
ms.openlocfilehash: 96949b371a3a5a1135d624690933a48ea0214a2e
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184717"
---
# <a name="quantum-oracles"></a>Oracle Quantum

Um Oracle $O $ é uma operação de "caixa preta" que é usada como entrada para outro algoritmo.
Muitas vezes, essas operações são definidas usando uma função clássica $f: \\{0, 1\\} ^ n \tO \\{0, 1\\} ^ m $, que usa uma entrada binária de $n de $ bits e produz uma saída binária de $ bits de $m.
Para fazer isso, considere uma entrada binária específica $x = (x_{0}, x_{1}, \dots, x_ {n-1}) $.
Podemos rotular Estados qubit como $ \ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}} $.

Primeiro, podemos tentar definir $O $ para que $O \ket{x} = \ket{f (x)} $, mas isso tem alguns problemas.
Primeiro, $f $ pode ter um tamanho diferente de entrada e saída ($n \ne m $), de modo que a aplicação de $O $ alteraria o número de qubits no registro.
Em segundo lugar, mesmo se $n = m $, a função pode não ser invertível: se $f (x) = f (y) $ para alguns $x \ne y $, $O \ket{x} = O\ket {y} $, $O ^ \dagger O\ket {x} \ne O ^ \dagger O\ket {y} $.
Isso significa que não será possível construir a operação de addefinição $O ^ \dagger $ e os Oracle precisam ter um adjacente definido para eles.

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>Definindo um Oracle por seu efeito nos Estados de base computacional
Podemos lidar com esses dois problemas introduzindo um segundo registro de $m $ qubits para manter nossa resposta.
Em seguida, vamos definir o efeito do Oracle em todos os Estados de base computacional: para todos os $x na \\{0, 1\\} ^ n $ e $y na \\{0, 1\\} ^ m $,

$ $ \begin{align} O (\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f (x)}.
\end{align} $ $

Agora $O = O ^ \dagger $ por construção, portanto, resolvemos os dois problemas anteriores.

> [!TIP]
> Para ver que $O = O ^ {\dagger} $, observe que $O ^ 2 = \boldone $ desde $a \oplus b \oplus b = a $ para todos os $a, b na \{0, 1\}$.
> Como resultado, $O \ket{x} \ket{y \oplus f (x)} = \ket{x} \ket{y \oplus f (x) \oplus f (x)} = \ket{x} \ket{y} $.

De forma importante, definir um Oracle dessa maneira para cada Estado de base computacional $ \ket{x}\ket{y} $ também define como o $O $ age para qualquer outro Estado.
Isso é seguido imediatamente do fato de que $O $, como todas as operações de Quantum, é linear no estado em que atua.
Considere a operação Hadamard, por exemplo, que é definida por $H \ket{0} = \ket{+} $ e $H \ket{1} = \ket{-}$.
Se quisermos saber como $H $ age em $ \ket{+} $, podemos usar essa $H $ é linear,

$ $ \begin{align} H\ket {+} & = \frac{1}{\sqrt{2}} H (\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ ket {+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0}-\ket{1}) = \ket{0}.
\end{align} $ $

No caso da definição de nosso Oracle $O $, podemos usar de forma semelhante que qualquer estado $ \ket{\psi} $ em $n + m $ qubits pode ser escrito como

$ $ \begin{align} \ket{\psi} & = \sum_{x na \\{0, 1\\} ^ n, y na \\{0, 1\\} ^ m} \alpha (x, y) \ket{x} \ket{y} \end{align} $ $

em que $ \alpha: \\{0, 1\\} ^ n \times \\{0, 1\\} ^ m \tO \mathbb{C} $ representa os coeficientes do estado $ \ket{\psi} $. Dessa

$ $ \begin{align} O \ket{\psi} & = O \sum_{x na \\{0, 1\\} ^ n, y na \\{0, 1\\} ^ m} \alpha (x, y) \ket{x} \ket{y} \\\\ & = \sum_{x na \\{0 , 1\\} ^ n, y na \\{0, 1\\} ^ m} \alpha (x, y) O \ket{x} \ket{y} \\\\ & = \sum_{x na \\{0, 1\\} ^ n, y na \\{0 , 1\\} ^ m} \alpha (x, y) \ket{x} \ket{y \oplus f (x)}.
\end{align} $ $

## <a name="phase-oracles"></a>Fase Oracle
Como alternativa, podemos codificar $f $ em um Oracle $O $ aplicando uma _fase_ com base na entrada para $O $.
Por exemplo, podemos definir $O $ de modo que $ $ \begin{align} O \ket{x} = (-1) ^ {f (x)} \ket{x}.
\end{align} $ $ se uma fase Oracle age em um registro inicialmente em um estado de base computacional $ \ket{x} $, essa fase é uma fase global e, portanto, não observável.
Mas tal Oracle pode ser um recurso muito potente se aplicado a uma superposição ou como uma operação controlada.
Por exemplo, considere uma fase orcale $O _F $ para uma função qubit única $f $.
Em seguida, $ $ \begin{align} O_f \ket{+} & = O_f (\ket{0} + \ket{1})/\sqrt{2} \\\\ & = ((-1) ^ {f (0)} \ket{0} + (-1) ^ {f (1)} \ket{1})/\sqrt{2} \\\\ & = (-1) ^ {f ( 0)} (\ket{0} + (-1) ^ {f (1)-f (0)} \ket{1})/\sqrt{2} \\\\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} \ket{+}.
\end{align} $ $

Em geral, as duas exibições de Oracle podem ser ampliadas para representar funções clássicas que retornam números reais em vez de apenas um único bit.

Escolher a melhor maneira de implementar um Oracle depende muito da forma como esse Oracle será usado dentro de um determinado algoritmo.
Por exemplo, o [algoritmo Deutsch-Jozsa](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) depende do Oracle implementado na primeira forma, enquanto o [algoritmo de Grover](https://en.wikipedia.org/wiki/Grover's_algorithm) se baseia no Oracle implementado da segunda maneira.


Para obter mais detalhes, sugerimos a discussão em [Gilyén *et al*. 1711, 465](https://arxiv.org/abs/1711.00465).
