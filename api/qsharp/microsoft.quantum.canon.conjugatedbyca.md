---
uid: Microsoft.Quantum.Canon.ConjugatedByCA
title: Função ConjugatedByCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByCA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: 54301f991d3bda14e2d2a0a6837ee89d299f2e04
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840820"
---
# <a name="conjugatedbyca-function"></a>Função ConjugatedByCA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dadas as operações exteriores e interiores, devolve uma nova operação que conjuga a operação interna pela operação exterior.

```qsharp
function ConjugatedByCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl)) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrada

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj

A operação $U$ que deve ser usada para conjugar $V dólares. Note que a operação exterior $U$ tem de ser adjacente, mas não precisa de ser controlável.


### <a name="inneroperation--t--unit--is-adj--ctl"></a>insuflação : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl

A operação $V dólares a ser conjugada.



## <a name="output--t--unit--is-adj--ctl"></a>Saída : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl

Uma nova operação cuja ação é representada pelo $U^{\dagger} V U$.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de alvo em que cada uma das operações internas e exteriores atuam.

## <a name="remarks"></a>Observações

Presume-se sempre que a operação exterior é contígua, mas não é necessário controlável para que a operação combinada seja controlável.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.conjugatedBya](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [Microsoft.Quantum.Canon.ConjugatedByC](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [Microsoft.Quantum.Canon.ConjugatedByCA](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [Microsoft.Quantum.Canon.ApplyWith](xref:Microsoft.Quantum.Canon.ApplyWith)