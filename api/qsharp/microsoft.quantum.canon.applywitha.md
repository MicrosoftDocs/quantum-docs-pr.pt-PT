---
uid: Microsoft.Quantum.Canon.ApplyWithA
title: Aplicação OperaçãoWithA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: b8847d4b3ddb88031ef360f183b86f6483706cc6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207875"
---
# <a name="applywitha-operation"></a>Aplicação OperaçãoWithA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tendo em conta duas operações, aplica-se uma como conjugada com a outra.

```qsharp
operation ApplyWithA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj), target : 'T) : Unit is Adj
```


## <a name="description"></a>Description

Tendo em conta duas operações, respectivamente descritas pelos operadores unitários $U$ e $V$, aplica-as na sequência $U^{\dagger} V U$. Ou seja, esta operação implementa o operador unitário dado por $V$ conjugado com $U$.

## <a name="input"></a>Entrada

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj

A operação $U$ que deve ser usada para conjugar $V dólares. Note que a operação exterior $U$ tem de ser adjacente, mas não precisa de ser controlável.


### <a name="inneroperation--t--unit--is-adj"></a>insuflação : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj

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
- [Microsoft.Quantum.Canon.ApplyWithC](xref:Microsoft.Quantum.Canon.ApplyWithC)
- [Microsoft.Quantum.Canon.ApplyWithCA](xref:Microsoft.Quantum.Canon.ApplyWithCA)