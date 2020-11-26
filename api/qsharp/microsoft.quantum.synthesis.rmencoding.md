---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: Função RMEncoding
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: a506ccb637b331a392ea75383c8bd605114af059
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202945"
---
# <a name="rmencoding-function"></a>Função RMEncoding

Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


{-1,1} codificação de um valor da verdade Boolean

```qsharp
function RMEncoding (b : Bool) : Int
```


## <a name="input"></a>Entrada

### <a name="b--bool"></a>b : [Bool](xref:microsoft.quantum.lang-ref.bool)

Valor booleano



## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

1, se `b` for falso, caso contrário -1