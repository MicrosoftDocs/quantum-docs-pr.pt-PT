---
uid: Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
title: MixedStatePreparationRequirements tipo definido pelo utilizador
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: MixedStatePreparationRequirements
qsharp.summary: Represents the number of qubits required in order to prepare a given mixed state.
ms.openlocfilehash: 3ea4757f6aa5125418b1e81db9f32e7b668eb359
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228700"
---
# <a name="mixedstatepreparationrequirements-user-defined-type"></a>MixedStatePreparationRequirements tipo definido pelo utilizador

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa o número de qubits necessários para preparar um determinado estado misto.

```qsharp

newtype MixedStatePreparationRequirements = (NTotalQubits : Int, (NIndexQubits : Int, NGarbageQubits : Int));
```



## <a name="named-items"></a>Itens nomeados

### <a name="ntotalqubits--int"></a>NTotalQubits : [Int](xref:microsoft.quantum.lang-ref.int)


### <a name="nindexqubits--int"></a>NIndexQubits : [Int](xref:microsoft.quantum.lang-ref.int)


### <a name="ngarbagequbits--int"></a>NGarbageQubits : [Int](xref:microsoft.quantum.lang-ref.int)



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.PurifiedMixedState](xref:Microsoft.Quantum.PurifiedMixedState)