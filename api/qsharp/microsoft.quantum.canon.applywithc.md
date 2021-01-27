---
uid: Microsoft.Quantum.Canon.ApplyWithC
title: Aplicação DeC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithC
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: 393db9f8ce092100abc157ace1ee9fbbb3b06d24
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850395"
---
# <a name="applywithc-operation"></a>Aplicação DeC

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tendo em conta duas operações, aplica-se uma como conjugada com a outra.

```qsharp
operation ApplyWithC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl), target : 'T) : Unit is Ctl
```


## <a name="description"></a>Descrição

Tendo em conta duas operações, respectivamente descritas pelos operadores unitários $U$ e $V$, aplica-as na sequência $U^{\dagger} V U$. Ou seja, esta operação implementa o operador unitário dado por $V$ conjugado com $U$.

## <a name="input"></a>Entrada

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj

A operação $U$ que deve ser usada para conjugar $V dólares. Note que a operação exterior $U$ tem de ser adjacente, mas não precisa de ser controlável.


### <a name="inneroperation--t--unit--is-ctl"></a>insuflação : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é CTL

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
- [Microsoft.Quantum.Canon.ApplyWithCA](xref:Microsoft.Quantum.Canon.ApplyWithCA)