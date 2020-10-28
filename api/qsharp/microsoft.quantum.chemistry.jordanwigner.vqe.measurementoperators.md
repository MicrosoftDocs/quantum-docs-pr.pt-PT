---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: Função Dos Operadores de Medição
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 24d752c4f198764b6e7c6ea6c49669c020c1a502
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713677"
---
# <a name="measurementoperators-function"></a>Função Dos Operadores de Medição

Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Pacote: [](https://nuget.org/packages/)


Calcula todos os operadores de medição necessários para calcular a expectativa de um termo Jordan-Wigner.

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a>Entrada

### <a name="nqubits--int"></a>nQubits : [Int](xref:microsoft.quantum.lang-ref.int)

O número de qubits necessários para simular o sistema molecular.


### <a name="indices--int"></a>índices : [Int](xref:microsoft.quantum.lang-ref.int)[]

É aplicada uma matriz contendo os índices do qubit a que cada operador Pauli é aplicado.


### <a name="termtype--int"></a>termoType : [Int](xref:microsoft.quantum.lang-ref.int)

O tipo de termo Jordan-Wigner.



## <a name="output--pauli"></a>Saída : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][ ]

Uma série de operadores de medição (cada um deles é um conjunto de Pauli).