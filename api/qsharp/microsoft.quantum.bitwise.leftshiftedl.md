---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: Função LeftShiftedL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 014653011574d0fabb4b9aa04cedf58b87ddf798
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842147"
---
# <a name="leftshiftedl-function"></a>Função LeftShiftedL

Espaço de nome: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

```qsharp
let c = a <<< b;
let c = LeftShiftedL(a, b);
```