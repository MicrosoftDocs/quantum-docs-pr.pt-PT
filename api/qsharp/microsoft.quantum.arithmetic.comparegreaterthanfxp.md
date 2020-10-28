---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: Comparar operação CompareGreaterThanFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: bd3bcedd7a4a81fc600f7f4b6bdf1d2a797abbd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721295"
---
# <a name="comparegreaterthanfxp-operation"></a>Comparar operação CompareGreaterThanFxP

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


Compara dois números de pontos fixos armazenados em registos quânticos e controla uma inversão do resultado.

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit
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