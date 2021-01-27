---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorL
title: Função ExtendedGreatestCommonDivisorL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorL
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 1445f1c3d2a5852459a492fa5e6bfd2a685786d9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857538"
---
# <a name="extendedgreatestcommondivisorl-function"></a>Função ExtendedGreatestCommonDivisorL

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Computa um tuple $(u,v)$ tal que $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, onde $\operatorname{GCD}$ é $a$ maior divisor comum de $a$ e $b$. O GCD é sempre positivo.

```qsharp
function ExtendedGreatestCommonDivisorL (a : BigInt, b : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a>Entrada

### <a name="a--bigint"></a>a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)

o primeiro número do qual o divisor mais alargado está a ser calculado


### <a name="b--bigint"></a>b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)

o segundo número do qual o divisor mais alargado está a ser calculado



## <a name="output--bigintbigint"></a>Saída :[(BigInt,](xref:microsoft.quantum.lang-ref.bigint)[BigInt)](xref:microsoft.quantum.lang-ref.bigint)

Tuple $(u,v)$ com a propriedade $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.

## <a name="references"></a>Referências

- Esta implementação é de acordo com https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm