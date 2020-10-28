---
uid: Microsoft.Quantum.Intrinsic.Message
title: Função de mensagem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 0428a46bc639bc8a0697f5bd392f85b8b9f40ee5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711423"
---
# <a name="message-function"></a>Função de mensagem

Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)

Pacote: [](https://nuget.org/packages/)


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