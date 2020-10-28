---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: AplicarOperaçãoControlledOnInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: c8ea76946143967de4b6ac65986a1c4407ecb633
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718354"
---
# <a name="applycontrolledonint-operation"></a>AplicarOperaçãoControlledOnInt

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Aplica uma operação unitária no registo-alvo se o estado do registo de controlo corresponder a um número inteiro positivo especificado.

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a>Entrada

### <a name="numberstate--int"></a>número Estado : [Int](xref:microsoft.quantum.lang-ref.int)

Um inteiro não-alemão em que a operação `oracle` deve ser controlada.


### <a name="oracle--t--unit-adj--ctl"></a>oráculo : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit)> Adj + Ctl

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