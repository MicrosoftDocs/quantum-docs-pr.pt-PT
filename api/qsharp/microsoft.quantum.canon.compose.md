---
uid: Microsoft.Quantum.Canon.Compose
title: Função de composição
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 02cff7eef4d55d27d5d72e6219a90b7d8f5beb3b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716491"
---
# <a name="compose-function"></a>Função de composição

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Devolve a composição de duas funções.

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a>Descrição

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