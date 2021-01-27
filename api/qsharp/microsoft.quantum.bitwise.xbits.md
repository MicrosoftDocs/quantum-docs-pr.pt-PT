---
uid: Microsoft.Quantum.Bitwise.XBits
title: Função XBits
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: ddaace8df6e4c47c4affe2eeffb8d8ce31f37327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845231"
---
# <a name="xbits-function"></a>Função XBits

Espaço de nome: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Devolve um inteiro que representa os X bits de uma série de operadores Pauli.

```qsharp
function XBits (paulis : Pauli[]) : Int
```


## <a name="input"></a>Entrada

### <a name="paulis--pauli"></a>paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Uma série de operadores pauli para ser representado como um inteiro.



## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

Um inteiro $x$ com representação binária $(p_ {62} \, p_ {61} \, \pontos \, p_0)$, onde $p_i = 0$ se for `paulis[i]` `PauliI` ou `PauliZ` onde $p_i = 1$ se `paulis[i]` for ou `PauliX` `PauliY` .

## <a name="remarks"></a>Observações

A função será lançada se o comprimento da matriz for superior a `paulis` 63.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Bitwise.ZBits](xref:Microsoft.Quantum.Bitwise.ZBits)