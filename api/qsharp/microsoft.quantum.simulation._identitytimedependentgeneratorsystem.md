---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: função _IdentityTimeDependentGeneratorSystem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 0b440ce9adaab562e16b02da46844c68a7470b11
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710692"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a>função _IdentityTimeDependentGeneratorSystem

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [](https://nuget.org/packages/)


Devolve um sistema gerador consistente com o `H(s) = 0` Hamiltonian, onde está um parâmetro de `s` agenda.

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Entrada

### <a name="schedule--double"></a>horário : [Duplo](xref:microsoft.quantum.lang-ref.double)

Esta entrada é ignorada e definida para a consistência com o tipo definido pelo <xref:microsoft.quantum.canon.timedependentgeneratorsystem> utilizador.



## <a name="output--generatorsystem"></a>Saída : [Sistema Gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Um sistema gerador que representa a evolução sob o $H(s) Hamiltonian = 0$ para todos os $s$.