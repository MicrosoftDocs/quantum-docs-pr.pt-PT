---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: Função IntToPauli
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 76f482b86ff4a27b6e6ce6ae4ec3d59422563f12
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842256"
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