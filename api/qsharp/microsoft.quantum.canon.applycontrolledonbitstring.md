---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: Aplicar operação ControlledOnBitString
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 82adc74e23e1d50cb6436176a973fdd1a0eeb3bd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841951"
---
# <a name="applycontrolledonbitstring-operation"></a>Aplicar operação ControlledOnBitString

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação unitária no registo-alvo, controlada num estado especificado por uma determinada máscara de bit.

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="bits--bool"></a>bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]

O fio da broca para controlar a operação unitária dada.


### <a name="oracle--t--unit--is-adj--ctl"></a>oráculo : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl

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

Por exemplo, `bits = [0,1,0,0,1]` significa que é aplicado se e `oracle` somente se estiver no estado `controlRegister` {0} $\ket {1} \ket {0} {0} {1} \ket \ket $.