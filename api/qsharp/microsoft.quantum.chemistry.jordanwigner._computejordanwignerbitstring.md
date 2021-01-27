---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: função _ComputeJordanWignerBitString
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 82b5e433f79c93c640b89e6365e5f468bacd892e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839533"
---
# <a name="_computejordanwignerbitstring-function"></a>função _ComputeJordanWignerBitString

Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Computes Z componente da cadeia Jordan-Wigner entre índices de fermiion em um operador fermiónico com um número par de operadores de criação/aniquilação.

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a>Entrada

### <a name="nfermions--int"></a>nFermions : [Int](xref:microsoft.quantum.lang-ref.int)

O Número de fermiões no sistema.


### <a name="idxfermions--int"></a>idxFermions : [Int](xref:microsoft.quantum.lang-ref.int)[]

índices de operador fermiónico.



## <a name="output--bool"></a>Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)[]

Mordendo `Bool[]` é `true` onde um `PauliZ` deve ser aplicado.

## <a name="example"></a>Exemplo

deixe o bitString = _ComputeJordanWignerBitString(6, [0,1,2,6]; bitString é [falso, falso, falso ,verdadeiro, verdadeiro, verdadeiro, falso].