---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: Aplicação Operação Deposição
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 46cf8c2c891aa02b0d8a1397e6c2b7a4b8618048
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855567"
---
# <a name="applytransposition-operation"></a>Aplicação Operação Deposição

Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrição

Esta operação troca a amplitude em índice `a` com a amplitude no índice no dado `b` estado-vector `register` de comprimento $n$.  Se `a` for `b` igual, o vetor do estado não é alterado.

## <a name="input"></a>Entrada

### <a name="a--int"></a>a : [Int](xref:microsoft.quantum.lang-ref.int)

Primeiro índice (deve ser um valor de 0 a $2^n - 1$)


### <a name="b--int"></a>b : [Int](xref:microsoft.quantum.lang-ref.int)

Segundo índice (deve ser um valor de 0 a $2^n - 1$)


### <a name="qubits--littleendian"></a>qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Uma lista de $n$ qubits aos quais a transposição é aplicada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Exemplo

Prepare uma superposição uniforme dos estados de número $|1\rangle$, $|2\rangle$, e $|3\rangle$ em 2 qubits.

```qsharp
using (qubits = Qubit[2]) {
  let register = LittleEndian(qubits);
  PrepareUniformSuperposition(3, register);
  ApplyTransposition(0, 3, register);
}
```