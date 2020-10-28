---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: Operação ApplyXorInPlace
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 5a35abc16a967e64c84466a47844ed7beeb618dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721391"
---
# <a name="applyxorinplace-operation"></a>Operação ApplyXorInPlace

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


Aplica uma operação pouco-XOR entre um inteiro clássico e um inteiro representado por um registo de qubits.

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Descrição

Aplica `X` operações a qubits num registo de pequenas extremidades com base em 1 bits num inteiro.

Vamos denotar `value` por um número inteiro não assinado codificado, em `target` seguida, executa uma `InPlaceXorLE` operação dada pelo seguinte mapa: $\ket{y}\rightarrow \ket{y\oplus a}, onde $\oplus$ é o operador exclusivo bitwise OR.

## <a name="input"></a>Entrada

### <a name="value--int"></a>valor : [Int](xref:microsoft.quantum.lang-ref.int)

Um inteiro que se assume não negativo.


### <a name="target--littleendian"></a>alvo : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Um registo quântico que é usado para armazenar `value` em codificação pouco endiana.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

