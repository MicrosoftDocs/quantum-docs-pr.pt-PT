---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: Função BoolArrayAsPauli
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c5ef71322dae248fc2c6b1db3adf891de7d72488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713604"
---
# <a name="boolarrayaspauli-function"></a>Função BoolArrayAsPauli

Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)

Pacote: [](https://nuget.org/packages/)


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