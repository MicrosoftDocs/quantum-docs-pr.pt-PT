---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: Função MultiplyGeneratorSystem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: effb9e3ca754f77bbe1ea0fb6ca30ae49e92d531
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229159"
---
# <a name="multiplygeneratorsystem-function"></a>Função MultiplyGeneratorSystem

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Multiplica o coeficiente de todos os termos em `GeneratorSystem` um .

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Entrada

### <a name="multiplier--double"></a>multiplicador : [Duplo](xref:microsoft.quantum.lang-ref.double)

O multiplicador do coeficiente.


### <a name="generatorsystem--generatorsystem"></a>sistema gerador : [Sistema gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

O `GeneratorSystem` a ser multiplicado.



## <a name="output--generatorsystem"></a>Saída : [Sistema Gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Um `GeneratorSystem` sistema representando um sistema com coeficientes um fator `multiplier` maior.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Simulation.GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)