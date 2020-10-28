---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: Função RightShiftedL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 2929ba58b636847257391930e1019769fd2c2580
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718571"
---
# <a name="rightshiftedl-function"></a>Função RightShiftedL

Espaço de nome: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)

Pacote: [](https://nuget.org/packages/)


Muda a representação de um número direito por um determinado número de bits.

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a>Entrada

### <a name="value--bigint"></a>valor : [BigInt](xref:microsoft.quantum.lang-ref.bigint)

O número cuja representação bitwise deve ser deslocada para a direita (menos significativa).


### <a name="amount--int"></a>quantidade : [Int](xref:microsoft.quantum.lang-ref.int)

O número de bits pelos quais `value` deve ser deslocado para a direita.



## <a name="output--bigint"></a>Saída : [BigInt](xref:microsoft.quantum.lang-ref.bigint)

O valor `value` de. `amount`

## <a name="remarks"></a>Observações

Os seguintes são equivalentes:

```Q#
let c = a >>> b;
let c = RightShiftedL(a, b);
```