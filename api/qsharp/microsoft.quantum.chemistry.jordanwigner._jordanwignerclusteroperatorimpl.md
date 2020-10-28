---
uid: Microsoft.Quantum.Chemistry.JordanWigner._JordanWignerClusterOperatorImpl
title: operação _JordanWignerClusterOperatorImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _JordanWignerClusterOperatorImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 9507558ebe73bce87d9089aad22b94c1d9d579d0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714601"
---
# <a name="_jordanwignerclusteroperatorimpl-operation"></a>operação _JordanWignerClusterOperatorImpl

Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Pacote: [](https://nuget.org/packages/)


Representa um gerador dinâmico como um conjunto de portões simulados e uma expansão na base JordanWigner.

Consulte [a Modelação do Gerador Dinâmico](../libraries/data-structures#dynamical-generator-modeling) para obter mais detalhes.

```qsharp
operation _JordanWignerClusterOperatorImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="generatorindex--generatorindex"></a>generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Um índice gerador a ser representado como evolução unitária no JordanWigner.


### <a name="stepsize--double"></a>stepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)

Variável manequim para combinar assinatura de algoritmos de simulação.


### <a name="qubits--qubit"></a>qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registo atuado pelo operador de evolução temporal.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

