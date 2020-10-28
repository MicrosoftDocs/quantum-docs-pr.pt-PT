---
uid: Microsoft.Quantum.Canon.ConjugatedBy
title: Função ConjugatedBy
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedBy
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: 37fbee9a7c11991645933a372f9f12c1fd696b66
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716474"
---
# <a name="conjugatedby-function"></a>Função ConjugatedBy

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Dadas as operações exteriores e interiores, devolve uma nova operação que conjuga a operação interna pela operação exterior.

```qsharp
function ConjugatedBy<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit)) : ('T => Unit)
```


## <a name="input"></a>Entrada

### <a name="outeroperation--t--unit-adj"></a>outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj

A operação $U$ que deve ser usada para conjugar $V dólares. Note que a operação exterior $U$ tem de ser adjacente, mas não precisa de ser controlável.


### <a name="inneroperation--t--unit"></a>inoperação interior : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

A operação $V dólares a ser conjugada.



## <a name="output--t--unit"></a>Saída : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

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