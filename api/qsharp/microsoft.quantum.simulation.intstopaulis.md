---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: Função IntsToPaulis
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 6904054bb1aff3a57c80882694b4c217812b2b81
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842231"
---
# <a name="intstopaulis-function"></a>Função IntsToPaulis

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Converte uma variedade de inteiros para uma variedade de operadores Pauli de um único qubit.

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a>Entrada

### <a name="ints--int"></a>ints : [Int](xref:microsoft.quantum.lang-ref.int)[]

Conjunto de inteiros na gama `0..3`  a converter para operadores Pauli.



## <a name="output--pauli"></a>Saída : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Uma matriz `paulis` de operadores Pauli `Pauli[]` com o mesmo comprimento que tal que é igual ao elemento dado por `ints` `paulis[idxPauli]` `[PauliI, PauliX, PauliY, PauliZ]` `ints[idxPauli]` .