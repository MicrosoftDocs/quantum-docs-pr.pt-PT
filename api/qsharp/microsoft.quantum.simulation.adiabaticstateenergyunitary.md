---
uid: Microsoft.Quantum.Simulation.AdiabaticStateEnergyUnitary
title: Operação AdiabaticStateEnergyUnitary
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AdiabaticStateEnergyUnitary
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on the input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: 642f6a0af76b3b2d0703f0377c379abf33ecee71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722767"
---
# <a name="adiabaticstateenergyunitary-operation"></a>Operação AdiabaticStateEnergyUnitary

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [](https://nuget.org/packages/)


Realiza a preparação do Estado aplicando um `statePrepUnitary` no estado de entrada, seguido da preparação do estado adiabático utilizando uma `adiabaticUnitary` estimativa de fase, e, finalmente, fase no que diz respeito `qpeUnitary` ao estado resultante utilizando a `phaseEstAlgorithm` .

```qsharp
operation AdiabaticStateEnergyUnitary (statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double), qubits : Qubit[]) : Double
```


## <a name="input"></a>Entrada

### <a name="stateprepunitary--qubit--unit"></a>EstadoPrepUnitário : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Um oráculo que representa a preparação do estado para o gerador dinâmico inicial.


### <a name="adiabaticunitary--qubit--unit"></a>adiabaticUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Um oráculo que representa o algoritmo de evolução adiabática para ser usado para implementar as varreduras para o estado final do algoritmo.


### <a name="qpeunitary--qubit--unit-adj--ctl"></a>qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit)> Adj + Ctl

Um oráculo que representa um operador unitário $U$ que representa a evolução para o tempo $\delta t$ sob um gerador dinâmico com estado de terra $\ket{\phi}$ e energia do estado do solo $E = \\ \phi,\delta t$.


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a>phaseEstAlgorithm :[(DiscreteOracle,](xref:Microsoft.Quantum.Oracles.DiscreteOracle)[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double) 

Uma operação que efetue a estimativa de fase numa determinada operação unitária.
Consulte [a estimativa da fase iterativa](/quantum/libraries/characterization#iterative-phase-estimation) para mais detalhes.


### <a name="qubits--qubit"></a>qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um registo de qubits para ser usado para realizar a simulação.



## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)

Uma estimativa de $\hat{\phi}$ da energia do estado do solo $\phi$ do gerador representado por $U$.