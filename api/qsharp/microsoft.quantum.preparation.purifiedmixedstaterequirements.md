---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements
title: Função de Excrementos do Estado Despromoficados
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateRequirements
qsharp.summary: Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".
ms.openlocfilehash: 6ddb48ba66eea87a07d515ff791bfb34f2d98b76
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856837"
---
# <a name="purifiedmixedstaterequirements-function"></a>Função de Excrementos do Estado Despromoficados

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve o número total de qubits que devem ser atribuídos para aplicar a operação devolvida por @"microsoft.quantum.preparation.purifiedmixedstate" .

```qsharp
function PurifiedMixedStateRequirements (targetError : Double, nCoefficients : Int) : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
```


## <a name="input"></a>Entrada

### <a name="targeterror--double"></a>targetError : [Duplo](xref:microsoft.quantum.lang-ref.double)

O erro do alvo $\epsilon$.


### <a name="ncoefficients--int"></a>nCoefficientes : [Int](xref:microsoft.quantum.lang-ref.int)

O número de coeficientes a especificar na preparação de um estado misto.



## <a name="output--mixedstatepreparationrequirements"></a>Saída : [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)

Uma descrição de quantos qubits são necessários no total, e para cada um dos registos de índice e lixo usados pela @"microsoft.quantum.preparation.purifiedmixedstate" função.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Preparation.PurifiedMixedState](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)