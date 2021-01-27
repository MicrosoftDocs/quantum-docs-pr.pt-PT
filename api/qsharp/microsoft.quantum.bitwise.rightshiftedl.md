---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: Função RightShiftedL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 03ed69c7151e62b91c4a036e301f99b45ce5ab62
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842102"
---
# <a name="rightshiftedl-function"></a>Função RightShiftedL

Espaço de nome: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

```qsharp
let c = a >>> b;
let c = RightShiftedL(a, b);
```