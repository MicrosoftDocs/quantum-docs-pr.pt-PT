---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: função _IdentityTimeDependentGeneratorSystem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 7b93a6674bec974e61496696a3d8403225b16d80
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225606"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a>função _IdentityTimeDependentGeneratorSystem

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve um sistema gerador consistente com o `H(s) = 0` Hamiltonian, onde está um parâmetro de `s` agenda.

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Entrada

### <a name="schedule--double"></a>horário : [Duplo](xref:microsoft.quantum.lang-ref.double)

Esta entrada é ignorada e definida para a consistência com o tipo definido pelo <xref:microsoft.quantum.canon.timedependentgeneratorsystem> utilizador.



## <a name="output--generatorsystem"></a>Saída : [Sistema Gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Um sistema gerador que representa a evolução sob o $H(s) Hamiltonian = 0$ para todos os $s$.