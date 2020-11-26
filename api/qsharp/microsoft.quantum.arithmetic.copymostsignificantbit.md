---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: Operação CopyMostSignificantBit
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 39a2dc2fe33f46c2767def06a44cde07e2f01497
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223294"
---
# <a name="copymostsignificantbit-operation"></a>Operação CopyMostSignificantBit

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Copia a parte mais significativa de um registo qubit `from` que representa um número inteiro não assinado no qubit `target` .

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj
```


## <a name="input"></a>Entrada

### <a name="from--littleendian"></a>de: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

O inteiro não assinado do qual a parte mais alta é copiada.
o inteiro é codificado em formato pouco endiano.


### <a name="target--qubit"></a>alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

O qubit em que a parte mais alta está a ser copiada. A codificação da broca está em base computacional.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Aritmetic.LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)