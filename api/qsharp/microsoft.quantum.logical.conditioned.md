---
uid: Microsoft.Quantum.Logical.Conditioned
title: Função condicionada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: ea3b8eba960acceb6540978c6fccd9f796b0f67d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817293"
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

```qsharp
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```