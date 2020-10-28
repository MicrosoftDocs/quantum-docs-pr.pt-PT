---
uid: Microsoft.Quantum.Core.RangeStep
title: Função RangeStep
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: f8e4c42330f2d6afdc1c0a9bdde36081ccab2f94
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713159"
---
# <a name="rangestep-function"></a>Função RangeStep

Espaço de nome: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)

Pacote: [](https://nuget.org/packages/)


Devolve o inteiro que especifica como o próximo valor de uma gama é calculado.

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a>Entrada

### <a name="range--range"></a>gama : [Gama](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

O valor de passo definido da gama dada.

## <a name="remarks"></a>Observações

O primeiro elemento de uma expressão de alcance é `start` , o seu segundo elemento é , terceiro elemento é , `start+step` `start+step+step` etc., até `end` ser passado.