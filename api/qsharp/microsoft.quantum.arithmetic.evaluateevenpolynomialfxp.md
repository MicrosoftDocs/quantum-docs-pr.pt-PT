---
uid: Microsoft.Quantum.Arithmetic.EvaluateEvenPolynomialFxP
title: Avaliação Operação EvenPolynomialFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateEvenPolynomialFxP
qsharp.summary: Evaluates an even polynomial in a fixed-point representation.
ms.openlocfilehash: e49a6d47553a60766b561525e8cfa37e95fda9e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721199"
---
# <a name="evaluateevenpolynomialfxp-operation"></a>Avaliação Operação EvenPolynomialFxP

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


Avalia um polinómio uniforme numa representação de ponto fixo.

```qsharp
operation EvaluateEvenPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a>Entrada

### <a name="coefficients--double"></a>coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Coeficientes do mesmo polinómio como uma matriz dupla, ou seja, a matriz $[a_0, a_1, ..., a_k]$ para o $P polinomial(x) = a_0 + a_1 x^2 + \cdots + a_k x^{2k}$.


### <a name="fpx--fixedpoint"></a>fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Inserir número de ponto fixo para avaliar o polinómio.


### <a name="result--fixedpoint"></a>resultado : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Número de ponto fixo de saída que terá $P(x)$. Deve estar no estado $\ket {0} $ inicialmente.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

