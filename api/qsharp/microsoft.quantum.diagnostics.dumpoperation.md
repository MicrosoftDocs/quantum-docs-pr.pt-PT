---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: Operação DumpOperation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: 444d42e2440b30b3bdf50d55a399568bed063222
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712862"
---
# <a name="dumpoperation-operation"></a>Operação DumpOperation

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [](https://nuget.org/packages/)


Dada uma operação, apresenta diagnósticos sobre a operação que são disponibilizados pelo alvo de execução atual.

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Entrada

### <a name="nqubits--int"></a>nQubits : [Int](xref:microsoft.quantum.lang-ref.int)

O número de qubits em que a determinada operação atua.


### <a name="op--qubit--unit-adj"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj

A operação que deve ser diagnosticada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Chamar esta operação não tem nenhum efeito observável dentro de Q#. Os diagnósticos exatos que são apresentados, se houver, dependem do atual objetivo de execução e do ambiente de editor.
Por exemplo, quando utilizado no simulador quântico de estado inteiro, é apresentada uma matriz unitária utilizada para `op` representar.

Note que, quando executados em simuladores que admitem uma ambiguidade de fase global (por exemplo: o simulador de estado completo), as representações devolvidas podem variar até uma fase global.

Da mesma forma, a ordenação de representações matricias de linhas e colunas pode variar com as convenções utilizadas por cada simulador que suporta esta operação.