---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: Avaliação OperaçãoOddPolynomialFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: 1bf9b6e7c416e994e70b93e5967caefd444f6426
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223226"
---
# <a name="evaluateoddpolynomialfxp-operation"></a>Avaliação OperaçãoOddPolynomialFxP

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Avalia um polinômio ímpar numa representação de ponto fixo.

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="coefficients--double"></a>coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Coeficientes do polinómio ímpar como uma matriz dupla, ou seja, a matriz $[a_0, a_1, ..., a_k]$ para o estranho polinomial $P(x) = a_0 x + a_1 x^3 + \cdots + a_k x^2k+1$}


### <a name="fpx--fixedpoint"></a>fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Inserir número de ponto fixo para avaliar o polinómio.


### <a name="result--fixedpoint"></a>resultado : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Número de ponto fixo de saída que irá conter P(x). Deve estar no estado $\ket {0} $ inicialmente.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

