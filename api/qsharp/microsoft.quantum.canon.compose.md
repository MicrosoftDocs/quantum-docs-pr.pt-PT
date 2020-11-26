---
uid: Microsoft.Quantum.Canon.Compose
title: Função de composição
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: f8c6ad36220b48be1723c2d91cbf7c0a4947af14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216766"
---
# <a name="compose-function"></a>Função de composição

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve a composição de duas funções.

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a>Description

Tendo em conta duas funções $f$ e $g$, devolve uma nova função que representa $f \circ g$.

## <a name="input"></a>Entrada

### <a name="outer--u---v"></a>exterior : 'U -> 'V

A segunda função a ser aplicada.


### <a name="inner--t---u"></a>interior : 'T-> 'U

A primeira função a ser aplicada.



## <a name="output--t---v"></a>Saída : 'T-> 'V

Uma nova função $h$ tal que para todas as entradas $x$, $f(g(x)= h(x)$.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de entrada da primeira função a aplicar.
### <a name="u"></a>'U

O tipo de saída da primeira função a aplicar e o tipo de entrada da segunda função a aplicar.
### <a name="v"></a>'V

O tipo de saída da segunda função a aplicar.