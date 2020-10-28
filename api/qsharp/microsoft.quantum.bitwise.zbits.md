---
uid: Microsoft.Quantum.Bitwise.ZBits
title: Função ZBits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: f66b8ef0370e898dd1d095ff2840c91566f32cb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718534"
---
# <a name="zbits-function"></a>Função ZBits

Espaço de nome: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)

Pacote: [](https://nuget.org/packages/)


Devolve um inteiro que representa os bits Z de uma série de operadores Pauli.

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a>Entrada

### <a name="paulis--pauli"></a>paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Uma série de operadores pauli para ser representado como um inteiro.



## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

Um inteiro $x$ com representação binária $(p_ {62} \, p_ {61} \, \pontos \, p_0)$, onde $p_i = 0$ se for `paulis[i]` `PauliI` ou `PauliX` onde $p_i = 1$ se `paulis[i]` for ou `PauliY` `PauliZ` .

## <a name="remarks"></a>Observações

A função será lançada se o comprimento da matriz for superior a `paulis` 63.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Bitwise.XBits](xref:Microsoft.Quantum.Bitwise.XBits)