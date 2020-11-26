---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: Operação MultiplyFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 3c9ef9ade660e1f420d85162104d773b96722eeb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222614"
---
# <a name="multiplyfxp-operation"></a>Operação MultiplyFxP

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Multiplica dois números de pontos fixos nos registos quânticos.

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="fp1--fixedpoint"></a>FP1 : [Ponto Fixo](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Primeiro número de ponto fixo.


### <a name="fp2--fixedpoint"></a>FP2 : [Ponto Fixo](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Segundo ponto fixo.


### <a name="result--fixedpoint"></a>resultado : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Resultado ponto fixo, deve estar no estado $\ket {0} $ inicialmente.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

A atual implementação requer que os três números de pontos fixos tenham a mesma posição e o mesmo número de qubits.