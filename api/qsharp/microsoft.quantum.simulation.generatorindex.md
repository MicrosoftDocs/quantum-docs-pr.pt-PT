---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: Tipo definido pelo utilizador GeneratorIndex
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: 762dac81ea0963443f0338cea1b879856c84b0ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858386"
---
# <a name="generatorindex-user-defined-type"></a>Tipo definido pelo utilizador GeneratorIndex

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa um único termo primitivo no conjunto de todos os geradores dinâmicos, por exemplo, operadores hermitianos, para os quais existe um mapa desse gerador para a evolução temporal por aquele gerador, através `EvolutionSet` de .

O primeiro elemento (Int[], Double[]) é índices que um único termo -- Por exemplo, a cadeia Pauli XXY com coeficiente 0,5 seria indexada por ([1,1,2], [0,5]). Alternativamente, os hamiltonianos parametrizados por uma variável contínua, como X cos φ + Y sin φ, podem, por exemplo, ser representados por ([], [φ]). O segundo elemento indexa o subsistema no qual o gerador atua.

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="example"></a>Exemplo

Utilizando,  <xref:microsoft.quantum.simulation.paulievolutionset> o operador $\pi X_2 X_5 Y_9$ é representado como:

```qsharp
let index = GeneratorIndex(([1, 1, 2], [PI()]), [2, 5, 9]);
```

## <a name="remarks"></a>Observações

> [!WARNING]
> A interpretação de um `GeneratorIndex` não é definida exceto com referência a um determinado conjunto de geradores.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.SimulationSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [Microsoft.Quantum.Simulation.PauliEvolutionSet](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)