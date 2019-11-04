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
# <a name="type-conversions"></a><span data-ttu-id="e7bb2-103">Conversões de tipo</span><span class="sxs-lookup"><span data-stu-id="e7bb2-103">Type Conversions</span></span> #

<span data-ttu-id="e7bb2-104">Q # é uma linguagem **fortemente tipada** .</span><span class="sxs-lookup"><span data-stu-id="e7bb2-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="e7bb2-105">Em particular, a p # não é implicitamente convertida entre tipos distintos.</span><span class="sxs-lookup"><span data-stu-id="e7bb2-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="e7bb2-106">Por exemplo, `1 + 2.0` não é uma expressão Q # válida.</span><span class="sxs-lookup"><span data-stu-id="e7bb2-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="e7bb2-107">Em vez disso, o Q # fornece uma variedade de funções de conversão de tipo para construir novos valores de um determinado tipo.</span><span class="sxs-lookup"><span data-stu-id="e7bb2-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="e7bb2-108">Por exemplo, <xref:microsoft.quantum.core.length> tem um tipo de saída de `Int`, portanto, sua saída deve primeiro ser convertida em um `Double` antes que possa ser usada como parte de uma expressão de ponto flutuante.</span><span class="sxs-lookup"><span data-stu-id="e7bb2-108">For example, <xref:microsoft.quantum.core.length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="e7bb2-109">Isso pode ser feito usando a função <xref:microsoft.quantum.convert.intasdouble>:</span><span class="sxs-lookup"><span data-stu-id="e7bb2-109">This can be done using the <xref:microsoft.quantum.convert.intasdouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="e7bb2-110">O namespace <xref:microsoft.quantum.convert> fornece funções comuns de conversão de tipos para trabalhar com os tipos internos básicos, como `Int`, `Double`, `BigInt`, `Result`e `Bool`:</span><span class="sxs-lookup"><span data-stu-id="e7bb2-110">The <xref:microsoft.quantum.convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="e7bb2-111">O namespace <xref:microsoft.quantum.convert> também fornece algumas conversões mais exóticas, como `FunctionAsOperation`, que converte as funções `'T -> 'U` em novas operações `'T => 'U`.</span><span class="sxs-lookup"><span data-stu-id="e7bb2-111">The <xref:microsoft.quantum.convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="e7bb2-112">Por fim, a biblioteca padrão de Q # fornece vários tipos definidos pelo usuário, como <xref:microsoft.quantum.math.complex> e <xref:microsoft.quantum.arithmetic.littleendian>.</span><span class="sxs-lookup"><span data-stu-id="e7bb2-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:microsoft.quantum.math.complex> and <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>
<span data-ttu-id="e7bb2-113">Juntamente com esses tipos, a biblioteca padrão fornece funções como <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span><span class="sxs-lookup"><span data-stu-id="e7bb2-113">Along with these types, the standard library provides functions such as <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span></span>

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
