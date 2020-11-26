---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: CompareGTSI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: a0e8ef66f1e1a62d4f6a78364135376810507534
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223498"
---
# <a name="comparegtsi-operation"></a>CompareGTSI

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Invólucro para comparação de inteiros assinado: `result = xs > ys` .

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="xs--signedlittleendian"></a>xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

Primeiro número de $n$-bit


### <a name="ys--signedlittleendian"></a>ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

Segundo número de $n$-bit


### <a name="result--qubit"></a>resultado : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Será virado se $xs > ys$



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

