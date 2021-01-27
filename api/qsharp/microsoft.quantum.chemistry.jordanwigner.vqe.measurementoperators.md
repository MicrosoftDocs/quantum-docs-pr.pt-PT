---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: Função Dos Operadores de Medição
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 204ae621b77559a894f0bce14e494824d58e4ad6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835406"
---
# <a name="measurementoperators-function"></a>Função Dos Operadores de Medição

Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


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