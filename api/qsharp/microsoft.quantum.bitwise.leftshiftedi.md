---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: Função LeftShiftedI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 3f551bdba5c8e2a1456838769e4cee0660d0f969
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845313"
---
# <a name="leftshiftedi-function"></a>Função LeftShiftedI

Espaço de nome: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

```qsharp
let c = a <<< b;
let c = LeftShiftedI(a, b);
```