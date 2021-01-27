---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: AplicarMajorityInPlace
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 10b512392b2098663c09b2e07a09c4025da90706
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843734"
---
# <a name="applymajorityinplace-operation"></a>AplicarMajorityInPlace

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica a operação por maioria de três qubits no local num registo de qubits.

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrição

Esta operação calcula a função maioritária no local em 3 qubits.

Se denotarmos o qubit de saída como $z$ e qubits de entrada como $x$ e $y$, a operação executa a seguinte transformação: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}.

## <a name="input"></a>Entrada

### <a name="output--qubit"></a>saída : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Primeiro qubit de entrada. Note que a saída é calculada no local e armazenada neste qubit.


### <a name="input--qubit"></a>entrada : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Segundo e terceiro qubits de entrada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

