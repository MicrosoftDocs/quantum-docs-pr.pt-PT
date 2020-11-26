---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: Preparar Operação Estado DeEnangled
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 5f6e3ea1e7638d3bc446f21ace2968cf8284353a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210476"
---
# <a name="prepareentangledstate-operation"></a>Preparar Operação Estado DeEnangled

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Em pares envolve dois registos qubit.

Ou seja, tendo em conta dois registos, prepara o estado máximo emaranhado $\frac {1} {\sqrt {2} } \left(\ket {00} + \ket {11} \right)$ entre cada par de qubits nos respetivos registos, assumindo que cada registo começa no estado $\ket{0\cdots 0}$

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="left--qubit"></a>esquerda : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um qubit array no estado $\ket{0\cdots 0}$


### <a name="right--qubit"></a>direita: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um qubit array no estado $\ket{0\cdots 0}$



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

