---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: b7d37b5115c51596c1b3ed93c53a29e9f36b811d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829150"
---
# <a name="equalityfactl-function"></a>EqualityFactL

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Afirma que uma variável clássica bigint tem o valor esperado.

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a>Entrada

### <a name="actual--bigint"></a>real : [BigInt](xref:microsoft.quantum.lang-ref.bigint)

O número a ser verificado.


### <a name="expected--bigint"></a>esperado : [BigInt](xref:microsoft.quantum.lang-ref.bigint)

O valor esperado.


### <a name="message--string"></a>mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)

Cadeia de mensagem de falha a ser utilizada quando a afirmação é desencadeada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

