---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Função IsPermutation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 7e563650f33b0292e1e41f629829a2d3b9e5fd28
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848103"
---
# <a name="ispermutation-function"></a>Função IsPermutation

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>Exemplo

O seguinte código Q# imprime a mensagem "Todos os diagnósticos concluídos com sucesso":

```qsharp
Fact(IsPermutation([2, 0, 1], "");
Contradiction(IsPermutation([5, 0, 1], "[5, 0, 1] isn't a permutation");
Message("All diagnostics completed successfully.");
```

## <a name="remarks"></a>Observações

Uma matriz de comprimento zero é trivialmente uma permutação.