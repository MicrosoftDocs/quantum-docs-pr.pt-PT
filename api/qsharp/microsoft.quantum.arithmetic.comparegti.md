---
uid: Microsoft.Quantum.Arithmetic.CompareGTI
title: Comparar operação CompareGTI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTI
qsharp.summary: 'Wrapper for integer comparison: `result = x > y`.'
ms.openlocfilehash: b6e82eb7e9c068eff5bb320bb797a8fb0f8f921b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223481"
---
# <a name="comparegti-operation"></a>Comparar operação CompareGTI

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Invólucro para comparação de inteiros: `result = x > y` .

```qsharp
operation CompareGTI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="xs--littleendian"></a>xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Primeiro número de $n$-bit


### <a name="ys--littleendian"></a>ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Segundo número de $n$-bit


### <a name="result--qubit"></a>resultado : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Será virado se $x > y$



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

