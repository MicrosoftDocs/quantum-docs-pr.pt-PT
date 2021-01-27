---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: função _DeltaParityCNOTbitstring
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 3dd2d299a094577d377780d731e76287815e8d03
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847610"
---
# <a name="_deltaparitycnotbitstring-function"></a>função _DeltaParityCNOTbitstring

Espaço de nome: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)

Pacote: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


Passo de processamento clássico de `ApplyDeltaParity` .
Isto calcula uma lista de qubits de controlo para avaliar a diferença de paridade entre dois PQRS... termos de mesmo comprimento.

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a>Entrada

### <a name="prevfermionicterm--int"></a>prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="nextfermionicterm--int"></a>nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--intbool"></a>Saída :[(Int,](xref:microsoft.quantum.lang-ref.int)[Bool](xref:microsoft.quantum.lang-ref.bool)[])



## <a name="remarks"></a>Observações

Isto pressupõe que a duração dos termos é par.
Lista de controlos de cálculo para diferença de paridade entre dois termos.
Isto pressupõe que as listas de entradas estão ordenadas por ordem ascendente.