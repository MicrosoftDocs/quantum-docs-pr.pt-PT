---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorIndex
title: Função MultiplyGeneratorIndex
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorIndex
qsharp.summary: Multiplies the coefficient in a `GeneratorIndex`.
ms.openlocfilehash: b53a483a0c2b8c99b733c9c87289fb212b5ffc89
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848020"
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

## <a name="example"></a>Exemplo

```qsharp
let gen = GeneratorIndex(([1,2,3],[coeff]),[1,2,3]);
let ((idxPaulis, idxDoubles), idxQubits) = MultiplyGeneratorIndex(multiplier, gen);
// idxDoubles[0] == multiplier * coeff;
```

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Simulation.GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)