---
title: Conversões de tipo nas Q# bibliotecas padrão
description: Saiba mais sobre funções comuns e definidas pelo utilizador nas Q# bibliotecas padrão.
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: 67f47339363a52097f342c8ae4e43a8a93d606a8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858029"
---
# <a name="type-conversions"></a>Conversões de tipo #

Q#é uma linguagem **fortemente dactilografada.**
Em particular, Q# não é implicitamente lançado entre tipos distintos. Por exemplo, `1 + 2.0` não é uma expressão Q# válida.
Em vez disso, Q# fornece uma variedade de funções de conversão de tipo para a construção de novos valores de um determinado tipo.

Por exemplo, <xref:Microsoft.Quantum.Core.Length> tem um tipo de saída de , por isso a sua saída deve primeiro ser convertida para um `Int` antes de poder ser usada como parte de uma expressão de ponto `Double` flutuante.
Isto pode ser feito utilizando a <xref:Microsoft.Quantum.Convert.IntAsDouble> função:

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

O <xref:Microsoft.Quantum.Convert> espaço de nomes fornece funções comuns de conversão de tipo para trabalhar com os tipos básicos incorporados, tais `Int` como, e `Double` `BigInt` `Result` `Bool` :

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

O <xref:Microsoft.Quantum.Convert> espaço de nome também fornece algumas conversões mais exóticas, como, por `FunctionAsOperation` exemplo, que converte funções `'T -> 'U` em novas operações. `'T => 'U`

Finalmente, a Q# biblioteca padrão fornece uma série de tipos definidos pelo utilizador, tais como <xref:Microsoft.Quantum.Math.Complex> <xref:Microsoft.Quantum.Arithmetic.LittleEndian> .
Juntamente com estes tipos, a biblioteca padrão fornece funções <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian> como:

```qsharp
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
