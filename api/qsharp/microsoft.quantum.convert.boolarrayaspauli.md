---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: Função BoolArrayAsPauli
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: 8e7088ec3918165d7b2afb1056a8319c6fb17796
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214284"
---
# <a name="boolarrayaspauli-function"></a>Função BoolArrayAsPauli

Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dado um pouco de corda, devolve um operador pauli multi-qubit representado como uma variedade de operadores pauli de um único qubit.

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a>Entrada

### <a name="pauli--pauli"></a>pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Operador Pauli para aplicar aos qubits onde `bitsApply == bits[idx]` .


### <a name="bitapply--bool"></a>bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)

aplicar Pauli se bit é este valor.


### <a name="bits--bool"></a>bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]

Matriz booleana.



## <a name="output--pauli"></a>Saída : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]



## <a name="remarks"></a>Observações

A matriz booleana e o registo quântico devem ter o mesmo comprimento.