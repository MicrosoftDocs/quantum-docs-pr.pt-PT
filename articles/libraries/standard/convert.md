---
title: 'Q # bibliotecas padrão – conversões de tipo | Microsoft Docs'
description: 'Q # bibliotecas padrão – conversões de tipo'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 4716f0d9562229f08ef6f0f5f80961f793de4c5c
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184479"
---
# <a name="type-conversions"></a>Conversões de tipo #

Q # é uma linguagem **fortemente tipada** .
Em particular, a p # não é implicitamente convertida entre tipos distintos. Por exemplo, `1 + 2.0` não é uma expressão Q # válida.
Em vez disso, o Q # fornece uma variedade de funções de conversão de tipo para construir novos valores de um determinado tipo.

Por exemplo, <xref:microsoft.quantum.core.length> tem um tipo de saída de `Int`, portanto, sua saída deve primeiro ser convertida em um `Double` antes que possa ser usada como parte de uma expressão de ponto flutuante.
Isso pode ser feito usando a função <xref:microsoft.quantum.convert.intasdouble>:

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

O namespace <xref:microsoft.quantum.convert> fornece funções comuns de conversão de tipos para trabalhar com os tipos internos básicos, como `Int`, `Double`, `BigInt`, `Result`e `Bool`:

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

O namespace <xref:microsoft.quantum.convert> também fornece algumas conversões mais exóticas, como `FunctionAsOperation`, que converte as funções `'T -> 'U` em novas operações `'T => 'U`.

Por fim, a biblioteca padrão de Q # fornece vários tipos definidos pelo usuário, como <xref:microsoft.quantum.math.complex> e <xref:microsoft.quantum.arithmetic.littleendian>.
Juntamente com esses tipos, a biblioteca padrão fornece funções como <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
