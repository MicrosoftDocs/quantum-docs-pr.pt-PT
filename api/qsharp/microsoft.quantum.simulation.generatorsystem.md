---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: Tipo definido pelo utilizador Do Sistema gerador
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 3748d3fb79597fb526c86a91bc28290155189014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858415"
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