---
uid: Microsoft.Quantum.Arrays.IndexOf
title: Indexação da função
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 7ff80f13f432a18f216b2dee4bd65b1e82034fa5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719171"
---
# <a name="indexof-function"></a>Indexação da função

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


Devolve o primeiro índice do primeiro elemento numa matriz que satisfaz um dado predicado. Se não existir tal elemento, de volta -1.

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a>Entrada

### <a name="predicate--t---bool"></a>predicado: 'T-> [Bool](xref:microsoft.quantum.lang-ref.bool)

Uma função predicado agindo sobre elementos da matriz.


### <a name="arr--t"></a>arr : 'T]]

Uma matriz a ser revistada usando o predicado dado.



## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

Ou o menor índice `idx` que `predicate(arr[idx])` é verdade, ou -1 se tal elemento não existir.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

