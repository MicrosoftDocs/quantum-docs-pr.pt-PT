---
uid: Microsoft.Quantum.Core.RangeEnd
title: Função RangeEnd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 4dbcf517c4dc17775040444c77deb0e449082390
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713243"
---
# <a name="rangeend-function"></a>Função RangeEnd

Espaço de nome: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)

Pacote: [](https://nuget.org/packages/)


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