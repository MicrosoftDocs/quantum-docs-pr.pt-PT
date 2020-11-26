---
uid: Microsoft.Quantum.Arrays.Padded
title: Função acolchoada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 2b7a80d1cf5c82a1ff52bc4aa207cfe335b40061
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220540"
---
# <a name="padded-function"></a>Função acolchoada

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve uma matriz acolchoada com valores especificados até um comprimento especificado.

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a>Entrada

### <a name="nelementstotal--int"></a>nElementsTotal : [Int](xref:microsoft.quantum.lang-ref.int)

O comprimento da matriz acolchoada. Se isto for positivo, `inputArray` é acolchoado na cabeça. Se isto for negativo, `inputArray` é acolchoado na cauda.


### <a name="defaultelement--t"></a>defaultElement : 'T

Valor predefinido a utilizar para elementos de enchimento.


### <a name="inputarray--t"></a>inputArray : 'T[]

Matriz cujos valores estão na cabeça da matriz de saída.



## <a name="output--t"></a>Saída : 'T].

Uma matriz `output` que é o `inputArray` acolchoado na cabeça com `defaultElement` s até ter `output` comprimento `nElementsTotal`

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de elementos de matriz.