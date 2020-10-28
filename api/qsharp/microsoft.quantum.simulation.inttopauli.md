---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: Função IntToPauli
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: f0f1186f14a0dc30bb34bd29f148cdc830fd1337
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724850"
---
# <a name="inttopauli-function"></a>Função IntToPauli

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [](https://nuget.org/packages/)


Converte um inteiro para um operador pauli de um único qubit.

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a>Entrada

### <a name="idx--int"></a>idx : [Int](xref:microsoft.quantum.lang-ref.int)

Inteiro na gama `0..3` a converter para operadores Pauli.



## <a name="output--pauli"></a>Saída : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Um `Pauli` operador dado por `[PauliI, PauliX, PauliY, PauliZ][idx]` .