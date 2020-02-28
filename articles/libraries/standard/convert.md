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
# <a name="type-conversions"></a><span data-ttu-id="d5b55-103">Conversões de tipo</span><span class="sxs-lookup"><span data-stu-id="d5b55-103">Type Conversions</span></span> #

<span data-ttu-id="d5b55-104">Q# é uma linguagem **fortemente dactilografada.**</span><span class="sxs-lookup"><span data-stu-id="d5b55-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="d5b55-105">Em particular, Q# não é implicitamente lançado entre tipos distintos.</span><span class="sxs-lookup"><span data-stu-id="d5b55-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="d5b55-106">Por exemplo, `1 + 2.0` não é uma expressão Q# válida.</span><span class="sxs-lookup"><span data-stu-id="d5b55-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="d5b55-107">Pelo contrário, q# fornece uma variedade de funções de conversão de tipo para a construção de novos valores de um dado tipo.</span><span class="sxs-lookup"><span data-stu-id="d5b55-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="d5b55-108">Por exemplo, <xref:microsoft.quantum.core.length> tem um tipo de saída de `Int`, pelo que a sua saída deve ser convertida primeiro para um `Double` antes de poder ser utilizada como parte de uma expressão de ponto flutuante.</span><span class="sxs-lookup"><span data-stu-id="d5b55-108">For example, <xref:microsoft.quantum.core.length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="d5b55-109">Isto pode ser feito utilizando a função <xref:microsoft.quantum.convert.intasdouble>:</span><span class="sxs-lookup"><span data-stu-id="d5b55-109">This can be done using the <xref:microsoft.quantum.convert.intasdouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="d5b55-110">O espaço de nome<xref:microsoft.quantum.convert> fornece funções comuns de conversão de tipos para trabalhar com os tipos básicos incorporados, tais como `Int`, `Double`, `BigInt`, `Result`e `Bool`:</span><span class="sxs-lookup"><span data-stu-id="d5b55-110">The <xref:microsoft.quantum.convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="d5b55-111">O espaço de nome <xref:microsoft.quantum.convert> também fornece algumas conversões mais exóticas, como `FunctionAsOperation`, que converte funções `'T -> 'U` em novas operações `'T => 'U`.</span><span class="sxs-lookup"><span data-stu-id="d5b55-111">The <xref:microsoft.quantum.convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="d5b55-112">Finalmente, a biblioteca padrão Q# fornece uma série de tipos definidos pelo utilizador, tais como <xref:microsoft.quantum.math.complex> e <xref:microsoft.quantum.arithmetic.littleendian>.</span><span class="sxs-lookup"><span data-stu-id="d5b55-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:microsoft.quantum.math.complex> and <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>
<span data-ttu-id="d5b55-113">Juntamente com estes tipos, a biblioteca padrão fornece funções como <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span><span class="sxs-lookup"><span data-stu-id="d5b55-113">Along with these types, the standard library provides functions such as <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span></span>

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
