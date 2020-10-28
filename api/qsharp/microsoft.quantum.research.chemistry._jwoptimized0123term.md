---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimized0123Term
title: operação _JWOptimized0123Term
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimized0123Term
qsharp.summary: Applies time-evolution by a PQRS term described by a `GeneratorIndex`.
ms.openlocfilehash: 7382f3167055bbc2a499fa9490f89a0eb147e3e2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710846"
---
# <a name="_jwoptimized0123term-operation"></a>operação _JWOptimized0123Term

Espaço de nome: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)

Pacote: [](https://nuget.org/packages/)


Aplica a evolução temporal por um termo PQRS descrito por um `GeneratorIndex` .

```qsharp
operation _JWOptimized0123Term (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="term--generatorindex"></a>termo : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` representando um termo PQRS.


### <a name="stepsize--double"></a>stepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)

Duração da evolução do tempo.


### <a name="parityqubit--qubit"></a>parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit que determina o sinal da evolução do tempo.


### <a name="qubits--qubit"></a>qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits de Hamiltonian.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

