---
uid: Microsoft.Quantum.Core.RangeEnd
title: Função RangeEnd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 196fab0bd97a441a16976033dc0d660c54cdfd6a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831370"
---
# <a name="rangeend-function"></a>Função RangeEnd

Espaço de nome: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Devolve o valor final definido da gama dada, que não é necessariamente o último elemento na sequência.

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a>Entrada

### <a name="range--range"></a>gama : [Gama](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

O valor final definido da gama dada.

## <a name="remarks"></a>Observações

O primeiro elemento de uma expressão de alcance é `start` , o seu segundo elemento é , terceiro elemento é , `start+step` `start+step+step` etc., até `end` ser passado.

Note-se que o valor final definido de uma gama pode diferir do último elemento na sequência especificada pela gama; por exemplo, num intervalo de 0 .. 2 .. 5 o último elemento é 4, mas o valor final é 5.