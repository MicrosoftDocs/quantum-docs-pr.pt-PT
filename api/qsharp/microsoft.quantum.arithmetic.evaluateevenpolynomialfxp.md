---
uid: Microsoft.Quantum.Arithmetic.EvaluateEvenPolynomialFxP
title: Avaliação Operação EvenPolynomialFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateEvenPolynomialFxP
qsharp.summary: Evaluates an even polynomial in a fixed-point representation.
ms.openlocfilehash: 21c700ccb2b87b906fc4d8b65eddf962353948c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223260"
---
# <a name="evaluateevenpolynomialfxp-operation"></a>Avaliação Operação EvenPolynomialFxP

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Avalia um polinómio uniforme numa representação de ponto fixo.

```qsharp
operation EvaluateEvenPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="coefficients--double"></a>coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Coeficientes do mesmo polinómio como uma matriz dupla, ou seja, a matriz $[a_0, a_1, ..., a_k]$ para o $P polinomial(x) = a_0 + a_1 x^2 + \cdots + a_k x^{2k}$.


### <a name="fpx--fixedpoint"></a>fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Inserir número de ponto fixo para avaliar o polinómio.


### <a name="result--fixedpoint"></a>resultado : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Número de ponto fixo de saída que terá $P(x)$. Deve estar no estado $\ket {0} $ inicialmente.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

