---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: Função EqualityFactR
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 2b293dc581ed58f7e3864a952fb3ecafa68e759c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712739"
---
# <a name="equalityfactr-function"></a>Função EqualityFactR

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [](https://nuget.org/packages/)


Afirma que uma variável de Resultado clássico tem o valor esperado.

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a>Entrada

### <a name="actual--__invalidresult__"></a>real : __inválido <Result>__

A variável a ser verificada.


### <a name="expected--__invalidresult__"></a>esperado : __inválido <Result>__

O valor esperado.


### <a name="message--string"></a>mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)

Cadeia de mensagem de falha a ser utilizada quando a afirmação é desencadeada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

