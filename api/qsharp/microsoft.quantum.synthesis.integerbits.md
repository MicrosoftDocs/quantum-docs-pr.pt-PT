---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: Função InteiroBits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: ab459cd841cdac116cf0e98c094834f628b6a2d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719843"
---
# <a name="integerbits-function"></a>Função InteiroBits

Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacote: [](https://nuget.org/packages/)


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