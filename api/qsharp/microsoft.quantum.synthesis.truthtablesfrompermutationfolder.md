---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: Função TruthTablesFromPermutationFolder
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 86e112782825303805029b2f9f6cfd9d6ce9e8b6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231029"
---
# <a name="truthtablesfrompermutationfolder-function"></a>Função TruthTablesFromPermutationFolder

Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Lógica de decomposição para um único índice variável

```qsharp
function TruthTablesFromPermutationFolder (numVars : Int, state : Microsoft.Quantum.Synthesis.DecompositionState, index : Int) : Microsoft.Quantum.Synthesis.DecompositionState
```


## <a name="description"></a>Description

Isto toma o estado atual e gera uma permutação atualizada e possivelmente adiciona novas funções para portões controlados.

## <a name="input"></a>Entrada

### <a name="numvars--int"></a>numVars : [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="state--decompositionstate"></a>estado : [DecomposiçãoState](xref:Microsoft.Quantum.Synthesis.DecompositionState)




### <a name="index--int"></a>índice : [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--decompositionstate"></a>Saída : [DecomposiçãoState](xref:Microsoft.Quantum.Synthesis.DecompositionState)

