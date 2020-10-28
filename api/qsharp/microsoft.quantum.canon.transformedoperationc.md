---
uid: Microsoft.Quantum.Canon.TransformedOperationC
title: Função TransformedOperationC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationC
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: b6867a076b654337f6127657189a8453c9973cc2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715326"
---
# <a name="transformedoperationc-function"></a>Função TransformedOperationC

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Dada a função e uma operação, devolve uma nova operação cuja entrada é transformada pela função dada.

```qsharp
function TransformedOperationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl)) : ('U => Unit is Ctl)
```


## <a name="input"></a>Entrada

### <a name="fn--u---t"></a>fn : 'U -> 'T

Uma função que transforma a entrada dada num formulário esperado pela operação.


### <a name="op--t--unit-ctl"></a>op : 'T => [Unidade](xref:microsoft.quantum.lang-ref.unit) Ctl

A operação a ser transformada.



## <a name="output--u--unit-ctl"></a>Saída : 'U = unidade> [Ctl](xref:microsoft.quantum.lang-ref.unit)

Uma nova operação de tbat chama `fn` com a sua entrada e, em seguida, passa a saída resultante para `op` .

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T


### <a name="u"></a>'U



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [Microsoft.Quantum.Canon.TransformedOperationA](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [Microsoft.Quantum.Canon.TransformedOperationCA](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [Microsoft.Quantum.Canon.ApplyWithInputTransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft.Quantum.Canon.Composed](xref:Microsoft.Quantum.Canon.Composed)