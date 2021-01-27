---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: Função QuantumROMQubitCount
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: >-
  > [!WARNING]

  > QuantumROMQubitCount has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.


  Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: d6eac64eb62ec7a88d3231249b0bb1e05818f6e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856801"
---
# <a name="quantumromqubitcount-function"></a>Função QuantumROMQubitCount

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> QuantumROMQubitCount foi depreciado. Por favor, use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> em vez disso.

Devolve o número total de qubits que devem ser atribuídos à operação devolvido por `QuantumROM` .

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a>Entrada

### <a name="targeterror--double"></a>targetError : [Duplo](xref:microsoft.quantum.lang-ref.double)

O erro do alvo $\epsilon$.


### <a name="ncoeffs--int"></a>nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)

Número de coeficientes especificados em `QuantumROM` .



## <a name="output--intintint"></a>Saída : ([Int](xref:microsoft.quantum.lang-ref.int)[(Int](xref:microsoft.quantum.lang-ref.int),[Int))](xref:microsoft.quantum.lang-ref.int)

## <a name="first-parameter"></a>Primeiro parâmetro

Um tuple `(x,(y,z))` onde está o número total de `x = y + z` qubits atribuídos, `y` é o número de qubits para o `LittleEndian` registo, e é o número de `z` qubits de lixo.