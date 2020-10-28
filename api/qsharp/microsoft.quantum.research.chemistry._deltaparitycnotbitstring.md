---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: função _DeltaParityCNOTbitstring
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 95b4c2df05f32cb937ec2cf421f43f2fdbf319da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710849"
---
# <a name="_deltaparitycnotbitstring-function"></a>função _DeltaParityCNOTbitstring

Espaço de nome: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)

Pacote: [](https://nuget.org/packages/)


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