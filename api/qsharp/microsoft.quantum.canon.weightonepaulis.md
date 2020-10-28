---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: Função WeightOnePaulis
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 89802c1bc6f3da8edef27b698eb61098e47dfc85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715200"
---
# <a name="weightonepaulis-function"></a>Função WeightOnePaulis

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Devolve uma série de todos os operadores de Peso-1 Pauli num dado número de qubits.

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a>Entrada

### <a name="nqubits--int"></a>nQubits : [Int](xref:microsoft.quantum.lang-ref.int)

O número de qubits em que os operadores pauli devolvidos são definidos.



## <a name="output--pauli"></a>Saída : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][ ]

Uma matriz de operadores pauli multi-qubit, cada um dos quais é representado como uma matriz com comprimento `nQubits` .