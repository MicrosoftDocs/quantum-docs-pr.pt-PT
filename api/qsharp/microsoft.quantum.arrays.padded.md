---
uid: Microsoft.Quantum.Arrays.Padded
title: Função acolchoada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 556e5f5175ee54470a99f32c037eeb2cd80588d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845568"
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

## <a name="example"></a>Exemplo

```qsharp
let array = [10, 11, 12];
// The following line returns [10, 12, 15, 2, 2, 2].
let output = Padded(-6, array, 2);
// The following line returns [2, 2, 2, 10, 12, 15].
let output = Padded(6, array, 2);
```