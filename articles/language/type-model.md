---
title: Modelo tipo Q# [ modelo] Microsoft Docs
description: Modelo de tipo Q#
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 0aabb144779da301b71ad215c8e975cc29b4dcce
ms.sourcegitcommit: ca5015fed409eaf0395a89c2e4bc6a890c360aa2
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76871639"
---
# <a name="the-type-model"></a><span data-ttu-id="3c8cf-103">O Modelo Tipo</span><span class="sxs-lookup"><span data-stu-id="3c8cf-103">The Type Model</span></span>

<span data-ttu-id="3c8cf-104">Esta secção estabelece o modelo do tipo Q# e descreve a sintaxe para especificar e trabalhar com tipos.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-104">This section lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>
<span data-ttu-id="3c8cf-105">Notamos que q# é uma linguagem *fortemente dactilografada,* de tal forma que uma utilização cuidadosa destes tipos pode ajudar o compilador a fornecer fortes garantias sobre os programas Q# no momento da compilação.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-105">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>

<span data-ttu-id="3c8cf-106">A fim de fornecer as garantias mais fortes possíveis, as conversões entre tipos em Q# devem ser explícitas utilizando chamadas para funções que expressem essa conversão.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-106">In order to provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="3c8cf-107">Uma variedade dessas funções são fornecidas como parte do espaço de nome <xref:microsoft.quantum.convert>.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-107">A variety of such functions are provided as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="3c8cf-108">As upcasts para tipos compatíveis, por outro lado, acontecem implicitamente.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-108">Upcasts to compatible types on the other hand happen implicitly.</span></span> 

<span data-ttu-id="3c8cf-109">Q# fornece ambos os tipos primitivos, que podem ser usados diretamente, e uma variedade de maneiras de produzir novos tipos de outros tipos.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-109">Q# provides both primitive types, which can be used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="3c8cf-110">Descrevemos cada um no resto desta secção.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-110">We describe each in the rest of this section.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="3c8cf-111">Tipos Primitivos</span><span class="sxs-lookup"><span data-stu-id="3c8cf-111">Primitive Types</span></span>

<span data-ttu-id="3c8cf-112">A língua Q# fornece vários *tipos primitivos,* a partir dos quais outros tipos podem ser construídos:</span><span class="sxs-lookup"><span data-stu-id="3c8cf-112">The Q# language provides several *primitive types*, from which other types can be constructed:</span></span>

- <span data-ttu-id="3c8cf-113">O tipo `Int` representa um inteiro assinado de 64 bits, por exemplo: `2`, `107`, `-5`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-113">The `Int` type represents a 64-bit signed integer, e.g.: `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="3c8cf-114">O tipo `BigInt` representa um inteiro assinado de tamanho arbitrário, por exemplo, `2L`, `107L`, `-5L`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-114">The `BigInt` type represents a signed integer of arbitrary size, e.g. `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="3c8cf-115">Este tipo baseia-se no <xref:System.Numerics.BigInteger> .NET</span><span class="sxs-lookup"><span data-stu-id="3c8cf-115">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="3c8cf-116">tipo.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-116">type.</span></span>
- <span data-ttu-id="3c8cf-117">O tipo `Double` representa um número de ponto flutuante de dupla precisão, por exemplo: `0.0`, `-1.3`, `4e-7`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-117">The `Double` type represents a double-precision floating-point number, e.g.: `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="3c8cf-118">O tipo `Bool` representa um valor booleano que pode ser `true` ou `false`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-118">The `Bool` type represents a Boolean value which can either be `true` or `false`.</span></span>
- <span data-ttu-id="3c8cf-119">O tipo `Qubit` representa um bit quântico ou qubit.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-119">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="3c8cf-120">`Qubit`são opacos para o utilizador; a única operação possível com eles, para além de os passar para outra operação, é testar a identidade (igualdade).</span><span class="sxs-lookup"><span data-stu-id="3c8cf-120">`Qubit`s are opaque to the user; the only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="3c8cf-121">Em última análise, as ações em `Qubit`s são implementadas chamando instruções intrínsecas num processador quântico (ou uma simulação do mesmo).</span><span class="sxs-lookup"><span data-stu-id="3c8cf-121">Ultimately, actions on `Qubit`s are implemented by calling intrinsic instructions on a quantum processor (or a simulation thereof).</span></span>
- <span data-ttu-id="3c8cf-122">O tipo `Pauli` representa um dos quatro operadores pauli de um único qubit.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-122">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="3c8cf-123">Este tipo é utilizado para denotar o funcionamento da base para rotações e para especificar o observável que está a ser medido.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-123">This type is used to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="3c8cf-124">Este é um tipo enumerado que tem quatro valores possíveis: `PauliI`, `PauliX`, `PauliY`e `PauliZ`, que são constantes de tipo `Pauli`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-124">This is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="3c8cf-125">O `Result` tipo representa o resultado de uma medição.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-125">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="3c8cf-126">Este é um tipo enumerado com dois valores possíveis: `One` e `Zero`, que são constantes de tipo `Result`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-126">This is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="3c8cf-127">`Zero` indica que o valor +1 foi medido; `One` indica o valor de -1.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-127">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue.</span></span>
- <span data-ttu-id="3c8cf-128">O tipo `Range` representa uma sequência de inteiros, denotados por `start..step..stop`, onde denotar o passo são opções.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-128">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is options.</span></span> 
   <span data-ttu-id="3c8cf-129">Isto é `start .. stop` corresponde a `start..1..stop`, e, por exemplo, `1..2..7` representa a sequência de $\{1, 3, 5, 7\}$.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-129">That is `start .. stop` corresponds to `start..1..stop`, and e.g. `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="3c8cf-130">O tipo `String` é uma sequência de caracteres Unicode que é opaco para o utilizador uma vez criado.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-130">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="3c8cf-131">Este tipo é usado para relatar mensagens a um hospedeiro clássico em caso de erro ou evento de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-131">This type is used to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="3c8cf-132">O tipo `Unit` é do tipo que permite apenas um valor `()`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-132">The `Unit` type is the type that allows only one value `()`.</span></span> 
  <span data-ttu-id="3c8cf-133">Este tipo é utilizado para indicar que a função ou operação Q# não devolve nenhuma informação.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-133">This type is used to indicate that Q# function or operation returns no information.</span></span> 

<span data-ttu-id="3c8cf-134">As constantes `true`, `false`, `PauliI`, `PauliX``PauliY`, `PauliZ`, `One`e `Zero` são símbolos reservados em Q#.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-134">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="3c8cf-135">Tipos de matriz</span><span class="sxs-lookup"><span data-stu-id="3c8cf-135">Array Types</span></span>

<span data-ttu-id="3c8cf-136">Dado qualquer `'T`de tipo Q# válido, existe um tipo que representa uma matriz de valores de tipo `'T`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-136">Given any valid Q# type `'T`, there is a type that represents an array of values of type `'T`.</span></span>
<span data-ttu-id="3c8cf-137">Este tipo de matriz é representado como `'T[]`; por exemplo, `Qubit[]` ou `Int[][]`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-137">This array type is represented as `'T[]`; for example, `Qubit[]` or `Int[][]`.</span></span>
<span data-ttu-id="3c8cf-138">Por exemplo, uma coleção de inteiros é denotada `Int[]`, enquanto uma série de conjuntos de valores `(Bool, Pauli)` é denotado `(Bool, Pauli)[][]`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-138">For instance, a collection of integers is denoted `Int[]`, while an array of arrays of `(Bool, Pauli)` values is denoted `(Bool, Pauli)[][]`.</span></span>

<span data-ttu-id="3c8cf-139">No segundo exemplo, note que isto representa uma matriz potencialmente irregular de matrizes, e não uma matriz bidimensional retangular.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-139">In the second example, note that this represents a potentially jagged array of arrays, and not a rectangular two-dimensional array.</span></span>
<span data-ttu-id="3c8cf-140">Q# não fornece suporte para matrizes multidimensionais retangulares.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-140">Q# does not provide support for rectangular multi-dimensional arrays.</span></span>

<span data-ttu-id="3c8cf-141">Um valor de matriz pode ser escrito no código fonte Q# utilizando suportes quadrados em torno dos elementos de uma matriz, como em `[PauliI, PauliX, PauliY, PauliZ]`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-141">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="3c8cf-142">O tipo de matriz literal é determinado pelo tipo de base comum de todos os itens da matriz.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-142">The type of an array literal is determined by the common base type of all items in the array.</span></span> 

> [!WARNING]
> <span data-ttu-id="3c8cf-143">Os elementos de uma matriz não podem ser alterados após a criação da matriz.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-143">The elements of an array cannot be changed after the array has been created.</span></span>
> <span data-ttu-id="3c8cf-144">As declarações de atualização e reatribuição e/ou expressões de cópia e atualização podem ser utilizadas para construir uma matriz modificada.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-144">Update-and-reassign statements and/or copy-and-update expressions can be used to construct a modified array.</span></span>

<span data-ttu-id="3c8cf-145">Alternativamente, uma matriz pode ser criada a partir do seu tamanho usando a palavra-chave `new`:</span><span class="sxs-lookup"><span data-stu-id="3c8cf-145">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

<span data-ttu-id="3c8cf-146">Em qualquer dos casos, uma vez construída uma matriz, a função central `Length` pode ser utilizada para obter o número de elementos como `Int`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-146">In either case, once an array has been constructed, the core function `Length` can be used to obtain the number of elements as an `Int`.</span></span>
<span data-ttu-id="3c8cf-147">As matrizes podem ser subscritas utilizando suportes quadrados, com subscripts com tipo `Int` ou tipo `Range`, para obter elementos únicos ou novas matrizes contendo um subconjunto dos elementos de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-147">Arrays can be subscripted using square brackets, with subscripts either having type `Int` or type `Range`, to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="3c8cf-148">Os subscripts de matrizes são baseados em zero:</span><span class="sxs-lookup"><span data-stu-id="3c8cf-148">The subscripts of arrays are zero-based:</span></span>

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a><span data-ttu-id="3c8cf-149">Tipos de tuple</span><span class="sxs-lookup"><span data-stu-id="3c8cf-149">Tuple Types</span></span>

<span data-ttu-id="3c8cf-150">Tendo em conta os tipos zero ou mais diferentes `T0`, `T1`, ..., `Tn`, podemos notar um novo tipo de *tuple* como `(T0, T1, ..., Tn)`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-150">Given zero or more different types `T0`, `T1`, ..., `Tn`, we can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="3c8cf-151">Os tipos utilizados para construir um novo tipo de tuple podem ser por si mesmos tuples, como em `(Int, (Qubit, Qubit))`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-151">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="3c8cf-152">No entanto, esta nidificação é sempre finita, uma vez que os tipos de tuple não podem, em circunstância alguma, conter-se.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-152">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

<span data-ttu-id="3c8cf-153">Os valores do novo tipo de tuple são tuples formados por sequências de valores de cada tipo na tuple.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-153">Values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="3c8cf-154">Por exemplo, `(3, false)` é uma tuple cujo tipo é o tipo de tuple `(Int, Bool)`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-154">For instance, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="3c8cf-155">É possível criar conjuntos de tuples, tuples de matrizes, tuples de sub-tuples, etc.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-155">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, etc.</span></span>

<span data-ttu-id="3c8cf-156">A partir do Q#0.3, `Unit` é o nome do *tipo* de tuple vazio; `()` é utilizado para o *valor*vazio do tuple .</span><span class="sxs-lookup"><span data-stu-id="3c8cf-156">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the empty tuple *value*.</span></span>

<span data-ttu-id="3c8cf-157">Os casos de tuple são imutáveis.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-157">Tuple instances are immutable.</span></span>
<span data-ttu-id="3c8cf-158">Q# não fornece um mecanismo para alterar o conteúdo de uma tuple uma vez criado.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-158">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>

<span data-ttu-id="3c8cf-159">Tuples são um conceito poderoso usado ao longo de Q# para recolher valores juntos em um único valor, tornando mais fácil passá-los ao redor.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-159">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="3c8cf-160">Em particular, usando a notação de tuple, podemos expressar que cada operação e callable leva exatamente uma entrada e devolve exatamente uma saída.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-160">In particular, using tuple notation, we can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="3c8cf-161">Equivalência singleton Tuple</span><span class="sxs-lookup"><span data-stu-id="3c8cf-161">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="3c8cf-162">É possível criar uma tuple singleton (elemento único), `('T1)`, como `(5)` ou `([1,2,3])`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-162">It is possible to create a singleton (single-element) tuple, `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="3c8cf-163">No entanto, Q# trata uma túnica singleton como completamente equivalente a um valor do tipo fechado.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-163">However, Q# treats a singleton tuple as completely equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="3c8cf-164">Ou seja, não há diferença entre `5` e `(5)`, ou entre `5` e `(((5)))`, ou entre `(5, (6))` e `(5, 6)`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-164">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>

<span data-ttu-id="3c8cf-165">Esta equivalência aplica-se a todos os fins, incluindo atribuição e expressões.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-165">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="3c8cf-166">É igualmente válido escrever `(5)+3` como escrever `5+3`, e ambas as expressões avaliarão para `8`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-166">It is just as valid to write `(5)+3` as to write `5+3`, and both expressions will evaluate to `8`.</span></span>
<span data-ttu-id="3c8cf-167">Isto significa, em particular, que uma operação ou função cujo tipo de tuple de entrada ou tuple de saída tem um campo pode ser considerado como tendo um único argumento ou devolvendo um único valor.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-167">In particular, this means that an operation or function whose input tuple or output tuple type has one field can be thought of as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="3c8cf-168">Referimo-nos a esta propriedade como _equivalência de tuple singleton._</span><span class="sxs-lookup"><span data-stu-id="3c8cf-168">We refer to this property as _singleton tuple equivalence_.</span></span>

## <a name="user-defined-types"></a><span data-ttu-id="3c8cf-169">Tipos definidos pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="3c8cf-169">User-Defined Types</span></span>

<span data-ttu-id="3c8cf-170">Um ficheiro Q# pode definir um novo tipo nomeado contendo um único valor de qualquer tipo legal.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-170">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="3c8cf-171">Para qualquer tipo de `T`, podemos declarar um novo tipo definido pelo utilizador que é um subtipo de `T` com a declaração `newtype`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-171">For any tuple type `T`, we can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="3c8cf-172">No espaço de nome @"microsoft.quantum.math", por exemplo, os números complexos são definidos como um tipo definido pelo utilizador:</span><span class="sxs-lookup"><span data-stu-id="3c8cf-172">In the @"microsoft.quantum.math" namespace, for instance, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```

<span data-ttu-id="3c8cf-173">Esta afirmação cria um novo tipo com dois itens anónimos de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-173">This statement creates a new type with two anonymous items of type `Double`.</span></span>   
<span data-ttu-id="3c8cf-174">Além de itens anónimos, os tipos definidos pelo utilizador também suportam itens nomeados a partir da versão Q# 0.7 ou superior.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-174">Aside from anonymous items, user defined types also support named items as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="3c8cf-175">Por exemplo, poderíamos ter nomeado os itens `Re` para o duplo que representa a parte real de um número complexo e `Im` para a parte imaginária:</span><span class="sxs-lookup"><span data-stu-id="3c8cf-175">For example, we could have named the to items `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="3c8cf-176">Nomear um item num tipo definido pelo utilizador não implica que todos os itens precisem de ser nomeados - qualquer combinação de itens nomeados e não nomeados é suportado.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-176">Naming one item in a user defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="3c8cf-177">Além disso, também podem ser nomeados itens internos.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-177">Furthermore, also inner items may be named.</span></span>
<span data-ttu-id="3c8cf-178">O tipo `Nested` como definido abaixo, por exemplo, tem um tipo subjacente `(Double, (Int, String))`, dos quais apenas o item de tipo `Int` é nomeado e todos os outros itens são anónimos.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-178">The type `Nested` as defined below for example has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
<span data-ttu-id="3c8cf-179">Os itens nomeados têm a vantagem de poderem ser acedidos diretamente através do operador de acesso `::`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-179">Named items have the advantage that they can be accessed directly via the access operator `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="3c8cf-180">Para aceder a itens anónimos, por outro lado, o valor embrulhado primeiro precisa de ser extraído utilizando o operador de pós-fixação `!`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-180">In order to access anonymous items on the other hand, the wrapped value first needs to be extracted using the postfix operator `!`.</span></span>
<span data-ttu-id="3c8cf-181">O operador "desembrulhar", `!`, permite extrair o valor contido num tipo definido pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-181">The "unwrap" operator, `!`, allows to extract the value contained in a user defined type.</span></span>
<span data-ttu-id="3c8cf-182">O tipo de expressão "desembrulhar" é o tipo subjacente do tipo definido pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-182">The type of such an "unwrap" expression is the underlying type of the user defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="3c8cf-183">O operador desembrulhar desembrulha exatamente uma camada de embrulho.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-183">The unwrap operator unwraps exactly one layer of wrapping.</span></span>
<span data-ttu-id="3c8cf-184">Vários operadores de desembrulhar podem ser utilizados para aceder a um valor embrulhado multiplicado.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-184">Multiple unwrap operators may be used to access a multiply-wrapped value.</span></span>

<span data-ttu-id="3c8cf-185">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3c8cf-185">For instance:</span></span>

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

<span data-ttu-id="3c8cf-186">Veja a secção sobre [expressões desembrulhadas](xref:microsoft.quantum.language.expressions#unwrap-expressions) e precedência dos [operadores](xref:microsoft.quantum.language.expressions#operator-precedence) para mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-186">Take a look at the section on [unwrap expressions](xref:microsoft.quantum.language.expressions#unwrap-expressions) and [operators precedence](xref:microsoft.quantum.language.expressions#operator-precedence) for more details.</span></span>

<span data-ttu-id="3c8cf-187">Os valores de um tipo definido pelo utilizador podem ser criados chamando o construtor de tipo correspondente:</span><span class="sxs-lookup"><span data-stu-id="3c8cf-187">Values of a user defined type can be created by calling the corresponding type constructor:</span></span>

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="3c8cf-188">Alternativamente, novos valores podem ser criados a partir dos existentes usando [expressões de cópia e atualização](xref:microsoft.quantum.language.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="3c8cf-188">Alternatively, new values can be created from existing ones using [copy-and-update expressions](xref:microsoft.quantum.language.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="3c8cf-189">Tal como para as matrizes, tais expressões copiam todos os valores de item da expressão original, com exceção dos itens nomeados especificados.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-189">Like for arrays, such expressions copy all item values of the original expression, with the exception of the specified named items.</span></span> <span data-ttu-id="3c8cf-190">Para estes, os valores são definidos para os definidos no lado direito da expressão.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-190">For these the values are set to the ones defined on the right hand side of the expression.</span></span> <span data-ttu-id="3c8cf-191">Quaisquer outras construções linguísticas, como, por exemplo, [declarações de atualização e reatribuição,](xref:microsoft.quantum.language.statements#update-and-reassign-statement)que estejam disponíveis para itens de matriz, existem também para itens nomeados em tipos definidos pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-191">Any other language constructs, like for example [update-and-reassign statements](xref:microsoft.quantum.language.statements#update-and-reassign-statement), that are available for array items exist for named-items in user defined types as well.</span></span>

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

<span data-ttu-id="3c8cf-192">Os tipos definidos pelo utilizador podem ser utilizados em qualquer outro tipo.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-192">User-defined types may be used anywhere any other type may be used.</span></span>
<span data-ttu-id="3c8cf-193">Em particular, é possível definir um conjunto de um tipo definido pelo utilizador e incluir um tipo definido pelo utilizador como um elemento de um tipo de tuple.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-193">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

<span data-ttu-id="3c8cf-194">Não é possível criar estruturas de tipo recursivos.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-194">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="3c8cf-195">Ou seja, o tipo que define um tipo definido pelo utilizador pode não ser um tipo de tuple que inclua um elemento do tipo definido pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-195">That is, the type that defines a user-defined type may not be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="3c8cf-196">De um modo mais geral, os tipos definidos pelo utilizador podem não ter dependências cíclicas entre si, pelo que o seguinte conjunto de definições de tipo seria ilegal:</span><span class="sxs-lookup"><span data-stu-id="3c8cf-196">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions would be illegal:</span></span>

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

<span data-ttu-id="3c8cf-197">Além de fornecer pseudónimos curtos para tipos de tuple potencialmente complicados, uma vantagem significativa de definir tais tipos é que eles podem documentar a intenção de um valor particular.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-197">In addition to providing short aliases for potentially complicated tuple types, one significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="3c8cf-198">Voltando ao exemplo de `Complex`, também se poderia ter definido as coordenadas polares 2D como um tipo definido pelo utilizador:</span><span class="sxs-lookup"><span data-stu-id="3c8cf-198">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="3c8cf-199">Apesar de ambos `Complex` e `Polar` terem um tipo subjacente `(Double, Double)`, os dois tipos são totalmente incompatíveis em Q#, minimizando o risco de chamar acidentalmente uma função matemática complexa com coordenadas polares e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-199">Even though both `Complex` and `Polar` are both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>
<span data-ttu-id="3c8cf-200">Desta forma, os tipos definidos pelo utilizador F# têm um papel semelhante ao dos Registos, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-200">In this way, user-defined types have a similar role as Records in F# for example.</span></span> 


## <a name="operation-and-function-types"></a><span data-ttu-id="3c8cf-201">Tipos de Funcionamento e Função</span><span class="sxs-lookup"><span data-stu-id="3c8cf-201">Operation and Function Types</span></span>

<span data-ttu-id="3c8cf-202">Uma _operação_ Q# é uma subrotina quântica.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-202">A Q# _operation_ is a quantum subroutine.</span></span>
<span data-ttu-id="3c8cf-203">Ou seja, é uma rotina que pode ser chamada que contém operações quânticas.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-203">That is, it is a callable routine that contains quantum operations.</span></span>

<span data-ttu-id="3c8cf-204">Uma _função_ Q# é uma subrotina clássica usada dentro de um algoritmo quântico.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-204">A Q# _function_ is a classical subroutine used within a quantum algorithm.</span></span>
<span data-ttu-id="3c8cf-205">Pode conter código clássico, mas sem operações quânticas.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-205">It may contain classical code but no quantum operations.</span></span>
<span data-ttu-id="3c8cf-206">Especificamente, as funções não podem alocar ou emprestar qubits, nem podem chamar operações.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-206">Specifically, functions may not allocate or borrow qubits, nor may they call operations.</span></span>
<span data-ttu-id="3c8cf-207">No entanto, é possível passar-lhes operações ou qubits para processamento.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-207">It is possible, however, to pass them operations or qubits for processing.</span></span>
<span data-ttu-id="3c8cf-208">As funções são, portanto, inteiramente determinísticas no sentido de que chamá-las com os mesmos argumentos produzirá sempre o mesmo resultado.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-208">Functions are thus entirely deterministic in the sense that calling them with the same arguments will always produce the same result.</span></span> 

<span data-ttu-id="3c8cf-209">Em conjunto, as operações e funções são chamadas _de callables_.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-209">Together, operations and functions are called _callables_.</span></span>  <span data-ttu-id="3c8cf-210">Pode ver [alguns exemplos destes](#examples) abaixo.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-210">You can see some [examples](#examples) of these below.</span></span>

<span data-ttu-id="3c8cf-211">Todos os callables Q# são considerados como tendo um único valor como entrada e devolver um único valor como saída.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-211">All Q# callables are considered to take a single value as input and return a single value as output.</span></span>
<span data-ttu-id="3c8cf-212">Tanto os valores de entrada como de saída podem ser tuples.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-212">Both the input and output values may be tuples.</span></span>
<span data-ttu-id="3c8cf-213">Callables que não têm resultado retorno `Unit`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-213">Callables that have no result return `Unit`.</span></span>
<span data-ttu-id="3c8cf-214">Os inputáveis que não têm entrada tomam a túnica vazia como entrada.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-214">Callables that have no input take the empty tuple as input.</span></span>

<span data-ttu-id="3c8cf-215">O tipo básico para qualquer callable é escrito como `('Tinput => 'Tresult)` ou `('Tinput -> 'Tresult)`, onde tanto `'Tinput` como `'Tresult` são tipos.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-215">The basic type for any callable is written as `('Tinput => 'Tresult)` or `('Tinput -> 'Tresult)`, where both `'Tinput` and `'Tresult` are types.</span></span>
<span data-ttu-id="3c8cf-216">A primeira forma, com `=>`, é utilizada para operações; a segunda forma, com `->`, para funções.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-216">The first form, with `=>`, is used for operations; the second form, with `->`, for functions.</span></span>
<span data-ttu-id="3c8cf-217">Por exemplo, `((Qubit, Pauli) => Result)` representa a assinatura para uma possível operação de medição de qubit único.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-217">For example, `((Qubit, Pauli) => Result)` represents the signature for a possible single-qubit measurement operation.</span></span>

<span data-ttu-id="3c8cf-218">Os tipos de funções são completamente especificados pela sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-218">Function types are completely specified by their signature.</span></span>
<span data-ttu-id="3c8cf-219">Por exemplo, uma função que computa o seno de um ângulo teria tipo `(Double -> Double)`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-219">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span>

<span data-ttu-id="3c8cf-220">As operações — mas não as funções — têm certas características adicionais que são _expressas_ como parte do tipo de operação.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-220">Operations—but not functions—have certain additional _characteristics_ that are expressed as part of the operation type.</span></span> <span data-ttu-id="3c8cf-221">Estas características incluem informações sobre os functores que a operação suporta.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-221">Such characteristics include information about what functors the operation supports.</span></span>
<span data-ttu-id="3c8cf-222">Os functores são meta-operações que geram uma especialização de uma operação base; ver [Functors,](#functors)abaixo.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-222">Functors are meta-operations that generate a specialization of a base operation; see [Functors](#functors), below.</span></span>

<span data-ttu-id="3c8cf-223">Os tipos de funcionamento são especificados pelo seu tipo de entrada, tipo de saída e suas características.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-223">Operation types are specified by the their input type, output type, and their characteristics.</span></span>    
<span data-ttu-id="3c8cf-224">Para exigir apoio para o `Controlled` e/ou `Adjoint` functor num tipo de operação, precisamos adicionar uma anotação indicando as características correspondentes.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-224">In order to require support for the `Controlled` and/or `Adjoint` functor in an operation type, we need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="3c8cf-225">Uma anotação `is Ctl` por exemplo indica que a operação é controlável.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-225">An annotation `is Ctl` for example indicates that the operation is controllable.</span></span> <span data-ttu-id="3c8cf-226">Se quisermos exigir que uma operação desse tipo suporte tanto o `Adjoint` como o functor `Controlled` podemos expressar isto como `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-226">If we want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor we can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="3c8cf-227">As características de funcionamento utilizadas `Adj` e `Ctl` estritamente falando são dois conjuntos de etiquetas pré-definidos, em que cada rótulo indica características de funcionamento específicas, como, por exemplo, o suporte a um functor específico.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-227">The used operation characteristics `Adj` and `Ctl` strictly speaking are two pre-defined sets of labels, where each label indicates a particular operation characteristics like e.g. support for a particular functor.</span></span>
<span data-ttu-id="3c8cf-228">Assim, `+` é usado para indicar a união desses dois conjuntos, e `*` é usado para indicar o cruzamento - isto é, os rótulos que são comuns a ambos os conjuntos.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-228">Hence, `+` is used to indicate the union of those two sets, and `*` is used to indicate the intersection - i.e. the labels that are common to both sets.</span></span>  

<span data-ttu-id="3c8cf-229">Por exemplo, a operação `X` Pauli tem tipo `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-229">For example, the Pauli `X` operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="3c8cf-230">Um tipo de funcionamento que não suporta functores é especificado apenas pelo seu tipo de entrada e saída, sem anotação adicional.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-230">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>


### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="3c8cf-231">Funções e operações parametrizadas tipo</span><span class="sxs-lookup"><span data-stu-id="3c8cf-231">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="3c8cf-232">Os tipos de callable podem conter parâmetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-232">Callable types may contain type parameters.</span></span>
<span data-ttu-id="3c8cf-233">Os parâmetros do tipo são indicados por um símbolo prefixado por uma única citação; por exemplo, `'A` é um parâmetro de tipo legal.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-233">Type parameters are indicated by a symbol prefixed by a single quote; for example, `'A` is a legal type parameter.</span></span>

<span data-ttu-id="3c8cf-234">Um parâmetro de tipo pode aparecer mais de uma vez numa única assinatura.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-234">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="3c8cf-235">Por exemplo, uma função que aplica outra função a cada elemento de uma matriz e devolve os resultados recolhidos teria assinatura `(('A[], 'A->'A) -> 'A[])`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-235">For example, a function that applies another function to each element of an array and returns the collected results would have signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="3c8cf-236">Da mesma forma, uma função que desliga a composição de duas operações pode ter assinatura `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-236">Similarly, a function that returns the composition of two operations might have signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="3c8cf-237">Ao invocar um tipo de escala tometável, todos os argumentos que tenham o mesmo parâmetro devem ser do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-237">When invoking a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="3c8cf-238">Q# não fornece um mecanismo para limitar os tipos possíveis que podem ser substituídos por um parâmetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-238">Q# does not provide a mechanism for constraining the possible types that might be substituted for a type parameter.</span></span>

### <a name="type-compatibility"></a><span data-ttu-id="3c8cf-239">Compatibilidade tipo</span><span class="sxs-lookup"><span data-stu-id="3c8cf-239">Type Compatibility</span></span>

<span data-ttu-id="3c8cf-240">Uma operação com functores adicionais suportados pode ser usada em qualquer lugar de uma operação com menos functores, mas a mesma assinatura é esperada.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-240">An operation with additional functors supported may be used anywhere an operation with fewer functors but the same signature is expected.</span></span>
<span data-ttu-id="3c8cf-241">Por exemplo, uma operação de tipo `(Qubit => Unit is Adj)` pode ser utilizada em qualquer lugar que se espere uma operação de tipo `(Qubit => Unit)`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-241">For instance, an operation of type `(Qubit => Unit is Adj)` may be used anywhere an operation of type `(Qubit => Unit)` is expected.</span></span>

<span data-ttu-id="3c8cf-242">Q# é covariante em relação aos tipos de retorno caltáveis: um callable que devolve um tipo `'A` é compatível com um callable com o mesmo tipo de entrada e um tipo de resultado com o qual `'A` é compatível.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-242">Q# is covariant with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that `'A` is compatible with.</span></span>

<span data-ttu-id="3c8cf-243">Q# é contravariante em relação aos tipos de entrada: um callable que leva um tipo `'A` pois a entrada é compatível com uma chamada com o mesmo tipo de resultado e um tipo de entrada compatível com `'A`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-243">Q# is contravariant with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="3c8cf-244">Ou seja, dadas as seguintes definições:</span><span class="sxs-lookup"><span data-stu-id="3c8cf-244">That is, given the following definitions:</span></span>

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

<span data-ttu-id="3c8cf-245">os seguintes são verdadeiros:</span><span class="sxs-lookup"><span data-stu-id="3c8cf-245">the following are true:</span></span>

- <span data-ttu-id="3c8cf-246">A função `ConjugateInvertWith` pode ser invocada com um argumento `inner` de `Invert` ou `ApplyUnitary`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-246">The function `ConjugateInvertWith` may be invoked with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="3c8cf-247">A função `ConjugateUnitaryWith` pode ser invocada com um argumento `inner` de `ApplyUnitary`, mas não `Invert`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-247">The function `ConjugateUnitaryWith` may be invoked with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="3c8cf-248">Um valor de `(Qubit[] => Unit is Adj + Ctl)` tipo pode ser devolvido de `ConjugateInvertWith`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-248">A value of type `(Qubit[] => Unit is Adj + Ctl)` may be returned from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3c8cf-249">Q# 0.3 introduz uma diferença significativa no comportamento dos tipos definidos pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-249">Q# 0.3 introduces a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="3c8cf-250">Os tipos definidos pelo utilizador são tratados como uma versão embrulhada do tipo subjacente, em vez de como um subtipo.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-250">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="3c8cf-251">Isto significa que um valor de um tipo definido pelo utilizador não é utilizável quando se espera um valor do tipo subjacente.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-251">This means that a value of a user-defined type is not usable where a value of the underlying type is expected.</span></span>

### <a name="functors"></a><span data-ttu-id="3c8cf-252">Functores</span><span class="sxs-lookup"><span data-stu-id="3c8cf-252">Functors</span></span>

<span data-ttu-id="3c8cf-253">Um functor em Q# é uma fábrica que define uma nova operação a partir de outra operação.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-253">A functor in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="3c8cf-254">Os functores têm acesso à implementação da operação base na definição da implementação da nova operação.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-254">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="3c8cf-255">Assim, os functores podem desempenhar funções mais complexas do que as funções tradicionais de alto nível.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-255">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span>

<span data-ttu-id="3c8cf-256">Os functores não têm representação no sistema do tipo Q#.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-256">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="3c8cf-257">Por conseguinte, não é atualmente possível ligá-los a uma variável ou aprová-los como argumentos.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-257">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="3c8cf-258">Um functor é utilizado aplicando-o a uma operação, devolvendo uma nova operação.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-258">A functor is used by applying it to an operation, returning a new operation.</span></span>
<span data-ttu-id="3c8cf-259">Por exemplo, a operação que resulta da aplicação do functor `Adjoint` à operação `Y` é escrita como `Adjoint Y`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-259">For example, the operation that results from applying the `Adjoint` functor to the `Y` operation is written as `Adjoint Y`.</span></span>
<span data-ttu-id="3c8cf-260">A nova operação pode então ser invocada como qualquer outra operação.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-260">The new operation may then be invoked like any other operation.</span></span>
<span data-ttu-id="3c8cf-261">Assim, `Adjoint Y(q1)` aplica o functor Adjoint à operação `Y` para gerar uma nova operação, e aplica essa nova operação para `q1`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-261">Thus, `Adjoint Y(q1)` applies the Adjoint functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>

<span data-ttu-id="3c8cf-262">Do mesmo modo, `Controlled X(controls, target)` aplica o functor controlado à operação `X` para gerar uma nova operação, e aplica essa nova operação para `controls` e `target`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-262">Similarly, `Controlled X(controls, target)` applies the Controlled functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

<span data-ttu-id="3c8cf-263">Os dois functores padrão em Q# são `Adjoint` e `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-263">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

#### <a name="adjoint"></a><span data-ttu-id="3c8cf-264">Adjoint</span><span class="sxs-lookup"><span data-stu-id="3c8cf-264">Adjoint</span></span>

<span data-ttu-id="3c8cf-265">Na computação quântica, a adjoint de uma operação é a complexa transposição conjugada da operação.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-265">In quantum computing, the adjoint of an operation is the complex conjugate transpose of the operation.</span></span>
<span data-ttu-id="3c8cf-266">Para operações que implementem um operador unitário, o adjoint é o inverso da operação.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-266">For operations that implement a unitary operator, the adjoint is the inverse of the operation.</span></span>
<span data-ttu-id="3c8cf-267">Para uma operação simples que apenas invoque uma sequência de outras operações unitárias num conjunto de qubits, o adjoint pode ser calculado aplicando as juntas de anúncios das suboperações nos mesmos qubits, na sequência inversa.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-267">For a simple operation that just invokes a sequence of other unitary operations on a set of qubits, the adjoint may be computed by applying the adjoints of the sub-operations on the same qubits, in the reverse sequence.</span></span>

<span data-ttu-id="3c8cf-268">Dada a expressão de operação, pode ser formada uma nova expressão de operação utilizando o functor `Adjoint`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-268">Given an operation expression, a new operation expression may be formed using the `Adjoint` functor.</span></span>
<span data-ttu-id="3c8cf-269">Por exemplo, `Adjoint QFT` designa o adjoint da operação `QFT`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-269">For instance, `Adjoint QFT` designates the adjoint of the `QFT` operation.</span></span>
<span data-ttu-id="3c8cf-270">A nova operação tem a mesma assinatura e tipo que a operação base.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-270">The new operation has the same signature and type as the base operation.</span></span>
<span data-ttu-id="3c8cf-271">Em particular, a nova operação também permite `Adjoint`, e permitirá `Controlled` se e apenas se a operação base o fizesse.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-271">In particular, the new operation also allows `Adjoint`, and will allow `Controlled` if and only if the base operation did.</span></span>

<span data-ttu-id="3c8cf-272">O functor Adjoint é o seu próprio inverso; isto é, `Adjoint Adjoint Op` é sempre o mesmo que `Op`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-272">The Adjoint functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled"></a><span data-ttu-id="3c8cf-273">Controlado</span><span class="sxs-lookup"><span data-stu-id="3c8cf-273">Controlled</span></span>

<span data-ttu-id="3c8cf-274">A versão controlada de uma operação é uma nova operação que aplica eficazmente o funcionamento da base apenas se todos os qubits de controlo estiverem num estado determinado.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-274">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="3c8cf-275">Se os qubits de controlo estiverem em sobreposição, então o funcionamento da base é aplicado de forma coerente à parte adequada da superposição.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-275">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="3c8cf-276">Assim, as operações controladas são frequentemente usadas para gerar emaranhado.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-276">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="3c8cf-277">Em Q#, as versões controladas tomam sempre uma série de qubits de controlo, e o estado especificado é sempre para todos os qubits de controlo estarem no estado computacional (`PauliZ``One` ), $\ket{1}$.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-277">In Q#, controlled versions always take an array of control qubits, and the specified state is always for all of the control qubits to be in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
<span data-ttu-id="3c8cf-278">O controlo baseado noutros Estados pode ser alcançado aplicando a operação unitária adequada aos qubits de controlo antes da operação controlada e aplicando os inversos da operação unitária após a operação controlada.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-278">Controlling based on other states may be achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
<span data-ttu-id="3c8cf-279">Por exemplo, a aplicação de uma operação `X` a um qubit de controlo antes e depois de uma operação controlada fará com que a operação controle o estado `Zero` ($\ket{0}$) para esse qubit; aplicação de uma operação `H` antes e depois controlará o `PauliX` estado `One`, ou seja, -1 eigenvalue de Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ em vez do `PauliZ` estado `One`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-279">For example, applying an `X` operation to a control qubit before and after a controlled operation will cause the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after will control on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="3c8cf-280">Dada a expressão de operação, pode ser formada uma nova expressão de operação utilizando o functor `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-280">Given an operation expression, a new operation expression may be formed using the `Controlled` functor.</span></span>
<span data-ttu-id="3c8cf-281">A assinatura da nova operação baseia-se na assinatura da operação original.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-281">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="3c8cf-282">O tipo de resultado é o mesmo, mas o tipo de entrada é um dois tuple com uma matriz qubit que detém o qubit de controlo como primeiro elemento e os argumentos da operação original como segundo elemento.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-282">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="3c8cf-283">A nova operação apoia `Controlled`, e apoiará `Adjoint` se e apenas se a operação original o fizesse.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-283">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="3c8cf-284">Se a operação original teve apenas um único argumento, então a equivalência de tuple singleton entrará em jogo aqui.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-284">If the original operation took only a single argument, then singleton tuple equivalence will come into play here.</span></span>
<span data-ttu-id="3c8cf-285">Por exemplo, `Controlled X` é a versão controlada da operação `X`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-285">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span>
<span data-ttu-id="3c8cf-286">`X` tem `(Qubit => Unit is Adj + Ctl)`tipo, por isso `Controlled X` tem `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`tipo; por causa da equivalência de tuple singleton, este é o mesmo que `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-286">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="3c8cf-287">Se a operação base tomou vários argumentos, lembre-se de encerrar os argumentos correspondentes da versão controlada da operação em parênteses para convertê-los em um tuple.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-287">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="3c8cf-288">Por exemplo, `Controlled Rz` é a versão controlada da operação `Rz`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-288">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span>
<span data-ttu-id="3c8cf-289">`Rz` tem `((Double, Qubit) => Unit is Adj + Ctl)`tipo, por isso `Controlled Rz` tem `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`tipo.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-289">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="3c8cf-290">Assim, `Controlled Rz(controls, (0.1, target))` seria uma invocação válida de `Controlled Rz` (note os parênteses em torno `0.1, target`).</span><span class="sxs-lookup"><span data-stu-id="3c8cf-290">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="3c8cf-291">Como outro exemplo, `CNOT(control, target)` pode ser implementado como `Controlled X([control], target)`.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-291">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="3c8cf-292">Se um alvo deve ser controlado por 2 qubits de controlo (CCNOT), podemos usar `Controlled X([control1, control2], target)` declaração.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-292">If a target should be controlled by 2 control qubits (CCNOT), we can use `Controlled X([control1, control2], target)` statement.</span></span>

### <a name="examples"></a><span data-ttu-id="3c8cf-293">Exemplos</span><span class="sxs-lookup"><span data-stu-id="3c8cf-293">Examples</span></span>

<span data-ttu-id="3c8cf-294">Este exemplo de uma operação Q# provém da amostra [de medição.](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement)</span><span class="sxs-lookup"><span data-stu-id="3c8cf-294">This example of a Q# operation comes from the [Measurement](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) sample.</span></span> <span data-ttu-id="3c8cf-295">No âmbito das operações, podemos alocar qubits e utilizar operações quânticas nesses qubits, tais como `H` e `X`:</span><span class="sxs-lookup"><span data-stu-id="3c8cf-295">Within operations, we can allocate qubits and use quantum operations on those qubits such as `H` and `X`:</span></span>

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit() : Result {
        mutable result = Zero;

        using (qubit = Qubit()) { // Allocate a qubit
            H(qubit);               // Use a quantum operation on that qubit
            set result = M(qubit);      // Measure the qubit
            if (result == One) {    // Reset the qubit so that it can be released
                X(qubit);
            }

            return result;
        }
 }
```

<span data-ttu-id="3c8cf-296">Este exemplo de função provém da amostra de Estimativa de [Fase.](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation)</span><span class="sxs-lookup"><span data-stu-id="3c8cf-296">This example of a function comes from the [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) sample.</span></span> <span data-ttu-id="3c8cf-297">Contém código puramente clássico.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-297">It contains purely classical code.</span></span> <span data-ttu-id="3c8cf-298">Pode ver que, ao contrário do exemplo acima, não são atribuídos qubits, e não são utilizadas operações quânticas.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-298">You can see that, unlike the example above, no qubits are allocated, and no quantum operations are used.</span></span>

```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function PointwiseProduct(left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

<span data-ttu-id="3c8cf-299">Também é possível que uma função seja passada qubits para processamento, como neste exemplo a partir da amostra [ReversívelLogicSynthesis.](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis)</span><span class="sxs-lookup"><span data-stu-id="3c8cf-299">It is also possible for a function to be passed qubits for processing, as in this example from the [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) sample.</span></span> <span data-ttu-id="3c8cf-300">Os qubits são passados para a função e usados para o processamento, embora em nenhum momento os próprios estados qubit sejam modificados.</span><span class="sxs-lookup"><span data-stu-id="3c8cf-300">Qubits are passed to the function and used for processing, although at no point are the qubit states themselves modified.</span></span>

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates(
    qubits : Qubit[], 
    masks : MCMTMask[]) 
: MCTGate[] {

    mutable result = new MCTGate[0];
    let n = Length(qubits);

    for (i in 0 .. Length(masks) - 1) {
        let (controls, targets) = (masks[i])!;
        let controlBits = IntegerBits(controls, n);
        let targetBits = IntegerBits(targets, n);
        let cQubits = Subarray(controlBits, qubits);
        let tQubits = Subarray(targetBits, qubits);

        for (target in tQubits) {
            set result += [MCTGate(cQubits, target)];
        }
    }

    return result;
}
```
