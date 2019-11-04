---
title: 'Modelo de tipo Q # | Microsoft Docs'
description: 'Modelo de tipo Q #'
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4e251053d1b8306bf8956314d8099e95c56bce55
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184751"
---
# <a name="the-type-model"></a><span data-ttu-id="8563a-103">O modelo de tipo</span><span class="sxs-lookup"><span data-stu-id="8563a-103">The Type Model</span></span>

<span data-ttu-id="8563a-104">Esta seção apresenta o modelo de tipo Q # e descreve a sintaxe para especificar e trabalhar com tipos.</span><span class="sxs-lookup"><span data-stu-id="8563a-104">This section lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>
<span data-ttu-id="8563a-105">Observe que Q # é uma linguagem *fortemente tipada* , de modo que o uso cuidadoso desses tipos pode ajudar o compilador a fornecer fortes garantias sobre programas do Q # no momento da compilação.</span><span class="sxs-lookup"><span data-stu-id="8563a-105">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>

<span data-ttu-id="8563a-106">Para fornecer as garantias mais fortes possíveis, as conversões entre os tipos em Q # devem ser explícitas usando chamadas para funções que expressam essa conversão.</span><span class="sxs-lookup"><span data-stu-id="8563a-106">In order to provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="8563a-107">Uma variedade dessas funções é fornecida como parte do namespace <xref:microsoft.quantum.convert>.</span><span class="sxs-lookup"><span data-stu-id="8563a-107">A variety of such functions are provided as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="8563a-108">Os upcasts para tipos compatíveis, por outro lado, acontecem implicitamente.</span><span class="sxs-lookup"><span data-stu-id="8563a-108">Upcasts to compatible types on the other hand happen implicitly.</span></span> 

<span data-ttu-id="8563a-109">O Q # fornece os dois tipos primitivos, que podem ser usados diretamente e várias maneiras de produzir novos tipos de outros tipos.</span><span class="sxs-lookup"><span data-stu-id="8563a-109">Q# provides both primitive types, which can be used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="8563a-110">Descrevemos cada um no restante desta seção.</span><span class="sxs-lookup"><span data-stu-id="8563a-110">We describe each in the rest of this section.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="8563a-111">Tipos primitivos</span><span class="sxs-lookup"><span data-stu-id="8563a-111">Primitive Types</span></span>

<span data-ttu-id="8563a-112">A linguagem Q # fornece vários *tipos primitivos*, dos quais outros tipos podem ser construídos:</span><span class="sxs-lookup"><span data-stu-id="8563a-112">The Q# language provides several *primitive types*, from which other types can be constructed:</span></span>

- <span data-ttu-id="8563a-113">O tipo de `Int` representa um inteiro com sinal de 64 bits, por exemplo: `2`, `107``-5`.</span><span class="sxs-lookup"><span data-stu-id="8563a-113">The `Int` type represents a 64-bit signed integer, e.g.: `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="8563a-114">O tipo de `BigInt` representa um inteiro assinado de tamanho arbitrário, por exemplo, `2L`, `107L``-5L`.</span><span class="sxs-lookup"><span data-stu-id="8563a-114">The `BigInt` type represents a signed integer of arbitrary size, e.g. `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="8563a-115">Esse tipo é baseado no .NET <xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="8563a-115">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="8563a-116">Escreva.</span><span class="sxs-lookup"><span data-stu-id="8563a-116">type.</span></span>
- <span data-ttu-id="8563a-117">O tipo de `Double` representa um número de ponto flutuante de precisão dupla, por exemplo: `0.0`, `-1.3``4e-7`.</span><span class="sxs-lookup"><span data-stu-id="8563a-117">The `Double` type represents a double-precision floating-point number, e.g.: `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="8563a-118">O tipo de `Bool` representa um valor booliano que pode ser `true` ou `false`.</span><span class="sxs-lookup"><span data-stu-id="8563a-118">The `Bool` type represents a Boolean value which can either be `true` or `false`.</span></span>
- <span data-ttu-id="8563a-119">O tipo de `Qubit` representa um bit quântico ou qubit.</span><span class="sxs-lookup"><span data-stu-id="8563a-119">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="8563a-120">`Qubit`s são opacas para o usuário; a única operação possível com eles, além de passá-los para outra operação, é testar a identidade (igualdade).</span><span class="sxs-lookup"><span data-stu-id="8563a-120">`Qubit`s are opaque to the user; the only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="8563a-121">Por fim, as ações em `Qubit`s são implementadas chamando instruções intrínsecas em um processador Quantum (ou em uma simulação delas).</span><span class="sxs-lookup"><span data-stu-id="8563a-121">Ultimately, actions on `Qubit`s are implemented by calling intrinsic instructions on a quantum processor (or a simulation thereof).</span></span>
- <span data-ttu-id="8563a-122">O tipo de `Pauli` representa um dos quatro operadores de Pauli de qubit único.</span><span class="sxs-lookup"><span data-stu-id="8563a-122">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="8563a-123">Esse tipo é usado para indicar a operação base para rotações e para especificar o observável que está sendo medido.</span><span class="sxs-lookup"><span data-stu-id="8563a-123">This type is used to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="8563a-124">Este é um tipo enumerado que tem quatro valores possíveis: `PauliI`, `PauliX`, `PauliY`e `PauliZ`, que são constantes do tipo `Pauli`.</span><span class="sxs-lookup"><span data-stu-id="8563a-124">This is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="8563a-125">O tipo de `Result` representa o resultado de uma medição.</span><span class="sxs-lookup"><span data-stu-id="8563a-125">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="8563a-126">Este é um tipo enumerado com dois valores possíveis: `One` e `Zero`, que são constantes do tipo `Result`.</span><span class="sxs-lookup"><span data-stu-id="8563a-126">This is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="8563a-127">`Zero` indica que a eigenvalue + 1 foi medida; `One` indica o-1 eigenvalue.</span><span class="sxs-lookup"><span data-stu-id="8563a-127">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue.</span></span>
- <span data-ttu-id="8563a-128">O tipo de `Range` representa uma sequência de inteiros, denotada por `start..step..stop`, em que a indica que a etapa é opções.</span><span class="sxs-lookup"><span data-stu-id="8563a-128">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is options.</span></span> 
   <span data-ttu-id="8563a-129">`start .. stop` corresponde a `start..1..stop`e, por exemplo, `1..2..7` representa a sequência $\{1, 3, 5, 7\}$.</span><span class="sxs-lookup"><span data-stu-id="8563a-129">That is `start .. stop` corresponds to `start..1..stop`, and e.g. `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="8563a-130">O tipo de `String` é uma sequência de caracteres Unicode que é opaca para o usuário depois de criado.</span><span class="sxs-lookup"><span data-stu-id="8563a-130">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="8563a-131">Esse tipo é usado para relatar mensagens a um host clássico no caso de um erro ou evento de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="8563a-131">This type is used to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="8563a-132">O tipo de `Unit` é o tipo que permite apenas um valor `()`.</span><span class="sxs-lookup"><span data-stu-id="8563a-132">The `Unit` type is the type that allows only one value `()`.</span></span> 
  <span data-ttu-id="8563a-133">Esse tipo é usado para indicar que a função ou operação Q # não retorna nenhuma informação.</span><span class="sxs-lookup"><span data-stu-id="8563a-133">This type is used to indicate that Q# function or operation returns no information.</span></span> 

<span data-ttu-id="8563a-134">As constantes `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`e `Zero` são todos símbolos reservados em Q #.</span><span class="sxs-lookup"><span data-stu-id="8563a-134">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="8563a-135">Tipos de matriz</span><span class="sxs-lookup"><span data-stu-id="8563a-135">Array Types</span></span>

<span data-ttu-id="8563a-136">Dado um tipo válido de Q # `'T`, há um tipo que representa uma matriz de valores do tipo `'T`.</span><span class="sxs-lookup"><span data-stu-id="8563a-136">Given any valid Q# type `'T`, there is a type that represents an array of values of type `'T`.</span></span>
<span data-ttu-id="8563a-137">Esse tipo de matriz é representado como `'T[]`; por exemplo, `Qubit[]` ou `Int[][]`.</span><span class="sxs-lookup"><span data-stu-id="8563a-137">This array type is represented as `'T[]`; for example, `Qubit[]` or `Int[][]`.</span></span>
<span data-ttu-id="8563a-138">Por exemplo, uma coleção de inteiros é denotada `Int[]`, enquanto uma matriz de matrizes de `(Bool, Pauli)` valores é denotada `(Bool, Pauli)[][]`.</span><span class="sxs-lookup"><span data-stu-id="8563a-138">For instance, a collection of integers is denoted `Int[]`, while an array of arrays of `(Bool, Pauli)` values is denoted `(Bool, Pauli)[][]`.</span></span>

<span data-ttu-id="8563a-139">No segundo exemplo, observe que isso representa uma matriz potencialmente irregular de matrizes e não uma matriz bidimensional retangular.</span><span class="sxs-lookup"><span data-stu-id="8563a-139">In the second example, note that this represents a potentially jagged array of arrays, and not a rectangular two-dimensional array.</span></span>
<span data-ttu-id="8563a-140">O Q # não fornece suporte para matrizes multidimensionais retangulares.</span><span class="sxs-lookup"><span data-stu-id="8563a-140">Q# does not provide support for rectangular multi-dimensional arrays.</span></span>

<span data-ttu-id="8563a-141">Um valor de matriz pode ser escrito em código-fonte Q # usando colchetes em volta dos elementos de uma matriz, como em `[PauliI, PauliX, PauliY, PauliZ]`.</span><span class="sxs-lookup"><span data-stu-id="8563a-141">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="8563a-142">O tipo de um literal de matriz é determinado pelo tipo base comum de todos os itens na matriz.</span><span class="sxs-lookup"><span data-stu-id="8563a-142">The type of an array literal is determined by the common base type of all items in the array.</span></span> 

> [!WARNING]
> <span data-ttu-id="8563a-143">Os elementos de uma matriz não podem ser alterados após a criação da matriz.</span><span class="sxs-lookup"><span data-stu-id="8563a-143">The elements of an array cannot be changed after the array has been created.</span></span>
> <span data-ttu-id="8563a-144">As instruções UPDATE-and-REASSIGN e/ou as expressões Copy-and-Update podem ser usadas para construir uma matriz modificada.</span><span class="sxs-lookup"><span data-stu-id="8563a-144">Update-and-reassign statements and/or copy-and-update expressions can be used to construct a modified array.</span></span>

<span data-ttu-id="8563a-145">Como alternativa, uma matriz pode ser criada a partir de seu tamanho usando a palavra-chave `new`:</span><span class="sxs-lookup"><span data-stu-id="8563a-145">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

<span data-ttu-id="8563a-146">Em ambos os casos, após a construção de uma matriz, a função principal `Length` pode ser usada para obter o número de elementos como um `Int`.</span><span class="sxs-lookup"><span data-stu-id="8563a-146">In either case, once an array has been constructed, the core function `Length` can be used to obtain the number of elements as an `Int`.</span></span>
<span data-ttu-id="8563a-147">As matrizes podem ser subscritos usando colchetes, com subscritos com o tipo `Int` ou tipo `Range`, para obter elementos únicos ou novas matrizes que contenham um subconjunto dos elementos de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="8563a-147">Arrays can be subscripted using square brackets, with subscripts either having type `Int` or type `Range`, to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="8563a-148">Os subscritos das matrizes são baseados em zero:</span><span class="sxs-lookup"><span data-stu-id="8563a-148">The subscripts of arrays are zero-based:</span></span>

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a><span data-ttu-id="8563a-149">Tipos de tupla</span><span class="sxs-lookup"><span data-stu-id="8563a-149">Tuple Types</span></span>

<span data-ttu-id="8563a-150">Dado zero ou mais tipos diferentes `T0`, `T1`,..., `Tn`, podemos denotar um novo *tipo de tupla* como `(T0, T1, ..., Tn)`.</span><span class="sxs-lookup"><span data-stu-id="8563a-150">Given zero or more different types `T0`, `T1`, ..., `Tn`, we can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="8563a-151">Os tipos usados para construir um novo tipo de tupla podem ser tuplas, como em `(Int, (Qubit, Qubit))`.</span><span class="sxs-lookup"><span data-stu-id="8563a-151">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="8563a-152">No entanto, esse aninhamento é sempre finito, pois os tipos de tupla não podem, sob nenhuma circunstância, conter.</span><span class="sxs-lookup"><span data-stu-id="8563a-152">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

<span data-ttu-id="8563a-153">Os valores do novo tipo de tupla são tuplas formadas por sequências de valores de cada tipo na tupla.</span><span class="sxs-lookup"><span data-stu-id="8563a-153">Values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="8563a-154">Por exemplo, `(3, false)` é uma tupla cujo tipo é o tipo de tupla `(Int, Bool)`.</span><span class="sxs-lookup"><span data-stu-id="8563a-154">For instance, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="8563a-155">É possível criar matrizes de tuplas, tuplas de matrizes, tuplas de subtuplas, etc.</span><span class="sxs-lookup"><span data-stu-id="8563a-155">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, etc.</span></span>

<span data-ttu-id="8563a-156">A partir de Q # 0,3, `Unit` é o nome do *tipo* da tupla vazia; `()` é usado para o *valor*de tupla vazio.</span><span class="sxs-lookup"><span data-stu-id="8563a-156">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the empty tuple *value*.</span></span>

<span data-ttu-id="8563a-157">As instâncias de tupla são imutáveis.</span><span class="sxs-lookup"><span data-stu-id="8563a-157">Tuple instances are immutable.</span></span>
<span data-ttu-id="8563a-158">O Q # não fornece um mecanismo para alterar o conteúdo de uma tupla depois de criada.</span><span class="sxs-lookup"><span data-stu-id="8563a-158">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>

<span data-ttu-id="8563a-159">As tuplas são um conceito poderoso usado em toda a p # para coletar valores juntos em um único valor, facilitando sua passagem.</span><span class="sxs-lookup"><span data-stu-id="8563a-159">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="8563a-160">Em particular, usando a notação de tupla, podemos expressar que cada operação e que pode ser chamado leva exatamente uma entrada e retorna exatamente uma saída.</span><span class="sxs-lookup"><span data-stu-id="8563a-160">In particular, using tuple notation, we can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="8563a-161">Equivalência de tupla singleton</span><span class="sxs-lookup"><span data-stu-id="8563a-161">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="8563a-162">É possível criar uma tupla singleton (elemento único), `('T1)`, como `(5)` ou `([1,2,3])`.</span><span class="sxs-lookup"><span data-stu-id="8563a-162">It is possible to create a singleton (single-element) tuple, `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="8563a-163">No entanto, Q # trata uma tupla singleton como totalmente equivalente a um valor do tipo incluído.</span><span class="sxs-lookup"><span data-stu-id="8563a-163">However, Q# treats a singleton tuple as completely equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="8563a-164">Ou seja, não há nenhuma diferença entre `5` e `(5)`, ou entre `5` e `(((5)))`ou entre `(5, (6))` e `(5, 6)`.</span><span class="sxs-lookup"><span data-stu-id="8563a-164">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>

<span data-ttu-id="8563a-165">Essa equivalência aplica-se a todas as finalidades, incluindo atribuições e expressões.</span><span class="sxs-lookup"><span data-stu-id="8563a-165">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="8563a-166">É tão válido gravar `(5)+3` quanto gravar `5+3`e as duas expressões serão avaliadas como `8`.</span><span class="sxs-lookup"><span data-stu-id="8563a-166">It is just as valid to write `(5)+3` as to write `5+3`, and both expressions will evaluate to `8`.</span></span>
<span data-ttu-id="8563a-167">Em particular, isso significa que uma operação ou função cuja tupla de entrada ou tipo de tupla de saída tem um campo pode ser considerada como um único argumento ou retornando um único valor.</span><span class="sxs-lookup"><span data-stu-id="8563a-167">In particular, this means that an operation or function whose input tuple or output tuple type has one field can be thought of as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="8563a-168">Nós nos referimos a essa propriedade como _equivalência de tupla singleton_.</span><span class="sxs-lookup"><span data-stu-id="8563a-168">We refer to this property as _singleton tuple equivalence_.</span></span>

## <a name="user-defined-types"></a><span data-ttu-id="8563a-169">Tipos definidos pelo usuário</span><span class="sxs-lookup"><span data-stu-id="8563a-169">User-Defined Types</span></span>

<span data-ttu-id="8563a-170">Um arquivo Q # pode definir um novo tipo nomeado contendo um único valor de qualquer tipo legal.</span><span class="sxs-lookup"><span data-stu-id="8563a-170">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="8563a-171">Para qualquer tipo de tupla `T`, podemos declarar um novo tipo definido pelo usuário que seja um subtipo de `T` com a instrução `newtype`.</span><span class="sxs-lookup"><span data-stu-id="8563a-171">For any tuple type `T`, we can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="8563a-172">No namespace @"microsoft.quantum.canon", por exemplo, números complexos são definidos como um tipo definido pelo usuário:</span><span class="sxs-lookup"><span data-stu-id="8563a-172">In the @"microsoft.quantum.canon" namespace, for instance, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```

<span data-ttu-id="8563a-173">Essa instrução cria um novo tipo com dois itens anônimos do tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="8563a-173">This statement creates a new type with two anonymous items of type `Double`.</span></span>   
<span data-ttu-id="8563a-174">Além de itens anônimos, os tipos definidos pelo usuário também dão suporte a itens nomeados a partir do Q # versão 0,7 ou superior.</span><span class="sxs-lookup"><span data-stu-id="8563a-174">Aside from anonymous items, user defined types also support named items as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="8563a-175">Por exemplo, poderíamos ter nomeado o to Items `Re` para o Double representando a parte real de um número complexo e `Im` para a parte imaginária:</span><span class="sxs-lookup"><span data-stu-id="8563a-175">For example, we could have named the to items `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="8563a-176">Nomear um item em um tipo definido pelo usuário não significa que todos os itens precisam ser nomeados-qualquer combinação de itens nomeados e sem nome é suportada.</span><span class="sxs-lookup"><span data-stu-id="8563a-176">Naming one item in a user defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="8563a-177">Além disso, os itens internos também podem ser nomeados.</span><span class="sxs-lookup"><span data-stu-id="8563a-177">Furthermore, also inner items may be named.</span></span>
<span data-ttu-id="8563a-178">O tipo `Nested` conforme definido abaixo, por exemplo, tem um tipo subjacente `(Double, (Int, String))`, do qual apenas o item do tipo `Int` é nomeado e todos os outros itens são anônimos.</span><span class="sxs-lookup"><span data-stu-id="8563a-178">The type `Nested` as defined below for example has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
<span data-ttu-id="8563a-179">Os itens nomeados têm a vantagem de que eles podem ser acessados diretamente por meio do operador de acesso `::`.</span><span class="sxs-lookup"><span data-stu-id="8563a-179">Named items have the advantage that they can be accessed directly via the access operator `::`.</span></span> 

```qsharp
function Addition (c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="8563a-180">Para acessar itens anônimos por outro lado, o valor encapsulado primeiro precisa ser extraído usando o operador de sufixo `!`.</span><span class="sxs-lookup"><span data-stu-id="8563a-180">In order to access anonymous items on the other hand, the wrapped value first needs to be extracted using the postfix operator `!`.</span></span>
<span data-ttu-id="8563a-181">O operador "Unwrap", `!`, permite extrair o valor contido em um tipo definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="8563a-181">The "unwrap" operator, `!`, allows to extract the value contained in a user defined type.</span></span>
<span data-ttu-id="8563a-182">O tipo dessa expressão de "desencapsulamento" é o tipo subjacente do tipo definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="8563a-182">The type of such an "unwrap" expression is the underlying type of the user defined type.</span></span> 

```qsharp
function PrintMsg (value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="8563a-183">O operador de desencapsulamento não encapsula exatamente uma camada de encapsulamento.</span><span class="sxs-lookup"><span data-stu-id="8563a-183">The unwrap operator unwraps exactly one layer of wrapping.</span></span>
<span data-ttu-id="8563a-184">Vários operadores de desencapsulamento podem ser usados para acessar um valor com disposição multiplicada.</span><span class="sxs-lookup"><span data-stu-id="8563a-184">Multiple unwrap operators may be used to access a multiply-wrapped value.</span></span>

<span data-ttu-id="8563a-185">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8563a-185">For instance:</span></span>

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

<span data-ttu-id="8563a-186">Dê uma olhada na seção sobre [desencapsulamento de expressões](xref:microsoft.quantum.language.expressions#unwrap-expressions) e [precedência de operadores](xref:microsoft.quantum.language.expressions#operator-precedence) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="8563a-186">Take a look at the section on [unwrap expressions](xref:microsoft.quantum.language.expressions#unwrap-expressions) and [operators precedence](xref:microsoft.quantum.language.expressions#operator-precedence) for more details.</span></span>

<span data-ttu-id="8563a-187">Os valores de um tipo definido pelo usuário podem ser criados chamando o construtor de tipo correspondente:</span><span class="sxs-lookup"><span data-stu-id="8563a-187">Values of a user defined type can be created by calling the corresponding type constructor:</span></span>

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="8563a-188">Como alternativa, novos valores podem ser criados de existentes usando [expressões de copiar e atualizar](xref:microsoft.quantum.language.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="8563a-188">Alternatively, new values can be created from existing ones using [copy-and-update expressions](xref:microsoft.quantum.language.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="8563a-189">Assim como para matrizes, essas expressões copiam todos os valores de item da expressão original, com exceção dos itens nomeados especificados.</span><span class="sxs-lookup"><span data-stu-id="8563a-189">Like for arrays, such expressions copy all item values of the original expression, with the exception of the specified named items.</span></span> <span data-ttu-id="8563a-190">Para esses valores são definidos como aqueles definidos no lado direito da expressão.</span><span class="sxs-lookup"><span data-stu-id="8563a-190">For these the values are set to the ones defined on the right hand side of the expression.</span></span> <span data-ttu-id="8563a-191">Qualquer outra construção de linguagem, como por exemplo, [atualizar e reatribuir instruções](xref:microsoft.quantum.language.statements#update-and-reassign-statement), que estão disponíveis para itens de matriz existem para itens nomeados em tipos definidos pelo usuário também.</span><span class="sxs-lookup"><span data-stu-id="8563a-191">Any other language constructs, like for example [update-and-reassign statements](xref:microsoft.quantum.language.statements#update-and-reassign-statement), that are available for array items exist for named-items in user defined types as well.</span></span>

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

<span data-ttu-id="8563a-192">Tipos definidos pelo usuário podem ser usados em qualquer lugar que qualquer outro tipo possa ser usado.</span><span class="sxs-lookup"><span data-stu-id="8563a-192">User-defined types may be used anywhere any other type may be used.</span></span>
<span data-ttu-id="8563a-193">Em particular, é possível definir uma matriz de um tipo definido pelo usuário e incluir um tipo definido pelo usuário como um elemento de um tipo de tupla.</span><span class="sxs-lookup"><span data-stu-id="8563a-193">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

<span data-ttu-id="8563a-194">Não é possível criar estruturas de tipo recursiva.</span><span class="sxs-lookup"><span data-stu-id="8563a-194">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="8563a-195">Ou seja, o tipo que define um tipo definido pelo usuário pode não ser um tipo de tupla que inclua um elemento do tipo definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="8563a-195">That is, the type that defines a user-defined type may not be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="8563a-196">Em geral, os tipos definidos pelo usuário podem não ter dependências cíclicas entre si, portanto, o seguinte conjunto de definições de tipo seria ilegal:</span><span class="sxs-lookup"><span data-stu-id="8563a-196">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions would be illegal:</span></span>

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

<span data-ttu-id="8563a-197">Além de fornecer aliases curtos para tipos de tupla potencialmente complicadas, uma vantagem significativa de definir esses tipos é que eles podem documentar a intenção de um valor específico.</span><span class="sxs-lookup"><span data-stu-id="8563a-197">In addition to providing short aliases for potentially complicated tuple types, one significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="8563a-198">Retornando ao exemplo de `Complex`, um também poderia ter definido as coordenadas polares 2D como um tipo definido pelo usuário:</span><span class="sxs-lookup"><span data-stu-id="8563a-198">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="8563a-199">Embora tanto `Complex` quanto `Polar` tenham um tipo subjacente `(Double, Double)`, os dois tipos são totalmente incompatíveis em Q #, minimizando o risco de chamar acidentalmente uma função matemática complexa com coordenadas polares e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="8563a-199">Even though both `Complex` and `Polar` are both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>
<span data-ttu-id="8563a-200">Dessa forma, os tipos definidos pelo usuário têm uma função semelhante à de registros F# , por exemplo.</span><span class="sxs-lookup"><span data-stu-id="8563a-200">In this way, user-defined types have a similar role as Records in F# for example.</span></span> 


## <a name="operation-and-function-types"></a><span data-ttu-id="8563a-201">Operação e tipos de função</span><span class="sxs-lookup"><span data-stu-id="8563a-201">Operation and Function Types</span></span>

<span data-ttu-id="8563a-202">Uma _operação_ Q # é uma sub-rotina Quantum.</span><span class="sxs-lookup"><span data-stu-id="8563a-202">A Q# _operation_ is a quantum subroutine.</span></span>
<span data-ttu-id="8563a-203">Ou seja, é uma rotina que possa ser chamada que contém operações Quantum.</span><span class="sxs-lookup"><span data-stu-id="8563a-203">That is, it is a callable routine that contains quantum operations.</span></span>

<span data-ttu-id="8563a-204">Uma _função_ Q # é uma sub-rotina clássica usada em um algoritmo Quantum.</span><span class="sxs-lookup"><span data-stu-id="8563a-204">A Q# _function_ is a classical subroutine used within a quantum algorithm.</span></span>
<span data-ttu-id="8563a-205">Ele pode conter código clássico, mas não há operações de Quantum.</span><span class="sxs-lookup"><span data-stu-id="8563a-205">It may contain classical code but no quantum operations.</span></span>
<span data-ttu-id="8563a-206">Especificamente, as funções podem não alocar ou emprestar qubits, nem podem chamar operações.</span><span class="sxs-lookup"><span data-stu-id="8563a-206">Specifically, functions may not allocate or borrow qubits, nor may they call operations.</span></span>
<span data-ttu-id="8563a-207">No entanto, é possível passá-los de operações ou qubits para processamento.</span><span class="sxs-lookup"><span data-stu-id="8563a-207">It is possible, however, to pass them operations or qubits for processing.</span></span>
<span data-ttu-id="8563a-208">As funções são, portanto, totalmente determinísticas no sentido de que chamá-las com os mesmos argumentos sempre produzirá o mesmo resultado.</span><span class="sxs-lookup"><span data-stu-id="8563a-208">Functions are thus entirely deterministic in the sense that calling them with the same arguments will always produce the same result.</span></span> 

<span data-ttu-id="8563a-209">Juntas, as operações e funções são chamadas de _callables_.</span><span class="sxs-lookup"><span data-stu-id="8563a-209">Together, operations and functions are called _callables_.</span></span>  <span data-ttu-id="8563a-210">Você pode ver alguns [exemplos](#examples) deles abaixo.</span><span class="sxs-lookup"><span data-stu-id="8563a-210">You can see some [examples](#examples) of these below.</span></span>

<span data-ttu-id="8563a-211">Todos os chamadores de Q # são considerados para pegar um único valor como entrada e retornar um único valor como saída.</span><span class="sxs-lookup"><span data-stu-id="8563a-211">All Q# callables are considered to take a single value as input and return a single value as output.</span></span>
<span data-ttu-id="8563a-212">Os valores de entrada e saída podem ser tuplas.</span><span class="sxs-lookup"><span data-stu-id="8563a-212">Both the input and output values may be tuples.</span></span>
<span data-ttu-id="8563a-213">Chamadores que não têm `Unit`de retorno de resultado.</span><span class="sxs-lookup"><span data-stu-id="8563a-213">Callables that have no result return `Unit`.</span></span>
<span data-ttu-id="8563a-214">Os chamadores que não têm nenhuma entrada usam a tupla vazia como entrada.</span><span class="sxs-lookup"><span data-stu-id="8563a-214">Callables that have no input take the empty tuple as input.</span></span>

<span data-ttu-id="8563a-215">O tipo básico para qualquer callable é escrito como `('Tinput => 'Tresult)` ou `('Tinput -> 'Tresult)`, onde `'Tinput` e `'Tresult` são tipos.</span><span class="sxs-lookup"><span data-stu-id="8563a-215">The basic type for any callable is written as `('Tinput => 'Tresult)` or `('Tinput -> 'Tresult)`, where both `'Tinput` and `'Tresult` are types.</span></span>
<span data-ttu-id="8563a-216">O primeiro formulário, com `=>`, é usado para operações; o segundo formulário, com `->`, para funções.</span><span class="sxs-lookup"><span data-stu-id="8563a-216">The first form, with `=>`, is used for operations; the second form, with `->`, for functions.</span></span>
<span data-ttu-id="8563a-217">Por exemplo, `((Qubit, Pauli) => Result)` representa a assinatura de uma possível operação de medição de qubit único.</span><span class="sxs-lookup"><span data-stu-id="8563a-217">For example, `((Qubit, Pauli) => Result)` represents the signature for a possible single-qubit measurement operation.</span></span>

<span data-ttu-id="8563a-218">Os tipos de função são completamente especificados por sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="8563a-218">Function types are completely specified by their signature.</span></span>
<span data-ttu-id="8563a-219">Por exemplo, uma função que computa o seno de um ângulo teria o tipo `(Double -> Double)`.</span><span class="sxs-lookup"><span data-stu-id="8563a-219">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span>

<span data-ttu-id="8563a-220">Operações — mas não funções — têm determinadas _características_ adicionais que são expressas como parte do tipo de operação.</span><span class="sxs-lookup"><span data-stu-id="8563a-220">Operations—but not functions—have certain additional _characteristics_ that are expressed as part of the operation type.</span></span> <span data-ttu-id="8563a-221">Essas características incluem informações sobre o que transmissão functors a operação dá suporte.</span><span class="sxs-lookup"><span data-stu-id="8563a-221">Such characteristics include information about what functors the operation supports.</span></span>
<span data-ttu-id="8563a-222">Transmissão functors são metaoperações que geram uma especialização de uma operação de base; consulte [transmissão functors](#functors), abaixo.</span><span class="sxs-lookup"><span data-stu-id="8563a-222">Functors are meta-operations that generate a specialization of a base operation; see [Functors](#functors), below.</span></span>

<span data-ttu-id="8563a-223">Os tipos de operação são especificados pelo tipo de entrada, tipo de saída e suas características.</span><span class="sxs-lookup"><span data-stu-id="8563a-223">Operation types are specified by the their input type, output type, and their characteristics.</span></span>    
<span data-ttu-id="8563a-224">Para exigir suporte para o `Controlled` e/ou `Adjoint` functor em um tipo de operação, precisamos adicionar uma anotação que indica as características correspondentes.</span><span class="sxs-lookup"><span data-stu-id="8563a-224">In order to require support for the `Controlled` and/or `Adjoint` functor in an operation type, we need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="8563a-225">Um `is Ctl` de anotação, por exemplo, indica que a operação é controlável.</span><span class="sxs-lookup"><span data-stu-id="8563a-225">An annotation `is Ctl` for example indicates that the operation is controllable.</span></span> <span data-ttu-id="8563a-226">Se quisermos exigir que uma operação desse tipo dê suporte a `Adjoint` e `Controlled` functor, poderemos expressar isso como `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="8563a-226">If we want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor we can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="8563a-227">As características de operação usadas `Adj` e `Ctl` estritamente falando são dois conjuntos predefinidos de rótulos, onde cada rótulo indica as características de uma operação específica como, por exemplo, o suporte para um determinado functor.</span><span class="sxs-lookup"><span data-stu-id="8563a-227">The used operation characteristics `Adj` and `Ctl` strictly speaking are two pre-defined sets of labels, where each label indicates a particular operation characteristics like e.g. support for a particular functor.</span></span>
<span data-ttu-id="8563a-228">Portanto, `+` é usado para indicar a União desses dois conjuntos, e `*` é usado para indicar a interseção, ou seja, os rótulos que são comuns a ambos os conjuntos.</span><span class="sxs-lookup"><span data-stu-id="8563a-228">Hence, `+` is used to indicate the union of those two sets, and `*` is used to indicate the intersection - i.e. the labels that are common to both sets.</span></span>  

<span data-ttu-id="8563a-229">Por exemplo, a operação de `X` Pauli tem o tipo `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="8563a-229">For example, the Pauli `X` operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="8563a-230">Um tipo de operação que não dá suporte a nenhum transmissão functors é especificado por seu tipo de entrada e saída sozinho, sem anotação adicional.</span><span class="sxs-lookup"><span data-stu-id="8563a-230">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>


### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="8563a-231">Funções e operações com parâmetros de tipo</span><span class="sxs-lookup"><span data-stu-id="8563a-231">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="8563a-232">Tipos chamáveis podem conter parâmetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="8563a-232">Callable types may contain type parameters.</span></span>
<span data-ttu-id="8563a-233">Os parâmetros de tipo são indicados por um símbolo prefixado por uma aspa simples; por exemplo, `'A` é um parâmetro de tipo legal.</span><span class="sxs-lookup"><span data-stu-id="8563a-233">Type parameters are indicated by a symbol prefixed by a single quote; for example, `'A` is a legal type parameter.</span></span>

<span data-ttu-id="8563a-234">Um parâmetro de tipo pode aparecer mais de uma vez em uma única assinatura.</span><span class="sxs-lookup"><span data-stu-id="8563a-234">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="8563a-235">Por exemplo, uma função que aplica outra função a cada elemento de uma matriz e retorna os resultados coletados teriam a assinatura `(('A[], 'A->'A) -> 'A[])`.</span><span class="sxs-lookup"><span data-stu-id="8563a-235">For example, a function that applies another function to each element of an array and returns the collected results would have signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="8563a-236">Da mesma forma, uma função que retorna a composição de duas operações pode ter `((('A=>'B), ('B=>'C)) -> ('A=>'C))`de assinatura.</span><span class="sxs-lookup"><span data-stu-id="8563a-236">Similarly, a function that returns the composition of two operations might have signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="8563a-237">Ao invocar um callable-parametrizado de tipo, todos os argumentos que têm o mesmo parâmetro de tipo devem ser do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="8563a-237">When invoking a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="8563a-238">O Q # não fornece um mecanismo para restringir os possíveis tipos que podem ser substituídos por um parâmetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="8563a-238">Q# does not provide a mechanism for constraining the possible types that might be substituted for a type parameter.</span></span>

### <a name="type-compatibility"></a><span data-ttu-id="8563a-239">Compatibilidade de tipo</span><span class="sxs-lookup"><span data-stu-id="8563a-239">Type Compatibility</span></span>

<span data-ttu-id="8563a-240">Uma operação com suporte adicional a transmissão functors pode ser usada em qualquer lugar de uma operação com menos transmissão functors, mas a mesma assinatura é esperada.</span><span class="sxs-lookup"><span data-stu-id="8563a-240">An operation with additional functors supported may be used anywhere an operation with fewer functors but the same signature is expected.</span></span>
<span data-ttu-id="8563a-241">Por exemplo, uma operação do tipo `(Qubit => Unit is Adj)` pode ser usada em qualquer lugar que uma operação do tipo `(Qubit => Unit)` seja esperada.</span><span class="sxs-lookup"><span data-stu-id="8563a-241">For instance, an operation of type `(Qubit => Unit is Adj)` may be used anywhere an operation of type `(Qubit => Unit)` is expected.</span></span>

<span data-ttu-id="8563a-242">Q # é covariant com relação a tipos de retorno que podem ser chamados: um callable que retorna um tipo `'A` é compatível com um callable com o mesmo tipo de entrada e um tipo de resultado ao qual `'A` é compatível.</span><span class="sxs-lookup"><span data-stu-id="8563a-242">Q# is covariant with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that `'A` is compatible with.</span></span>

<span data-ttu-id="8563a-243">Q # é contravariant em relação aos tipos de entrada: um callable que usa um tipo `'A` como entrada é compatível com um callable com o mesmo tipo de resultado e um tipo de entrada compatível com `'A`.</span><span class="sxs-lookup"><span data-stu-id="8563a-243">Q# is contravariant with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="8563a-244">Ou seja, dadas as seguintes definições:</span><span class="sxs-lookup"><span data-stu-id="8563a-244">That is, given the following definitions:</span></span>

```qsharp
operation Invertible (qs : Qubit[]) : Unit 
is Adj {...} 
operation Unitary (qs : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertibleWith (
   inner: (Qubit[] => Unit is Adj),
   outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith (
   inner: (Qubit[] => Unit is Adj + Ctl),
   outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

<span data-ttu-id="8563a-245">o seguinte é verdadeiro:</span><span class="sxs-lookup"><span data-stu-id="8563a-245">the following are true:</span></span>

- <span data-ttu-id="8563a-246">A operação `ConjugateInvertibleWith` pode ser invocada com um argumento `inner` de `Invertible` ou `Unitary`.</span><span class="sxs-lookup"><span data-stu-id="8563a-246">The operation `ConjugateInvertibleWith` may be invoked with an `inner` argument of either `Invertible` or `Unitary`.</span></span>
- <span data-ttu-id="8563a-247">A operação `ConjugateUnitaryWith` pode ser invocada com um argumento `inner` de `Unitary`, mas não `Invertible`.</span><span class="sxs-lookup"><span data-stu-id="8563a-247">The operation `ConjugateUnitaryWith` may be invoked with an `inner` argument of `Unitary`, but not `Invertible`.</span></span>
- <span data-ttu-id="8563a-248">Um valor do tipo `(Qubit[] => Unit is Adj + Ctl)` pode ser retornado de `ConjugateInvertibleWith`.</span><span class="sxs-lookup"><span data-stu-id="8563a-248">A value of type `(Qubit[] => Unit is Adj + Ctl)` may be returned from `ConjugateInvertibleWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8563a-249">A p # 0,3 apresenta uma diferença significativa no comportamento de tipos definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="8563a-249">Q# 0.3 introduces a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="8563a-250">Os tipos definidos pelo usuário são tratados como uma versão encapsulada do tipo subjacente, em vez de como um subtipo.</span><span class="sxs-lookup"><span data-stu-id="8563a-250">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="8563a-251">Isso significa que um valor de um tipo definido pelo usuário não é utilizável, em que um valor do tipo subjacente é esperado.</span><span class="sxs-lookup"><span data-stu-id="8563a-251">This means that a value of a user-defined type is not usable where a value of the underlying type is expected.</span></span>

### <a name="functors"></a><span data-ttu-id="8563a-252">Transmissão functors</span><span class="sxs-lookup"><span data-stu-id="8563a-252">Functors</span></span>

<span data-ttu-id="8563a-253">Um functor em Q # é um alocador que define uma nova operação de outra operação.</span><span class="sxs-lookup"><span data-stu-id="8563a-253">A functor in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="8563a-254">Transmissão functors têm acesso à implementação da operação base ao definir a implementação da nova operação.</span><span class="sxs-lookup"><span data-stu-id="8563a-254">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="8563a-255">Portanto, o transmissão functors pode executar funções mais complexas do que as funções tradicionais de nível superior.</span><span class="sxs-lookup"><span data-stu-id="8563a-255">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span>

<span data-ttu-id="8563a-256">Transmissão functors não tem uma representação no sistema do tipo Q #.</span><span class="sxs-lookup"><span data-stu-id="8563a-256">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="8563a-257">Portanto, no momento, não é possível associá-los a uma variável ou passá-los como argumentos.</span><span class="sxs-lookup"><span data-stu-id="8563a-257">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="8563a-258">Um functor é usado aplicando-o a uma operação, retornando uma nova operação.</span><span class="sxs-lookup"><span data-stu-id="8563a-258">A functor is used by applying it to an operation, returning a new operation.</span></span>
<span data-ttu-id="8563a-259">Por exemplo, a operação resultante da aplicação do `Adjoint` functor à operação `Y` é gravada como `Adjoint Y`.</span><span class="sxs-lookup"><span data-stu-id="8563a-259">For example, the operation that results from applying the `Adjoint` functor to the `Y` operation is written as `Adjoint Y`.</span></span>
<span data-ttu-id="8563a-260">A nova operação pode ser invocada como qualquer outra operação.</span><span class="sxs-lookup"><span data-stu-id="8563a-260">The new operation may then be invoked like any other operation.</span></span>
<span data-ttu-id="8563a-261">Assim, `Adjoint Y(q1)` aplica o functor de modo adjacente à operação `Y` para gerar uma nova operação e aplica essa nova operação a `q1`.</span><span class="sxs-lookup"><span data-stu-id="8563a-261">Thus, `Adjoint Y(q1)` applies the Adjoint functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>

<span data-ttu-id="8563a-262">Da mesma forma, `Controlled X(controls, target)` aplica o functor controlado à operação de `X` para gerar uma nova operação e aplica essa nova operação a `controls` e `target`.</span><span class="sxs-lookup"><span data-stu-id="8563a-262">Similarly, `Controlled X(controls, target)` applies the Controlled functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

<span data-ttu-id="8563a-263">Os dois transmissão functors padrão em Q # são `Adjoint` e `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="8563a-263">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

#### <a name="adjoint"></a><span data-ttu-id="8563a-264">Adjacente</span><span class="sxs-lookup"><span data-stu-id="8563a-264">Adjoint</span></span>

<span data-ttu-id="8563a-265">Na computação Quantum, o adjoin de uma operação é a transpoção de conjugada complexa da operação.</span><span class="sxs-lookup"><span data-stu-id="8563a-265">In quantum computing, the adjoint of an operation is the complex conjugate transpose of the operation.</span></span>
<span data-ttu-id="8563a-266">Para operações que implementam um operador unitário, o adjacente é o inverso da operação.</span><span class="sxs-lookup"><span data-stu-id="8563a-266">For operations that implement a unitary operator, the adjoint is the inverse of the operation.</span></span>
<span data-ttu-id="8563a-267">Para uma operação simples que simplesmente invoca uma sequência de outras operações de unitário em um conjunto de qubits, o erro pode ser computado aplicando o adjoints das suboperações no mesmo qubits, na sequência inversa.</span><span class="sxs-lookup"><span data-stu-id="8563a-267">For a simple operation that just invokes a sequence of other unitary operations on a set of qubits, the adjoint may be computed by applying the adjoints of the sub-operations on the same qubits, in the reverse sequence.</span></span>

<span data-ttu-id="8563a-268">Dada uma expressão de operação, uma nova expressão de operação pode ser formada usando o `Adjoint` functor.</span><span class="sxs-lookup"><span data-stu-id="8563a-268">Given an operation expression, a new operation expression may be formed using the `Adjoint` functor.</span></span>
<span data-ttu-id="8563a-269">Por exemplo, `Adjoint QFT` designa o adjoin da operação `QFT`.</span><span class="sxs-lookup"><span data-stu-id="8563a-269">For instance, `Adjoint QFT` designates the adjoint of the `QFT` operation.</span></span>
<span data-ttu-id="8563a-270">A nova operação tem a mesma assinatura e tipo que a operação base.</span><span class="sxs-lookup"><span data-stu-id="8563a-270">The new operation has the same signature and type as the base operation.</span></span>
<span data-ttu-id="8563a-271">Em particular, a nova operação também permite `Adjoint`e permitirá `Controlled` se e somente se a operação base tiver feito isso.</span><span class="sxs-lookup"><span data-stu-id="8563a-271">In particular, the new operation also allows `Adjoint`, and will allow `Controlled` if and only if the base operation did.</span></span>

<span data-ttu-id="8563a-272">O functor de adjacente é seu próprio inverso; ou seja, `Adjoint Adjoint Op` é sempre o mesmo que `Op`.</span><span class="sxs-lookup"><span data-stu-id="8563a-272">The Adjoint functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled"></a><span data-ttu-id="8563a-273">Controlado</span><span class="sxs-lookup"><span data-stu-id="8563a-273">Controlled</span></span>

<span data-ttu-id="8563a-274">A versão controlada de uma operação é uma nova operação que aplica efetivamente a operação base somente se todas as qubits de controle estiverem em um estado especificado.</span><span class="sxs-lookup"><span data-stu-id="8563a-274">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="8563a-275">Se o controle qubits estiver em superposição, a operação base será aplicada coerentemente à parte apropriada da superposição.</span><span class="sxs-lookup"><span data-stu-id="8563a-275">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="8563a-276">Portanto, as operações controladas geralmente são usadas para gerar Entanglement.</span><span class="sxs-lookup"><span data-stu-id="8563a-276">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="8563a-277">Em Q #, as versões controladas sempre pegam uma matriz de qubits de controle e o estado especificado é sempre para todas as qubits de controle no estado computacional (`PauliZ`) `One`, $ \ket{1}$.</span><span class="sxs-lookup"><span data-stu-id="8563a-277">In Q#, controlled versions always take an array of control qubits, and the specified state is always for all of the control qubits to be in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
<span data-ttu-id="8563a-278">O controle com base em outros Estados pode ser obtido aplicando a operação unitário apropriada ao qubits de controle antes da operação controlada e, em seguida, aplicando os inversos da operação unitário após a operação controlada.</span><span class="sxs-lookup"><span data-stu-id="8563a-278">Controlling based on other states may be achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
<span data-ttu-id="8563a-279">Por exemplo, a aplicação de uma operação de `X` a um qubit de controle antes e depois de uma operação controlada fará com que a operação controle o estado de `Zero` ($ \ket{0}$) para esse qubit; a aplicação de uma operação de `H` antes e depois controlará o estado de `One` de `PauliX`, que é-1 eigenvalue de Pauli X, $ \ket{-} \mathrel{: =} (\ket{0}-\ket{1})/\sqrt{2}$ em vez do estado `PauliZ` `One`.</span><span class="sxs-lookup"><span data-stu-id="8563a-279">For example, applying an `X` operation to a control qubit before and after a controlled operation will cause the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after will control on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="8563a-280">Dada uma expressão de operação, uma nova expressão de operação pode ser formada usando o `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="8563a-280">Given an operation expression, a new operation expression may be formed using the `Controlled` functor.</span></span>
<span data-ttu-id="8563a-281">A assinatura da nova operação é baseada na assinatura da operação original.</span><span class="sxs-lookup"><span data-stu-id="8563a-281">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="8563a-282">O tipo de resultado é o mesmo, mas o tipo de entrada é de duas tuplas com uma matriz qubit que mantém o controle qubit (s) como o primeiro elemento e os argumentos da operação original como o segundo elemento.</span><span class="sxs-lookup"><span data-stu-id="8563a-282">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="8563a-283">A nova operação dá suporte a `Controlled`e dará suporte a `Adjoint` se e somente se a operação original tiver feito isso.</span><span class="sxs-lookup"><span data-stu-id="8563a-283">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="8563a-284">Se a operação original levou apenas um único argumento, a equivalência de tupla singleton entrará em ação aqui.</span><span class="sxs-lookup"><span data-stu-id="8563a-284">If the original operation took only a single argument, then singleton tuple equivalence will come into play here.</span></span>
<span data-ttu-id="8563a-285">Por exemplo, `Controlled X` é a versão controlada da operação de `X`.</span><span class="sxs-lookup"><span data-stu-id="8563a-285">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span>
<span data-ttu-id="8563a-286">`X` tem `(Qubit => Unit is Adj + Ctl)`de tipo, portanto `Controlled X` tem o tipo `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; devido à equivalência de tupla singleton, isso é o mesmo que `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="8563a-286">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="8563a-287">Se a operação base levou vários argumentos, lembre-se de colocar os argumentos correspondentes da versão controlada da operação entre parênteses para convertê-los em uma tupla.</span><span class="sxs-lookup"><span data-stu-id="8563a-287">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="8563a-288">Por exemplo, `Controlled Rz` é a versão controlada da operação de `Rz`.</span><span class="sxs-lookup"><span data-stu-id="8563a-288">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span>
<span data-ttu-id="8563a-289">`Rz` tem `((Double, Qubit) => Unit is Adj + Ctl)`de tipo, portanto `Controlled Rz` tem o tipo `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="8563a-289">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="8563a-290">Portanto, `Controlled Rz(controls, (0.1, target))` seria uma invocação válida de `Controlled Rz` (Observe os parênteses ao `0.1, target`).</span><span class="sxs-lookup"><span data-stu-id="8563a-290">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="8563a-291">Como outro exemplo, `CNOT(control, target)` pode ser implementado como `Controlled X([control], target)`.</span><span class="sxs-lookup"><span data-stu-id="8563a-291">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="8563a-292">Se um destino deve ser controlado por dois qubits de controle (CCNOT), podemos usar `Controlled X([control1, control2], target)` instrução.</span><span class="sxs-lookup"><span data-stu-id="8563a-292">If a target should be controlled by 2 control qubits (CCNOT), we can use `Controlled X([control1, control2], target)` statement.</span></span>

### <a name="examples"></a><span data-ttu-id="8563a-293">Exemplos</span><span class="sxs-lookup"><span data-stu-id="8563a-293">Examples</span></span>

<span data-ttu-id="8563a-294">Este exemplo de uma operação Q # é proveniente do exemplo de [medida](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) .</span><span class="sxs-lookup"><span data-stu-id="8563a-294">This example of a Q# operation comes from the [Measurement](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) sample.</span></span> <span data-ttu-id="8563a-295">Em operações, podemos alocar qubits e usar operações Quantum nesses qubits, como `H` e `X`:</span><span class="sxs-lookup"><span data-stu-id="8563a-295">Within operations, we can allocate qubits and use quantum operations on those qubits such as `H` and `X`:</span></span>

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit () : Result {
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

<span data-ttu-id="8563a-296">Este exemplo de uma função é proveniente do exemplo de [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) .</span><span class="sxs-lookup"><span data-stu-id="8563a-296">This example of a function comes from the [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) sample.</span></span> <span data-ttu-id="8563a-297">Ele contém código puramente clássico.</span><span class="sxs-lookup"><span data-stu-id="8563a-297">It contains purely classical code.</span></span> <span data-ttu-id="8563a-298">Você pode ver que, ao contrário do exemplo acima, nenhum qubits está alocado e nenhuma operação de Quantum é usada.</span><span class="sxs-lookup"><span data-stu-id="8563a-298">You can see that, unlike the example above, no qubits are allocated, and no quantum operations are used.</span></span>


```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function MultiplyPointwise (left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

<span data-ttu-id="8563a-299">Também é possível que uma função seja passada qubits para processamento, como neste exemplo do exemplo de [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) .</span><span class="sxs-lookup"><span data-stu-id="8563a-299">It is also possible for a function to be passed qubits for processing, as in this example from the [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) sample.</span></span> <span data-ttu-id="8563a-300">Qubits são passados para a função e usados para processamento, embora em nenhum momento os próprios Estados de qubit sejam modificados.</span><span class="sxs-lookup"><span data-stu-id="8563a-300">Qubits are passed to the function and used for processing, although at no point are the qubit states themselves modified.</span></span>

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates (qubits : Qubit[], masks : MCMTMask[]) : MCTGate[] {

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
