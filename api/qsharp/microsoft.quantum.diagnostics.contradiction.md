---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Função de contradição
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: a5f3f26c5ada2eea9206699a2cc77575a9b5eebd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712865"
---
# <a name="contradiction-function"></a>Função de contradição

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [](https://nuget.org/packages/)


Declara que uma condição clássica é falsa.

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a>Entrada

### <a name="actual--bool"></a>real : [Bool](xref:microsoft.quantum.lang-ref.bool)

A condição a ser declarada.


### <a name="message--string"></a>mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)

Cadeia de mensagens de falha a ser impressa no caso de a condição clássica ser verdadeira.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Diagnostics.Fact](xref:Microsoft.Quantum.Diagnostics.Fact)