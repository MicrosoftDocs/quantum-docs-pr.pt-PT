---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: Função IntsToPaulis
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 605257aa7ca39e457127e3c3459b5891145b1863
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709449"
---
# <a name="intstopaulis-function"></a>Função IntsToPaulis

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [](https://nuget.org/packages/)


Converte uma variedade de inteiros para uma variedade de operadores Pauli de um único qubit.

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a>Entrada

### <a name="ints--int"></a>ints : [Int](xref:microsoft.quantum.lang-ref.int)[]

Conjunto de inteiros na gama `0..3`  a converter para operadores Pauli.



## <a name="output--pauli"></a>Saída : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Uma matriz `paulis` de operadores Pauli `Pauli[]` com o mesmo comprimento que tal que é igual ao elemento dado por `ints` `paulis[idxPauli]` `[PauliI, PauliX, PauliY, PauliZ]` `ints[idxPauli]` .