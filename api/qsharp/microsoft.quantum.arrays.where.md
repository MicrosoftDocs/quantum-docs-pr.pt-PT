---
uid: Microsoft.Quantum.Arrays.Where
title: Onde funciona
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 4a938114689177f7a9ee182e6e5f36debe4edac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842208"
---
# <a name="where-function"></a>Onde funciona

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dado um predicado e uma matriz, devolve os índices daquela matriz onde o predicado é verdadeiro.

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a>Entrada

### <a name="predicate--t---bool"></a>predicado: 'T-> [Bool](xref:microsoft.quantum.lang-ref.bool)

Uma função de `'T` Boolean que é usada para filtrar elementos.


### <a name="array--t"></a>matriz : 'T[]

Uma série de elementos sobre `'T` .



## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]

Uma série de índices onde `predicate` é verdade.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de `array` elementos.