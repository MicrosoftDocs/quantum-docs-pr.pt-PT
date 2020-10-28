---
uid: Microsoft.Quantum.Arrays.Merged
title: Função fundida
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: da15a36f8f057cdc15062c96070ec21becc4794a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719014"
---
# <a name="merged-function"></a>Função fundida

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


Tendo em conta duas matrizes ordenadas, devolve uma única matriz contendo os elementos de ambos em ordem ordenada. Usado internamente por tipo de fusão.

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a>Entrada

### <a name="comparison--tt---bool"></a>comparação: ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)




### <a name="left--t"></a>esquerda : 'T[]




### <a name="right--t"></a>direito : 'T[]





## <a name="output--t"></a>Saída : 'T].



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

