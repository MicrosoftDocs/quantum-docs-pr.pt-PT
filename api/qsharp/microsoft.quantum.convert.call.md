---
uid: Microsoft.Quantum.Convert.Call
title: Operação de chamada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 92c159cef878fb587b0ed514fd6660dd19527cab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214216"
---
# <a name="call-operation"></a>Operação de chamada

Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Chama uma função com uma dada entrada.

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a>Description

Dada uma função e uma entrada para essa função, chama a função e devolve a sua saída.

## <a name="input"></a>Entrada

### <a name="fn--input---output"></a>fn : 'Entrada -> 'Saída

Uma função a ser chamada.


### <a name="input--input"></a>entrada : 'Entrada

A entrada a ser passada para a função.



## <a name="output--output"></a>Saída : 'Saída

O resultado da `fn` chamada.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="input"></a>'Entrada


### <a name="output"></a>'Saída



## <a name="remarks"></a>Observações

Esta operação é principalmente útil para forçar uma função a ser chamada num local específico dentro de uma operação, ou para chamar uma função onde uma operação é esperada.