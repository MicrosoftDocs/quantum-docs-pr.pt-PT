---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: Função LeftShiftedL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 17e5c845755f74e9703381bc82bfd63be836d038
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718631"
---
# <a name="leftshiftedl-function"></a>Função LeftShiftedL

Espaço de nome: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)

Pacote: [](https://nuget.org/packages/)


Muda a representação de um número deixado por um determinado número de bits.

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a>Entrada

### <a name="value--bigint"></a>valor : [BigInt](xref:microsoft.quantum.lang-ref.bigint)

O número cuja representação bitwise deve ser deslocada para a esquerda (mais significativa).


### <a name="amount--int"></a>quantidade : [Int](xref:microsoft.quantum.lang-ref.int)

O número de bits pelos quais `value` deve ser deslocado para a esquerda.



## <a name="output--bigint"></a>Saída : [BigInt](xref:microsoft.quantum.lang-ref.bigint)

O valor `value` de, deslocado à esquerda por `amount` bocados.

## <a name="remarks"></a>Observações

Os seguintes são equivalentes:

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```