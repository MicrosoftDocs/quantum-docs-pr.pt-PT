---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: Comparar operação CompareGreaterThanFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: 1e9afc7645f62b932fa8ebc3d33e21a2a5182361
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223532"
---
# <a name="comparegreaterthanfxp-operation"></a>Comparar operação CompareGreaterThanFxP

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Compara dois números de pontos fixos armazenados em registos quânticos e controla uma inversão do resultado.

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="fp1--fixedpoint"></a>FP1 : [Ponto Fixo](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Primeiro número de ponto fixo a ser comparado.


### <a name="fp2--fixedpoint"></a>FP2 : [Ponto Fixo](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Segundo número de ponto fixo a ser comparado.


### <a name="result--qubit"></a>resultado : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Resultado da comparação. Será virado se `fp1 > fp2` . .



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

A atual implementação requer que os dois números de ponto fixo tenham a mesma posição e o mesmo número de qubits.