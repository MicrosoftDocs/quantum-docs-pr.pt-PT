---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: Função ControlledOnInt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 3cc5c00d9c7295106901149e06571ef1963d1323
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207263"
---
# <a name="controlledonint-function"></a>Função ControlledOnInt

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve um operador unitário que aplica um oráculo no registo-alvo se o estado do registo de controlo corresponder a um número inteiro positivo especificado.

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrada

### <a name="numberstate--int"></a>número Estado : [Int](xref:microsoft.quantum.lang-ref.int)

Inteiro positivo.


### <a name="oracle--t--unit--is-adj--ctl"></a>oráculo : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl

Operador unitário.



## <a name="output--qubitt--unit--is-adj--ctl"></a>Saída :[(Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) = [> Unidade](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl

Um operador unitário que se aplique `oracle` no registo-alvo se o estado do registo de controlo corresponder ao estado do número `numberState` .

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T



## <a name="remarks"></a>Observações

O valor `numberState` é interpretado usando uma codificação pouco endiana.