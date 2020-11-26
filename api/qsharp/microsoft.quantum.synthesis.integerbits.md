---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: Função InteiroBits
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: d6566716f5a63c090668d9582b7b000c16d1f6a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231097"
---
# <a name="integerbits-function"></a>Função InteiroBits

Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve todas as posições em que os pedaços de um inteiro são definidos.

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a>Entrada

### <a name="value--int"></a>valor : [Int](xref:microsoft.quantum.lang-ref.int)

Um número não-inggativo.


### <a name="length--int"></a>comprimento : [Int](xref:microsoft.quantum.lang-ref.int)

O número de bits na expansão binária de `value` .



## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]

Uma matriz que contém todas as posições de bits (a partir de 0) que são 1 na expansão binária de `value` considerar todos os bits até à posição `length - 1` .  Todas as posições são ordenadas na matriz por posição numa ordem crescente.