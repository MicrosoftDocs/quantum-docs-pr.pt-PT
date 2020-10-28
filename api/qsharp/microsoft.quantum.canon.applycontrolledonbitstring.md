---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: Aplicar operação ControlledOnBitString
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 7a054511bacff574e6f7e889ace048c78886cf91
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718355"
---
# <a name="applycontrolledonbitstring-operation"></a>Aplicar operação ControlledOnBitString

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Aplica uma operação unitária no registo-alvo, controlada num estado especificado por uma determinada máscara de bit.

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a>Entrada

### <a name="bits--bool"></a>bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]

O fio da broca para controlar a operação unitária dada.


### <a name="oracle--t--unit-adj--ctl"></a>oráculo : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit)> Adj + Ctl

A operação unitária a aplicar no registo-alvo.


### <a name="controlregister--qubit"></a>controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um registo quântico que controla a aplicação de `oracle` .


### <a name="targetregister--t"></a>targetRegister : 'T

O registo-alvo a ser passado `oracle` como entrada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T



## <a name="remarks"></a>Observações

O padrão dado pode `bits` ser mais curto do `controlRegister` que, caso em que os qubits de controlo adicionais são ignorados (isto é, nem controlados em $\ket {0} $ nem $\ket {1} $).
Se `bits` for mais longo do que , um erro é `controlRegister` levantado.

Por exemplo, `bits = [0,1,0,0,1]` significa que é aplicado se e `oracle` somente se estiver no estado `controlRegister` {0} $\ket {1} \ket {0} \ket {0} \ket \ket {1} \ket \ket $.