---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorIndex
title: Função MultiplyGeneratorIndex
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorIndex
qsharp.summary: Multiplies the coefficient in a `GeneratorIndex`.
ms.openlocfilehash: dc2bd02c40b53eca726f70578e3c5918add8f1bb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230451"
---
# <a name="multiplygeneratorindex-function"></a>Função MultiplyGeneratorIndex

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Multiplica o coeficiente num `GeneratorIndex` .

```qsharp
function MultiplyGeneratorIndex (multiplier : Double, generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Entrada

### <a name="multiplier--double"></a>multiplicador : [Duplo](xref:microsoft.quantum.lang-ref.double)

O multiplicador do coeficiente.


### <a name="generatorindex--generatorindex"></a>generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

O `GeneratorIndex` a ser multiplicado.



## <a name="output--generatorindex"></a>Saída : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Um `GeneratorIndex` termo representando um termo com coeficiente um fator `multiplier` maior.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Simulation.GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)