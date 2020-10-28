---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: Aplicação Operação Deposição
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 1bd6f9580e09752f1de75927d6bb35417bb1ff21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725259"
---
# <a name="applytransposition-operation"></a>Aplicação Operação Deposição

Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacote: [](https://nuget.org/packages/)




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
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

