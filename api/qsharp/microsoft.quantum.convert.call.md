---
uid: Microsoft.Quantum.Convert.Call
title: Operação de chamada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 8630f846b4b9823ce1c1dfd61dc8ca81e468517d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713534"
---
# <a name="call-operation"></a>Operação de chamada

Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)

Pacote: [](https://nuget.org/packages/)


Chama uma função com uma dada entrada.

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a>Descrição

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