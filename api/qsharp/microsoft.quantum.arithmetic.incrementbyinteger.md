---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: Operação IncrementByInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 363d48d697e3b2dad4d4896e6b1e701864649d9b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721114"
---
# <a name="incrementbyinteger-operation"></a>Operação IncrementByInteger

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


Incrementa um registo quântico não assinado por um inteiro clássico, usando rotações de fase.

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Descrição

Suponha que `target` codifica um inteiro não assinado $x$ em uma codificação pouco endiana e isso é igual a `increment` $a$.
Em seguida, esta operação implementa o unitário $\ket{x} \mapsto \ket{x + a}$, onde a adição é realizada modulo $2^n$, onde $n = \texttt{Comprimento (alvo!)} $.

## <a name="input"></a>Entrada

### <a name="increment--int"></a>incremento : [Int](xref:microsoft.quantum.lang-ref.int)

O inteiro pelo qual o `target` é incrementado por.


### <a name="target--littleendian"></a>alvo : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Um registo quântico que codifica um número inteiro não assinado usando a codificação de pequenas extremidades.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

