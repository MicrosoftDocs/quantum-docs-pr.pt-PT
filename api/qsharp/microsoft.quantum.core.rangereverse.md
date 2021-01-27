---
uid: Microsoft.Quantum.Core.RangeReverse
title: Função RangeReverse
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: f3b94d3c6fa6350a2c337f8bc8d889d24d87a85b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853647"
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

Note que o inverso de uma gama não é simplesmente `end` `-step` `start` ... . , porque o último elemento real de uma gama pode não ser o mesmo que `end` .