---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Função de contradição
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: 7d62c9341b768dfdfbfbf8e73e64748f04317595
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829370"
---
# <a name="contradiction-function"></a>Função de contradição

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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



## <a name="example"></a>Exemplo

O seguinte código Q# imprimirá "Olá, mundo":

```qsharp
Contradiction(2 == 3, "2 is not equal to 3.");
Message("Hello, world.");
```

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Diagnostics.Fact](xref:Microsoft.Quantum.Diagnostics.Fact)