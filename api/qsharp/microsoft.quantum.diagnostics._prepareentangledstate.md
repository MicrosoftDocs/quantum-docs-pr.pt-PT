---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: operação _prepareEntangledState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 97a55b4bb85095c7d8e8432dfcd1c6d6f7e93cdc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223940"
---
# <a name="_prepareentangledstate-operation"></a>operação _prepareEntangledState

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Tendo em conta dois registos, prepara o estado máximo emaranhado entre cada par de qubits nos respetivos registos.
Todos os qubits devem começar no estado de 0⟩.

O resultado é que os pares correspondentes de qubits de cada registo estão no $\bra{\beta_ {00} }\ket{\beta_ {00} }$.

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="left--qubit"></a>esquerda : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um qubit array no estado $\ket{0\cdots 0}$


### <a name="right--qubit"></a>direita: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um qubit array no estado $\ket{0\cdots 0}$



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

