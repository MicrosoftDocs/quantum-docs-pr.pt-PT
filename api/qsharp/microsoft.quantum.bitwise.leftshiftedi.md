---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: Função LeftShiftedI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: ce68311adf211169c2fb499bb189332370a6d6ac
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718666"
---
# <a name="leftshiftedi-function"></a>Função LeftShiftedI

Espaço de nome: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)

Pacote: [](https://nuget.org/packages/)


Muda a representação de um número deixado por um determinado número de bits.

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a>Entrada

### <a name="value--int"></a>valor : [Int](xref:microsoft.quantum.lang-ref.int)

O número cuja representação bitwise deve ser deslocada para a esquerda (mais significativa).


### <a name="amount--int"></a>quantidade : [Int](xref:microsoft.quantum.lang-ref.int)

O número de bits pelos quais `value` deve ser deslocado para a esquerda.



## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

O valor `value` de, deslocado à esquerda por `amount` bocados.

## <a name="remarks"></a>Observações

Os seguintes são equivalentes:

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```