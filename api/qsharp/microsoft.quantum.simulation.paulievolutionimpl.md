---
uid: Microsoft.Quantum.Simulation.PauliEvolutionImpl
title: Operação PauliEvolutionImpl
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.

  See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 868f3eef187e8e993127cfcab21e1574583ac845
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229142"
---
# <a name="paulievolutionimpl-operation"></a>Operação PauliEvolutionImpl

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa um gerador dinâmico como um conjunto de portões simulados e uma expansão na base Pauli.

Consulte [a Modelação do Gerador Dinâmico](/quantum/libraries/data-structures#dynamical-generator-modeling) para obter mais detalhes.

```qsharp
operation PauliEvolutionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, delta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="generatorindex--generatorindex"></a>generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Um índice gerador a ser representado como evolução unitária na base Pauli.


### <a name="delta--double"></a>delta : [Duplo](xref:microsoft.quantum.lang-ref.double)

Um multiplicador sobre a duração da evolução temporal pelo termo referenciado em `generatorIndex` .


### <a name="qubits--qubit"></a>qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registo atuado pelo operador de evolução temporal.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

