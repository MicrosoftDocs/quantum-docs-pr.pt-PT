---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: Função decompostaOn
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: fb7aa5af8f3eb07399e0d2dd2d50723f4e6b169a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855517"
---
# <a name="decomposedon-function"></a>Função decompostaOn

Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Decompõe-se uma permutação numa variável

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a>Descrição

Dada uma permutação $\pi$ `perm` e um índice $i$ ( ), este método devolve três `index` permutações $(\pi_l, \pi_r), \pi')$ de tal forma que as imagens de $\pi_l$ e $\pi_r$ não mudam bits nos seus elementos em índices que não $i$ e imagens de $\pi'$ não mudam um pouco $i$ nos seus elementos.

## <a name="input"></a>Entrada

### <a name="perm--int"></a>perm : [Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="index--int"></a>índice : [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--intintint"></a>Saída :[(Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[])



## <a name="example"></a>Exemplo

Suponha que a entrada é perm = [0, 2, 3, 5, 7, 1, 4, 6] e índice = 0, então esta função calcula três permutações com base na tabela seguinte, que lista a permutação `perm` na notação binária com elementos do grupo A e imagens do grupo D.  As colunas listam os índices de bits.

|   Um |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 |       |       | 0 0 0 | 0
| 0 0 1 |       |       | 0 1 0 | 2
| 0 1 0 |       |       | 0 1 1 | 3
| 0 1 1 |       |       | 1 0 1 | 5
| 1 0 0 |       |       | 1 1 1 | 7
| 1 0 1 |       |       | 0 0 1 | 1
| 1 1 0 |       |       | 1 0 0 | 4
| 1 1 1 |       |       | 1 1 0 | 6

Todos os valores para índices não iguais a 0 (= índice) são copiados de A a B e de D a C.

|   Um |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 | 0 0   | 0 0   | 0 0 0 |
| 0 0 1 | 0 0   | 0 1   | 0 1 0 |
| 0 1 0 | 0 1   | 0 1   | 0 1 1 |
| 0 1 1 | 0 1   | 1 0   | 1 0 1 |
| 1 0 0 | 1 0   | 1 1   | 1 1 1 |
| 1 0 1 | 1 0   | 0 0   | 0 0 1 |
| 1 1 0 | 1 1   | 1 0   | 1 0 0 |
| 1 1 1 | 1 1   | 1 1   | 1 1 0 |

Em seguida, um 0 é colocado para o primeiro elemento com um índice vazio na coluna 0 no bloco B e, em seguida, um 1 é colocado em B onde o prefixo corresponde (no primeiro caso a outra linha com índices 0 0).
Em seguida, um 1 é adicionado na mesma linha no bloco C, e em seguida um 0 para o prefixo correspondente no bloco C.  Este processo é repetido, até que todos os índices tenham sido colocados na coluna 0 nos blocos B e C.

|   Um |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 | 0 0 0 | 0 0 0 | 0 0 0 |
| 0 0 1 | 0 0 1 | 0 1 1 | 0 1 0 |
| 0 1 0 | 0 1 0 | 0 1 0 | 0 1 1 |
| 0 1 1 | 0 1 1 | 1 0 1 | 1 0 1 |
| 1 0 0 | 1 0 0 | 1 1 0 | 1 1 1 |
| 1 0 1 | 1 0 1 | 0 0 1 | 0 0 1 |
| 1 1 0 | 1 1 0 | 1 0 0 | 1 0 0 |
| 1 1 1 | 1 1 1 | 1 1 1 | 1 1 0 |

Podemos ler três novas permutações da mesa:

- $\pi_l$ com elementos em A, imagens em B (à esquerda)
- $\pi_r$ com elementos em D, imagens em C (à direita)
- $\pi'$ com elementos em B, imagens em C (restante)

Note que por design os valores dos bits não mudam em $\pi_l$ e $\pi_r$ para os índices 1 e 2, e os valores de bit não mudam para $\pi_'$ para índice 0.  Note também que $\pi_l$ e $\pi_r$ devem ser auto-inversos.

As permutações derivadas e devolvidas são: esquerda = [0, 1, 2, 3, 4, 5, 6, 7] direita = [0, 1, 3, 2, 4, 5, 7, 6] restante = [0, 3, 2, 5, 6, 1, 4, 7]