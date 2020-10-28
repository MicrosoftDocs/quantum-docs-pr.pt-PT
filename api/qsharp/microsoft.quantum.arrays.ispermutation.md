---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Função IsPermutation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 361bb21bedc725c25a1f3dfc811e9cfda4cb45ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719110"
---
# <a name="ispermutation-function"></a>Função IsPermutation

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


Saídas verdadeiras se e somente se uma determinada matriz representar uma permutação.

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a>Descrição

Dada uma matriz `array` de `n` comprimento, retorna verdadeira se e somente se cada inteiro de `0` aparecer `n - 1` exatamente uma vez dentro , tal que `array` pode ser interpretado como uma `array` permutação em `n` elementos.

## <a name="input"></a>Entrada

### <a name="permuation--int"></a>permutação : [Int](xref:microsoft.quantum.lang-ref.int)[]

Uma matriz que pode ou não representar uma permutação.



## <a name="output--bool"></a>Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)



## <a name="remarks"></a>Observações

Uma matriz de comprimento zero é trivialmente uma permutação.