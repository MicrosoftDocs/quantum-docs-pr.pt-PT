---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunçãoAsOperação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 90e9f0c922a77fbb6d6faf8945d4f5d1c8ff33b7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713509"
---
# <a name="functionasoperation-function"></a>FunçãoAsOperação

Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)

Pacote: [](https://nuget.org/packages/)


Converte funções em operações.

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a>Descrição

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