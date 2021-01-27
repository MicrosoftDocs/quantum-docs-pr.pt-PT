---
uid: Microsoft.Quantum.Canon.ApplyWithCA
title: Aplicação De operaçãoWithCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithCA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: a5ce7dc5ddfbb2fc06743d36614129c371850da2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841152"
---
# <a name="applywithca-operation"></a>Aplicação De operaçãoWithCA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tendo em conta duas operações, aplica-se uma como conjugada com a outra.

```qsharp
operation ApplyWithCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl), target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrição

Tendo em conta duas operações, respectivamente descritas pelos operadores unitários $U$ e $V$, aplica-as na sequência $U^{\dagger} V U$. Ou seja, esta operação implementa o operador unitário dado por $V$ conjugado com $U$.

## <a name="input"></a>Entrada

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj

A operação $U$ que deve ser usada para conjugar $V dólares. Note que a operação exterior $U$ tem de ser adjacente, mas não precisa de ser controlável.


### <a name="inneroperation--t--unit--is-adj--ctl"></a>insuflação : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl

A operação $V dólares a ser conjugada.


### <a name="target--t"></a>alvo : 'T

A entrada a fornecer às operações exteriores e internas.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O alvo em que cada uma das operações internas e exteriores atuam.

## <a name="remarks"></a>Observações

Presume-se sempre que a operação exterior é contígua, mas não é necessário controlável para que a operação combinada seja controlável.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyWith](xref:Microsoft.Quantum.Canon.ApplyWith)
- [Microsoft.Quantum.Canon.ApplyWithA](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [Microsoft.Quantum.Canon.ApplyWithC](xref:Microsoft.Quantum.Canon.ApplyWithC)