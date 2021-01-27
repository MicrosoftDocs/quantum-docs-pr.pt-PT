---
uid: Microsoft.Quantum.Preparation.MixedStatePreparation
title: MixedStatePreparation user type
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: MixedStatePreparation
qsharp.summary: Represents a particular mixed state that can be prepared on an index and a garbage register.
ms.openlocfilehash: 7e5b6ca755aac19a31b7e27e32e934bb823b128e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842410"
---
# <a name="mixedstatepreparation-user-defined-type"></a>MixedStatePreparation user type

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa um estado misto particular que pode ser preparado num índice e num registo de lixo.

```qsharp

newtype MixedStatePreparation = (Requirements : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements, Norm : Double, Prepare : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Itens nomeados

### <a name="requirements--mixedstatepreparationrequirements"></a>Requisitos : [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)


### <a name="norm--double"></a>Norma : [Duplo](xref:microsoft.quantum.lang-ref.double)


### <a name="prepare--littleendianqubitqubit--unit--is-adj--ctl"></a>Prepare:[(LittleEndian,](xref:Microsoft.Quantum.Arithmetic.LittleEndian)[Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = [> Unit](xref:microsoft.quantum.lang-ref.unit) é Adj + Ctl



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.PurifiedMixedState](xref:Microsoft.Quantum.PurifiedMixedState)