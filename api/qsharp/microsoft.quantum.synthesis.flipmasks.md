---
uid: Microsoft.Quantum.Synthesis.FlipMasks
title: Função FlipMasks
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FlipMasks
qsharp.summary: For every 2-level unitary calculates "flip mask", which denotes qubits which should be inverted before and after applying corresponding 1-qubit gate. For convenience prepends result with 0.
ms.openlocfilehash: ca0ce69b3353379a42cc109cebb32efe4e364825
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859206"
---
# <a name="flipmasks-function"></a>Função FlipMasks

Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Para cada 2 níveis unitário calcula "flip mask", que denota qubits que devem ser invertidos antes e depois de aplicar o portão de 1 qubit correspondente.
Para os preparativos de conveniência resultam com 0.

```qsharp
function FlipMasks (decomposition : (Microsoft.Quantum.Math.Complex[][], Int, Int)[], allQubitsMask : Int) : Int[]
```


## <a name="input"></a>Entrada

### <a name="decomposition--complexintint"></a>decomposição:[(Complexo](xref:Microsoft.Quantum.Math.Complex)[],[Int,](xref:microsoft.quantum.lang-ref.int)[Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="allqubitsmask--int"></a>allQubitsMask : [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]

