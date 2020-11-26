---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: Função PauliArrayAsInt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: 6077110cc07c8626b22eb404c1de096ed43efcc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224246"
---
# <a name="pauliarrayasint-function"></a>Função PauliArrayAsInt

Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Codifica um operador pauli multi-qubit representado como uma matriz de operadores pauli de um único qubit em um inteiro.

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a>Entrada

### <a name="paulis--pauli"></a>paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Uma série de, no máximo, 31 operadores de Pauli de um único qubit.



## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

Um inteiro identificando `paulis` exclusivamente, como descrito abaixo.

## <a name="remarks"></a>Observações

Cada operador Pauli pode ser codificado usando dois bits: $$ \start{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.
\end{align} $$

Dada uma série de operadores `[P0, ..., Pn]` Pauli, esta função devolve um inteiro com expansão binária formada pela concatenação dos mapeamentos de cada operador Pauli em ordem de grande `bits(Pn) ... bits(P0)` ponta.