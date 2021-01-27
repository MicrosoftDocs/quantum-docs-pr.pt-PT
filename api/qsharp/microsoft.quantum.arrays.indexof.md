---
uid: Microsoft.Quantum.Arrays.IndexOf
title: Indexação da função
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 64db55e831078a7130a3ced6a30bfbd2299c392d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848514"
---
# <a name="indexof-function"></a>Indexação da função

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>Exemplo

Suponha que `IsEven : Int -> Bool` esta é uma função que retorna `true` se e somente se a sua entrada for uniforme. Então, isto pode ser usado `IndexOf` para encontrar o primeiro elemento par em uma matriz:

```qsharp
let items = [1, 3, 17, 2, 21];
let idx = IndexOf(IsEven, items); // returns 3
```