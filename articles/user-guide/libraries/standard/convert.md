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
# <a name="type-conversions"></a><span data-ttu-id="9ca68-103">Conversões de tipo</span><span class="sxs-lookup"><span data-stu-id="9ca68-103">Type Conversions</span></span> #

<span data-ttu-id="9ca68-104">Q#é uma linguagem **fortemente dactilografada.**</span><span class="sxs-lookup"><span data-stu-id="9ca68-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="9ca68-105">Em particular, Q# não é implicitamente lançado entre tipos distintos.</span><span class="sxs-lookup"><span data-stu-id="9ca68-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="9ca68-106">Por exemplo, `1 + 2.0` não é uma expressão Q# válida.</span><span class="sxs-lookup"><span data-stu-id="9ca68-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="9ca68-107">Em vez disso, Q# fornece uma variedade de funções de conversão de tipo para a construção de novos valores de um determinado tipo.</span><span class="sxs-lookup"><span data-stu-id="9ca68-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="9ca68-108">Por exemplo, <xref:Microsoft.Quantum.Core.Length> tem um tipo de saída de , por isso a sua saída deve primeiro ser convertida para um `Int` antes de poder ser usada como parte de uma expressão de ponto `Double` flutuante.</span><span class="sxs-lookup"><span data-stu-id="9ca68-108">For example, <xref:Microsoft.Quantum.Core.Length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="9ca68-109">Isto pode ser feito utilizando a <xref:Microsoft.Quantum.Convert.IntAsDouble> função:</span><span class="sxs-lookup"><span data-stu-id="9ca68-109">This can be done using the <xref:Microsoft.Quantum.Convert.IntAsDouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="9ca68-110">O <xref:Microsoft.Quantum.Convert> espaço de nomes fornece funções comuns de conversão de tipo para trabalhar com os tipos básicos incorporados, tais `Int` como, e `Double` `BigInt` `Result` `Bool` :</span><span class="sxs-lookup"><span data-stu-id="9ca68-110">The <xref:Microsoft.Quantum.Convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="9ca68-111">O <xref:Microsoft.Quantum.Convert> espaço de nome também fornece algumas conversões mais exóticas, como, por `FunctionAsOperation` exemplo, que converte funções `'T -> 'U` em novas operações. `'T => 'U`</span><span class="sxs-lookup"><span data-stu-id="9ca68-111">The <xref:Microsoft.Quantum.Convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="9ca68-112">Finalmente, a Q# biblioteca padrão fornece uma série de tipos definidos pelo utilizador, tais como <xref:Microsoft.Quantum.Math.Complex> <xref:Microsoft.Quantum.Arithmetic.LittleEndian> .</span><span class="sxs-lookup"><span data-stu-id="9ca68-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:Microsoft.Quantum.Math.Complex> and <xref:Microsoft.Quantum.Arithmetic.LittleEndian>.</span></span>
<span data-ttu-id="9ca68-113">Juntamente com estes tipos, a biblioteca padrão fornece funções <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian> como:</span><span class="sxs-lookup"><span data-stu-id="9ca68-113">Along with these types, the standard library provides functions such as <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian>:</span></span>

```qsharp
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
