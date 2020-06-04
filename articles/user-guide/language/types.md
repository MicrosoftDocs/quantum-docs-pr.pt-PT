---
title: Tipos em Q#
description: Saiba mais sobre os diferentes tipos utilizados na linguagem de programação Q#.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: f7a3ac3813966c0ef695068297ce4d9949ead554
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327293"
---
# <a name="types-in-q"></a><span data-ttu-id="8696f-103">Tipos em Q#</span><span class="sxs-lookup"><span data-stu-id="8696f-103">Types in Q#</span></span>

<span data-ttu-id="8696f-104">Esta página define o modelo do tipo Q# e descreve a sintaxe para especificar e trabalhar com tipos.</span><span class="sxs-lookup"><span data-stu-id="8696f-104">This page lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>
<span data-ttu-id="8696f-105">Na página seguinte, [Tipo Expressões,](xref:microsoft.quantum.guide.expressions)detalha como criar e operar em expressões deste tipo.</span><span class="sxs-lookup"><span data-stu-id="8696f-105">The next page, [Type Expressions](xref:microsoft.quantum.guide.expressions), details how to create and operate on expressions of these types.</span></span>

<span data-ttu-id="8696f-106">Notamos que Q# é uma linguagem *fortemente dactilografada,* de modo que o uso cuidadoso destes tipos pode ajudar o compilador a fornecer garantias fortes sobre os programas Q# no momento da compilação.</span><span class="sxs-lookup"><span data-stu-id="8696f-106">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="8696f-107">Para fornecer as garantias mais fortes possíveis, as conversões entre os tipos em Q# devem ser explícitas utilizando chamadas para funções que expressem essa conversão.</span><span class="sxs-lookup"><span data-stu-id="8696f-107">In order to provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="8696f-108">Uma variedade de tais funções são fornecidas como parte do espaço de <xref:microsoft.quantum.convert> nome.</span><span class="sxs-lookup"><span data-stu-id="8696f-108">A variety of such functions are provided as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="8696f-109">Por outro lado, os upcasts para tipos compatíveis acontecem implicitamente.</span><span class="sxs-lookup"><span data-stu-id="8696f-109">Upcasts to compatible types on the other hand happen implicitly.</span></span> 

<span data-ttu-id="8696f-110">Q# fornece ambos os tipos primitivos, que podem ser usados diretamente, e uma variedade de maneiras de produzir novos tipos de outros tipos.</span><span class="sxs-lookup"><span data-stu-id="8696f-110">Q# provides both primitive types, which can be used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="8696f-111">Descrevemos cada um no resto desta secção.</span><span class="sxs-lookup"><span data-stu-id="8696f-111">We describe each in the rest of this section.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="8696f-112">Tipos Primitivos</span><span class="sxs-lookup"><span data-stu-id="8696f-112">Primitive Types</span></span>

<span data-ttu-id="8696f-113">A língua Q# fornece vários *tipos primitivos,* a partir dos quais outros tipos podem ser construídos:</span><span class="sxs-lookup"><span data-stu-id="8696f-113">The Q# language provides several *primitive types*, from which other types can be constructed:</span></span>

- <span data-ttu-id="8696f-114">O `Int` tipo representa um número inteiro assinado de 64 bits, por exemplo: . . `2` . . . `107` `-5` .</span><span class="sxs-lookup"><span data-stu-id="8696f-114">The `Int` type represents a 64-bit signed integer, e.g.: `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="8696f-115">O `BigInt` tipo representa um número inteiro assinado de tamanho arbitrário, por `2L` `107L` exemplo, . `-5L` .</span><span class="sxs-lookup"><span data-stu-id="8696f-115">The `BigInt` type represents a signed integer of arbitrary size, e.g. `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="8696f-116">Este tipo baseia-se no .NET<xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="8696f-116">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="8696f-117">tipo.</span><span class="sxs-lookup"><span data-stu-id="8696f-117">type.</span></span>
- <span data-ttu-id="8696f-118">O `Double` tipo representa um número de ponto flutuante de dupla precisão, por exemplo: `0.0` . . . `-1.3` `4e-7` .</span><span class="sxs-lookup"><span data-stu-id="8696f-118">The `Double` type represents a double-precision floating-point number, e.g.: `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="8696f-119">O `Bool` tipo representa um valor Boolean que pode ser ou `true` `false` .</span><span class="sxs-lookup"><span data-stu-id="8696f-119">The `Bool` type represents a Boolean value which can either be `true` or `false`.</span></span>
- <span data-ttu-id="8696f-120">O `Range` tipo representa uma sequência de inteiros, denotada `start..step..stop` por, onde denotar o passo é opcional.</span><span class="sxs-lookup"><span data-stu-id="8696f-120">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is optional.</span></span> 
   <span data-ttu-id="8696f-121">Isto corresponde a , e por `start .. stop` `start..1..stop` exemplo, `1..2..7` representa a sequência $ \{ 1, 3, 5, 7 \} $.</span><span class="sxs-lookup"><span data-stu-id="8696f-121">That is `start .. stop` corresponds to `start..1..stop`, and e.g. `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="8696f-122">O `String` tipo é uma sequência de caracteres Unicode que é opaco para o utilizador uma vez criado.</span><span class="sxs-lookup"><span data-stu-id="8696f-122">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="8696f-123">Este tipo é utilizado para reportar mensagens a um anfitrião clássico em caso de erro ou evento de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="8696f-123">This type is used to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="8696f-124">O `Unit` tipo é o tipo que permite apenas um `()` valor.</span><span class="sxs-lookup"><span data-stu-id="8696f-124">The `Unit` type is the type that allows only one value `()`.</span></span> 
  <span data-ttu-id="8696f-125">Este tipo é utilizado para indicar que a função Q# ou a operação não retorna nenhuma informação.</span><span class="sxs-lookup"><span data-stu-id="8696f-125">This type is used to indicate that Q# function or operation returns no information.</span></span> 
- <span data-ttu-id="8696f-126">O `Qubit` tipo representa um bit quântico ou qubit.</span><span class="sxs-lookup"><span data-stu-id="8696f-126">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="8696f-127">`Qubit`s são opacos para o utilizador; a única operação possível com eles, para além de passá-los para outra operação, é testar a identidade (igualdade).</span><span class="sxs-lookup"><span data-stu-id="8696f-127">`Qubit`s are opaque to the user; the only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="8696f-128">Em última análise, as ações em `Qubit` s são implementadas chamando instruções intrínsecas num processador quântico (ou uma simulação dos mesmos).</span><span class="sxs-lookup"><span data-stu-id="8696f-128">Ultimately, actions on `Qubit`s are implemented by calling intrinsic instructions on a quantum processor (or a simulation thereof).</span></span>
- <span data-ttu-id="8696f-129">O `Pauli` tipo representa um dos quatro operadores pauli de um único qubit.</span><span class="sxs-lookup"><span data-stu-id="8696f-129">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="8696f-130">Este tipo é utilizado para denotar a operação base para rotações e especificar o que está a ser medido.</span><span class="sxs-lookup"><span data-stu-id="8696f-130">This type is used to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="8696f-131">Este é um tipo enumerado que tem quatro valores possíveis: `PauliI` `PauliX` , , `PauliY` `PauliZ` e, que são constantes de tipo `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="8696f-131">This is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="8696f-132">O `Result` tipo representa o resultado de uma medição.</span><span class="sxs-lookup"><span data-stu-id="8696f-132">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="8696f-133">Este é um tipo enumerado com dois valores possíveis: `One` `Zero` e, que são constantes do tipo `Result` .</span><span class="sxs-lookup"><span data-stu-id="8696f-133">This is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="8696f-134">`Zero`indica que o valor de +1 eigen foi medido; `One`indica o -1 eigenvalue.</span><span class="sxs-lookup"><span data-stu-id="8696f-134">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue.</span></span>

<span data-ttu-id="8696f-135">As constantes `true` , , , , , , , e são `false` todos `PauliI` `PauliX` `PauliY` `PauliZ` `One` `Zero` símbolos reservados em Q#.</span><span class="sxs-lookup"><span data-stu-id="8696f-135">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="8696f-136">Tipos de Matrizes</span><span class="sxs-lookup"><span data-stu-id="8696f-136">Array Types</span></span>

<span data-ttu-id="8696f-137">Dado qualquer tipo Q# `'T` válido, existe um tipo que representa uma matriz de valores do tipo `'T` .</span><span class="sxs-lookup"><span data-stu-id="8696f-137">Given any valid Q# type `'T`, there is a type that represents an array of values of type `'T`.</span></span>
<span data-ttu-id="8696f-138">Este tipo de matriz é representado `'T[]` como; por exemplo, `Qubit[]` ou `Int[][]` .</span><span class="sxs-lookup"><span data-stu-id="8696f-138">This array type is represented as `'T[]`; for example, `Qubit[]` or `Int[][]`.</span></span>
<span data-ttu-id="8696f-139">Por exemplo, uma coleção de inteiros é denotada, `Int[]` enquanto uma variedade de matrizes de `(Bool, Pauli)` valores é denotada `(Bool, Pauli)[][]` .</span><span class="sxs-lookup"><span data-stu-id="8696f-139">For instance, a collection of integers is denoted `Int[]`, while an array of arrays of `(Bool, Pauli)` values is denoted `(Bool, Pauli)[][]`.</span></span>

<span data-ttu-id="8696f-140">No segundo exemplo, note que isto representa uma matriz potencialmente irregular de matrizes, e não uma matriz bidimensional retangular.</span><span class="sxs-lookup"><span data-stu-id="8696f-140">In the second example, note that this represents a potentially jagged array of arrays, and not a rectangular two-dimensional array.</span></span>
<span data-ttu-id="8696f-141">Q# não fornece suporte para matrizes multidimensionais retangulares.</span><span class="sxs-lookup"><span data-stu-id="8696f-141">Q# does not provide support for rectangular multi-dimensional arrays.</span></span>

<span data-ttu-id="8696f-142">Um valor de matriz pode ser escrito no código fonte Q# utilizando suportes quadrados em torno dos elementos de uma matriz, como em `[PauliI, PauliX, PauliY, PauliZ]` .</span><span class="sxs-lookup"><span data-stu-id="8696f-142">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="8696f-143">O tipo de matriz literal é determinado pelo tipo de base comum de todos os itens da matriz.</span><span class="sxs-lookup"><span data-stu-id="8696f-143">The type of an array literal is determined by the common base type of all items in the array.</span></span> <span data-ttu-id="8696f-144">Assim, tentar construir uma matriz com elementos que não têm um tipo de base comum levantará um erro.</span><span class="sxs-lookup"><span data-stu-id="8696f-144">Hence trying to construct an array with elements that have no common base type will raise an error.</span></span>  
<span data-ttu-id="8696f-145">Consulte [as matrizes de chamadas](xref:microsoft.quantum.guide.expressions#arrays-of-callables) para um exemplo disso.</span><span class="sxs-lookup"><span data-stu-id="8696f-145">See [arrays of callables](xref:microsoft.quantum.guide.expressions#arrays-of-callables) for an example of this.</span></span>

> [!WARNING]
> <span data-ttu-id="8696f-146">Os elementos de uma matriz não podem ser alterados após a criação da matriz.</span><span class="sxs-lookup"><span data-stu-id="8696f-146">The elements of an array cannot be changed after the array has been created.</span></span>
> <span data-ttu-id="8696f-147">[As declarações de atualização e reatribuição](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) e/ou [expressões de cópia e atualização](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) podem ser usadas para construir uma matriz modificada.</span><span class="sxs-lookup"><span data-stu-id="8696f-147">[Update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) and/or [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) can be used to construct a modified array.</span></span>

<span data-ttu-id="8696f-148">Alternativamente, uma matriz pode ser criada a partir do seu tamanho usando a `new` palavra-chave:</span><span class="sxs-lookup"><span data-stu-id="8696f-148">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

<span data-ttu-id="8696f-149">Em qualquer dos casos, uma vez construída uma matriz, a função central `Length` pode ser usada para obter o número de elementos como `Int` .</span><span class="sxs-lookup"><span data-stu-id="8696f-149">In either case, once an array has been constructed, the core function `Length` can be used to obtain the number of elements as an `Int`.</span></span>
<span data-ttu-id="8696f-150">As matrizes podem ser subscritadas utilizando suportes quadrados, com subscritos com tipo `Int` ou `Range` tipo, para obter elementos únicos ou novos arrays que contenham um subconjunto dos elementos de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="8696f-150">Arrays can be subscripted using square brackets, with subscripts either having type `Int` or type `Range`, to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="8696f-151">Os subscritos de matrizes são baseados em zero:</span><span class="sxs-lookup"><span data-stu-id="8696f-151">The subscripts of arrays are zero-based:</span></span>

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a><span data-ttu-id="8696f-152">Tipos tuple</span><span class="sxs-lookup"><span data-stu-id="8696f-152">Tuple Types</span></span>

<span data-ttu-id="8696f-153">Dado zero ou mais tipos `T0` `T1` diferentes, podemos `Tn` denotar um novo *tipo de tuple* como `(T0, T1, ..., Tn)` .</span><span class="sxs-lookup"><span data-stu-id="8696f-153">Given zero or more different types `T0`, `T1`, ..., `Tn`, we can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="8696f-154">Os tipos usados para construir um novo tipo de tuple podem ser tuples, como em `(Int, (Qubit, Qubit))` .</span><span class="sxs-lookup"><span data-stu-id="8696f-154">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="8696f-155">No entanto, esse nidificação é sempre finito, uma vez que os tipos de tuple não podem, em circunstância alguma, conter-se.</span><span class="sxs-lookup"><span data-stu-id="8696f-155">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

<span data-ttu-id="8696f-156">Os valores do novo tipo tuple são tuples formados por sequências de valores de cada tipo no tuple.</span><span class="sxs-lookup"><span data-stu-id="8696f-156">Values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="8696f-157">Por exemplo, `(3, false)` é um tuple cujo tipo é o tipo tuple `(Int, Bool)` .</span><span class="sxs-lookup"><span data-stu-id="8696f-157">For instance, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="8696f-158">É possível criar matrizes de tuples, tuples de matrizes, tuples de sub-tuples, etc.</span><span class="sxs-lookup"><span data-stu-id="8696f-158">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, etc.</span></span>

<span data-ttu-id="8696f-159">A partir de Q# 0.3, `Unit` é o nome do *tipo* de tuple vazio; é usado para `()` o *valor*de tuple vazio .</span><span class="sxs-lookup"><span data-stu-id="8696f-159">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the empty tuple *value*.</span></span>

<span data-ttu-id="8696f-160">As instâncias de tuple são imutáveis.</span><span class="sxs-lookup"><span data-stu-id="8696f-160">Tuple instances are immutable.</span></span>
<span data-ttu-id="8696f-161">Q# não fornece um mecanismo para alterar o conteúdo de um tuple uma vez criado.</span><span class="sxs-lookup"><span data-stu-id="8696f-161">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>

<span data-ttu-id="8696f-162">Tuples é um conceito poderoso usado ao longo de Q# para recolher valores juntos em um único valor, tornando mais fácil passá-los ao redor.</span><span class="sxs-lookup"><span data-stu-id="8696f-162">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="8696f-163">Em particular, usando a notação de tuple, podemos expressar que cada operação e callable leva exatamente uma entrada e devolve exatamente uma saída.</span><span class="sxs-lookup"><span data-stu-id="8696f-163">In particular, using tuple notation, we can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="8696f-164">Equivalência de Tuple Singleton</span><span class="sxs-lookup"><span data-stu-id="8696f-164">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="8696f-165">É possível criar um tuple singleton (single-element), `('T1)` como `(5)` ou `([1,2,3])` .</span><span class="sxs-lookup"><span data-stu-id="8696f-165">It is possible to create a singleton (single-element) tuple, `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="8696f-166">No entanto, Q# trata um tuple singleton como completamente equivalente a um valor do tipo fechado.</span><span class="sxs-lookup"><span data-stu-id="8696f-166">However, Q# treats a singleton tuple as completely equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="8696f-167">Ou seja, não há diferença entre `5` `(5)` e, ou entre `5` `(((5)))` e, ou entre `(5, (6))` e `(5, 6)` .</span><span class="sxs-lookup"><span data-stu-id="8696f-167">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>
<span data-ttu-id="8696f-168">É igualmente válido escrever `(5)+3` como `5+3` escrever, e ambas as expressões irão avaliar para `8` .</span><span class="sxs-lookup"><span data-stu-id="8696f-168">It is just as valid to write `(5)+3` as to write `5+3`, and both expressions will evaluate to `8`.</span></span>

<span data-ttu-id="8696f-169">Esta equivalência aplica-se para todos os efeitos, incluindo atribuição e expressões.</span><span class="sxs-lookup"><span data-stu-id="8696f-169">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="8696f-170">Dada qualquer expressão, a mesma expressão em anexo em parênteses é uma expressão do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="8696f-170">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="8696f-171">Por exemplo, `(7)` é uma `Int` expressão, é uma expressão do tipo `([1,2,3])` de matriz de `Int` s, e é uma expressão com tipo `((1,2))` `(Int, Int)` .</span><span class="sxs-lookup"><span data-stu-id="8696f-171">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="8696f-172">Isto significa, em particular, que uma operação ou função cujo tipo de tuple de entrada ou de saída tem um campo pode ser considerado como tendo um único argumento ou devolvendo um único valor.</span><span class="sxs-lookup"><span data-stu-id="8696f-172">In particular, this means that an operation or function whose input tuple or output tuple type has one field can be thought of as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="8696f-173">Referimo-nos a esta propriedade como _equivalência de tuple singleton._</span><span class="sxs-lookup"><span data-stu-id="8696f-173">We refer to this property as _singleton tuple equivalence_.</span></span>


## <a name="user-defined-types"></a><span data-ttu-id="8696f-174">Tipos definidos pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="8696f-174">User-Defined Types</span></span>

<span data-ttu-id="8696f-175">Uma declaração de tipo definido pelo utilizador consiste na `newtype` palavra-chave, seguida do nome do tipo definido pelo utilizador, `=` uma especificação de tipo válido e um ponto de terminação.</span><span class="sxs-lookup"><span data-stu-id="8696f-175">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="8696f-176">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8696f-176">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```

<span data-ttu-id="8696f-177">Cada ficheiro de origem Q# pode declarar qualquer número de tipos definidos pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="8696f-177">Each Q# source file may declare any number of user-defined types.</span></span>
<span data-ttu-id="8696f-178">Os nomes de tipo devem ser únicos dentro de um espaço de nome e não podem entrar em conflito com o funcionamento e os nomes das funções.</span><span class="sxs-lookup"><span data-stu-id="8696f-178">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>

<span data-ttu-id="8696f-179">Os tipos definidos pelo utilizador são distintos mesmo que os tipos de base sejam idênticos.</span><span class="sxs-lookup"><span data-stu-id="8696f-179">User-defined types are distinct even if the base types are identical.</span></span>
<span data-ttu-id="8696f-180">Em particular, não existe uma conversão automática entre valores de dois tipos definidos pelo utilizador, mesmo que os tipos subjacentes sejam idênticos.</span><span class="sxs-lookup"><span data-stu-id="8696f-180">In particular, there is no automatic conversion between values of two user-defined types even if the underlying types are identical.</span></span>

### <a name="named-vs-anonymous-items"></a><span data-ttu-id="8696f-181">Nomeados vs. itens anónimos</span><span class="sxs-lookup"><span data-stu-id="8696f-181">Named vs. anonymous items</span></span>

<span data-ttu-id="8696f-182">Um ficheiro Q# pode definir um novo tipo nomeado contendo um único valor de qualquer tipo legal.</span><span class="sxs-lookup"><span data-stu-id="8696f-182">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="8696f-183">Para qualquer tipo de `T` tuple, podemos declarar um novo tipo definido pelo utilizador que é um subtipo de `T` com a `newtype` declaração.</span><span class="sxs-lookup"><span data-stu-id="8696f-183">For any tuple type `T`, we can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="8696f-184">No @"microsoft.quantum.math" espaço de nomes, por exemplo, os números complexos são definidos como um tipo definido pelo utilizador:</span><span class="sxs-lookup"><span data-stu-id="8696f-184">In the @"microsoft.quantum.math" namespace, for instance, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```
<span data-ttu-id="8696f-185">Esta afirmação cria um novo tipo com dois itens anónimos do tipo `Double` .</span><span class="sxs-lookup"><span data-stu-id="8696f-185">This statement creates a new type with two anonymous items of type `Double`.</span></span>   

<span data-ttu-id="8696f-186">Além de itens anónimos, os tipos definidos pelo utilizador também *suportam itens nomeados* a partir da versão Q# 0.7 ou superior.</span><span class="sxs-lookup"><span data-stu-id="8696f-186">Aside from anonymous items, user-defined types also support *named items* as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="8696f-187">Por exemplo, poderíamos ter nomeado os itens `Re` para o duplo representando a parte real de um número complexo e para a parte `Im` imaginária:</span><span class="sxs-lookup"><span data-stu-id="8696f-187">For example, we could have named the to items `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="8696f-188">Nomear um item num tipo definido pelo utilizador não implica que todos os itens precisem de ser nomeados - qualquer combinação de itens nomeados e não nomeados é suportada.</span><span class="sxs-lookup"><span data-stu-id="8696f-188">Naming one item in a user-defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="8696f-189">Além disso, os itens internos também podem ser nomeados.</span><span class="sxs-lookup"><span data-stu-id="8696f-189">Furthermore, inner items may also be named.</span></span>
<span data-ttu-id="8696f-190">O tipo `Nested` definido abaixo, por exemplo, tem um tipo `(Double, (Int, String))` subjacente, do qual apenas o item do tipo `Int` é nomeado e todos os outros itens são anónimos.</span><span class="sxs-lookup"><span data-stu-id="8696f-190">The type `Nested` as defined below for example has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

<span data-ttu-id="8696f-191">Os itens nomeados têm a vantagem de poderem ser acedidos diretamente através do *operador de acesso.* `::`</span><span class="sxs-lookup"><span data-stu-id="8696f-191">Named items have the advantage that they can be accessed directly via the *access operator* `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="8696f-192">Além de fornecer pseudónimos curtos para tipos de tuple potencialmente complicados, uma vantagem significativa de definir tais tipos é que eles podem documentar a intenção de um determinado valor.</span><span class="sxs-lookup"><span data-stu-id="8696f-192">In addition to providing short aliases for potentially complicated tuple types, one significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="8696f-193">Voltando ao exemplo de `Complex` , poderia também ter definido coordenadas polares 2D como um tipo definido pelo utilizador:</span><span class="sxs-lookup"><span data-stu-id="8696f-193">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="8696f-194">Apesar de ambos `Complex` e ambos terem um tipo `Polar` `(Double, Double)` subjacente, os dois tipos são totalmente incompatíveis em Q#, minimizando o risco de acidentalmente chamar uma função matemática complexa com coordenadas polares e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="8696f-194">Even though both `Complex` and `Polar` are both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>
<span data-ttu-id="8696f-195">Desta forma, os tipos definidos pelo utilizador têm um papel semelhante ao Records em F# por exemplo.</span><span class="sxs-lookup"><span data-stu-id="8696f-195">In this way, user-defined types have a similar role as Records in F# for example.</span></span> 


#### <a name="access-anonymous-items-with-the-unwrap-operator"></a><span data-ttu-id="8696f-196">Aceda a itens anónimos com o operador de desembrulhar</span><span class="sxs-lookup"><span data-stu-id="8696f-196">Access anonymous items with the unwrap operator</span></span>

<span data-ttu-id="8696f-197">Por outro lado, para aceder a itens anónimos, o valor embrulhado tem primeiro de ser extraído através do operador de pós-estan `!` fixação .</span><span class="sxs-lookup"><span data-stu-id="8696f-197">In order to access anonymous items on the other hand, the wrapped value first needs to be extracted using the postfix operator `!`.</span></span>
<span data-ttu-id="8696f-198">O operador "desembrulhar", `!` permite extrair o valor contido num tipo definido pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="8696f-198">The "unwrap" operator, `!`, allows to extract the value contained in a user-defined type.</span></span>
<span data-ttu-id="8696f-199">O tipo de expressão "desembrulhar" é o tipo subjacente do tipo definido pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="8696f-199">The type of such an "unwrap" expression is the underlying type of the user-defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="8696f-200">O operador desembrulha exatamente uma camada de embrulho.</span><span class="sxs-lookup"><span data-stu-id="8696f-200">The unwrap operator unwraps exactly one layer of wrapping.</span></span>
<span data-ttu-id="8696f-201">Vários operadores de desembrulhásse podem ser utilizados para aceder a um valor multiplicado.</span><span class="sxs-lookup"><span data-stu-id="8696f-201">Multiple unwrap operators may be used to access a multiply-wrapped value.</span></span>

<span data-ttu-id="8696f-202">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8696f-202">For instance:</span></span>

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

<span data-ttu-id="8696f-203">Mais detalhes sobre o operador de desembrulhar podem ser [encontrados em Expressões Tipo em Q#](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="8696f-203">More details on the unwrap operator can be found at [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span>

### <a name="creating-values-of-user-defined-types"></a><span data-ttu-id="8696f-204">Criação de valores de tipos definidos pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="8696f-204">Creating values of user-defined types</span></span>

<span data-ttu-id="8696f-205">Os valores de um tipo definido pelo utilizador podem ser criados chamando o construtor de tipo correspondente:</span><span class="sxs-lookup"><span data-stu-id="8696f-205">Values of a user-defined type can be created by calling the corresponding type constructor:</span></span>

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="8696f-206">Alternativamente, novos valores podem ser criados a partir dos existentes usando [expressões de cópia e atualização](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="8696f-206">Alternatively, new values can be created from existing ones using [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="8696f-207">Tal como para as matrizes, tais expressões copiam todos os valores de item da expressão original, com exceção dos itens nomeados especificados.</span><span class="sxs-lookup"><span data-stu-id="8696f-207">Like for arrays, such expressions copy all item values of the original expression, with the exception of the specified named items.</span></span> <span data-ttu-id="8696f-208">Para estes os valores são definidos no lado direito da expressão.</span><span class="sxs-lookup"><span data-stu-id="8696f-208">For these the values are set to the ones defined on the right hand side of the expression.</span></span> <span data-ttu-id="8696f-209">Quaisquer outras construções linguísticas, como por [exemplo, declarações de atualização e reatribuição,](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)que estejam disponíveis para itens de matriz existem para itens nomeados em tipos definidos pelo utilizador também.</span><span class="sxs-lookup"><span data-stu-id="8696f-209">Any other language constructs, like for example [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), that are available for array items exist for named-items in user-defined types as well.</span></span>

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

<span data-ttu-id="8696f-210">Os tipos definidos pelo utilizador podem ser utilizados em qualquer outro tipo que possa ser utilizado.</span><span class="sxs-lookup"><span data-stu-id="8696f-210">User-defined types may be used anywhere any other type may be used.</span></span>
<span data-ttu-id="8696f-211">Em particular, é possível definir uma matriz de um tipo definido pelo utilizador e incluir um tipo definido pelo utilizador como elemento de um tipo de tuple.</span><span class="sxs-lookup"><span data-stu-id="8696f-211">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

<span data-ttu-id="8696f-212">Nota não é possível criar estruturas de tipo recursivo.</span><span class="sxs-lookup"><span data-stu-id="8696f-212">Note is not possible to create recursive type structures.</span></span>
<span data-ttu-id="8696f-213">Ou seja, o tipo que define um tipo definido pelo utilizador pode não ser um tipo de tuple que inclua um elemento do tipo definido pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="8696f-213">That is, the type that defines a user-defined type may not be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="8696f-214">De um modo mais geral, os tipos definidos pelo utilizador podem não ter dependências cíclicas uns dos outros, pelo que o seguinte conjunto de definições de tipo seria ilegal:</span><span class="sxs-lookup"><span data-stu-id="8696f-214">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions would be illegal:</span></span>

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```


## <a name="operation-and-function-types"></a><span data-ttu-id="8696f-215">Tipos de funcionamento e função</span><span class="sxs-lookup"><span data-stu-id="8696f-215">Operation and Function Types</span></span>

<span data-ttu-id="8696f-216">O tipo básico para qualquer chamada é escrito como `('Tinput => 'Tresult)` `('Tinput -> 'Tresult)` ou, onde ambos `'Tinput` e são `'Tresult` tipos.</span><span class="sxs-lookup"><span data-stu-id="8696f-216">The basic type for any callable is written as `('Tinput => 'Tresult)` or `('Tinput -> 'Tresult)`, where both `'Tinput` and `'Tresult` are types.</span></span>
<span data-ttu-id="8696f-217">Estes são chamados a *assinatura* do chamado.</span><span class="sxs-lookup"><span data-stu-id="8696f-217">These are called the *signature* of the callable.</span></span>

<span data-ttu-id="8696f-218">Todos os callables Q# são considerados para ter um único valor como entrada e devolver um único valor como saída.</span><span class="sxs-lookup"><span data-stu-id="8696f-218">All Q# callables are considered to take a single value as input and return a single value as output.</span></span>
<span data-ttu-id="8696f-219">Tanto os valores de entrada como de saída podem ser tuples.</span><span class="sxs-lookup"><span data-stu-id="8696f-219">Both the input and output values may be tuples.</span></span>
<span data-ttu-id="8696f-220">Calíveis que não têm retorno de `Unit` resultados .</span><span class="sxs-lookup"><span data-stu-id="8696f-220">Callables that have no result return `Unit`.</span></span>
<span data-ttu-id="8696f-221">Os callables que não têm entrada tomam a tuple vazia como entrada.</span><span class="sxs-lookup"><span data-stu-id="8696f-221">Callables that have no input take the empty tuple as input.</span></span>

> [!NOTE]
> <span data-ttu-id="8696f-222">O primeiro formulário, `=>` com, é usado para operações; o segundo formulário, `->` com, para funções.</span><span class="sxs-lookup"><span data-stu-id="8696f-222">The first form, with `=>`, is used for operations; the second form, with `->`, for functions.</span></span>
> <span data-ttu-id="8696f-223">Por exemplo, `((Qubit, Pauli) => Result)` representa a assinatura para uma possível operação de medição de um único qubit.</span><span class="sxs-lookup"><span data-stu-id="8696f-223">For example, `((Qubit, Pauli) => Result)` represents the signature for a possible single-qubit measurement operation.</span></span>
<span data-ttu-id="8696f-224">Os tipos *de função* são completamente especificados pela sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="8696f-224">*Function* types are completely specified by their signature.</span></span>
<span data-ttu-id="8696f-225">Por exemplo, uma função que calcula o seno de um ângulo teria tipo `(Double -> Double)` .</span><span class="sxs-lookup"><span data-stu-id="8696f-225">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span>

<span data-ttu-id="8696f-226">*As operações*---mas não funcionam---se de certas características adicionais que são expressas como parte do tipo de funcionamento.</span><span class="sxs-lookup"><span data-stu-id="8696f-226">*Operations*---but not functions---have certain additional characteristics that are expressed as part of the operation type.</span></span> <span data-ttu-id="8696f-227">Essas características incluem informações sobre os *funtores* que a operação suporta.</span><span class="sxs-lookup"><span data-stu-id="8696f-227">Such characteristics include information about what *functors* the operation supports.</span></span>
<span data-ttu-id="8696f-228">Por exemplo, se a execução da operação pode ser condicionada ao estado de outros qubits, deve apoiar o `Controlled` functor; se a operação tiver um inverso, deve apoiar o `Adjoint` functor.</span><span class="sxs-lookup"><span data-stu-id="8696f-228">For example, if execution of the operation can be conditioned on the state of other qubits, it should support the `Controlled` functor; if the operation has an inverse, it should support the `Adjoint` functor.</span></span> <span data-ttu-id="8696f-229">Os funtores e operações são discutidos em detalhe em [Operações e Funções em Q#](xref:microsoft.quantum.guide.operationsfunctions), mas aqui simplesmente discutimos como isso altera a assinatura da operação.</span><span class="sxs-lookup"><span data-stu-id="8696f-229">Functors and operations are discussed in detail at [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions), but here we simply discuss how this alters the operation signature.</span></span>

<span data-ttu-id="8696f-230">Para exigir apoio ao `Controlled` e/ou `Adjoint` functor num tipo de operação, precisamos de adicionar uma anotação indicando as características correspondentes.</span><span class="sxs-lookup"><span data-stu-id="8696f-230">In order to require support for the `Controlled` and/or `Adjoint` functor in an operation type, we need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="8696f-231">Uma anotação `is Ctl` (por `(Qubit => Unit is Ctl)` exemplo) indica que a operação é controlável---é que é, é a execução condicionada ao estado de outro qubit ou qubits.</span><span class="sxs-lookup"><span data-stu-id="8696f-231">An annotation `is Ctl` (e.g. `(Qubit => Unit is Ctl)`) indicates that the operation is controllable---that is, it's execution conditioned on the state of another qubit or qubits.</span></span> <span data-ttu-id="8696f-232">Da mesma forma, `is Adj` indica que a operação tem um adjacente; ou simplesmente, pode ser "invertida" de tal forma que aplicar sucessivamente uma operação e, em seguida, o seu contíguo a um estado deixa o estado inalterado.</span><span class="sxs-lookup"><span data-stu-id="8696f-232">Similarly, `is Adj` indicates that the operation has an adjoint; or simply, it can be "inverted" such that successively applying an operation and then its adjoint to a state leaves the state unchanged.</span></span> 

<span data-ttu-id="8696f-233">Se quisermos exigir que uma operação desse tipo suporte tanto o `Adjoint` `Controlled` functor como o functor, podemos expressar isto como `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="8696f-233">If we want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor we can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="8696f-234">Por exemplo, a operação Pauli incorporada <xref:microsoft.quantum.intrinsic.x> tem tipo `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="8696f-234">For example, the built-in Pauli <xref:microsoft.quantum.intrinsic.x> operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span> 

<span data-ttu-id="8696f-235">Um tipo de operação que não suporta nenhum functor é especificado apenas pelo seu tipo de entrada e saída, sem anotação adicional.</span><span class="sxs-lookup"><span data-stu-id="8696f-235">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>

### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="8696f-236">Funções e operações por tipo-parametrizadas</span><span class="sxs-lookup"><span data-stu-id="8696f-236">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="8696f-237">Os tipos de caloisos podem conter parâmetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="8696f-237">Callable types may contain type parameters.</span></span>
<span data-ttu-id="8696f-238">Os parâmetros do tipo são indicados por um símbolo prefixado por uma única cotação; por exemplo, `'A` é um parâmetro de tipo legal.</span><span class="sxs-lookup"><span data-stu-id="8696f-238">Type parameters are indicated by a symbol prefixed by a single quote; for example, `'A` is a legal type parameter.</span></span>
<span data-ttu-id="8696f-239">Os detalhes sobre a definição de calcários por tipo são fornecidos na página [Operações e Funções na página Q#.](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)</span><span class="sxs-lookup"><span data-stu-id="8696f-239">Details on defining type-parameterized callables are provided on the [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) page.</span></span>

<span data-ttu-id="8696f-240">Um parâmetro do tipo pode aparecer mais de uma vez numa única assinatura.</span><span class="sxs-lookup"><span data-stu-id="8696f-240">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="8696f-241">Por exemplo, uma função que aplique outra função a cada elemento de uma matriz e devolva os resultados recolhidos teria assinatura `(('A[], 'A->'A) -> 'A[])` .</span><span class="sxs-lookup"><span data-stu-id="8696f-241">For example, a function that applies another function to each element of an array and returns the collected results would have signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="8696f-242">Da mesma forma, uma função que retorne a composição de duas operações pode ter assinatura `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .</span><span class="sxs-lookup"><span data-stu-id="8696f-242">Similarly, a function that returns the composition of two operations might have signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="8696f-243">Ao invocar um tipo de pôr tipo-paradizável, todos os argumentos que tenham o mesmo parâmetro do tipo devem ser do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="8696f-243">When invoking a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="8696f-244">Q# não fornece um mecanismo para limitar os tipos possíveis que podem ser substituídos por um parâmetro do tipo.</span><span class="sxs-lookup"><span data-stu-id="8696f-244">Q# does not provide a mechanism for constraining the possible types that might be substituted for a type parameter.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8696f-245">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="8696f-245">Next steps</span></span>

<span data-ttu-id="8696f-246">Agora que viu todos os tipos que compõem a linguagem Q#, pode dirigir-se a [Expressãos tipo em Q#](xref:microsoft.quantum.guide.expressions) para ver como criar e manipular expressões destes vários tipos.</span><span class="sxs-lookup"><span data-stu-id="8696f-246">Now that you've seen all the types which comprise the Q# language, you can head to [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) to see how to create and manipulate expressions of these various types.</span></span>


