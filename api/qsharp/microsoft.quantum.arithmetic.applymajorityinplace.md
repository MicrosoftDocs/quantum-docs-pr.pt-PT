---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: AplicarMajorityInPlace
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 3664ffe96cd1db8cf5e8898387fe7f2d45b4ea98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721595"
---
# <a name="applymajorityinplace-operation"></a>AplicarMajorityInPlace

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


Aplica a operação por maioria de três qubits no local num registo de qubits.

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit
```


## <a name="description"></a>Descrição

Esta operação calcula a função maioritária no local em 3 qubits.

Se denotarmos o qubit de saída como $z$ e qubits de entrada como $x$ e $y$, a operação executa a seguinte transformação: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\\\operatorname{MAJ} (x, y, z)}.

## <a name="input"></a>Entrada

### <a name="output--qubit"></a>saída : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Primeiro qubit de entrada. Note que a saída é calculada no local e armazenada neste qubit.


### <a name="input--qubit"></a>entrada : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Segundo e terceiro qubits de entrada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

