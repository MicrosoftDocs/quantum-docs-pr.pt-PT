---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: Função IntToPauli
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 18edb600f7b5b33c7ad98e78e32903c570082225
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229210"
---
# <a name="inttopauli-function"></a>Função IntToPauli

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Converte um inteiro para um operador pauli de um único qubit.

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a>Entrada

### <a name="idx--int"></a>idx : [Int](xref:microsoft.quantum.lang-ref.int)

Inteiro na gama `0..3` a converter para operadores Pauli.



## <a name="output--pauli"></a>Saída : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Um `Pauli` operador dado por `[PauliI, PauliX, PauliY, PauliZ][idx]` .