---
title: Conversões de tipo nas bibliotecas padrão Q#
description: Saiba mais sobre funções comuns e definidas pelo utilizador nas bibliotecas padrão Q#.
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: e941d7e3d76459546861410e91a03d7315183867
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275739"
---
# <a name="type-conversions"></a>Conversões de tipo #

Q# é uma língua **fortemente dactilografada.**
Em particular, Q# não lança implicitamente entre tipos distintos. Por exemplo, `1 + 2.0` não é uma expressão Q# válida.
Em vez disso, q# fornece uma variedade de funções de conversão de tipo para a construção de novos valores de um determinado tipo.

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

Finalmente, a biblioteca padrão Q# fornece uma série de tipos definidos pelo utilizador, tais como <xref:microsoft.quantum.math.complex> <xref:microsoft.quantum.arithmetic.littleendian> e .
Juntamente com estes tipos, a biblioteca padrão fornece funções <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> como:

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
