---
uid: Microsoft.Quantum.Core.RangeReverse
title: Função RangeReverse
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: d4e612d2f175015b7193634aeec12f9df12df7d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713229"
---
# <a name="rangereverse-function"></a>Função RangeReverse

Espaço de nome: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)

Pacote: [](https://nuget.org/packages/)


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