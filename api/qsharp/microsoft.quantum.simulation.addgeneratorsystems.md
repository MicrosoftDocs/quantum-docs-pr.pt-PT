---
uid: Microsoft.Quantum.Simulation.AddGeneratorSystems
title: Função AddGeneratorSystems
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AddGeneratorSystems
qsharp.summary: Adds two `GeneratorSystem`s to create a new `GeneratorSystem`.
ms.openlocfilehash: 494037aa7635cccf25978bea9339ecc7aee75142
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710639"
---
# <a name="addgeneratorsystems-function"></a>Função AddGeneratorSystems

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [](https://nuget.org/packages/)


Adiciona dois `GeneratorSystem` s para criar um novo `GeneratorSystem` .

```qsharp
function AddGeneratorSystems (generatorSystemA : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemB : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Entrada

### <a name="generatorsystema--generatorsystem"></a>generatorSystemA : [Sistema gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

O `GeneratorSystem` primeiro.


### <a name="generatorsystemb--generatorsystem"></a>generatorSystemB : [Sistema gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

A `GeneratorSystem` segunda.



## <a name="output--generatorsystem"></a>Saída : [Sistema Gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Um `GeneratorSystem` sistema que representa um sistema que é a soma dos sistemas geradores de entrada.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Simulation.GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)