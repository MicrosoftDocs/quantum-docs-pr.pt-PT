---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunçãoAsOperação
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 10703818242cf6b3853f08a45bfb9094f397f6c2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224382"
---
# <a name="functionasoperation-function"></a>FunçãoAsOperação

Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Converte funções em operações.

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a>Description

Dada uma função, retorna uma operação que chama a essa função, e que não faz mais nada.

## <a name="input"></a>Entrada

### <a name="fn--input---output"></a>fn : 'Entrada -> 'Saída

Uma função a converter para uma operação.



## <a name="output--input--output"></a>Saída : 'Entrada => 'Saída 

Uma operação `op` idêntica `op(input)` a `fn(input)` `input` todas.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="input"></a>'Entrada

Tipo de entrada da função a converter.
### <a name="output"></a>'Saída

Tipo de saída da função a converter.

## <a name="remarks"></a>Observações

Isto é principalmente útil para passar funções para funções ou operações que esperam uma operação como entrada.