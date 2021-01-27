---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: Função EqualityFactCP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: a207ba1c4d08ec58095f5db34ee32c7341002920
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829179"
---
# <a name="equalityfactcp-function"></a>Função EqualityFactCP

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Afirma que um número complexo tem o valor esperado.

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a>Entrada

### <a name="actual--complexpolar"></a>real : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

O valor a ser verificado.


### <a name="expected--complexpolar"></a>esperado : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

O valor esperado.


### <a name="message--string"></a>mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)

Cadeia de mensagem de falha a ser utilizada quando a afirmação é desencadeada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

