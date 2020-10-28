---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: Avaliação OperaçãoOddPolynomialFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: d52da4092f16d43ab9d08b03f798a4d6789c7348
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721198"
---
# <a name="evaluateoddpolynomialfxp-operation"></a>Avaliação OperaçãoOddPolynomialFxP

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


Avalia um polinômio ímpar numa representação de ponto fixo.

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a>Entrada

### <a name="coefficients--double"></a>coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Coeficientes do polinómio ímpar como uma matriz dupla, ou seja, a matriz $[a_0, a_1, ..., a_k]$ para o estranho polinomial $P(x) = a_0 x + a_1 x^3 + \cdots + a_k x^2k+1$}


### <a name="fpx--fixedpoint"></a>fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Inserir número de ponto fixo para avaliar o polinómio.


### <a name="result--fixedpoint"></a>resultado : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Número de ponto fixo de saída que irá conter P(x). Deve estar no estado $\ket {0} $ inicialmente.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

