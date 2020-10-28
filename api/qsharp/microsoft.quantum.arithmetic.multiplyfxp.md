---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: Operação MultiplyFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 18883f3f4c3793b91e248f4bd89f9def640bf254
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719782"
---
# <a name="multiplyfxp-operation"></a>Operação MultiplyFxP

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


Multiplica dois números de pontos fixos nos registos quânticos.

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
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