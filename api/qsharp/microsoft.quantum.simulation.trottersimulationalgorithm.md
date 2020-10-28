---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithm
title: Função TrotterSimulationAlgorithm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithm
qsharp.summary: '`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.'
ms.openlocfilehash: c52acf293e69c78e7a82b0cf5d94de52d0f5a293
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719866"
---
# <a name="trottersimulationalgorithm-function"></a>Função TrotterSimulationAlgorithm

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [](https://nuget.org/packages/)


`SimulationAlgorithm` função que utiliza uma decomposição Trotter-Suzuki para aproximar o operador de evolução temporal _exp(-iHt)_ .

```qsharp
function TrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.SimulationAlgorithm
```


## <a name="input"></a>Entrada

### <a name="trotterstepsize--double"></a>trotterStepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)

Duração da evolução do tempo simulada num único passo Trotter.


### <a name="trotterorder--int"></a>trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)

Ordem do integrador Trotter. Isto deve ser um ou um número par.



## <a name="output--simulationalgorithm"></a>Saída : [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)

Um `SimulationAlgorithm` tipo.