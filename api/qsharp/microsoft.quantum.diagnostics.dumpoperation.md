---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: Operação DumpOperation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: b0e07173ddbeb8a96d4a85928258b6e30deb394d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202061"
---
# <a name="dumpoperation-operation"></a>Operação DumpOperation

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada uma operação, apresenta diagnósticos sobre a operação que são disponibilizados pelo alvo de execução atual.

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Entrada

### <a name="nqubits--int"></a>nQubits : [Int](xref:microsoft.quantum.lang-ref.int)

O número de qubits em que a determinada operação atua.


### <a name="op--qubit--unit--is-adj"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj

A operação que deve ser diagnosticada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Chamar esta operação não tem nenhum efeito observável dentro de Q#. Os diagnósticos exatos que são apresentados, se houver, dependem do atual objetivo de execução e do ambiente de editor.
Por exemplo, quando utilizado no simulador quântico de estado inteiro, é apresentada uma matriz unitária utilizada para `op` representar.

Note que, quando executados em simuladores que admitem uma ambiguidade de fase global (por exemplo: o simulador de estado completo), as representações devolvidas podem variar até uma fase global.

Da mesma forma, a ordenação de representações matricias de linhas e colunas pode variar com as convenções utilizadas por cada simulador que suporta esta operação.