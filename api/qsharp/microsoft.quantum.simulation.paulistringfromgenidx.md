---
uid: Microsoft.Quantum.Simulation.PauliStringFromGenIdx
title: Função PauliStringFromGenIdx
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliStringFromGenIdx
qsharp.summary: Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 33da4bc3d7e58b87aef75b453b6af09a51214923
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710541"
---
# <a name="paulistringfromgenidx-function"></a>Função PauliStringFromGenIdx

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [](https://nuget.org/packages/)


Extrai a corda Pauli e os seus índices qubit de um termo Pauli descrito por um `GeneratorIndex` .

```qsharp
function PauliStringFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : (Pauli[], Int[])
```


## <a name="input"></a>Entrada

### <a name="generatorindex--generatorindex"></a>generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` tipo que codifica um termo Pauli.



## <a name="output--pauliint"></a>Saída :[(Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])

A cadeia Pauli do termo descrito por um `GeneratorIndex` , e índices para os qubits em que atua.