---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystems
title: Função InterpolateGeneratorSystems
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystems
qsharp.summary: Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.
ms.openlocfilehash: c56f1eaf13afb649777c0d9368e97d85996cc67b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842266"
---
# <a name="interpolategeneratorsystems-function"></a>Função InterpolateGeneratorSystems

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve um `TimeDependentGeneratorSystem` representante da interpolação linear entre dois `GeneratorSystem` s.

```qsharp
function InterpolateGeneratorSystems (generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
```


## <a name="input"></a>Entrada

### <a name="generatorsystemstart--generatorsystem"></a>generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

O `GeneratorSystem` início.


### <a name="generatorsystemend--generatorsystem"></a>sistema geradorEnd : [Sistema gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

O `GeneratorSystem` fim.



## <a name="output--timedependentgeneratorsystem"></a>Saída : [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)

Um `TimeDependentGeneratorSystem` sistema que representa um sistema que é a soma dos sistemas geradores de entrada, com peso $(1-s)$ `generatorSystemStart` e peso $s$ em `generatorSystemEnd` .

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Simulation.GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)
- [Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)