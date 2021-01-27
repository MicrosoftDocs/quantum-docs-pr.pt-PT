---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: AplicarOperaçãoControlledOnInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 499a25104742b2d03886065baad4d535ea92e83b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845104"
---
# <a name="applycontrolledonint-operation"></a>AplicarOperaçãoControlledOnInt

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação unitária no registo-alvo se o estado do registo de controlo corresponder a um número inteiro positivo especificado.

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="numberstate--int"></a>número Estado : [Int](xref:microsoft.quantum.lang-ref.int)

Um inteiro não-alemão em que a operação `oracle` deve ser controlada.


### <a name="oracle--t--unit--is-adj--ctl"></a>oráculo : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl

Uma operação unitária a ser controlada.


### <a name="controlregister--qubit"></a>controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um registo quântico que controla a aplicação de `oracle` .


### <a name="targetregister--t"></a>targetRegister : 'T

Um registo sobre o qual se `oracle` candidatará.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T



## <a name="remarks"></a>Observações

O valor `numberState` é interpretado usando uma codificação pouco endiana.

`numberState` deve ser no máximo $2^\texttt{Comprimento (controlRegister)} - 1$.
Por exemplo, `numberState = 537` significa que é aplicado se e `oracle` somente se estiver no estado `controlRegister` $\ket {537} $.