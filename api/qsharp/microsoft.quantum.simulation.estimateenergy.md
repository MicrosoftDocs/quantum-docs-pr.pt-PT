---
uid: Microsoft.Quantum.Simulation.EstimateEnergy
title: Estimativa OperaçãoEnergia
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergy
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: 0a02a8aad891c45b184b9b18d4e9383236485940
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229499"
---
# <a name="estimateenergy-operation"></a>Estimativa OperaçãoEnergia

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Executa a preparação do Estado aplicando uma `statePrepUnitary` numa estimativa de fase de fase de entrada atribuída automaticamente no que diz respeito ao estado resultante utilizando `qpeUnitary` a `phaseEstAlgorithm` .

```qsharp
operation EstimateEnergy (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a>Entrada

### <a name="nqubits--int"></a>nQubits : [Int](xref:microsoft.quantum.lang-ref.int)

Número de qubits usados para realizar simulação.


### <a name="stateprepunitary--qubit--unit"></a>EstadoPrepUnitário : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Um oráculo que representa a preparação do estado para o gerador dinâmico inicial.


### <a name="qpeunitary--qubit--unit--is-adj--ctl"></a>qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl

Um oráculo que representa um operador unitário $U$ que representa a evolução para o tempo $\delta t$ sob um gerador dinâmico com estado de terra $\ket{\phi}$ e energia do estado do solo $E = \\ \phi,\delta t$.


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a>phaseEstAlgorithm :[(DiscreteOracle,](xref:Microsoft.Quantum.Oracles.DiscreteOracle)[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double) 

Uma operação que efetue a estimativa de fase numa determinada operação unitária.
Consulte [a estimativa da fase iterativa](/quantum/libraries/characterization#iterative-phase-estimation) para mais detalhes.



## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)

Uma estimativa de $\hat{\phi}$ da energia do estado do solo $\phi$ da energia do estado terrestre do gerador representada por $U$.