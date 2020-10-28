---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystems
title: Função InterpolateGeneratorSystems
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystems
qsharp.summary: Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.
ms.openlocfilehash: 9881c27577023dafff0bfc6d961877db44fec0eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710566"
---
# <a name="interpolategeneratorsystems-function"></a>Função InterpolateGeneratorSystems

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [](https://nuget.org/packages/)


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