---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystemsImpl
title: Função InterpolateGeneratorSystemsImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystemsImpl
qsharp.summary: Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).
ms.openlocfilehash: 212ed4c473fab3572f73ea250061057ad13e393f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709435"
---
# <a name="interpolategeneratorsystemsimpl-function"></a>Função InterpolateGeneratorSystemsImpl

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [](https://nuget.org/packages/)


Interpola linearmente entre dois `GeneratorSystems` de acordo com um parâmetro de programação entre `s` 0 e 1 (inclusive).

```qsharp
function InterpolateGeneratorSystemsImpl (schedule : Double, generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Entrada

### <a name="schedule--double"></a>horário : [Duplo](xref:microsoft.quantum.lang-ref.double)

Um parâmetro de agenda $s\in[0,1]$.


### <a name="generatorsystemstart--generatorsystem"></a>generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

O `GeneratorSystem` início.


### <a name="generatorsystemend--generatorsystem"></a>sistema geradorEnd : [Sistema gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

O `GeneratorSystem` fim.



## <a name="output--generatorsystem"></a>Saída : [Sistema Gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Um `GeneratorSystem` sistema que representa um sistema que é a soma dos sistemas geradores de entrada, com peso $(1-s)$ `generatorSystemStart` e peso $s$ em `generatorSystemEnd` .

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Simulation.GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)