---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: Tipo definido pelo utilizador ReflectionPhases
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: fc3642b76c6e01f0709e78ea42c9ea7237389afa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847170"
---
# <a name="reflectionphases-user-defined-type"></a>Tipo definido pelo utilizador ReflectionPhases

Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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