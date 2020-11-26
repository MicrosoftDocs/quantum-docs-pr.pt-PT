---
uid: Microsoft.Quantum.Canon.CurriedOp
title: Função CurriedOp
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: 6c1917d6f1ee69cb29fed1ab173106af1e206533
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216630"
---
# <a name="curriedop-function"></a>Função CurriedOp

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve uma versão cosidada de uma operação em duas entradas.

Ou seja, dada uma operação com duas entradas, esta função aplica o isomorfismo de Curry $f(x, y) \equiv f(x)(y)$ para devolver uma operação de uma entrada que devolve uma operação de uma entrada.

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a>Entrada

### <a name="op--tu--unit"></a>op : ('T,'U) = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Uma operação cuja entrada é um par.



## <a name="output--t---u--unit"></a>Saída : 'T-> 'U = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Uma operação que aceite o primeiro elemento de um par e devolva uma operação que aceite como entrada o segundo elemento da entrada da operação original.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de primeiro componente de uma função definida em pares.
### <a name="u"></a>'U

O tipo do segundo componente de uma função definida em pares.

## <a name="remarks"></a>Observações

Os seguintes são equivalentes:

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```