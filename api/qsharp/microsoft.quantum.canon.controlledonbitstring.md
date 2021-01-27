---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: Função ControlledOnBitString
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: 176170cc972ca67b812b84f79cf97ba5418be9b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840809"
---
# <a name="controlledonbitstring-function"></a>Função ControlledOnBitString

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve uma operação unitária que aplica um oráculo no registo-alvo se o estado do registo de controlo corresponder a uma máscara de bits especificada.

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a>Descrição

A saída desta função é uma operação que pode ser representada por uma transformação unitária $U$ de tal forma que \start{align} U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{{b_0 b_1 \cdots b_{n-1}} \otimes \start{} ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\ \\ \ket{\psi} & \textrm{de outra forma} \end{cases}, \end{align} onde $V$ é uma transformação unitária que representa a ação da `oracle` operação.

## <a name="input"></a>Entrada

### <a name="bits--bool"></a>bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]

O fio da broca para controlar a operação unitária dada.


### <a name="oracle--t--unit--is-adj--ctl"></a>oráculo : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl

A operação unitária a aplicar no registo-alvo.



## <a name="output--qubitt--unit--is-adj--ctl"></a>Saída :[(Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) = [> Unidade](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl

Uma operação unitária que se aplica `oracle` no registo-alvo se o estado do registo de controlo corresponder à máscara de `bits` bits .

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T



## <a name="example"></a>Exemplo

Os seguintes fragmentos de código são equivalentes:

```qsharp
(ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
```

e

```qsharp
within {
    ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
} apply {
    Controlled oracle(controlRegister, targetRegister);
}
```

O seguinte código prepara um estado $\frac {1} {2} (\ket {00} - \ket {01} + \ket {10} + \ket + \ket {11} )$:

```qsharp
using (register = Qubit[2]) {
    ApplyToEach(H, register);
    (ControlledOnBitString([false], Z))(register[0..0], register[1]);
}
```

## <a name="remarks"></a>Observações

O padrão dado pode `bits` ser mais curto do `controlRegister` que, caso em que os qubits de controlo adicionais são ignorados (isto é, nem controlados em $\ket {0} $ nem $\ket {1} $).
Se `bits` for mais longo do que , um erro é `controlRegister` levantado.

Dada uma matriz `bits` Booleana e uma operação unitária, a saída desta `oracle` função é uma operação que executa os seguintes passos:

* Aplicar uma `X` operação a cada qubit do registo de controlo que corresponda ao `false` elemento `bits` do;
* aplicar-se `Controlled oracle` aos registos de controlo e de destino;
* aplicar uma `X` operação a cada qubit do registo de controlo que corresponda ao `false` elemento da nova volta para devolver o registo de controlo ao estado `bits` original.

A saída do `Controlled` functor é um caso especial de `ControlledOnBitString` onde é igual a `bits` `[true, ..., true]` .