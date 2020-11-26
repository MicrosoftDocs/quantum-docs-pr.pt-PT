---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: Tipo definido pelo utilizador GeneratorIndex
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: dae23db9bee34be4aa99d96799efad64a66d7193
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229329"
---
# <a name="generatorindex-user-defined-type"></a>Tipo definido pelo utilizador GeneratorIndex

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa um único termo primitivo no conjunto de todos os geradores dinâmicos, por exemplo, operadores hermitianos, para os quais existe um mapa desse gerador para a evolução temporal por aquele gerador, através `EvolutionSet` de .

O primeiro elemento (Int[], Double[]) é índices que um único termo -- Por exemplo, a cadeia Pauli XXY com coeficiente 0,5 seria indexada por ([1,1,2], [0,5]). Alternativamente, os hamiltonianos parametrizados por uma variável contínua, como X cos φ + Y sin φ, podem, por exemplo, ser representados por ([], [φ]). O segundo elemento indexa o subsistema no qual o gerador atua.

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="remarks"></a>Observações

> [!WARNING]
> A interpretação de um `GeneratorIndex` não é definida exceto com referência a um determinado conjunto de geradores.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.SimulationSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [Microsoft.Quantum.Simulation.PauliEvolutionSet](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)