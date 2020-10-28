---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorL
title: Função ExtendedGreatestCommonDivisorL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorL
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: e671405045d6d2587a8c6ccbac4ae3402f92f722
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723716"
---
# <a name="extendedgreatestcommondivisorl-function"></a>Função ExtendedGreatestCommonDivisorL

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [](https://nuget.org/packages/)


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