---
uid: Microsoft.Quantum.Core.RangeStep
title: Função RangeStep
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 39c8581fe795a1b76d2a6e81c238a271287c2c38
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213808"
---
# <a name="rangestep-function"></a>Função RangeStep

Espaço de nome: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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