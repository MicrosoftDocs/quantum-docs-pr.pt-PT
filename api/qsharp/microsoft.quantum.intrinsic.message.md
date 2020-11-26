---
uid: Microsoft.Quantum.Intrinsic.Message
title: Função de mensagem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 4eb55dd4fd8d78e4b5a9bb289dacfbdb3aa4beb8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199017"
---
# <a name="message-function"></a>Função de mensagem

Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Regista uma mensagem.

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a>Entrada

### <a name="msg--string"></a>msg : [Corda](xref:microsoft.quantum.lang-ref.string)

A mensagem a ser reportada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

O comportamento específico desta função é dependente do simulador, mas na maioria dos casos a mensagem dada será escrita para a consola.