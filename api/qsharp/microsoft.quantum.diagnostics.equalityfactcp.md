---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: Função EqualityFactCP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 1ea790debb5a9123fb8bee3a5f8a1fde0a050b37
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712767"
---
# <a name="equalityfactcp-function"></a>Função EqualityFactCP

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [](https://nuget.org/packages/)


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

