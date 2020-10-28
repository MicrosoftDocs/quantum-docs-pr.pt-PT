---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: Preparar Operação Estado DeEnangled
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 299d586f7581acdecf22da2f6bbfbb8d45f372f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722176"
---
# <a name="prepareentangledstate-operation"></a>Preparar Operação Estado DeEnangled

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [](https://nuget.org/packages/)


Em pares envolve dois registos qubit.

Ou seja, tendo em conta dois registos, prepara o estado máximo emaranhado $\frac {1} {\sqrt {2} } \left(\ket {00} + \ket {11} \right)$ entre cada par de qubits nos respetivos registos, assumindo que cada registo começa no estado $\ket{0\cdots 0}$

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="left--qubit"></a>esquerda : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um qubit array no estado $\ket{0\cdots 0}$


### <a name="right--qubit"></a>direita: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um qubit array no estado $\ket{0\cdots 0}$



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

