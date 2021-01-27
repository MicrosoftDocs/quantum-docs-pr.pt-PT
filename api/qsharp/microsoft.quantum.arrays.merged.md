---
uid: Microsoft.Quantum.Arrays.Merged
title: Função fundida
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: 262e7450188370212a7e2a57bf15e9f8ab162814
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845614"
---
# <a name="merged-function"></a>Função fundida

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

