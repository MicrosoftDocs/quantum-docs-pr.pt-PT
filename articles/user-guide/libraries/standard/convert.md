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
# <a name="type-conversions"></a><span data-ttu-id="7f5c3-103">Conversões de tipo</span><span class="sxs-lookup"><span data-stu-id="7f5c3-103">Type Conversions</span></span> #

<span data-ttu-id="7f5c3-104">Q#é uma linguagem **fortemente dactilografada.**</span><span class="sxs-lookup"><span data-stu-id="7f5c3-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="7f5c3-105">Em particular, Q# não é implicitamente lançado entre tipos distintos.</span><span class="sxs-lookup"><span data-stu-id="7f5c3-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="7f5c3-106">Por exemplo, `1 + 2.0` não é uma expressão Q# válida.</span><span class="sxs-lookup"><span data-stu-id="7f5c3-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="7f5c3-107">Em vez disso, Q# fornece uma variedade de funções de conversão de tipo para a construção de novos valores de um determinado tipo.</span><span class="sxs-lookup"><span data-stu-id="7f5c3-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="7f5c3-108">Por exemplo, <xref:microsoft.quantum.core.length> tem um tipo de saída de , por isso a sua saída deve primeiro ser convertida para um `Int` antes de poder ser usada como parte de uma expressão de ponto `Double` flutuante.</span><span class="sxs-lookup"><span data-stu-id="7f5c3-108">For example, <xref:microsoft.quantum.core.length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="7f5c3-109">Isto pode ser feito utilizando a <xref:microsoft.quantum.convert.intasdouble> função:</span><span class="sxs-lookup"><span data-stu-id="7f5c3-109">This can be done using the <xref:microsoft.quantum.convert.intasdouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="7f5c3-110">O <xref:microsoft.quantum.convert> espaço de nomes fornece funções comuns de conversão de tipo para trabalhar com os tipos básicos incorporados, tais `Int` como, , , e `Double` `BigInt` `Result` `Bool` :</span><span class="sxs-lookup"><span data-stu-id="7f5c3-110">The <xref:microsoft.quantum.convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="7f5c3-111">O <xref:microsoft.quantum.convert> espaço de nome também fornece algumas conversões mais exóticas, como, por `FunctionAsOperation` exemplo, que converte funções `'T -> 'U` em novas operações. `'T => 'U`</span><span class="sxs-lookup"><span data-stu-id="7f5c3-111">The <xref:microsoft.quantum.convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="7f5c3-112">Finalmente, a Q# biblioteca padrão fornece uma série de tipos definidos pelo utilizador, tais como <xref:microsoft.quantum.math.complex> <xref:microsoft.quantum.arithmetic.littleendian> .</span><span class="sxs-lookup"><span data-stu-id="7f5c3-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:microsoft.quantum.math.complex> and <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>
<span data-ttu-id="7f5c3-113">Juntamente com estes tipos, a biblioteca padrão fornece funções <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> como:</span><span class="sxs-lookup"><span data-stu-id="7f5c3-113">Along with these types, the standard library provides functions such as <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span></span>

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
