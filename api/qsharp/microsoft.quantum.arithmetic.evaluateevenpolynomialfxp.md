---
uid: Microsoft.Quantum.Arithmetic.EvaluateEvenPolynomialFxP
title: Avaliação Operação EvenPolynomialFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateEvenPolynomialFxP
qsharp.summary: Evaluates an even polynomial in a fixed-point representation.
ms.openlocfilehash: c3129cb796a344f7ad38a585183db285d48892bf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843237"
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

