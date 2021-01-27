---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: Função RMEncoding
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: f3c54d2e40511dacb21618b4eaf1eef9f4903f9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855334"
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