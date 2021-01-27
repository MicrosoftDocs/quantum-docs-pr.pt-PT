---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: Função CumulativeFolded
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: 95cd5233a09a1234bba4de9fe870b9d93c0f86a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846225"
---
# <a name="cumulativefolded-function"></a>Função CumulativeFolded

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Combina Mapeado e Dobre numa única função

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a>Descrição

Esta função iteriza a `fn` função através da matriz, partindo de um estado inicial `state` e devolve todos os valores intermédios, sem incluir o estado inicial.

## <a name="input"></a>Entrada

### <a name="fn--statet---state"></a>fn : ('Estado,'T) -> 'Estado

Uma função a ser dobrada sobre a matriz


### <a name="state--state"></a>estado : 'Estado

O estado inicial a ser dobrado


### <a name="array--t"></a>matriz : 'T[]

Uma matriz de valores a dobrar



## <a name="output--state"></a>Saída : 'Estado].

Todos os estados intermédios, incluindo o estado final, mas não o estado inicial.
O comprimento da matriz de saída tem o mesmo comprimento que `array` . .

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="state"></a>'Estado

O tipo de estados em que a `fn` função funciona, ou seja, aceita como primeira entrada e retorno.
### <a name="t"></a>'T

O tipo de `array` elementos.

## <a name="example"></a>Exemplo

```qsharp
// same as sums = [1, 3, 6, 10, 15]
let sums = CumulativeFolded(PlusI, 0, SequenceI(1, 5));
```