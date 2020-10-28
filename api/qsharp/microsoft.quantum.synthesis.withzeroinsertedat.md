---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: Com a função ComZeroInsertedAt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 6e13251741dadb19740b208cdfc13a14964a48dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725158"
---
# <a name="withzeroinsertedat-function"></a>Com a função ComZeroInsertedAt

Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacote: [](https://nuget.org/packages/)


Insira um 0-bit num inteiro

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a>Descrição

Esta operação requer um inteiro, insere um 0 em `position` pouco, e devolve o valor atualizado como um inteiro.  Por exemplo, inserir um 0 na posição 2 no número 10 ($10_ {10} = 1010_ {2} $) devolve o número 18 ($18_ {10} = 10010_ {2} $).

## <a name="input"></a>Entrada

### <a name="position--int"></a>posição : [Int](xref:microsoft.quantum.lang-ref.int)

A posição em que 0 é inserido


### <a name="value--int"></a>valor : [Int](xref:microsoft.quantum.lang-ref.int)

O valor que é modificado



## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

Valor modificado