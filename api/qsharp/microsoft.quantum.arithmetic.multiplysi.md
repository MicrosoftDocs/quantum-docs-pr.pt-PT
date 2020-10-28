---
uid: Microsoft.Quantum.Arithmetic.MultiplySI
title: Operação MultiplySI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplySI
qsharp.summary: Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 9ca781cbe90a8ec13e6a85a5babaf043bc8f2b5b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719747"
---
# <a name="multiplysi-operation"></a>Operação MultiplySI

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


Multiplique o inteiro assinado `xs` por inteiro assinado e `ys` guarde o resultado em , que deve `result` ser zero inicialmente.

```qsharp
operation MultiplySI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit
```


## <a name="input"></a>Entrada

### <a name="xs--signedlittleendian"></a>xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

multiplicand n bit (SignedLittleEndian)


### <a name="ys--signedlittleendian"></a>ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

multiplicador n bit (SignedLittleEndian)


### <a name="result--signedlittleendian"></a>resultado : [AssinadoLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

Resultado de 2n-bit (SignedLittleEndian), deve estar no estado $\ket {0} $ inicialmente.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

