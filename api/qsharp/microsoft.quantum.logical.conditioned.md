---
uid: Microsoft.Quantum.Logical.Conditioned
title: Função condicionada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: c0f55d4db95ad1f0d2b7f291cbc6ba8ae704cb81
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198491"
---
# <a name="conditioned-function"></a>Função condicionada

Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve um de dois valores, dependendo do valor de uma condição Booleana.

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a>Entrada

### <a name="condition--bool"></a>condição : [Bool](xref:microsoft.quantum.lang-ref.bool)

Uma condição usada para controlar a entrada que é devolvida.


### <a name="iftrue--t"></a>ifTrue : 'T

O valor a devolver quando `condition` `true` for.


### <a name="iffalse--t"></a>ifFalse : 'T

O valor a devolver quando `condition` `false` for.



## <a name="output--t"></a>Saída : 'T

`ifTrue` se `condition` `true` for, e `ifFalse` de outra forma.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T



## <a name="remarks"></a>Observações

Ao contrário do `?|` operador, esta função não faz um curto-circuito, de modo a que ambas as entradas sejam totalmente avaliadas.

Até um comportamento de curto-circuito, os seguintes são equivalentes:

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```