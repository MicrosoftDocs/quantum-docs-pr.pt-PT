---
title: Conversões de tipo nas bibliotecas padrão Q#
description: Conheça as funções comuns e definidas pelo utilizador nas bibliotecas padrão Q#.
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: e941d7e3d76459546861410e91a03d7315183867
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907805"
---
# <a name="type-conversions"></a>Conversões de tipo #

Q# é uma linguagem **fortemente dactilografada.**
Em particular, Q# não é implicitamente lançado entre tipos distintos. Por exemplo, `1 + 2.0` não é uma expressão Q# válida.
Pelo contrário, q# fornece uma variedade de funções de conversão de tipo para a construção de novos valores de um dado tipo.

Por exemplo, <xref:microsoft.quantum.core.length> tem um tipo de saída de `Int`, pelo que a sua saída deve ser convertida primeiro para um `Double` antes de poder ser utilizada como parte de uma expressão de ponto flutuante.
Isto pode ser feito utilizando a função <xref:microsoft.quantum.convert.intasdouble>:

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

O espaço de nome<xref:microsoft.quantum.convert> fornece funções comuns de conversão de tipos para trabalhar com os tipos básicos incorporados, tais como `Int`, `Double`, `BigInt`, `Result`e `Bool`:

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

O espaço de nome <xref:microsoft.quantum.convert> também fornece algumas conversões mais exóticas, como `FunctionAsOperation`, que converte funções `'T -> 'U` em novas operações `'T => 'U`.

Finalmente, a biblioteca padrão Q# fornece uma série de tipos definidos pelo utilizador, tais como <xref:microsoft.quantum.math.complex> e <xref:microsoft.quantum.arithmetic.littleendian>.
Juntamente com estes tipos, a biblioteca padrão fornece funções como <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
