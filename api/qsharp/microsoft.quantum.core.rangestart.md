---
uid: Microsoft.Quantum.Core.RangeStart
title: Função RangeStart
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 3e4b0cebe34b4c98cb1d582a9cd11b46ff778517
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713170"
---
# <a name="rangestart-function"></a>Função RangeStart

Espaço de nome: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)

Pacote: [](https://nuget.org/packages/)


Devolve o valor de início definido da gama dada.

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a>Entrada

### <a name="range--range"></a>gama : [Gama](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

O valor inicial definido da gama dada.

## <a name="remarks"></a>Observações

O primeiro elemento de uma expressão de alcance é `start` , o seu segundo elemento é , terceiro elemento é , `start+step` `start+step+step` etc., até `end` ser passado.

Note que o valor inicial definido de uma gama é o mesmo que o primeiro elemento da sequência, a menos que o intervalo especifique uma sequência vazia (por exemplo, 2 .. 1).