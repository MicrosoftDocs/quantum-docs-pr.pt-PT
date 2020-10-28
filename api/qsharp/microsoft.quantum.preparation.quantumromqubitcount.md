---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: Função QuantumROMQubitCount
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: 988d5efa3e27cf5e9a276ab3ab443c10f88fe1ad
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722932"
---
# <a name="quantumromqubitcount-function"></a>Função QuantumROMQubitCount

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [](https://nuget.org/packages/)


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