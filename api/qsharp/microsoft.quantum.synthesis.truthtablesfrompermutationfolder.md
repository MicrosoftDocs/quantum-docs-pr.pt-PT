---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: Função TruthTablesFromPermutationFolder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 6b00c9e880ed7b7b3bf446dcb17dab3bab7a83a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724458"
---
# <a name="truthtablesfrompermutationfolder-function"></a>Função TruthTablesFromPermutationFolder

Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacote: [](https://nuget.org/packages/)


Lógica de decomposição para um único índice variável

```qsharp
function TruthTablesFromPermutationFolder (numVars : Int, state : Microsoft.Quantum.Synthesis.DecompositionState, index : Int) : Microsoft.Quantum.Synthesis.DecompositionState
```


## <a name="description"></a>Descrição

Isto toma o estado atual e gera uma permutação atualizada e possivelmente adiciona novas funções para portões controlados.

## <a name="input"></a>Entrada

### <a name="numvars--int"></a>numVars : [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="state--decompositionstate"></a>estado : [DecomposiçãoState](xref:Microsoft.Quantum.Synthesis.DecompositionState)




### <a name="index--int"></a>índice : [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--decompositionstate"></a>Saída : [DecomposiçãoState](xref:Microsoft.Quantum.Synthesis.DecompositionState)

