---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: MedidaSStabilizer Operação deGeradores
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: 6c048c17df21d1026dc671f30d72a13ed8d8b7f5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200633"
---
# <a name="measurestabilizergenerators-operation"></a>MedidaSStabilizer Operação deGeradores

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Mede o conjunto de geradores de um grupo estabilizador.

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a>Entrada

### <a name="stabilizergroup--pauli"></a>stabilizerGroup : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]

Uma variedade de operadores de Pauli multiqubit.
Por exemplo, `stabilizerGroup[0]` é uma lista de matrizes Pauli de um único qubit, o produto tensor do qual é um gerador estabilizador.


### <a name="logicalregister--logicalregister"></a>LogicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Uma matriz de qubits onde o código estabilizador é definido.


### <a name="gadget--pauliqubit--__invalidresult__"></a>gadget :[(Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __inválidos <Result>__ 

Uma operação que especifica como medir um operador pauli multiqubit.



## <a name="output--syndrome"></a>Saída : [Síndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

O resultado das medições.

## <a name="remarks"></a>Observações

Isto não verifica se o conjunto de geradores está a deslocar-se.
Se não estiverem a deslocar-se, o resultado das medições pode ser arbitrário.