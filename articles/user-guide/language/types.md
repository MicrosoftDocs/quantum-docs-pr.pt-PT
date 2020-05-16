---
title: 'Tipos em Q #'
description: Conheça os diferentes tipos utilizados na linguagem de programação Q#.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: 58370193bd62e306197a9e07c28f8611f043e55c
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431143"
---
# <a name="types-in-q"></a><span data-ttu-id="25319-103">Tipos em Q #</span><span class="sxs-lookup"><span data-stu-id="25319-103">Types in Q#</span></span>

<span data-ttu-id="25319-104">Esta página descreve o modelo do tipo Q# e descreve a sintaxe para especificar e trabalhar com tipos.</span><span class="sxs-lookup"><span data-stu-id="25319-104">This page lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>
<span data-ttu-id="25319-105">A página seguinte, [Type Expressions,](xref:microsoft.quantum.guide.expressions)detalha como criar e operar em expressões deste tipo.</span><span class="sxs-lookup"><span data-stu-id="25319-105">The next page, [Type Expressions](xref:microsoft.quantum.guide.expressions), details how to create and operate on expressions of these types.</span></span>

<span data-ttu-id="25319-106">Notamos que q# é uma linguagem *fortemente dactilografada,* de tal forma que uma utilização cuidadosa destes tipos pode ajudar o compilador a fornecer fortes garantias sobre os programas Q# no momento da compilação.</span><span class="sxs-lookup"><span data-stu-id="25319-106">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="25319-107">A fim de fornecer as garantias mais fortes possíveis, as conversões entre tipos em Q# devem ser explícitas utilizando chamadas para funções que expressem essa conversão.</span><span class="sxs-lookup"><span data-stu-id="25319-107">In order to provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="25319-108">Uma variedade dessas funções são fornecidas como parte do espaço de <xref:microsoft.quantum.convert> nome.</span><span class="sxs-lookup"><span data-stu-id="25319-108">A variety of such functions are provided as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="25319-109">As upcasts para tipos compatíveis, por outro lado, acontecem implicitamente.</span><span class="sxs-lookup"><span data-stu-id="25319-109">Upcasts to compatible types on the other hand happen implicitly.</span></span> 

<span data-ttu-id="25319-110">Q# fornece ambos os tipos primitivos, que podem ser usados diretamente, e uma variedade de maneiras de produzir novos tipos de outros tipos.</span><span class="sxs-lookup"><span data-stu-id="25319-110">Q# provides both primitive types, which can be used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="25319-111">Descrevemos cada um no resto desta secção.</span><span class="sxs-lookup"><span data-stu-id="25319-111">We describe each in the rest of this section.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="25319-112">Tipos Primitivos</span><span class="sxs-lookup"><span data-stu-id="25319-112">Primitive Types</span></span>

<span data-ttu-id="25319-113">A língua Q# fornece vários *tipos primitivos,* a partir dos quais outros tipos podem ser construídos:</span><span class="sxs-lookup"><span data-stu-id="25319-113">The Q# language provides several *primitive types*, from which other types can be constructed:</span></span>

- <span data-ttu-id="25319-114">O tipo representa um inteiro assinado de `Int` 64 bits, por exemplo: `2` `107` . `-5`</span><span class="sxs-lookup"><span data-stu-id="25319-114">The `Int` type represents a 64-bit signed integer, e.g.: `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="25319-115">O `BigInt` tipo representa um inteiro assinado de tamanho arbitrário, por `2L` exemplo, `107L` `-5L` .</span><span class="sxs-lookup"><span data-stu-id="25319-115">The `BigInt` type represents a signed integer of arbitrary size, e.g. `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="25319-116">Este tipo baseia-se no .NET<xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="25319-116">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="25319-117">tipo.</span><span class="sxs-lookup"><span data-stu-id="25319-117">type.</span></span>
- <span data-ttu-id="25319-118">O `Double` tipo representa um número de ponto flutuante de dupla precisão, por exemplo: `0.0` . . `-1.3` `4e-7` .</span><span class="sxs-lookup"><span data-stu-id="25319-118">The `Double` type represents a double-precision floating-point number, e.g.: `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="25319-119">O `Bool` tipo representa um valor Boolean o que pode ser ou `true` `false` .</span><span class="sxs-lookup"><span data-stu-id="25319-119">The `Bool` type represents a Boolean value which can either be `true` or `false`.</span></span>
- <span data-ttu-id="25319-120">O `Range` tipo representa uma sequência de inteiros, denotadopor, onde `start..step..stop` denotar o passo são opções.</span><span class="sxs-lookup"><span data-stu-id="25319-120">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is options.</span></span> 
   <span data-ttu-id="25319-121">Isto `start .. stop` corresponde `start..1..stop` a, e por exemplo, `1..2..7` representa a sequência $ \{ 1, 3, 5, 7 \} $.</span><span class="sxs-lookup"><span data-stu-id="25319-121">That is `start .. stop` corresponds to `start..1..stop`, and e.g. `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="25319-122">O `String` tipo é uma sequência de caracteres Unicode que é opaco para o utilizador uma vez criado.</span><span class="sxs-lookup"><span data-stu-id="25319-122">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="25319-123">Este tipo é usado para relatar mensagens a um hospedeiro clássico em caso de erro ou evento de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="25319-123">This type is used to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="25319-124">O `Unit` tipo é do tipo que permite apenas um valor `()` .</span><span class="sxs-lookup"><span data-stu-id="25319-124">The `Unit` type is the type that allows only one value `()`.</span></span> 
  <span data-ttu-id="25319-125">Este tipo é utilizado para indicar que a função ou operação Q# não devolve nenhuma informação.</span><span class="sxs-lookup"><span data-stu-id="25319-125">This type is used to indicate that Q# function or operation returns no information.</span></span> 
- <span data-ttu-id="25319-126">O `Qubit` tipo representa um bit quântico ou qubit.</span><span class="sxs-lookup"><span data-stu-id="25319-126">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="25319-127">`Qubit`s são opacos para o utilizador; a única operação possível com eles, para além de os passar para outra operação, é testar a identidade (igualdade).</span><span class="sxs-lookup"><span data-stu-id="25319-127">`Qubit`s are opaque to the user; the only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="25319-128">Em última análise, as ações em `Qubit` s são implementadas chamando instruções intrínsecas num processador quântico (ou uma simulação do mesmo).</span><span class="sxs-lookup"><span data-stu-id="25319-128">Ultimately, actions on `Qubit`s are implemented by calling intrinsic instructions on a quantum processor (or a simulation thereof).</span></span>
- <span data-ttu-id="25319-129">O `Pauli` tipo representa um dos quatro operadores de Moqubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="25319-129">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="25319-130">Este tipo é utilizado para denotar o funcionamento da base para rotações e para especificar o observável que está a ser medido.</span><span class="sxs-lookup"><span data-stu-id="25319-130">This type is used to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="25319-131">Este é um tipo enumerado que tem quatro valores possíveis: `PauliI` , , e , que são `PauliX` `PauliY` `PauliZ` constantes de `Pauli` tipo.</span><span class="sxs-lookup"><span data-stu-id="25319-131">This is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="25319-132">O `Result` tipo representa o resultado de uma medição.</span><span class="sxs-lookup"><span data-stu-id="25319-132">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="25319-133">Este é um tipo enumerado com dois valores possíveis: `One` `Zero` e, que são constantes de `Result` tipo.</span><span class="sxs-lookup"><span data-stu-id="25319-133">This is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="25319-134">`Zero`indica que o valor +1 foi medido; `One`indica o -1 eigenvalue.</span><span class="sxs-lookup"><span data-stu-id="25319-134">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue.</span></span>

<span data-ttu-id="25319-135">As `true` constantes, , , , , , e são `false` todos `PauliI` `PauliX` `PauliY` `PauliZ` `One` `Zero` símbolos reservados em Q#.</span><span class="sxs-lookup"><span data-stu-id="25319-135">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="25319-136">Tipos de matriz</span><span class="sxs-lookup"><span data-stu-id="25319-136">Array Types</span></span>

<span data-ttu-id="25319-137">Dado qualquer tipo Q# `'T` válido, existe um tipo que representa uma variedade de valores de tipo `'T` .</span><span class="sxs-lookup"><span data-stu-id="25319-137">Given any valid Q# type `'T`, there is a type that represents an array of values of type `'T`.</span></span>
<span data-ttu-id="25319-138">Este tipo de matriz é representado `'T[]` como; por exemplo, `Qubit[]` ou `Int[][]` .</span><span class="sxs-lookup"><span data-stu-id="25319-138">This array type is represented as `'T[]`; for example, `Qubit[]` or `Int[][]`.</span></span>
<span data-ttu-id="25319-139">Por exemplo, uma coleção de inteiros é denotada, `Int[]` enquanto uma série de conjuntos de `(Bool, Pauli)` valores é denotado `(Bool, Pauli)[][]` .</span><span class="sxs-lookup"><span data-stu-id="25319-139">For instance, a collection of integers is denoted `Int[]`, while an array of arrays of `(Bool, Pauli)` values is denoted `(Bool, Pauli)[][]`.</span></span>

<span data-ttu-id="25319-140">No segundo exemplo, note que isto representa uma matriz potencialmente irregular de matrizes, e não uma matriz bidimensional retangular.</span><span class="sxs-lookup"><span data-stu-id="25319-140">In the second example, note that this represents a potentially jagged array of arrays, and not a rectangular two-dimensional array.</span></span>
<span data-ttu-id="25319-141">Q# não fornece suporte para matrizes multidimensionais retangulares.</span><span class="sxs-lookup"><span data-stu-id="25319-141">Q# does not provide support for rectangular multi-dimensional arrays.</span></span>

<span data-ttu-id="25319-142">Um valor de matriz pode ser escrito no código fonte Q# utilizando suportes quadrados em torno dos elementos de uma matriz, como em `[PauliI, PauliX, PauliY, PauliZ]` .</span><span class="sxs-lookup"><span data-stu-id="25319-142">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="25319-143">O tipo de matriz literal é determinado pelo tipo de base comum de todos os itens da matriz.</span><span class="sxs-lookup"><span data-stu-id="25319-143">The type of an array literal is determined by the common base type of all items in the array.</span></span> 

> [!WARNING]
> <span data-ttu-id="25319-144">Os elementos de uma matriz não podem ser alterados após a criação da matriz.</span><span class="sxs-lookup"><span data-stu-id="25319-144">The elements of an array cannot be changed after the array has been created.</span></span>
> <span data-ttu-id="25319-145">[As declarações de atualização e reatribuição](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) e/ou [expressões de cópia e atualização](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) podem ser utilizadas para construir uma matriz modificada.</span><span class="sxs-lookup"><span data-stu-id="25319-145">[Update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) and/or [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) can be used to construct a modified array.</span></span>

<span data-ttu-id="25319-146">Alternativamente, uma matriz pode ser criada a partir do seu tamanho usando a `new` palavra-chave:</span><span class="sxs-lookup"><span data-stu-id="25319-146">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

<span data-ttu-id="25319-147">Em qualquer dos casos, uma vez construída uma matriz, a função central `Length` pode ser utilizada para obter o número de elementos como `Int` .</span><span class="sxs-lookup"><span data-stu-id="25319-147">In either case, once an array has been constructed, the core function `Length` can be used to obtain the number of elements as an `Int`.</span></span>
<span data-ttu-id="25319-148">As matrizes podem ser subscritas utilizando suportes quadrados, com subscripts que tenham tipo `Int` ou `Range` tipo, para obter elementos únicos ou novas matrizes contendo um subconjunto dos elementos de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="25319-148">Arrays can be subscripted using square brackets, with subscripts either having type `Int` or type `Range`, to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="25319-149">Os subscripts de matrizes são baseados em zero:</span><span class="sxs-lookup"><span data-stu-id="25319-149">The subscripts of arrays are zero-based:</span></span>

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a><span data-ttu-id="25319-150">Tipos de tuple</span><span class="sxs-lookup"><span data-stu-id="25319-150">Tuple Types</span></span>

<span data-ttu-id="25319-151">Tendo em conta tipos zero ou mais `T0` `T1` diferentes, `Tn` podemos denotar um novo tipo de *tuple* como `(T0, T1, ..., Tn)` .</span><span class="sxs-lookup"><span data-stu-id="25319-151">Given zero or more different types `T0`, `T1`, ..., `Tn`, we can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="25319-152">Os tipos usados para construir um novo tipo de tuple podem ser tuples, como em `(Int, (Qubit, Qubit))` .</span><span class="sxs-lookup"><span data-stu-id="25319-152">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="25319-153">No entanto, esta nidificação é sempre finita, uma vez que os tipos de tuple não podem, em circunstância alguma, conter-se.</span><span class="sxs-lookup"><span data-stu-id="25319-153">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

<span data-ttu-id="25319-154">Os valores do novo tipo de tuple são tuples formados por sequências de valores de cada tipo na tuple.</span><span class="sxs-lookup"><span data-stu-id="25319-154">Values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="25319-155">Por exemplo, `(3, false)` é uma tuple cujo tipo é do tipo tuple `(Int, Bool)` .</span><span class="sxs-lookup"><span data-stu-id="25319-155">For instance, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="25319-156">É possível criar conjuntos de tuples, tuples de matrizes, tuples de sub-tuples, etc.</span><span class="sxs-lookup"><span data-stu-id="25319-156">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, etc.</span></span>

<span data-ttu-id="25319-157">A partir do Q# 0.3, `Unit` é o nome do *tipo* de tuple vazio; é usado para `()` o *valor*de tuple vazio .</span><span class="sxs-lookup"><span data-stu-id="25319-157">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the empty tuple *value*.</span></span>

<span data-ttu-id="25319-158">Os casos de tuple são imutáveis.</span><span class="sxs-lookup"><span data-stu-id="25319-158">Tuple instances are immutable.</span></span>
<span data-ttu-id="25319-159">Q# não fornece um mecanismo para alterar o conteúdo de uma tuple uma vez criado.</span><span class="sxs-lookup"><span data-stu-id="25319-159">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>

<span data-ttu-id="25319-160">Tuples são um conceito poderoso usado ao longo de Q# para recolher valores juntos em um único valor, tornando mais fácil passá-los ao redor.</span><span class="sxs-lookup"><span data-stu-id="25319-160">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="25319-161">Em particular, usando a notação de tuple, podemos expressar que cada operação e callable leva exatamente uma entrada e devolve exatamente uma saída.</span><span class="sxs-lookup"><span data-stu-id="25319-161">In particular, using tuple notation, we can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="25319-162">Equivalência singleton Tuple</span><span class="sxs-lookup"><span data-stu-id="25319-162">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="25319-163">É possível criar uma tuple singleton (elemento único), `('T1)` como `(5)` ou `([1,2,3])` .</span><span class="sxs-lookup"><span data-stu-id="25319-163">It is possible to create a singleton (single-element) tuple, `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="25319-164">No entanto, Q# trata uma túnica singleton como completamente equivalente a um valor do tipo fechado.</span><span class="sxs-lookup"><span data-stu-id="25319-164">However, Q# treats a singleton tuple as completely equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="25319-165">Ou seja, não há diferença entre `5` `(5)` e, ou entre `5` `(((5)))` e, ou entre `(5, (6))` e `(5, 6)` .</span><span class="sxs-lookup"><span data-stu-id="25319-165">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>
<span data-ttu-id="25319-166">É tão válido escrever `(5)+3` como `5+3` escrever, e ambas as expressões avaliarão para `8` .</span><span class="sxs-lookup"><span data-stu-id="25319-166">It is just as valid to write `(5)+3` as to write `5+3`, and both expressions will evaluate to `8`.</span></span>

<span data-ttu-id="25319-167">Esta equivalência aplica-se a todos os fins, incluindo atribuição e expressões.</span><span class="sxs-lookup"><span data-stu-id="25319-167">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="25319-168">Dada qualquer expressão, essa mesma expressão em parênteses é uma expressão do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="25319-168">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="25319-169">Por exemplo, `(7)` é uma `Int` expressão, é uma expressão de tipo `([1,2,3])` de matriz de `Int` s, e é uma expressão com tipo `((1,2))` `(Int, Int)` .</span><span class="sxs-lookup"><span data-stu-id="25319-169">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="25319-170">Isto significa, em particular, que uma operação ou função cujo tipo de tuple de entrada ou tuple de saída tem um campo pode ser considerado como tendo um único argumento ou devolvendo um único valor.</span><span class="sxs-lookup"><span data-stu-id="25319-170">In particular, this means that an operation or function whose input tuple or output tuple type has one field can be thought of as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="25319-171">Referimo-nos a esta propriedade como _equivalência de tuple singleton._</span><span class="sxs-lookup"><span data-stu-id="25319-171">We refer to this property as _singleton tuple equivalence_.</span></span>


## <a name="user-defined-types"></a><span data-ttu-id="25319-172">Tipos definidos pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="25319-172">User-Defined Types</span></span>

<span data-ttu-id="25319-173">Uma declaração de tipo definido pelo utilizador consiste na palavra-chave, seguida do nome do tipo definido pelo `newtype` utilizador, uma `=` especificação de tipo válido e um ponto evíomina terminando.</span><span class="sxs-lookup"><span data-stu-id="25319-173">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="25319-174">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="25319-174">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```

<span data-ttu-id="25319-175">Cada ficheiro de origem Q# pode declarar qualquer número de tipos definidos pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="25319-175">Each Q# source file may declare any number of user-defined types.</span></span>
<span data-ttu-id="25319-176">Os nomes de tipo devem ser únicos dentro de um espaço de nome e não podem entrar em conflito com nomes de funcionamento e função.</span><span class="sxs-lookup"><span data-stu-id="25319-176">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>

<span data-ttu-id="25319-177">Os tipos definidos pelo utilizador são distintos mesmo que os tipos de base sejam idênticos.</span><span class="sxs-lookup"><span data-stu-id="25319-177">User-defined types are distinct even if the base types are identical.</span></span>
<span data-ttu-id="25319-178">Em particular, não existe uma conversão automática entre valores de dois tipos definidos pelo utilizador, mesmo que os tipos subjacentes sejam idênticos.</span><span class="sxs-lookup"><span data-stu-id="25319-178">In particular, there is no automatic conversion between values of two user-defined types even if the underlying types are identical.</span></span>

### <a name="named-vs-anonymous-items"></a><span data-ttu-id="25319-179">Nomeado vs. itens anónimos</span><span class="sxs-lookup"><span data-stu-id="25319-179">Named vs. anonymous items</span></span>

<span data-ttu-id="25319-180">Um ficheiro Q# pode definir um novo tipo nomeado contendo um único valor de qualquer tipo legal.</span><span class="sxs-lookup"><span data-stu-id="25319-180">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="25319-181">Para qualquer tipo de `T` tuple, podemos declarar um novo tipo definido pelo utilizador que é um subtipo de `T` com a `newtype` declaração.</span><span class="sxs-lookup"><span data-stu-id="25319-181">For any tuple type `T`, we can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="25319-182">No @"microsoft.quantum.math" espaço de nome, por exemplo, os números complexos são definidos como um tipo definido pelo utilizador:</span><span class="sxs-lookup"><span data-stu-id="25319-182">In the @"microsoft.quantum.math" namespace, for instance, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```
<span data-ttu-id="25319-183">Esta afirmação cria um novo tipo com dois itens anónimos de tipo `Double` .</span><span class="sxs-lookup"><span data-stu-id="25319-183">This statement creates a new type with two anonymous items of type `Double`.</span></span>   

<span data-ttu-id="25319-184">Além de itens anónimos, os tipos definidos pelo utilizador também suportam *itens nomeados* a partir da versão Q# 0.7 ou superior.</span><span class="sxs-lookup"><span data-stu-id="25319-184">Aside from anonymous items, user-defined types also support *named items* as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="25319-185">Por exemplo, poderíamos ter nomeado os itens `Re` para o duplo representando a parte real de um número complexo e para a parte `Im` imaginária:</span><span class="sxs-lookup"><span data-stu-id="25319-185">For example, we could have named the to items `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="25319-186">Nomear um item num tipo definido pelo utilizador não implica que todos os itens precisem de ser nomeados - qualquer combinação de itens nomeados e não nomeados é suportado.</span><span class="sxs-lookup"><span data-stu-id="25319-186">Naming one item in a user-defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="25319-187">Além disso, os itens internos também podem ser nomeados.</span><span class="sxs-lookup"><span data-stu-id="25319-187">Furthermore, inner items may also be named.</span></span>
<span data-ttu-id="25319-188">O tipo `Nested` definido abaixo, por exemplo, tem um tipo `(Double, (Int, String))` subjacente, do qual apenas o item do tipo `Int` é nomeado e todos os outros itens são anónimos.</span><span class="sxs-lookup"><span data-stu-id="25319-188">The type `Nested` as defined below for example has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

<span data-ttu-id="25319-189">Os itens nomeados têm a vantagem de poderem ser acedidos diretamente através do *operador* de `::` acesso.</span><span class="sxs-lookup"><span data-stu-id="25319-189">Named items have the advantage that they can be accessed directly via the *access operator* `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="25319-190">Além de fornecer pseudónimos curtos para tipos de tuple potencialmente complicados, uma vantagem significativa de definir tais tipos é que eles podem documentar a intenção de um valor particular.</span><span class="sxs-lookup"><span data-stu-id="25319-190">In addition to providing short aliases for potentially complicated tuple types, one significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="25319-191">Voltando ao exemplo `Complex` de, poderia também ter definido coordenadas polares 2D como um tipo definido pelo utilizador:</span><span class="sxs-lookup"><span data-stu-id="25319-191">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="25319-192">Apesar de ambos `Complex` e ambos terem um tipo `Polar` `(Double, Double)` subjacente, os dois tipos são totalmente incompatíveis em Q#, minimizando o risco de chamar acidentalmente uma função matemática complexa com coordenadas polares e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="25319-192">Even though both `Complex` and `Polar` are both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>
<span data-ttu-id="25319-193">Desta forma, os tipos definidos pelo utilizador têm um papel semelhante ao dos Registos em F# por exemplo.</span><span class="sxs-lookup"><span data-stu-id="25319-193">In this way, user-defined types have a similar role as Records in F# for example.</span></span> 


#### <a name="access-anonymous-items-with-the-unwrap-operator"></a><span data-ttu-id="25319-194">Aceda a itens anónimos com o operador de desembrulhar</span><span class="sxs-lookup"><span data-stu-id="25319-194">Access anonymous items with the unwrap operator</span></span>

<span data-ttu-id="25319-195">Para aceder a itens anónimos, por outro lado, o valor embrulhado primeiro precisa de ser extraído através do operador de postfix `!` .</span><span class="sxs-lookup"><span data-stu-id="25319-195">In order to access anonymous items on the other hand, the wrapped value first needs to be extracted using the postfix operator `!`.</span></span>
<span data-ttu-id="25319-196">O operador "desembrulhar", `!` permite extrair o valor contido num tipo definido pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="25319-196">The "unwrap" operator, `!`, allows to extract the value contained in a user-defined type.</span></span>
<span data-ttu-id="25319-197">O tipo de expressão "desembrulhar" é o tipo subjacente do tipo definido pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="25319-197">The type of such an "unwrap" expression is the underlying type of the user-defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="25319-198">O operador desembrulhar desembrulha exatamente uma camada de embrulho.</span><span class="sxs-lookup"><span data-stu-id="25319-198">The unwrap operator unwraps exactly one layer of wrapping.</span></span>
<span data-ttu-id="25319-199">Vários operadores de desembrulhar podem ser utilizados para aceder a um valor embrulhado multiplicado.</span><span class="sxs-lookup"><span data-stu-id="25319-199">Multiple unwrap operators may be used to access a multiply-wrapped value.</span></span>

<span data-ttu-id="25319-200">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="25319-200">For instance:</span></span>

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

<span data-ttu-id="25319-201">Mais detalhes sobre o operador de desembrulhar podem ser encontrados em [Expressões tipo em Q#](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="25319-201">More details on the unwrap operator can be found at [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span>

### <a name="creating-values-of-user-defined-types"></a><span data-ttu-id="25319-202">Criação de valores de tipos definidos pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="25319-202">Creating values of user-defined types</span></span>

<span data-ttu-id="25319-203">Os valores de um tipo definido pelo utilizador podem ser criados chamando o construtor de tipo correspondente:</span><span class="sxs-lookup"><span data-stu-id="25319-203">Values of a user-defined type can be created by calling the corresponding type constructor:</span></span>

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="25319-204">Alternativamente, novos valores podem ser criados a partir dos existentes usando [expressões de cópia e atualização](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="25319-204">Alternatively, new values can be created from existing ones using [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="25319-205">Tal como para as matrizes, tais expressões copiam todos os valores de item da expressão original, com exceção dos itens nomeados especificados.</span><span class="sxs-lookup"><span data-stu-id="25319-205">Like for arrays, such expressions copy all item values of the original expression, with the exception of the specified named items.</span></span> <span data-ttu-id="25319-206">Para estes, os valores são definidos para os definidos no lado direito da expressão.</span><span class="sxs-lookup"><span data-stu-id="25319-206">For these the values are set to the ones defined on the right hand side of the expression.</span></span> <span data-ttu-id="25319-207">Quaisquer outras construções linguísticas, como, por exemplo, [declarações de atualização e reatribuição,](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)que estejam disponíveis para itens de matriz, existem também para itens nomeados em tipos definidos pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="25319-207">Any other language constructs, like for example [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), that are available for array items exist for named-items in user-defined types as well.</span></span>

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

<span data-ttu-id="25319-208">Os tipos definidos pelo utilizador podem ser utilizados em qualquer outro tipo.</span><span class="sxs-lookup"><span data-stu-id="25319-208">User-defined types may be used anywhere any other type may be used.</span></span>
<span data-ttu-id="25319-209">Em particular, é possível definir um conjunto de um tipo definido pelo utilizador e incluir um tipo definido pelo utilizador como um elemento de um tipo de tuple.</span><span class="sxs-lookup"><span data-stu-id="25319-209">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

<span data-ttu-id="25319-210">Nota não é possível criar estruturas de tipo recursivos.</span><span class="sxs-lookup"><span data-stu-id="25319-210">Note is not possible to create recursive type structures.</span></span>
<span data-ttu-id="25319-211">Ou seja, o tipo que define um tipo definido pelo utilizador pode não ser um tipo de tuple que inclua um elemento do tipo definido pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="25319-211">That is, the type that defines a user-defined type may not be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="25319-212">De um modo mais geral, os tipos definidos pelo utilizador podem não ter dependências cíclicas entre si, pelo que o seguinte conjunto de definições de tipo seria ilegal:</span><span class="sxs-lookup"><span data-stu-id="25319-212">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions would be illegal:</span></span>

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```


## <a name="operation-and-function-types"></a><span data-ttu-id="25319-213">Tipos de Funcionamento e Função</span><span class="sxs-lookup"><span data-stu-id="25319-213">Operation and Function Types</span></span>

<span data-ttu-id="25319-214">O tipo básico para qualquer callable é escrito como `('Tinput => 'Tresult)` ou , onde ambos e tipos `('Tinput -> 'Tresult)` `'Tinput` `'Tresult` são.</span><span class="sxs-lookup"><span data-stu-id="25319-214">The basic type for any callable is written as `('Tinput => 'Tresult)` or `('Tinput -> 'Tresult)`, where both `'Tinput` and `'Tresult` are types.</span></span>
<span data-ttu-id="25319-215">Estes são chamados a *assinatura* do callable.</span><span class="sxs-lookup"><span data-stu-id="25319-215">These are called the *signature* of the callable.</span></span>

<span data-ttu-id="25319-216">Todos os callables Q# são considerados como tendo um único valor como entrada e devolver um único valor como saída.</span><span class="sxs-lookup"><span data-stu-id="25319-216">All Q# callables are considered to take a single value as input and return a single value as output.</span></span>
<span data-ttu-id="25319-217">Tanto os valores de entrada como de saída podem ser tuples.</span><span class="sxs-lookup"><span data-stu-id="25319-217">Both the input and output values may be tuples.</span></span>
<span data-ttu-id="25319-218">Callables que não têm retorno de `Unit` resultados.</span><span class="sxs-lookup"><span data-stu-id="25319-218">Callables that have no result return `Unit`.</span></span>
<span data-ttu-id="25319-219">Os inputáveis que não têm entrada tomam a túnica vazia como entrada.</span><span class="sxs-lookup"><span data-stu-id="25319-219">Callables that have no input take the empty tuple as input.</span></span>

> [!NOTE]
> <span data-ttu-id="25319-220">A primeira forma, `=>` com, é utilizada para operações; a segunda forma, `->` com, para funções.</span><span class="sxs-lookup"><span data-stu-id="25319-220">The first form, with `=>`, is used for operations; the second form, with `->`, for functions.</span></span>
> <span data-ttu-id="25319-221">Por exemplo, `((Qubit, Pauli) => Result)` representa a assinatura para uma possível operação de medição de qubit único.</span><span class="sxs-lookup"><span data-stu-id="25319-221">For example, `((Qubit, Pauli) => Result)` represents the signature for a possible single-qubit measurement operation.</span></span>
<span data-ttu-id="25319-222">Os tipos de *funções* são completamente especificados pela sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="25319-222">*Function* types are completely specified by their signature.</span></span>
<span data-ttu-id="25319-223">Por exemplo, uma função que computa o seno de um ângulo teria tipo `(Double -> Double)` .</span><span class="sxs-lookup"><span data-stu-id="25319-223">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span>

<span data-ttu-id="25319-224">*Operações*---mas não funções---têm certas características adicionais que são expressas como parte do tipo de operação.</span><span class="sxs-lookup"><span data-stu-id="25319-224">*Operations*---but not functions---have certain additional characteristics that are expressed as part of the operation type.</span></span> <span data-ttu-id="25319-225">Estas características incluem informações sobre os *functores* que a operação suporta.</span><span class="sxs-lookup"><span data-stu-id="25319-225">Such characteristics include information about what *functors* the operation supports.</span></span>
<span data-ttu-id="25319-226">Por exemplo, se a execução da operação puder ser condicionada ao estado de outros qubits, deve apoiar o `Controlled` functor; se a operação tiver um inverso, deverá apoiar o `Adjoint` functor.</span><span class="sxs-lookup"><span data-stu-id="25319-226">For example, if execution of the operation can be conditioned on the state of other qubits, it should support the `Controlled` functor; if the operation has an inverse, it should support the `Adjoint` functor.</span></span> <span data-ttu-id="25319-227">Os functores e as operações são discutidos detalhadamente nas [Operações e Funções em Q#](xref:microsoft.quantum.guide.operationsfunctions), mas aqui simplesmente discutimos como isso altera a assinatura da operação.</span><span class="sxs-lookup"><span data-stu-id="25319-227">Functors and operations are discussed in detail at [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions), but here we simply discuss how this alters the operation signature.</span></span>

<span data-ttu-id="25319-228">Para exigir apoio ao `Controlled` functor e/ou `Adjoint` functor num tipo de operação, precisamos adicionar uma anotação indicando as características correspondentes.</span><span class="sxs-lookup"><span data-stu-id="25319-228">In order to require support for the `Controlled` and/or `Adjoint` functor in an operation type, we need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="25319-229">Uma anotação `is Ctl` (por `(Qubit => Unit is Ctl)` exemplo) indica que a operação é controlável--- ou seja, é a execução condicionada no estado de outro qubit ou qubits.</span><span class="sxs-lookup"><span data-stu-id="25319-229">An annotation `is Ctl` (e.g. `(Qubit => Unit is Ctl)`) indicates that the operation is controllable---that is, it's execution conditioned on the state of another qubit or qubits.</span></span> <span data-ttu-id="25319-230">Da mesma forma, `is Adj` indica que a operação tem um adjoint; ou simplesmente, pode ser "invertida" de modo a que sucessivamente aplique uma operação e, em seguida, o seu adjoint a um Estado deixe o Estado inalterado.</span><span class="sxs-lookup"><span data-stu-id="25319-230">Similarly, `is Adj` indicates that the operation has an adjoint; or simply, it can be "inverted" such that successively applying an operation and then its adjoint to a state leaves the state unchanged.</span></span> 

<span data-ttu-id="25319-231">Se quisermos exigir que uma operação desse tipo suporte tanto o `Adjoint` functor como o `Controlled` functor podemos expressar isto como `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="25319-231">If we want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor we can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="25319-232">Por exemplo, a operação Pauli incorporada <xref:microsoft.quantum.intrinsic.x> tem tipo `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="25319-232">For example, the built-in Pauli <xref:microsoft.quantum.intrinsic.x> operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span> 

<span data-ttu-id="25319-233">Um tipo de funcionamento que não suporta functores é especificado apenas pelo seu tipo de entrada e saída, sem anotação adicional.</span><span class="sxs-lookup"><span data-stu-id="25319-233">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>

### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="25319-234">Funções e operações parametrizadas tipo</span><span class="sxs-lookup"><span data-stu-id="25319-234">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="25319-235">Os tipos de callable podem conter parâmetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="25319-235">Callable types may contain type parameters.</span></span>
<span data-ttu-id="25319-236">Os parâmetros do tipo são indicados por um símbolo prefixado por uma única citação; por exemplo, `'A` é um parâmetro de tipo legal.</span><span class="sxs-lookup"><span data-stu-id="25319-236">Type parameters are indicated by a symbol prefixed by a single quote; for example, `'A` is a legal type parameter.</span></span>
<span data-ttu-id="25319-237">Os detalhes sobre a definição de callables parâmetros tipo são fornecidos na página [Operações e Funções na](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) página Q# .</span><span class="sxs-lookup"><span data-stu-id="25319-237">Details on defining type-parameterized callables are provided on the [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) page.</span></span>

<span data-ttu-id="25319-238">Um parâmetro de tipo pode aparecer mais de uma vez numa única assinatura.</span><span class="sxs-lookup"><span data-stu-id="25319-238">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="25319-239">Por exemplo, uma função que aplica outra função a cada elemento de uma matriz e devolve os resultados recolhidos teria assinatura `(('A[], 'A->'A) -> 'A[])` .</span><span class="sxs-lookup"><span data-stu-id="25319-239">For example, a function that applies another function to each element of an array and returns the collected results would have signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="25319-240">Da mesma forma, uma função que retorne a composição de duas operações pode ter assinatura `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .</span><span class="sxs-lookup"><span data-stu-id="25319-240">Similarly, a function that returns the composition of two operations might have signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="25319-241">Ao invocar um tipo de escala tometável, todos os argumentos que tenham o mesmo parâmetro devem ser do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="25319-241">When invoking a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="25319-242">Q# não fornece um mecanismo para limitar os tipos possíveis que podem ser substituídos por um parâmetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="25319-242">Q# does not provide a mechanism for constraining the possible types that might be substituted for a type parameter.</span></span>

## <a name="whats-next"></a><span data-ttu-id="25319-243">O que se segue?</span><span class="sxs-lookup"><span data-stu-id="25319-243">What's Next?</span></span>
<span data-ttu-id="25319-244">Agora que já viu todos os tipos que compõem a língua Q#, pode dirigir-se a [Type Expressions em Q#](xref:microsoft.quantum.guide.expressions) para ver como criar e manipular expressões destes vários tipos.</span><span class="sxs-lookup"><span data-stu-id="25319-244">Now that you've seen all the types which comprise the Q# language, you can head to [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) to see how to create and manipulate expressions of these various types.</span></span>


