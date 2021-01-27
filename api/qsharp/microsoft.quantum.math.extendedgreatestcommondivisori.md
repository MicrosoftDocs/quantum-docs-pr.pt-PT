---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorI
title: Função ExtendedGreatestCommonDivisorI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorI
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: e86237f39e696485a3496f1c6dd571cd516214ec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857542"
---
# <a name="extendedgreatestcommondivisori-function"></a>Função ExtendedGreatestCommonDivisorI

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Computa um tuple $(u,v)$ tal que $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, onde $\operatorname{GCD}$ é $a$ maior divisor comum de $a$ e $b$. O GCD é sempre positivo.

```qsharp
function ExtendedGreatestCommonDivisorI (a : Int, b : Int) : (Int, Int)
```


## <a name="input"></a>Entrada

### <a name="a--int"></a>a : [Int](xref:microsoft.quantum.lang-ref.int)

o primeiro número do qual o divisor mais alargado está a ser calculado


### <a name="b--int"></a>b : [Int](xref:microsoft.quantum.lang-ref.int)

o segundo número do qual o divisor mais alargado está a ser calculado



## <a name="output--intint"></a>Saída : ([Int](xref:microsoft.quantum.lang-ref.int),[Int)](xref:microsoft.quantum.lang-ref.int)

Tuple $(u,v)$ com a propriedade $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.

## <a name="references"></a>Referências

- Esta implementação é de acordo com https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm