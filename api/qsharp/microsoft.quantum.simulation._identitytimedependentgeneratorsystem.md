---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: função _IdentityTimeDependentGeneratorSystem
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 960842f50353c01362f90eb38d979fb7c4f15d9a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857992"
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