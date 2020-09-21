---
title: Conversões de tipo nas Q# bibliotecas padrão
description: Saiba mais sobre funções comuns e definidas pelo utilizador nas Q# bibliotecas padrão.
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: aa8a1ad624067906998d2735c7a95174a163ce97
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835609"
---
# <a name="type-conversions"></a>Conversões de tipo #

Q#é uma linguagem **fortemente dactilografada.**
Em particular, Q# não é implicitamente lançado entre tipos distintos. Por exemplo, `1 + 2.0` não é uma expressão Q# válida.
Em vez disso, Q# fornece uma variedade de funções de conversão de tipo para a construção de novos valores de um determinado tipo.

Por exemplo, <xref:microsoft.quantum.core.length> tem um tipo de saída de , por isso a sua saída deve primeiro ser convertida para um `Int` antes de poder ser usada como parte de uma expressão de ponto `Double` flutuante.
Isto pode ser feito utilizando a <xref:microsoft.quantum.convert.intasdouble> função:

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

O <xref:microsoft.quantum.convert> espaço de nomes fornece funções comuns de conversão de tipo para trabalhar com os tipos básicos incorporados, tais `Int` como, , , e `Double` `BigInt` `Result` `Bool` :

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

O <xref:microsoft.quantum.convert> espaço de nome também fornece algumas conversões mais exóticas, como, por `FunctionAsOperation` exemplo, que converte funções `'T -> 'U` em novas operações. `'T => 'U`

Finalmente, a Q# biblioteca padrão fornece uma série de tipos definidos pelo utilizador, tais como <xref:microsoft.quantum.math.complex> <xref:microsoft.quantum.arithmetic.littleendian> .
Juntamente com estes tipos, a biblioteca padrão fornece funções <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> como:

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
