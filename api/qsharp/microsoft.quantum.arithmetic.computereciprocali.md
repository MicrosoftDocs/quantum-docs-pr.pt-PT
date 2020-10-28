---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalI
title: Operação ComputeReciprocalI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalI
qsharp.summary: Computes the reciprocal 1/x for an unsigned integer x using integer division. The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.
ms.openlocfilehash: b99e816ed69af6e6d1758442d6f95c5ab0e5c07a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721223"
---
# <a name="computereciprocali-operation"></a>Operação ComputeReciprocalI

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


Calcula o 1/x recíproco para um inteiro inteiro não assinado x usando a divisão inteiro. O resultado, interpretado como um inteiro, `floor(2^(2*n-1) / x)` será.

```qsharp
operation ComputeReciprocalI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Entrada

### <a name="xs--littleendian"></a>xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

inteiro não assinado n-bit


### <a name="result--littleendian"></a>resultado : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Saída de 2n bit, deve estar em $\ket {0} $ inicialmente.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Para a entrada x=0, a saída será só uma.