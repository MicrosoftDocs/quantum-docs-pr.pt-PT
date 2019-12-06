---
title: 'Técnicas de Q # – indo além | Microsoft Docs'
description: 'Técnicas de Q #-aprofundando'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: c079364f8808304e0132fa2a4226cd6400e81339
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74863151"
---
# <a name="going-further"></a><span data-ttu-id="c0ad5-103">Aprofundando...</span><span class="sxs-lookup"><span data-stu-id="c0ad5-103">Going Further</span></span> #

<span data-ttu-id="c0ad5-104">Agora que você já viu como escrever programas de Quantum interessantes em Q #, esta seção vai além, apresentando alguns tópicos mais avançados que devem ser úteis no futuro.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-104">Now that you've seen how to write interesting quantum programs in Q#, this section goes further by introducing a few more advanced topics that should prove useful going forward.</span></span>


## <a name="generic-operations-and-functions"></a><span data-ttu-id="c0ad5-105">Operações e funções genéricas</span><span class="sxs-lookup"><span data-stu-id="c0ad5-105">Generic Operations and Functions</span></span> ##

> [!TIP]
> <span data-ttu-id="c0ad5-106">Esta seção pressupõe alguma familiaridade básica com [genéricos C# ](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), em [genéricos, em F# ](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/) [ C++ modelos](https://docs.microsoft.com/cpp/cpp/templates-cpp), ou abordagens semelhantes à metaprogramação em outras linguagens.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-106">This section assumes some basic familiarity with [generics in C#](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), [generics in F#](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [C++ templates](https://docs.microsoft.com/cpp/cpp/templates-cpp), or similar approaches to metaprogramming in other languages.</span></span>

<span data-ttu-id="c0ad5-107">Muitas funções e operações que desejamos definir não dependem muito dos tipos de suas entradas, mas, em vez disso, apenas usam implicitamente seus tipos por meio de alguma outra função ou operação.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-107">Many functions and operations that we might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="c0ad5-108">Por exemplo, considere o conceito de *mapa* comum a muitas linguagens funcionais; dada uma função $f (x) $ e uma coleção de valores $\{x_1, x_2, \dots, x_n\}$, MAP retorna uma nova coleção $\{f (x_1), f (x_2), \dots, f (x_n)\}$.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-108">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="c0ad5-109">Para implementar isso em Q #, podemos aproveitar essas funções como primeira classe.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-109">To implement this in Q#, we can take advantage of that functions are first class.</span></span>
<span data-ttu-id="c0ad5-110">Vamos escrever um exemplo rápido de `Map`, usando ★ como um espaço reservado enquanto descobrimos quais tipos precisamos.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-110">Let's write out a quick example of `Map`, using ★ as a placeholder while we figure out what types we need.</span></span>

```qsharp
function Map(fn : ★ -> ★, values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="c0ad5-111">Observe que essa função parece muito boa, independentemente de quais tipos reais substituímos.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-111">Note this function looks very much the same no matter what actual types we substitute in.</span></span>
<span data-ttu-id="c0ad5-112">Um mapa de inteiros para Paulis, por exemplo, parece muito o mesmo que um mapa de números de ponto flutuante para cadeias de caracteres:</span><span class="sxs-lookup"><span data-stu-id="c0ad5-112">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

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

<span data-ttu-id="c0ad5-113">Em princípio, poderíamos escrever uma versão do `Map` para cada par de tipos que encontramos, mas isso apresenta uma série de dificuldades.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-113">In principle, we could write a version of `Map` for every pair of types that we encounter, but this introduces a number of difficulties.</span></span>
<span data-ttu-id="c0ad5-114">Por exemplo, se encontrarmos um bug no `Map`, devemos garantir que a correção seja aplicada uniformemente em todas as versões do `Map`.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-114">For instance, if we find a bug in `Map`, then we must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="c0ad5-115">Além disso, se construirmos uma nova tupla ou UDT, agora devemos também construir um novo `Map` para acompanhar o novo tipo.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-115">Moreover, if we construct a new tuple or UDT, then we must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="c0ad5-116">Embora isso seja indevido a um pequeno número dessas funções, à medida que coletamos cada vez mais funções da mesma forma que `Map`, o custo da introdução de novos tipos torna-se razoavelmente grande em ordem razoavelmente curta.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-116">While this is tractable for a small number of such functions, as we collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="c0ad5-117">No entanto, grande parte dessa dificuldade faz com que não tenhamos dado ao compilador as informações de que ele precisa para reconhecer como as diferentes versões do `Map` estão relacionadas.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-117">Much of this difficulty results, however, from that the we have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="c0ad5-118">Efetivamente, queremos que o compilador trate `Map` como um tipo de função matemática de *tipos* q # para funções q #.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-118">Effectively, we want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>
<span data-ttu-id="c0ad5-119">Essa noção é formalizada permitindo que funções e operações tenham *parâmetros de tipo*, bem como seus parâmetros de tupla comuns.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-119">This notion is formalized by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="c0ad5-120">Nos exemplos acima, desejamos considerar `Map` como tendo parâmetros de tipo `Int, Pauli` no primeiro caso e `Double, String` no segundo caso.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-120">In the examples above, we wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="c0ad5-121">Na maior parte, esses parâmetros de tipo podem ser usados como se fossem tipos comuns: usamos valores de parâmetros de tipo para criar matrizes e tuplas, chamar funções e operações e atribuir a variáveis comuns ou mutáveis.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-121">For the most part, these type parameters can then be used as though they were ordinary types: we use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="c0ad5-122">O caso mais extremo de dependência indireta é o de qubits, em que um programa Q # não pode contar diretamente com a estrutura do tipo de `Qubit`, mas **deve** passar esses tipos para outras operações e funções.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-122">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type, but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="c0ad5-123">Retornando ao exemplo acima, podemos ver que precisamos que `Map` tenha parâmetros de tipo, um para representar a entrada para `fn` e outro para representar a saída de `fn`.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-123">Returning to the example above, then, we can see that we need `Map` to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="c0ad5-124">Em Q #, isso é escrito pela adição de colchetes angulares (`<>`, não brakets $ \braket{}$!) após o nome de uma função ou operação em sua declaração e listando cada parâmetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-124">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="c0ad5-125">O nome de cada parâmetro de tipo deve começar com um `'`de tique, indicando que ele é um parâmetro de tipo e não um tipo comum (também conhecido como um tipo *concreto* ).</span><span class="sxs-lookup"><span data-stu-id="c0ad5-125">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="c0ad5-126">Por `Map`, portanto, escrevemos:</span><span class="sxs-lookup"><span data-stu-id="c0ad5-126">For `Map`, we thus write:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : 'Input -> 'Output, values : 'Input[]) : 'Output {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="c0ad5-127">Observe que a definição de `Map<'Input, 'Output>` é muito semelhante às versões que escrevemos antes.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-127">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the versions we wrote out before.</span></span>
<span data-ttu-id="c0ad5-128">A única diferença é que nós informamos explicitamente o compilador de que `Map` não depende diretamente do que `'Input` e `'Output` são, mas funciona para dois tipos usando-os indiretamente por meio de `fn`.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-128">The only difference is that we have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="c0ad5-129">Depois de definirmos `Map<'Input, 'Output>` dessa forma, podemos chamá-lo como se fosse uma função comum:</span><span class="sxs-lookup"><span data-stu-id="c0ad5-129">Once we have defined `Map<'Input, 'Output>` in this way, we can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="c0ad5-130">Escrever funções e operações genéricas é um lugar em que "tupla-in-out" é uma maneira muito útil de pensar em funções e operações do Q #.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-130">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="c0ad5-131">Como cada função usa exatamente uma entrada e retorna exatamente uma saída, uma entrada do tipo `'T -> 'U` corresponde a *qualquer* função Q # qualquer.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-131">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="c0ad5-132">Da mesma forma, qualquer operação pode ser passada para uma entrada do tipo `'T => 'U`.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-132">Similarly, any operation can be passed to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="c0ad5-133">Como um segundo exemplo, considere o desafio de escrever uma função que retorne a composição de duas outras funções:</span><span class="sxs-lookup"><span data-stu-id="c0ad5-133">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="c0ad5-134">Aqui, devemos especificar exatamente o que `A`, `B`e `C` são, portanto, limitando seriamente o utilitário de nossa nova função `Compose`.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-134">Here, we must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="c0ad5-135">Afinal, `Compose` depende apenas `A`, `B`e `C` *via* `innerFn` e `outerFn`.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-135">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="c0ad5-136">Como alternativa, podemos adicionar parâmetros de tipo a `Compose` que indicam que ele funciona para *qualquer* `A`, `B`e `C`, contanto que esses parâmetros correspondam aos esperados por `innerFn` e `outerFn`:</span><span class="sxs-lookup"><span data-stu-id="c0ad5-136">As an alternative, then, we can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="c0ad5-137">As bibliotecas padrão de Q # fornecem uma variedade de operações e funções parametrizadas por tipo para facilitar o expressar o fluxo de controle de ordem mais alta.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-137">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="c0ad5-138">Eles são abordados mais detalhadamente no [Guia de biblioteca padrão do Q #](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="c0ad5-138">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>

## <a name="borrowing-qubits"></a><span data-ttu-id="c0ad5-139">Qubits emprestando</span><span class="sxs-lookup"><span data-stu-id="c0ad5-139">Borrowing Qubits</span></span> ##

<span data-ttu-id="c0ad5-140">O mecanismo de empréstimo permite a alocação de qubits que pode ser usada como espaço transitório durante uma computação.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-140">The borrowing mechanism allows the allocation of qubits that can be used as scratch space during a computation.</span></span> <span data-ttu-id="c0ad5-141">Esses qubits geralmente não estão em um estado limpo, ou seja, eles não são necessariamente inicializados em um estado conhecido, como $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-141">These qubits are generally not in a clean state, i.e., they are not necessarily initialized in a known state such as $\ket{0}$.</span></span> <span data-ttu-id="c0ad5-142">Um também fala sobre o qubits "sujo", pois seu estado é desconhecido e pode até mesmo ser confusas com outras partes da memória do computador Quantum.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-142">One also speaks of "dirty" qubits as their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span> <span data-ttu-id="c0ad5-143">Entre os casos de uso conhecidos de qubits sujos estão implementações de Gates de CNOT de vários controle que exigem apenas poucos qubits e implementação de incrementais.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-143">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>

<span data-ttu-id="c0ad5-144">Na Canon, há exemplos que usam a palavra-chave `borrowing`, por exemplo, a função `MultiControlledXBorrow` definida abaixo.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-144">In the canon there are examples that use the `borrowing` keyword, for instance the function `MultiControlledXBorrow` defined below.</span></span>
<span data-ttu-id="c0ad5-145">Se `controls` denota o qubits de controle que deve ser adicionado a uma operação `X`, um geral de `Length(controls)-2` muitos ancillas sujos serão adicionados por essa implementação.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-145">If `controls` denotes the control qubits that should be added to an `X` operation, then an overall of `Length(controls)-2` many dirty ancillas will be added by this implementation.</span></span>

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

<span data-ttu-id="c0ad5-146">Observe que o uso extensivo do `With` combinador---em seu formato aplicável a operações que dão suporte a adpositivo, ou seja, `WithA`---foi feita neste exemplo, o que é bom estilo de programação, pois adicionar controle às estruturas que envolvem `With` só propaga o controle para a operação interna.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-146">Note that extensive use of the `With` combinator---in its form that is applicable for operations that support adjoint, i.e., `WithA`---was made in this example which is good programming style as adding control to structures involving `With` only propagates control to the inner operation.</span></span> <span data-ttu-id="c0ad5-147">Observe ainda que, além do `body` da operação, uma implementação do `controlled` corpo da operação foi explicitamente fornecida, em vez de recorrer a uma instrução `controlled auto`.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-147">Further note that here in addition to the `body` of the operation an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span> <span data-ttu-id="c0ad5-148">O motivo disso é que sabemos da estrutura do circuito como adicionar com facilidade mais controles, o que é benéfico em comparação à adição de controle a cada porta individual na `body`.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-148">The reason for this is that we know from the structure of the circuit how to easily add further controls which is beneficial compared to adding control to each and every individual gate in the `body`.</span></span> 

<span data-ttu-id="c0ad5-149">É instrutivo comparar esse código com outra função Canon `MultiControlledXClean` que atinge o mesmo objetivo de implementar uma operação de `X` com controle de multiplicação, no entanto, que usa várias qubits limpas usando o mecanismo de `using`.</span><span class="sxs-lookup"><span data-stu-id="c0ad5-149">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 
