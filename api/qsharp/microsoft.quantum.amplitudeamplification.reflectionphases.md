---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: Tipo definido pelo utilizador ReflectionPhases
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: e0c7db6cd1aad636a34684958be117de1b9888f8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721815"
---
# <a name="reflectionphases-user-defined-type"></a>Tipo definido pelo utilizador ReflectionPhases

Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacote: [](https://nuget.org/packages/)


Fases para uma sequência de reflexos parciais na amplificação da amplitude.

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a>Itens nomeados

### <a name="aboutstart--double"></a>Sobre o Início: [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Uma série de fases para reflexão sobre o estado inicial.
### <a name="abouttarget--double"></a>Sobre oTarget : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Uma série de fases para reflexão sobre o estado alvo.

## <a name="remarks"></a>Observações

Ambas as matrizes devem ter o mesmo comprimento. Note que em muitos casos, a primeira fase sobre o estado de início e última fase sobre o estado-alvo introduz uma mudança de fase global e pode ser definida para $0$.