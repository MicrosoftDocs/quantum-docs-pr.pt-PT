---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: Operação ComputeReciprocalFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: 3ca050d6ce9daaa10e14c2f12dd571398cf436b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223396"
---
# <a name="computereciprocalfxp-operation"></a>Operação ComputeReciprocalFxP

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Calcula $1/x$ para um número de ponto fixo $x$.

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="x--fixedpoint"></a>x : [Ponto Fixo](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Número de ponto fixo a ser invertido.


### <a name="result--fixedpoint"></a>resultado : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Número de ponto fixo que irá manter o resultado. Deve ser inicializado para $\ket{0.0}$.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

