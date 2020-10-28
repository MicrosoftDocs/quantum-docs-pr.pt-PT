---
uid: Microsoft.Quantum.Arrays.Subarray
title: Função subarray
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: be7b6ee1a396d67ebc311d8d97f4bd751a32d171
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718846"
---
# <a name="subarray-function"></a>Função subarray

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


Pega numa matriz e numa lista de locais e produz uma nova matriz formada a partir dos elementos da matriz original que combinam com os locais dados.

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>Entrada

### <a name="indices--int"></a>índices : [Int](xref:microsoft.quantum.lang-ref.int)[]

Uma lista de inteiros que é usado para definir a subarray.


### <a name="array--t"></a>matriz : 'T[]

Uma série de elementos sobre `'T` .



## <a name="output--t"></a>Saída : 'T].

Uma série `out` de elementos cujos índices correspondem à subarray, de tal forma que `out[idx] == array[indices[idx]]` . .

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de `array` elementos.

## <a name="remarks"></a>Observações

A função é definida para tipos genéricos, ou seja, sempre que temos uma matriz `'T[]` e uma lista de locais que `Int[]` definem a subarray.
A construção da subarray baseia-se na geração de uma nova cópia profunda da matriz dada em oposição à manutenção de referências.

Se `Length(indices) < Length(array)` esta função devolver um subconjunto de `array` . Por outro lado, se `indices` contiver elementos repetidos, os elementos correspondentes `array` serão igualmente repetidos.
Se `indices` e tiver o mesmo `array` comprimento, esta função fornece permutações de `array` .