---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: Tipo definido pelo utilizador Do Sistema gerador
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 20092a8deca50c90f46f4d79c6b40b805f135754
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225232"
---
# <a name="generatorsystem-user-defined-type"></a>Tipo definido pelo utilizador Do Sistema gerador

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa uma coleção de `GeneratorIndex` es.

Nós iteramos sobre esta coleção usando um inteiro de índice único, e o tamanho da coleção é assumido como sendo conhecido.

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a>Observações

As instâncias `GeneratorSystem` podem ser definidas facilmente usando a <xref:microsoft.quantum.arrays.lookupfunction> função.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Arrays.LookupFunction](xref:Microsoft.Quantum.Arrays.LookupFunction)