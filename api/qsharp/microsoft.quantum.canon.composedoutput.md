---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: Função Compostaoutput
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 7e361a62679ab93e9a0ebc04fa52be193805c78d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207467"
---
# <a name="composedoutput-function"></a>Função Compostaoutput

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve a saída da composição `inner` de e para uma dada `outer` entrada.

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a>Entrada

### <a name="outer--u---v"></a>exterior : 'U -> 'V




### <a name="inner--t---u"></a>interior : 'T-> 'U




### <a name="target--t"></a>alvo : 'T





## <a name="output--v"></a>Saída : 'V



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T


### <a name="u"></a>'U


### <a name="v"></a>'V

