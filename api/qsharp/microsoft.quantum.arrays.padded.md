---
uid: Microsoft.Quantum.Arrays.Padded
title: Função acolchoada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 8742d4726e7ee32349bf3d0bd5077352ffca350b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718979"
---
# <a name="padded-function"></a>Função acolchoada

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


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