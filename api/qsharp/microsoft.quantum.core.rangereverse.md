---
uid: Microsoft.Quantum.Core.RangeReverse
title: Função RangeReverse
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: 7bd7c55abe0b56b9d30b4c6e91f7175101dd2948
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213842"
---
# <a name="rangereverse-function"></a>Função RangeReverse

Espaço de nome: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Devolve uma nova gama que é o inverso da gama de entrada.

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a>Entrada

### <a name="r--range"></a>r : [Gama](xref:microsoft.quantum.lang-ref.range)

Intervalo de entrada.



## <a name="output--range"></a>Saída : [Gama](xref:microsoft.quantum.lang-ref.range)

Uma nova gama que é o inverso da gama dada.

## <a name="remarks"></a>Observações

Note que o inverso de uma gama não é simplesmente `end` `-step` ... . , porque o último elemento real de uma gama pode não ser o mesmo que . . . . . `start` . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . `end`