---
title: Ir mais longe - Q# técnicas / Microsoft Docs
description: Ir mais longe - Técnicas Q#
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.going-further
ms.openlocfilehash: bd2b799d4001e280baccb04158247891b9cbb5bc
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820203"
---
# <a name="going-further"></a><span data-ttu-id="700a2-103">Indo mais longe</span><span class="sxs-lookup"><span data-stu-id="700a2-103">Going Further</span></span> #

<span data-ttu-id="700a2-104">Agora que já viu como escrever programas quânticos interessantes em Q#, esta secção vai mais longe introduzindo alguns tópicos mais avançados que devem ser úteis para avançar.</span><span class="sxs-lookup"><span data-stu-id="700a2-104">Now that you've seen how to write interesting quantum programs in Q#, this section goes further by introducing a few more advanced topics that should prove useful going forward.</span></span>


## <a name="generic-operations-and-functions"></a><span data-ttu-id="700a2-105">Operações e Funções Genéricas</span><span class="sxs-lookup"><span data-stu-id="700a2-105">Generic Operations and Functions</span></span> ##

> [!TIP]
> <span data-ttu-id="700a2-106">Esta secção assume alguma familiaridade básica com [genéricos C#em, ](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics) [genéricos em, F# ](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/) [ C++ modelos,](https://docs.microsoft.com/cpp/cpp/templates-cpp)ou abordagens semelhantes à metaprogramação em outras línguas.</span><span class="sxs-lookup"><span data-stu-id="700a2-106">This section assumes some basic familiarity with [generics in C#](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), [generics in F#](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [C++ templates](https://docs.microsoft.com/cpp/cpp/templates-cpp), or similar approaches to metaprogramming in other languages.</span></span>

<span data-ttu-id="700a2-107">Muitas funções e operações que podemos querer definir não dependem muito dos tipos das suas inputs, mas apenas utilizam implicitamente os seus tipos através de outra função ou operação.</span><span class="sxs-lookup"><span data-stu-id="700a2-107">Many functions and operations that we might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="700a2-108">Por exemplo, considere o conceito de *mapa* comum a muitas línguas funcionais; dada uma função $f(x)$ e uma coleção de valores $\{x_1, x_2, \dots, x_n\}$, o mapa devolve uma nova coleção $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span><span class="sxs-lookup"><span data-stu-id="700a2-108">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="700a2-109">Para implementar isto em Q#, podemos tirar partido dessas funções são de primeira classe.</span><span class="sxs-lookup"><span data-stu-id="700a2-109">To implement this in Q#, we can take advantage of that functions are first class.</span></span>
<span data-ttu-id="700a2-110">Vamos escrever um exemplo rápido de `Map`, usando ★ como espaço reservado enquanto descobrimos que tipos precisamos.</span><span class="sxs-lookup"><span data-stu-id="700a2-110">Let's write out a quick example of `Map`, using ★ as a placeholder while we figure out what types we need.</span></span>

```qsharp
function Map(fn : ★ -> ★, values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="700a2-111">Note que esta função parece muito a mesma, independentemente dos tipos reais em que substituímos.</span><span class="sxs-lookup"><span data-stu-id="700a2-111">Note this function looks very much the same no matter what actual types we substitute in.</span></span>
<span data-ttu-id="700a2-112">Um mapa de inteiros a Paulis, por exemplo, parece muito parecido com um mapa de números de pontos flutuantes a cordas:</span><span class="sxs-lookup"><span data-stu-id="700a2-112">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

```qsharp
function MapIntsToPaulis(fn : Int -> Pauli, values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : Double -> String, values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="700a2-113">Em princípio, poderíamos escrever uma versão de `Map` para cada par de tipos que encontramos, mas isso introduz uma série de dificuldades.</span><span class="sxs-lookup"><span data-stu-id="700a2-113">In principle, we could write a version of `Map` for every pair of types that we encounter, but this introduces a number of difficulties.</span></span>
<span data-ttu-id="700a2-114">Por exemplo, se encontrarmos um bug em `Map`, então temos de garantir que a correção seja aplicada uniformemente em todas as versões de `Map`.</span><span class="sxs-lookup"><span data-stu-id="700a2-114">For instance, if we find a bug in `Map`, then we must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="700a2-115">Além disso, se construirmos um novo tuple ou UDT, então temos agora de construir também um novo `Map` para acompanhar o novo tipo.</span><span class="sxs-lookup"><span data-stu-id="700a2-115">Moreover, if we construct a new tuple or UDT, then we must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="700a2-116">Embora isto seja tratável para um pequeno número de tais funções, à medida que recolhemos cada vez mais funções da mesma forma que `Map`, o custo da introdução de novos tipos torna-se irracionalmente grande em ordem bastante curta.</span><span class="sxs-lookup"><span data-stu-id="700a2-116">While this is tractable for a small number of such functions, as we collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="700a2-117">Grande parte desta dificuldade resulta, no entanto, do facto de não termos dado ao compilador a informação de que necessita para reconhecer como estão relacionadas as diferentes versões de `Map`.</span><span class="sxs-lookup"><span data-stu-id="700a2-117">Much of this difficulty results, however, from that the we have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="700a2-118">Efetivamente, queremos que o compilador trate `Map` como uma espécie de função matemática dos *tipos* Q# para as funções Q#.</span><span class="sxs-lookup"><span data-stu-id="700a2-118">Effectively, we want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>
<span data-ttu-id="700a2-119">Esta noção é formalizada permitindo que funções e operações tenham *parâmetros de tipo,* bem como os seus parâmetros normais de tuple.</span><span class="sxs-lookup"><span data-stu-id="700a2-119">This notion is formalized by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="700a2-120">Nos exemplos acima referidos, queremos pensar em `Map` como tendo parâmetros de tipo `Int, Pauli` no primeiro caso e `Double, String` no segundo caso.</span><span class="sxs-lookup"><span data-stu-id="700a2-120">In the examples above, we wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="700a2-121">Na maior parte dos casos, estes parâmetros de tipo podem então ser usados como se fossem tipos comuns: usamos valores de parâmetros de tipo para fazer matrizes e tuples, funções de chamada e operações, e atribuir a variáveis ordinárias ou mutáveis.</span><span class="sxs-lookup"><span data-stu-id="700a2-121">For the most part, these type parameters can then be used as though they were ordinary types: we use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="700a2-122">O caso mais extremo de dependência indireta é o dos qubits, onde um programa Q# não pode depender diretamente da estrutura do tipo `Qubit`, mas **deve** passar esses tipos para outras operações e funções.</span><span class="sxs-lookup"><span data-stu-id="700a2-122">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type, but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="700a2-123">Voltando ao exemplo acima, podemos ver que precisamos de `Map` para ter parâmetros de tipo, um para representar a entrada para `fn` e outro para representar a saída de `fn`.</span><span class="sxs-lookup"><span data-stu-id="700a2-123">Returning to the example above, then, we can see that we need `Map` to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="700a2-124">Em Q#, isto é escrito adicionando suportes de ângulo (isto é `<>`, não travões $\braket{}$!) após o nome de uma função ou operação na sua declaração, e listando cada parâmetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="700a2-124">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="700a2-125">O nome de cada parâmetro de tipo deve começar com um tique `'`, indicando que se trata de um parâmetro tipo e não de um tipo ordinário (também conhecido como tipo *de concreto).*</span><span class="sxs-lookup"><span data-stu-id="700a2-125">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="700a2-126">Para `Map`, escrevemos assim:</span><span class="sxs-lookup"><span data-stu-id="700a2-126">For `Map`, we thus write:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : 'Input -> 'Output, values : 'Input[]) : 'Output {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="700a2-127">Note que a definição de `Map<'Input, 'Output>` se parece extremamente com as versões que escrevemos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="700a2-127">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the versions we wrote out before.</span></span>
<span data-ttu-id="700a2-128">A única diferença é que informamos explicitamente o compilador de que `Map` não depende diretamente do que `'Input` e `'Output` são, mas funciona para qualquer dois tipos, utilizando-os indiretamente através `fn`.</span><span class="sxs-lookup"><span data-stu-id="700a2-128">The only difference is that we have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="700a2-129">Uma vez definido`Map<'Input, 'Output>` desta forma, podemos chamá-lo como se fosse uma função comum:</span><span class="sxs-lookup"><span data-stu-id="700a2-129">Once we have defined `Map<'Input, 'Output>` in this way, we can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="700a2-130">Escrever funções e operações genéricas é um lugar onde "tuple-in tuple-out" é uma forma muito útil de pensar sobre as funções e operações q#.</span><span class="sxs-lookup"><span data-stu-id="700a2-130">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="700a2-131">Uma vez que cada função requer exatamente uma entrada e devolve exatamente uma saída, uma entrada de tipo `'T -> 'U` corresponde a *qualquer* função Q# qualquer.</span><span class="sxs-lookup"><span data-stu-id="700a2-131">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="700a2-132">Da mesma forma, qualquer operação pode ser passada para uma entrada de tipo `'T => 'U`.</span><span class="sxs-lookup"><span data-stu-id="700a2-132">Similarly, any operation can be passed to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="700a2-133">Como segundo exemplo, considere o desafio de escrever uma função que retorne a composição de duas outras funções:</span><span class="sxs-lookup"><span data-stu-id="700a2-133">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="700a2-134">Aqui, temos de especificar exatamente quais são os `A`, `B`e `C`, limitando assim severamente a utilidade da nossa nova função `Compose`.</span><span class="sxs-lookup"><span data-stu-id="700a2-134">Here, we must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="700a2-135">Afinal, `Compose` só depende de `A`, `B`e `C` *via* `innerFn` e `outerFn`.</span><span class="sxs-lookup"><span data-stu-id="700a2-135">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="700a2-136">Como alternativa, podemos, então, adicionar parâmetros de tipo a `Compose` que indiquem que funciona para *qualquer* `A`, `B`e `C`, desde que estes parâmetros correspondam aos esperados por `innerFn` e `outerFn`:</span><span class="sxs-lookup"><span data-stu-id="700a2-136">As an alternative, then, we can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="700a2-137">As bibliotecas padrão Q# fornecem uma gama dessas operações e funções paramétricas tipo para facilitar o fluxo de controlo de ordem mais fácil de expressar.</span><span class="sxs-lookup"><span data-stu-id="700a2-137">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="700a2-138">Estes são discutidos mais no guia padrão da [biblioteca Q#](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="700a2-138">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>

## <a name="borrowing-qubits"></a><span data-ttu-id="700a2-139">Qubits emprestados</span><span class="sxs-lookup"><span data-stu-id="700a2-139">Borrowing Qubits</span></span> ##

<span data-ttu-id="700a2-140">O mecanismo de empréstimo permite a atribuição de qubits que podem ser usados como espaço de risco durante um cálculo.</span><span class="sxs-lookup"><span data-stu-id="700a2-140">The borrowing mechanism allows the allocation of qubits that can be used as scratch space during a computation.</span></span> <span data-ttu-id="700a2-141">Estes qubits geralmente não estão em um estado limpo, ou seja, não são necessariamente inicializados em um estado conhecido como $\ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="700a2-141">These qubits are generally not in a clean state, i.e., they are not necessarily initialized in a known state such as $\ket{0}$.</span></span> <span data-ttu-id="700a2-142">Fala-se também de qubits "sujos", uma vez que o seu estado é desconhecido e pode até ser enredado com outras partes da memória do computador quântico.</span><span class="sxs-lookup"><span data-stu-id="700a2-142">One also speaks of "dirty" qubits as their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span> <span data-ttu-id="700a2-143">Entre os casos de utilização conhecidos de qubits sujos estão implementações de portões CNOT multi-controlados que requerem apenas muito poucos qubits e implementação de incrementadores.</span><span class="sxs-lookup"><span data-stu-id="700a2-143">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>

<span data-ttu-id="700a2-144">No cândia existem exemplos que usam a palavra-chave `borrowing`, por exemplo, a função `MultiControlledXBorrow` definida abaixo.</span><span class="sxs-lookup"><span data-stu-id="700a2-144">In the canon there are examples that use the `borrowing` keyword, for instance the function `MultiControlledXBorrow` defined below.</span></span>
<span data-ttu-id="700a2-145">Se `controls` denota os qubits de controlo que devem ser adicionados a uma operação `X`, então uma geral de `Length(controls)-2` muitas auxiliares sujas serão adicionadas por esta implementação.</span><span class="sxs-lookup"><span data-stu-id="700a2-145">If `controls` denotes the control qubits that should be added to an `X` operation, then an overall of `Length(controls)-2` many dirty ancillas will be added by this implementation.</span></span>

```qsharp
operation MultiControlledXBorrow ( controls : Qubit[] , target : Qubit ) : Unit
is Adj + Ctl {

    body (...) {
        ... // skipping some case handling here
        let numberOfDirtyQubits = numberOfControls - 2;
        borrowing( dirtyQubits = Qubit[ numberOfDirtyQubits ] ) {

            let allQubits = [ target ] + dirtyQubits + controls;
            let lastDirtyQubit = numberOfDirtyQubits;
            let totalNumberOfQubits = Length(allQubits);

            let outerOperation1 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 1, 1, 0, numberOfDirtyQubits , _ );
            
            let innerOperation = 
                CCNOTByIndex(
                    totalNumberOfQubits - 1, totalNumberOfQubits - 2, lastDirtyQubit, _ );
            
            WithA(outerOperation1, innerOperation, allQubits);
            
            let outerOperation2 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 2, 2, 1, numberOfDirtyQubits - 1 , _ );
            
            WithA(outerOperation2, innerOperation, allQubits);
        }
    }

    controlled(extraControls, ...) {
        MultiControlledXBorrow( extraControls + controls, target );
    }
}
```

<span data-ttu-id="700a2-146">Note-se que foi feita uma utilização extensiva do `With` combinador---na sua forma aplicável às operações que suportam a adjoint, ou seja, `WithA`---foi feita neste exemplo, que é um bom estilo de programação como um bom estilo de programação como um bom estilo de programação como um bom estilo de programação como um bom estilo de programação como um bom estilo de programação como um bom estilo de programação como um bom estilo de programação como um bom estilo de programação como a adição de controlo às estruturas que envolvem `With` apenas propaga o controlo à operação interna.</span><span class="sxs-lookup"><span data-stu-id="700a2-146">Note that extensive use of the `With` combinator---in its form that is applicable for operations that support adjoint, i.e., `WithA`---was made in this example which is good programming style as adding control to structures involving `With` only propagates control to the inner operation.</span></span> <span data-ttu-id="700a2-147">Note-se ainda que, para além do `body` da operação, foi explicitamente fornecida uma execução do organismo `controlled` da operação, em vez de recorrer a uma declaração `controlled auto`.</span><span class="sxs-lookup"><span data-stu-id="700a2-147">Further note that here in addition to the `body` of the operation an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span> <span data-ttu-id="700a2-148">A razão para isso é que sabemos pela estrutura do circuito como adicionar facilmente mais controlos que são benéficos em comparação com a adição de controlo a cada portão individual do `body`.</span><span class="sxs-lookup"><span data-stu-id="700a2-148">The reason for this is that we know from the structure of the circuit how to easily add further controls which is beneficial compared to adding control to each and every individual gate in the `body`.</span></span> 

<span data-ttu-id="700a2-149">É instrutivo comparar este código com outra função canon `MultiControlledXClean` que atinja o mesmo objetivo de implementar uma operação de `X` controlada por multiplicação, no entanto, que utiliza vários qubits limpos utilizando o mecanismo `using`.</span><span class="sxs-lookup"><span data-stu-id="700a2-149">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 
