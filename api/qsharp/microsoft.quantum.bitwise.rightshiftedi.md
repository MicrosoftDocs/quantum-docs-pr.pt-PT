---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: Função RightShiftedI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b0ca7d3cb84c58429e9b3a29893a6140a717006b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718582"
---
# <a name="rightshiftedi-function"></a>Função RightShiftedI

Espaço de nome: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)

Pacote: [](https://nuget.org/packages/)


Muda a representação de um número direito por um determinado número de bits.

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a>Entrada

### <a name="value--int"></a>valor : [Int](xref:microsoft.quantum.lang-ref.int)

O número cuja representação bitwise deve ser deslocada para a direita (menos significativa).


### <a name="amount--int"></a>quantidade : [Int](xref:microsoft.quantum.lang-ref.int)

O número de bits pelos quais `value` deve ser deslocado para a direita.



## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

O valor `value` de. `amount`

## <a name="remarks"></a>Observações

Os seguintes são equivalentes:

```Q#
let c = a >>> b;
let c = RightShiftedI(a, b);
```