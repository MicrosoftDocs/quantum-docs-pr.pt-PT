---
title: Tipos em Q#
description: Saiba mais sobre os diferentes tipos utilizados na Q# linguagem de programação.
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
no-loc:
- Q#
- $$v
ms.openlocfilehash: c4a3e6563b8cabee87d1db6b9cb1c1f1c1a7131b
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835830"
---
# <a name="types-in-no-locq"></a><span data-ttu-id="c0f52-103">Tipos em Q#</span><span class="sxs-lookup"><span data-stu-id="c0f52-103">Types in Q#</span></span>

<span data-ttu-id="c0f52-104">Este artigo descreve o Q# modelo de tipo e a sintaxe para especificar e trabalhar com tipos.</span><span class="sxs-lookup"><span data-stu-id="c0f52-104">This article describes the Q# type model and the syntax for specifying and working with types.</span></span> <span data-ttu-id="c0f52-105">Para obter detalhes sobre como criar e operar em expressões deste tipo, consulte [Expressões tipo](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="c0f52-105">For details on how to create and operate on expressions of these types, see [Type Expressions](xref:microsoft.quantum.guide.expressions).</span></span>

<span data-ttu-id="c0f52-106">Notamos que Q# é uma linguagem *fortemente dactilografada,* de modo que o uso cuidadoso destes tipos pode ajudar o compilador a fornecer garantias fortes sobre programas em tempo de Q# compilação.</span><span class="sxs-lookup"><span data-stu-id="c0f52-106">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="c0f52-107">Para fornecer as garantias mais fortes possíveis, as conversões entre os tipos Q# dentro devem ser explícitas usando chamadas para funções que expressem essa conversão.</span><span class="sxs-lookup"><span data-stu-id="c0f52-107">To provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> 
<span data-ttu-id="c0f52-108">Q# fornece uma variedade de tais funções como parte do espaço de <xref:microsoft.quantum.convert> nome.</span><span class="sxs-lookup"><span data-stu-id="c0f52-108">Q# provides a variety of such functions as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="c0f52-109">As upcasts para tipos compatíveis, por outro lado, acontecem implicitamente.</span><span class="sxs-lookup"><span data-stu-id="c0f52-109">Upcasts to compatible types, on the other hand, happen implicitly.</span></span> 

<span data-ttu-id="c0f52-110">Q# fornece ambos os tipos primitivos, que são usados diretamente, e uma variedade de maneiras de produzir novos tipos de outros tipos.</span><span class="sxs-lookup"><span data-stu-id="c0f52-110">Q# provides both primitive types, which are used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="c0f52-111">Descrevemos cada um no resto deste artigo.</span><span class="sxs-lookup"><span data-stu-id="c0f52-111">We describe each in the rest of this article.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="c0f52-112">Tipos Primitivos</span><span class="sxs-lookup"><span data-stu-id="c0f52-112">Primitive Types</span></span>

<span data-ttu-id="c0f52-113">O Q# idioma fornece os seguintes *tipos primitivos,* todos os quais pode usar diretamente em Q# programas.</span><span class="sxs-lookup"><span data-stu-id="c0f52-113">The Q# language provides the following *primitive types*, all of which you can use directly in Q# programs.</span></span> <span data-ttu-id="c0f52-114">Também pode usar estes tipos primitivos para construir novos tipos.</span><span class="sxs-lookup"><span data-stu-id="c0f52-114">You can also use these primitive types to construct new types.</span></span>

- <span data-ttu-id="c0f52-115">O `Int` tipo representa um número inteiro assinado de 64 bits, por exemplo, `2` . . . `107` `-5` .</span><span class="sxs-lookup"><span data-stu-id="c0f52-115">The `Int` type represents a 64-bit signed integer, for example, `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="c0f52-116">O `BigInt` tipo representa um número inteiro assinado de tamanho arbitrário, por `2L` `107L` exemplo, , . `-5L` .</span><span class="sxs-lookup"><span data-stu-id="c0f52-116">The `BigInt` type represents a signed integer of arbitrary size, for example, `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="c0f52-117">Este tipo baseia-se no .NET <xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="c0f52-117">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="c0f52-118">tipo.</span><span class="sxs-lookup"><span data-stu-id="c0f52-118">type.</span></span>

- <span data-ttu-id="c0f52-119">O `Double` tipo representa um número de ponto flutuante de dupla precisão, por `0.0` exemplo, , . . `-1.3` `4e-7` .</span><span class="sxs-lookup"><span data-stu-id="c0f52-119">The `Double` type represents a double-precision floating-point number, for example, `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="c0f52-120">O `Bool` tipo representa um valor booleano de qualquer um ou `true` `false` .</span><span class="sxs-lookup"><span data-stu-id="c0f52-120">The `Bool` type represents a Boolean value of either `true` or `false`.</span></span>
- <span data-ttu-id="c0f52-121">O `Range` tipo representa uma sequência de inteiros, denotada `start..step..stop` por, onde denotar o passo é opcional.</span><span class="sxs-lookup"><span data-stu-id="c0f52-121">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is optional.</span></span> 
   <span data-ttu-id="c0f52-122">Por exemplo, `start .. stop` corresponde a , e representa a sequência $ `start..1..stop` `1..2..7` \{ 1, 3, 5, 7 \} $.</span><span class="sxs-lookup"><span data-stu-id="c0f52-122">For example, `start .. stop` corresponds to `start..1..stop`, and `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="c0f52-123">O `String` tipo é uma sequência de caracteres Unicode que é opaco para o utilizador uma vez criado.</span><span class="sxs-lookup"><span data-stu-id="c0f52-123">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="c0f52-124">Utilize o `string` tipo para reportar mensagens a um anfitrião clássico em caso de erro ou evento de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="c0f52-124">Use the `string` type to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="c0f52-125">O `Unit` tipo pode ter apenas um valor, `()` .</span><span class="sxs-lookup"><span data-stu-id="c0f52-125">The `Unit` type can have only one value, `()`.</span></span> 
  <span data-ttu-id="c0f52-126">Utilize este tipo para indicar que uma Q# função ou operação não devolve nenhuma informação.</span><span class="sxs-lookup"><span data-stu-id="c0f52-126">Use this type to indicate that a Q# function or operation returns no information.</span></span> 
- <span data-ttu-id="c0f52-127">O `Qubit` tipo representa um bit quântico ou qubit.</span><span class="sxs-lookup"><span data-stu-id="c0f52-127">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="c0f52-128">`Qubit`s são opacos para o utilizador.</span><span class="sxs-lookup"><span data-stu-id="c0f52-128">`Qubit`s are opaque to the user.</span></span> <span data-ttu-id="c0f52-129">A única operação possível com eles, para além de passá-los para outra operação, é testar a identidade (igualdade).</span><span class="sxs-lookup"><span data-stu-id="c0f52-129">The only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="c0f52-130">Em última análise, implementa ações em `Qubit` s, chamando instruções intrínsecas num processador quântico (ou um simulador quântico).</span><span class="sxs-lookup"><span data-stu-id="c0f52-130">Ultimately, you implement actions on `Qubit`s by calling intrinsic instructions on a quantum processor (or a quantum simulator).</span></span>
- <span data-ttu-id="c0f52-131">O `Pauli` tipo representa um dos quatro operadores pauli de um único qubit.</span><span class="sxs-lookup"><span data-stu-id="c0f52-131">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="c0f52-132">Utilize este tipo para denotar o funcionamento da base para rotações e especificar o que está a ser medido.</span><span class="sxs-lookup"><span data-stu-id="c0f52-132">Use this type to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="c0f52-133">É um tipo enumerado que tem quatro valores possíveis: `PauliI` `PauliX` , , `PauliY` `PauliZ` e, que são constantes de tipo `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="c0f52-133">It is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="c0f52-134">O `Result` tipo representa o resultado de uma medição.</span><span class="sxs-lookup"><span data-stu-id="c0f52-134">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="c0f52-135">É um tipo enumerado com dois valores possíveis: `One` `Zero` e, que são constantes do tipo `Result` .</span><span class="sxs-lookup"><span data-stu-id="c0f52-135">It is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="c0f52-136">`Zero` indica que o valor de +1 eigen foi medido; `One` indica que o -1 eigenvalue foi medido.</span><span class="sxs-lookup"><span data-stu-id="c0f52-136">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue was measured.</span></span>

<span data-ttu-id="c0f52-137">As `true` constantes, , , , , , , `false` , , e são `PauliI` todos `PauliX` `PauliY` `PauliZ` `One` `Zero` símbolos reservados em Q# .</span><span class="sxs-lookup"><span data-stu-id="c0f52-137">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="c0f52-138">Tipos de Matrizes</span><span class="sxs-lookup"><span data-stu-id="c0f52-138">Array Types</span></span>

* <span data-ttu-id="c0f52-139">Para qualquer Q# tipo válido, existe um tipo que representa uma matriz de valores desse tipo.</span><span class="sxs-lookup"><span data-stu-id="c0f52-139">For any valid Q# type, there is a type that represents an array of values of that type.</span></span>
    <span data-ttu-id="c0f52-140">Por exemplo, `Qubit[]` e `(Bool, Pauli)[]` representam matrizes de `Qubit` valores e `(Bool, Pauli)` valores de tuple.</span><span class="sxs-lookup"><span data-stu-id="c0f52-140">For example, `Qubit[]` and `(Bool, Pauli)[]` represent arrays of `Qubit` values and `(Bool, Pauli)` tuple values.</span></span>

* <span data-ttu-id="c0f52-141">Uma variedade de matrizes também é válida.</span><span class="sxs-lookup"><span data-stu-id="c0f52-141">An array of arrays is also valid.</span></span> <span data-ttu-id="c0f52-142">Expandindo-se no exemplo anterior, uma série de `(Bool, Pauli)` matrizes é denotada `(Bool, Pauli)[][]` .</span><span class="sxs-lookup"><span data-stu-id="c0f52-142">Expanding on the previous example, an array of `(Bool, Pauli)` arrays is denoted `(Bool, Pauli)[][]`.</span></span>

> [!NOTE] 
> <span data-ttu-id="c0f52-143">Este `(Bool, Pauli)[][]` exemplo, representa uma matriz potencialmente irregular de matrizes e não uma matriz bidimensional retangular.</span><span class="sxs-lookup"><span data-stu-id="c0f52-143">This example, `(Bool, Pauli)[][]`, represents a potentially jagged array of arrays and not a rectangular two-dimensional array.</span></span> <span data-ttu-id="c0f52-144">Q# não suporta matrizes multidimensionais retangulares.</span><span class="sxs-lookup"><span data-stu-id="c0f52-144">Q# does not support rectangular multi-dimensional arrays.</span></span>

* <span data-ttu-id="c0f52-145">Um valor de matriz pode ser escrito em Q# código fonte utilizando suportes quadrados em torno dos elementos de uma matriz, como em `[PauliI, PauliX, PauliY, PauliZ]` .</span><span class="sxs-lookup"><span data-stu-id="c0f52-145">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="c0f52-146">O tipo de base comum de todos os itens da matriz determina o tipo de matriz literal.</span><span class="sxs-lookup"><span data-stu-id="c0f52-146">The common base type of all items in the array determines the type of an array literal.</span></span> <span data-ttu-id="c0f52-147">Assim, construir uma matriz com elementos que não têm um tipo de base comum levanta um erro.</span><span class="sxs-lookup"><span data-stu-id="c0f52-147">Hence, constructing an array with elements that have no common base type raises an error.</span></span>  
<span data-ttu-id="c0f52-148">Por exemplo, consulte [conjuntos de chamadas.](xref:microsoft.quantum.guide.expressions#arrays-of-callables)</span><span class="sxs-lookup"><span data-stu-id="c0f52-148">For an example, see [arrays of callables](xref:microsoft.quantum.guide.expressions#arrays-of-callables).</span></span>

    > [!WARNING]
    > <span data-ttu-id="c0f52-149">Uma vez criados, os elementos de uma matriz não podem ser alterados.</span><span class="sxs-lookup"><span data-stu-id="c0f52-149">Once created, the elements of an array cannot be changed.</span></span>
    > <span data-ttu-id="c0f52-150">Para construir uma matriz modificada, utilize [declarações de atualização e reatribuição](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) ou [expressões de cópia e atualização](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="c0f52-150">To construct a modified array, use [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) or [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span>

* <span data-ttu-id="c0f52-151">Alternativamente, uma matriz pode ser criada a partir do seu tamanho usando a `new` palavra-chave:</span><span class="sxs-lookup"><span data-stu-id="c0f52-151">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* <span data-ttu-id="c0f52-152">Utilize a função central `Length` para obter o número de elementos de uma matriz como `Int` .</span><span class="sxs-lookup"><span data-stu-id="c0f52-152">Use the core function `Length` to obtain the number of elements from an array as an `Int`.</span></span>
* <span data-ttu-id="c0f52-153">As matrizes podem ser subscritadas para obter elementos únicos ou novas matrizes que contenham um subconjunto dos elementos de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="c0f52-153">Arrays can be subscripted to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="c0f52-154">Os subscritos de matrizes são de base zero e devem ser tipo `Int` ou `Range` tipo:</span><span class="sxs-lookup"><span data-stu-id="c0f52-154">The subscripts of arrays are zero-based and must be type `Int` or type `Range`:</span></span>

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a><span data-ttu-id="c0f52-155">Tipos tuple</span><span class="sxs-lookup"><span data-stu-id="c0f52-155">Tuple Types</span></span>

<span data-ttu-id="c0f52-156">Tuples é um conceito poderoso usado ao longo de todo Q# para recolher valores juntos em um único valor, tornando mais fácil passá-los ao redor.</span><span class="sxs-lookup"><span data-stu-id="c0f52-156">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="c0f52-157">Em particular, usando a notação de tuple, você pode expressar que cada operação e callable leva exatamente uma entrada e devolve exatamente uma saída.</span><span class="sxs-lookup"><span data-stu-id="c0f52-157">In particular, using tuple notation, you can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

* <span data-ttu-id="c0f52-158">Dado zero ou mais tipos `T0` `T1` diferentes, ...pode `Tn` denotar um novo  *tipo de tuple* como `(T0, T1, ..., Tn)` .</span><span class="sxs-lookup"><span data-stu-id="c0f52-158">Given zero or more different types `T0`, `T1`, ..., `Tn`, you can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="c0f52-159">Os tipos usados para construir um novo tipo de tuple podem ser tuples, como em `(Int, (Qubit, Qubit))` .</span><span class="sxs-lookup"><span data-stu-id="c0f52-159">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="c0f52-160">No entanto, esse nidificação é sempre finito, uma vez que os tipos de tuple não podem, em circunstância alguma, conter-se.</span><span class="sxs-lookup"><span data-stu-id="c0f52-160">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

* <span data-ttu-id="c0f52-161">Os valores do novo tipo tuple são tuples formados por sequências de valores de cada tipo no tuple.</span><span class="sxs-lookup"><span data-stu-id="c0f52-161">The values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="c0f52-162">Por exemplo, `(3, false)` é um tuple cujo tipo é o tipo tuple `(Int, Bool)` .</span><span class="sxs-lookup"><span data-stu-id="c0f52-162">For example, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="c0f52-163">É possível criar matrizes de tuples, tuples de matrizes, tuples de sub-tuples, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="c0f52-163">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, and so on.</span></span>

* <span data-ttu-id="c0f52-164">A partir de Q# 0.3, `Unit` é o nome do *tipo* do tuple vazio; é usado para `()` o *valor* do tuple vazio.</span><span class="sxs-lookup"><span data-stu-id="c0f52-164">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the *value* of the empty tuple.</span></span>

* <span data-ttu-id="c0f52-165">As instâncias de tuple são imutáveis.</span><span class="sxs-lookup"><span data-stu-id="c0f52-165">Tuple instances are immutable.</span></span>
<span data-ttu-id="c0f52-166">Q# não fornece um mecanismo para alterar o conteúdo de uma tuple uma vez criada.</span><span class="sxs-lookup"><span data-stu-id="c0f52-166">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>



### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="c0f52-167">Equivalência de Tuple Singleton</span><span class="sxs-lookup"><span data-stu-id="c0f52-167">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="c0f52-168">É possível criar uma tuple singleton (single-element), `('T1)` como `(5)` ou `([1,2,3])` .</span><span class="sxs-lookup"><span data-stu-id="c0f52-168">It is possible to create a singleton (single-element) tuple `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="c0f52-169">No entanto, Q# trata uma tuple singleton como equivalente a um valor do tipo fechado.</span><span class="sxs-lookup"><span data-stu-id="c0f52-169">However, Q# treats a singleton tuple as equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="c0f52-170">Ou seja, não há diferença entre `5` `(5)` e, ou entre `5` `(((5)))` e, ou entre `(5, (6))` e `(5, 6)` .</span><span class="sxs-lookup"><span data-stu-id="c0f52-170">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>
<span data-ttu-id="c0f52-171">É tão válido escrever `(5)+3` como `5+3` escrever; ambas as expressões `8` avaliam.</span><span class="sxs-lookup"><span data-stu-id="c0f52-171">It is just as valid to write `(5)+3` as it is to write `5+3`; both expressions evaluate to `8`.</span></span>

<span data-ttu-id="c0f52-172">Esta equivalência aplica-se para todos os efeitos, incluindo atribuição e expressões.</span><span class="sxs-lookup"><span data-stu-id="c0f52-172">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="c0f52-173">Dada qualquer expressão, a mesma expressão em anexo em parênteses é uma expressão do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="c0f52-173">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="c0f52-174">Por exemplo, `(7)` é uma expressão do `Int` tipo, é uma expressão do `([1,2,3])` `Int[]` tipo, e é uma expressão do `((1,2))` `(Int, Int)` tipo.</span><span class="sxs-lookup"><span data-stu-id="c0f52-174">For example, `(7)` is an expression of type `Int`, `([1,2,3])` is an expression of type `Int[]`, and `((1,2))` is an expression of type `(Int, Int)`.</span></span>

<span data-ttu-id="c0f52-175">Isto significa, em particular, que pode ver uma operação ou função cujo tipo de tuple ou de saída tem um campo como tendo um único argumento ou devolvendo um único valor.</span><span class="sxs-lookup"><span data-stu-id="c0f52-175">In particular, this means that you can view an operation or function whose input tuple or output tuple type has one field as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="c0f52-176">Referimo-nos a esta propriedade como _equivalência de tuple singleton._</span><span class="sxs-lookup"><span data-stu-id="c0f52-176">We refer to this property as _singleton tuple equivalence_.</span></span>


## <a name="user-defined-types"></a><span data-ttu-id="c0f52-177">Tipos definidos pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="c0f52-177">User-Defined Types</span></span>

<span data-ttu-id="c0f52-178">Uma declaração de tipo definido pelo utilizador consiste na `newtype` palavra-chave, seguida do nome do tipo definido pelo utilizador, `=` uma especificação de tipo válido e um ponto de terminação.</span><span class="sxs-lookup"><span data-stu-id="c0f52-178">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="c0f52-179">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c0f52-179">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* <span data-ttu-id="c0f52-180">Cada Q# ficheiro de origem pode declarar qualquer número de tipos definidos pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="c0f52-180">Each Q# source file may declare any number of user-defined types.</span></span>
* <span data-ttu-id="c0f52-181">Os nomes de tipo devem ser únicos dentro de um espaço de nome e não podem entrar em conflito com o funcionamento e os nomes das funções.</span><span class="sxs-lookup"><span data-stu-id="c0f52-181">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>
* <span data-ttu-id="c0f52-182">Os tipos definidos pelo utilizador são distintos, mesmo que os tipos de base sejam idênticos.</span><span class="sxs-lookup"><span data-stu-id="c0f52-182">User-defined types are distinct, even if the base types are identical.</span></span>
<span data-ttu-id="c0f52-183">Em particular, não existe uma conversão automática entre os valores de dois tipos definidos pelo utilizador, mesmo que os tipos subjacentes sejam idênticos.</span><span class="sxs-lookup"><span data-stu-id="c0f52-183">In particular, there is no automatic conversion between the values of two user-defined types, even if the underlying types are identical.</span></span>

### <a name="named-vs-anonymous-items"></a><span data-ttu-id="c0f52-184">Nomeados vs. itens anónimos</span><span class="sxs-lookup"><span data-stu-id="c0f52-184">Named vs. anonymous items</span></span>

<span data-ttu-id="c0f52-185">Um Q# ficheiro pode definir um novo tipo de nome contendo um único valor de qualquer tipo legal.</span><span class="sxs-lookup"><span data-stu-id="c0f52-185">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="c0f52-186">Para qualquer tipo de `T` tuple, pode declarar um novo tipo definido pelo utilizador que é um subtipo `T` de com a `newtype` declaração.</span><span class="sxs-lookup"><span data-stu-id="c0f52-186">For any tuple type `T`, you can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="c0f52-187">No @"microsoft.quantum.math" espaço de nomes, por exemplo, os números complexos são definidos como um tipo definido pelo utilizador:</span><span class="sxs-lookup"><span data-stu-id="c0f52-187">In the @"microsoft.quantum.math" namespace, for example, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```
<span data-ttu-id="c0f52-188">Esta afirmação cria um novo tipo com dois itens anónimos do tipo `Double` .</span><span class="sxs-lookup"><span data-stu-id="c0f52-188">This statement creates a new type with two anonymous items of type `Double`.</span></span>   

<span data-ttu-id="c0f52-189">Além de itens anónimos, os tipos definidos pelo utilizador também *suportam itens nomeados* a partir da Q# versão 0.7 ou superior.</span><span class="sxs-lookup"><span data-stu-id="c0f52-189">Aside from anonymous items, user-defined types also support *named items* as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="c0f52-190">Por exemplo, pode nomear os itens `Real` para o duplo representando a parte real de um número complexo e para a parte `Imag` imaginária:</span><span class="sxs-lookup"><span data-stu-id="c0f52-190">For example, you could name the items to `Real` for the double representing the real part of a complex number and `Imag` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Real : Double, Imag : Double);
```
<span data-ttu-id="c0f52-191">Nomear um item num tipo definido pelo utilizador não implica que todos os itens precisem de ser nomeados - qualquer combinação de itens nomeados e não nomeados é suportada.</span><span class="sxs-lookup"><span data-stu-id="c0f52-191">Naming one item in a user-defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="c0f52-192">Além disso, os itens internos também podem ser nomeados.</span><span class="sxs-lookup"><span data-stu-id="c0f52-192">Furthermore, inner items may also be named.</span></span>
<span data-ttu-id="c0f52-193">O tipo `Nested` , tal como definido abaixo, por exemplo, tem um tipo `(Double, (Int, String))` subjacente, do qual apenas o item do tipo `Int` é nomeado, e todos os outros itens são anónimos.</span><span class="sxs-lookup"><span data-stu-id="c0f52-193">The type `Nested`, as defined below for example, has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named, and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

<span data-ttu-id="c0f52-194">Os itens nomeados têm a vantagem de poderem ser acedidos diretamente através do *operador de acesso.* `::`</span><span class="sxs-lookup"><span data-stu-id="c0f52-194">Named items have the advantage that they can be accessed directly via the *access operator* `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Real + c2::Real, c1::Imag + c2::Imag);
}
```

<span data-ttu-id="c0f52-195">Além de fornecer pseudónimos curtos para tipos de tuple potencialmente complicados, uma vantagem significativa de definir tais tipos é que eles podem documentar a intenção de um determinado valor.</span><span class="sxs-lookup"><span data-stu-id="c0f52-195">In addition to providing short aliases for potentially complicated tuple types, a significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="c0f52-196">Voltando ao exemplo de `Complex` , poderia também ter definido uma reavaliação de coordenadas polares como um tipo definido pelo utilizador:</span><span class="sxs-lookup"><span data-stu-id="c0f52-196">Returning to the example of `Complex`, one could have also defined a polar coordinate represenation as a user-defined type:</span></span>

```qsharp
newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```

<span data-ttu-id="c0f52-197">Apesar de ambos `Complex` e ambos terem um tipo `ComplexPolar` `(Double, Double)` subjacente, os dois tipos são totalmente incompatíveis, Q# minimizando o risco de acidentalmente chamar uma função matemática complexa com coordenadas polares e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="c0f52-197">Even though both `Complex` and `ComplexPolar` both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a><span data-ttu-id="c0f52-198">Aceda a itens anónimos com o operador de desembrulhar</span><span class="sxs-lookup"><span data-stu-id="c0f52-198">Access anonymous items with the unwrap operator</span></span>

<span data-ttu-id="c0f52-199">Para aceder a itens anónimos, extrair primeiro o valor embrulhado utilizando o operador de pós-estação `!` .</span><span class="sxs-lookup"><span data-stu-id="c0f52-199">To access anonymous items, first extract the wrapped value using the postfix operator `!`.</span></span>
<span data-ttu-id="c0f52-200">Com o operador "desembrulhar", `!` pode extrair o valor contido num tipo definido pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="c0f52-200">With the "unwrap" operator, `!`, you can extract the value contained in a user-defined type.</span></span>
<span data-ttu-id="c0f52-201">O tipo de expressão "desembrulhar" é o tipo subjacente do tipo definido pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="c0f52-201">The type of such an "unwrap" expression is the underlying type of the user-defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="c0f52-202">Um único operador desembrulha uma camada de embrulho.</span><span class="sxs-lookup"><span data-stu-id="c0f52-202">A single unwrap operator unwraps one layer of wrapping.</span></span> <span data-ttu-id="c0f52-203">Utilize vários operadores de desembrulhar para aceder a um valor multiplicado.</span><span class="sxs-lookup"><span data-stu-id="c0f52-203">Use multiple unwrap operators to access a multiply-wrapped value.</span></span>

<span data-ttu-id="c0f52-204">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c0f52-204">For example:</span></span>

```qsharp
newtype WrappedInt = Int;
newtype DoublyWrappedInt = WrappedInt;

...
    let x = DoublyWrappedInt(WrappedInt(6));
    let y = x!;       // y is WrappedInt(6)
    let z = x!!;      // z is 6
    let a = x + 5;    // This is an error, a DoublyWrappedInt isn't an Int
    let b = x! + 5;   // Also an error
    let c = x!! + 5;  // This is valid, c will be 11
...
```

<span data-ttu-id="c0f52-205">Para obter mais detalhes sobre o operador de desembrulhar, consulte [As Expressões tipo em Q# ](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="c0f52-205">For more details on the unwrap operator, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span>

### <a name="creating-values-of-user-defined-types"></a><span data-ttu-id="c0f52-206">Criação de valores de tipos definidos pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="c0f52-206">Creating values of user-defined types</span></span>

<span data-ttu-id="c0f52-207">Criar valores de um tipo definido pelo utilizador chamando o construtor de tipo correspondente:</span><span class="sxs-lookup"><span data-stu-id="c0f52-207">Create values of a user-defined type by calling the corresponding type constructor:</span></span>

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="c0f52-208">Em alternativa, pode criar novos valores a partir dos existentes utilizando [expressões de cópia e atualização](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="c0f52-208">Alternatively, you can create new values from existing ones using [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="c0f52-209">Tal como fazem com as matrizes, as expressões de cópia e atualização copiam todos os valores de produto da expressão original, exceto nos itens nomeados especificados.</span><span class="sxs-lookup"><span data-stu-id="c0f52-209">Just as they do with arrays, copy-and-update expressions copy all item values of the original expression, except for the specified named items.</span></span> <span data-ttu-id="c0f52-210">Para estas exceções, os valores destes itens são os valores definidos no lado direito da expressão.</span><span class="sxs-lookup"><span data-stu-id="c0f52-210">For these exceptions, the values of these items are the values defined on the right-hand side of the expression.</span></span> <span data-ttu-id="c0f52-211">Quaisquer outras construções linguísticas que estejam disponíveis para itens de matriz, por [exemplo, declarações de atualização e reatribuição,](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)existem para itens nomeados em tipos definidos pelo utilizador também.</span><span class="sxs-lookup"><span data-stu-id="c0f52-211">Any other language constructs that are available for array items, for example [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), exist for named-items in user-defined types as well.</span></span>

```qsharp
newtype ComplexArray = (Count : Int, Data : Complex[]);

function AsComplexArray (data : Double[]) : ComplexArray {

    mutable res = ComplexArray(0, new Complex[0]);
    for (item in data) {
        set res w/= Data <- res::Data + [Complex(item, 0.)]; // update-and-reassign statement
    }
    return res w/ Count <- Length(res::Data); // returning a copy-and-update expression
}
```

* <span data-ttu-id="c0f52-212">Pode utilizar tipos definidos pelo utilizador em qualquer lugar que utilize outros tipos.</span><span class="sxs-lookup"><span data-stu-id="c0f52-212">You can use user-defined types anywhere you use any other types.</span></span>
<span data-ttu-id="c0f52-213">Em particular, é possível definir uma matriz de um tipo definido pelo utilizador e incluir um tipo definido pelo utilizador como elemento de um tipo de tuple.</span><span class="sxs-lookup"><span data-stu-id="c0f52-213">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

* <span data-ttu-id="c0f52-214">Não é possível criar estruturas de tipo recursivo.</span><span class="sxs-lookup"><span data-stu-id="c0f52-214">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="c0f52-215">Ou seja, o tipo que define um tipo definido pelo utilizador não pode ser um tipo de tuple que inclua um elemento do tipo definido pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="c0f52-215">That is, the type that defines a user-defined type cannot be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="c0f52-216">De uma forma mais geral, os tipos definidos pelo utilizador podem não ter dependências cíclicas uns dos outros, pelo que o seguinte conjunto de definições de tipo é inválido:</span><span class="sxs-lookup"><span data-stu-id="c0f52-216">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions are invalid:</span></span>

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a><span data-ttu-id="c0f52-217">Tipos de funcionamento e função</span><span class="sxs-lookup"><span data-stu-id="c0f52-217">Operation and Function Types</span></span>

<span data-ttu-id="c0f52-218">Dados os tipos `'Tinput` `'Tresult` e:</span><span class="sxs-lookup"><span data-stu-id="c0f52-218">Given the types `'Tinput` and `'Tresult`:</span></span>

* <span data-ttu-id="c0f52-219">`('Tinput => 'Tresult)` é o tipo básico para qualquer *operação,* por `((Qubit, Pauli) => Result)` exemplo.</span><span class="sxs-lookup"><span data-stu-id="c0f52-219">`('Tinput => 'Tresult)` is the basic type for any *operation*, for example `((Qubit, Pauli) => Result)`.</span></span>
* <span data-ttu-id="c0f52-220">`('Tinput -> 'Tresult)` é o tipo básico para qualquer *função,* por `(Int -> Int)` exemplo.</span><span class="sxs-lookup"><span data-stu-id="c0f52-220">`('Tinput -> 'Tresult)` is the basic type for any *function*, for example `(Int -> Int)`.</span></span> 

<span data-ttu-id="c0f52-221">Estes são chamados a *assinatura* do chamado.</span><span class="sxs-lookup"><span data-stu-id="c0f52-221">These are called the *signature* of the callable.</span></span>

* <span data-ttu-id="c0f52-222">Todos os Q# callables têm um único valor como entrada e devolvem um único valor como saída.</span><span class="sxs-lookup"><span data-stu-id="c0f52-222">All Q# callables take a single value as input and return a single value as output.</span></span>
* <span data-ttu-id="c0f52-223">Pode utilizar tuples tanto para os valores de entrada como para a saída.</span><span class="sxs-lookup"><span data-stu-id="c0f52-223">You can use tuples for both the input and output values.</span></span>
* <span data-ttu-id="c0f52-224">Calíveis que não têm resultado, `Unit` devolvam.</span><span class="sxs-lookup"><span data-stu-id="c0f52-224">Callables that have no result, return `Unit`.</span></span>
* <span data-ttu-id="c0f52-225">Os callables que não têm entrada tomam a tuple vazia como entrada.</span><span class="sxs-lookup"><span data-stu-id="c0f52-225">Callables that have no input take the empty tuple as input.</span></span>

### <a name="functors"></a><span data-ttu-id="c0f52-226">Functors</span><span class="sxs-lookup"><span data-stu-id="c0f52-226">Functors</span></span>

<span data-ttu-id="c0f52-227">Os tipos *de função* são completamente especificados pela sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="c0f52-227">*Function* types are completely specified by their signature.</span></span> <span data-ttu-id="c0f52-228">Por exemplo, uma função que calcula o seno de um ângulo teria tipo `(Double -> Double)` .</span><span class="sxs-lookup"><span data-stu-id="c0f52-228">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span> 

<span data-ttu-id="c0f52-229">*As operações* têm determinadas características adicionais que são expressas como parte do tipo de operação.</span><span class="sxs-lookup"><span data-stu-id="c0f52-229">*Operations* have certain additional characteristics that are expressed as part of the operation type.</span></span> <span data-ttu-id="c0f52-230">Essas características incluem informações sobre *quais os funtores que* a operação suporta.</span><span class="sxs-lookup"><span data-stu-id="c0f52-230">Such characteristics include information about which *functors* the operation supports.</span></span>
<span data-ttu-id="c0f52-231">Por exemplo, se o funcionamento da operação depende do estado de outros qubits, então deve apoiar o `Controlled` functor; se a operação tiver um inverso, então deve apoiar o `Adjoint` functor.</span><span class="sxs-lookup"><span data-stu-id="c0f52-231">For example, if the running of the operation relies on the state of other qubits, then it should support the `Controlled` functor; if the operation has an inverse, then it should support the `Adjoint` functor.</span></span>

> [!NOTE]
> <span data-ttu-id="c0f52-232">Este artigo só discute como os funtores alteram a assinatura da operação.</span><span class="sxs-lookup"><span data-stu-id="c0f52-232">This article only discuss how functors alter the operation signature.</span></span> <span data-ttu-id="c0f52-233">Para obter mais detalhes sobre funtores e operações, consulte [Operações e Q# Funções em ](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="c0f52-233">For more details about functors and operations, see [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span> 

<span data-ttu-id="c0f52-234">Para necessitar de suporte para o `Controlled` e/ou `Adjoint` functor num tipo de operação, é necessário adicionar uma anotação que indique as características correspondentes.</span><span class="sxs-lookup"><span data-stu-id="c0f52-234">To require support for the `Controlled` and/or `Adjoint` functor in an operation type, you need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="c0f52-235">A anotação `is Ctl` (por `(Qubit => Unit is Ctl)` exemplo,) indica que a operação é controlável.</span><span class="sxs-lookup"><span data-stu-id="c0f52-235">The annotation `is Ctl` (for example, `(Qubit => Unit is Ctl)`) indicates that the operation is controllable.</span></span> <span data-ttu-id="c0f52-236">Ou seja, a sua execução depende do estado de outro qubit ou qubits.</span><span class="sxs-lookup"><span data-stu-id="c0f52-236">That is, its run relies on the state of another qubit or qubits.</span></span> <span data-ttu-id="c0f52-237">Da mesma forma, a anotação `is Adj` indica que a operação tem um adjacente, ou seja, pode ser "invertida" de tal forma que aplicar sucessivamente uma operação e, em seguida, o seu contíguo a um estado deixa o estado inalterado.</span><span class="sxs-lookup"><span data-stu-id="c0f52-237">Similarly, the annotation `is Adj` indicates that the operation has an adjoint, that is, it can be "inverted" such that successively applying an operation and then its adjoint to a state leaves the state unchanged.</span></span> 

<span data-ttu-id="c0f52-238">Se quiser exigir que uma operação deste tipo suporte tanto o `Adjoint` `Controlled` functor como o functor, pode expressar isto como `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="c0f52-238">If you want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor you can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="c0f52-239">Por exemplo, a operação Pauli incorporada <xref:microsoft.quantum.intrinsic.x> tem tipo `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="c0f52-239">For example, the built-in Pauli <xref:microsoft.quantum.intrinsic.x> operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span> 

<span data-ttu-id="c0f52-240">Um tipo de operação que não suporta nenhum functor é especificado apenas pelo seu tipo de entrada e saída, sem anotação adicional.</span><span class="sxs-lookup"><span data-stu-id="c0f52-240">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>

### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="c0f52-241">Funções e operações por tipo-parametrizadas</span><span class="sxs-lookup"><span data-stu-id="c0f52-241">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="c0f52-242">Os tipos de caloisos podem conter *parâmetros de tipo*.</span><span class="sxs-lookup"><span data-stu-id="c0f52-242">Callable types may contain *type parameters*.</span></span>
<span data-ttu-id="c0f52-243">Utilizar um símbolo prefixado por uma única citação para indicar um parâmetro do tipo; por exemplo, `'A` é um parâmetro de tipo legal.</span><span class="sxs-lookup"><span data-stu-id="c0f52-243">Use a symbol prefixed by a single quote to indicated a type parameter; for example, `'A` is a legal type parameter.</span></span>
<span data-ttu-id="c0f52-244">Para obter mais informações e detalhes sobre como definir as chamadas por parâmetros do tipo, consulte [Operações e Q# Funções em ](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).</span><span class="sxs-lookup"><span data-stu-id="c0f52-244">For more information and details on how to define type-parameterized callables, see [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).</span></span>

<span data-ttu-id="c0f52-245">Um parâmetro do tipo pode aparecer mais de uma vez numa única assinatura.</span><span class="sxs-lookup"><span data-stu-id="c0f52-245">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="c0f52-246">Por exemplo, uma função que aplica outra função a cada elemento de uma matriz e devolve os resultados recolhidos tem a assinatura `(('A[], 'A->'A) -> 'A[])` .</span><span class="sxs-lookup"><span data-stu-id="c0f52-246">For example, a function that applies another function to each element of an array and returns the collected results has the signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="c0f52-247">Da mesma forma, uma função que devolve a composição de duas operações tem a assinatura `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .</span><span class="sxs-lookup"><span data-stu-id="c0f52-247">Similarly, a function that returns the composition of two operations has the signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="c0f52-248">Quando invoca um tipo de chamada parametrizada, todos os argumentos que tenham o mesmo parâmetro do tipo devem ser do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="c0f52-248">When you invoke a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="c0f52-249">Q# não fornece um mecanismo para limitar os tipos possíveis que um utilizador pode substituir por um parâmetro do tipo.</span><span class="sxs-lookup"><span data-stu-id="c0f52-249">Q# does not provide a mechanism for constraining the possible types that a user might substitute for a type parameter.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c0f52-250">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="c0f52-250">Next steps</span></span>

<span data-ttu-id="c0f52-251">Agora que viu todos os tipos que compõem a Q# linguagem, consulte [Expressões Q# tipo](xref:microsoft.quantum.guide.expressions) para aprender a criar e manipular expressões destes vários tipos.</span><span class="sxs-lookup"><span data-stu-id="c0f52-251">Now that you've seen all the types which comprise the Q# language, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) to learn how to create and manipulate expressions of these various types.</span></span>
