---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: Função ControlledOnBitString
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: ca5a6e116eff187060f7a160e42836b170f0362d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716446"
---
# <a name="controlledonbitstring-function"></a>Função ControlledOnBitString

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Devolve uma operação unitária que aplica um oráculo no registo-alvo se o estado do registo de controlo corresponder a uma máscara de bits especificada.

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a>Descrição

A saída desta função é uma operação que pode ser representada por uma transformação unitária $U$ de tal forma que \start{align} U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{{{{{{b_0 b_1 \cdots b_{n-1}} \otimes \start{} ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\ \\ \ket{\psi} & \textrm{de outra forma} \end{cases}, \end{align} onde $V$ é uma transformação unitária que representa a ação da `oracle` operação.

## <a name="input"></a>Entrada

### <a name="bits--bool"></a>bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]

O fio da broca para controlar a operação unitária dada.


### <a name="oracle--t--unit-adj--ctl"></a>oráculo : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit)> Adj + Ctl

A operação unitária a aplicar no registo-alvo.



## <a name="output--qubitt--unit-adj--ctl"></a>Saída :[(Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl

Uma operação unitária que se aplica `oracle` no registo-alvo se o estado do registo de controlo corresponder à máscara de `bits` bits .

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T



## <a name="remarks"></a>Observações

O padrão dado pode `bits` ser mais curto do `controlRegister` que, caso em que os qubits de controlo adicionais são ignorados (isto é, nem controlados em $\ket {0} $ nem $\ket {1} $).
Se `bits` for mais longo do que , um erro é `controlRegister` levantado.

Dada uma matriz `bits` Booleana e uma operação unitária, a saída desta `oracle` função é uma operação que executa os seguintes passos:

* Aplicar uma `X` operação a cada qubit do registo de controlo que corresponda ao `false` elemento `bits` do;
* aplicar-se `Controlled oracle` aos registos de controlo e de destino;
* aplicar uma `X` operação a cada qubit do registo de controlo que corresponda ao `false` elemento da nova volta para devolver o registo de controlo ao estado `bits` original.

A saída do `Controlled` functor é um caso especial de `ControlledOnBitString` onde é igual a `bits` `[true, ..., true]` .