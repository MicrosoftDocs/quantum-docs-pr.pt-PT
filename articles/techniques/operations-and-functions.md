---
title: 'Q # técnicas-operações e funções | Microsoft Docs'
description: 'Técnicas de Q # – operações e funções'
uid: microsoft.quantum.techniques.opsandfunctions
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 06da09dc9c6e0ba0331db6bc0cd3d2ddeb287113
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183459"
---
# <a name="q-operations-and-functions"></a><span data-ttu-id="164b6-103">Operações e funções do Q #</span><span class="sxs-lookup"><span data-stu-id="164b6-103">Q# Operations and Functions</span></span>

<span data-ttu-id="164b6-104">Os programas de Q # consistem em uma ou mais *operações* que descrevem os efeitos colaterais que as operações Quantum podem ter em dados Quantum e uma ou mais *funções* que permitem modificações em dados clássicos.</span><span class="sxs-lookup"><span data-stu-id="164b6-104">Q# programs consist of one or more *operations* that describe side effects quantum operations can have on quantum data, and one or more *functions* that allow modifications to classical data.</span></span> <span data-ttu-id="164b6-105">Em contraste com as operações, as funções são usadas para descrever o comportamento puramente clássico e não têm nenhum efeito além de calcular os valores de saída clássicas.</span><span class="sxs-lookup"><span data-stu-id="164b6-105">In contrast to operations, functions are used to describe purely classical behavior and do not have any effects besides computing classical output values.</span></span>

<span data-ttu-id="164b6-106">Cada operação definida em Q # pode então chamar qualquer número de outras operações, incluindo as operações intrínsecas internas definidas pelo idioma.</span><span class="sxs-lookup"><span data-stu-id="164b6-106">Each operation defined in Q# may then call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="164b6-107">A maneira específica em que essas operações intrínsecas são definidas depende da máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="164b6-107">The particular way in which these intrinsic operations are defined depends on the target machine.</span></span> <span data-ttu-id="164b6-108">Quando compilada, cada operação é representada como um tipo de classe do .NET que pode ser fornecido para os computadores de destino.</span><span class="sxs-lookup"><span data-stu-id="164b6-108">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="164b6-109">Definindo novas operações</span><span class="sxs-lookup"><span data-stu-id="164b6-109">Defining New Operations</span></span>

<span data-ttu-id="164b6-110">Conforme descrito acima, o bloco de construção mais básico de um programa Quantum escrito em Q # é uma *operação*, que pode ser chamada a partir de aplicativos .net clássicos, por exemplo, usando um simulador ou por outras operações em Q #.</span><span class="sxs-lookup"><span data-stu-id="164b6-110">As described above, the most basic building block of a quantum program written in Q# is an *operation*, which can either be called from classical .NET applications, e.g., using a simulator, or by other operations within Q#.</span></span>
<span data-ttu-id="164b6-111">Cada operação usa uma entrada, produz uma saída e especifica a implementação para uma ou mais especializações de operação.</span><span class="sxs-lookup"><span data-stu-id="164b6-111">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="164b6-112">Por exemplo, a operação a seguir define apenas uma especialização de corpo padrão e usa um único qubit como sua entrada e, em seguida, chama a operação de `X` interna nessa entrada:</span><span class="sxs-lookup"><span data-stu-id="164b6-112">For instance, the following operation defines only a default body specialization and takes a single qubit as its input, then calls the built-in `X` operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="164b6-113">A palavra-chave `operation` começa a definição da operação e é seguida pelo nome; aqui, `BitFlip`.</span><span class="sxs-lookup"><span data-stu-id="164b6-113">The keyword `operation` begins the operation definition, and is followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="164b6-114">Em seguida, o tipo da entrada é definido como `Qubit`, juntamente com um nome `target` para fazer referência à entrada dentro da nova operação.</span><span class="sxs-lookup"><span data-stu-id="164b6-114">Next, the type of the input is defined as `Qubit`, along with a name `target` for referring to the input within the new operation.</span></span>
<span data-ttu-id="164b6-115">Da mesma forma, a `Unit` define que a saída da operação está vazia.</span><span class="sxs-lookup"><span data-stu-id="164b6-115">Similarly, the `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="164b6-116">Isso é usado da mesma forma para C# `void` e outras linguagens imperativas e é equivalente a F# `unit` no e outras linguagens funcionais.</span><span class="sxs-lookup"><span data-stu-id="164b6-116">This is used similarly to `void` in C# and other imperative languages, and is equivalent to `unit` in F# and other functional languages.</span></span>

> [!NOTE]
> <span data-ttu-id="164b6-117">Exploraremos isso mais detalhadamente abaixo, mas cada operação em Q # usa exatamente uma entrada e retorna exatamente uma saída.</span><span class="sxs-lookup"><span data-stu-id="164b6-117">We will explore this in more detail below, but each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="164b6-118">Várias entradas e saídas são representadas usando *tuplas*, que coletam vários valores juntos em um único valor.</span><span class="sxs-lookup"><span data-stu-id="164b6-118">Multiple inputs and outputs are then represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="164b6-119">Informalmente, dizemos que Q # é uma linguagem de "tupla na tupla".</span><span class="sxs-lookup"><span data-stu-id="164b6-119">Informally, we say that Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="164b6-120">Seguindo esse conceito, `()` deve ser lido como a tupla "Empty", que tem o tipo `Unit`.</span><span class="sxs-lookup"><span data-stu-id="164b6-120">Following this concept, `()` should then be read as the "empty" tuple, which has the type `Unit`.</span></span>

<span data-ttu-id="164b6-121">Na nova operação, a implementação pode ser especificada diretamente na declaração se apenas a implementação da especialização de corpo padrão precisar ser especificada explicitamente.</span><span class="sxs-lookup"><span data-stu-id="164b6-121">Within the new operation, the implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to be specified explicitly.</span></span> <span data-ttu-id="164b6-122">Além disso, é possível definir as implementações de, por exemplo, uma ou mais operações de `functor`, conforme elaborado abaixo.</span><span class="sxs-lookup"><span data-stu-id="164b6-122">Additionally, it is possible to define the implementations of, for example, one or more `functor` operations, as elaborated below.</span></span> <span data-ttu-id="164b6-123">No exemplo acima, a única instrução é chamar a operação interna Q # <xref:microsoft.quantum.intrinsic.x>.</span><span class="sxs-lookup"><span data-stu-id="164b6-123">In the example above, the only statement is to call the built-in Q# operation <xref:microsoft.quantum.intrinsic.x>.</span></span>

<span data-ttu-id="164b6-124">As operações também podem retornar tipos mais interessantes do que `Unit`.</span><span class="sxs-lookup"><span data-stu-id="164b6-124">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="164b6-125">Por exemplo, a operação <xref:microsoft.quantum.intrinsic.m> retorna uma saída do tipo `Result`, representando tendo realizado uma medição.</span><span class="sxs-lookup"><span data-stu-id="164b6-125">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span> <span data-ttu-id="164b6-126">Podemos passar a saída de uma operação para outra operação ou pode usá-la com a palavra-chave `let` para definir uma nova variável.</span><span class="sxs-lookup"><span data-stu-id="164b6-126">We can either pass the output from an operation to another operation, or can use it with the `let` keyword to define a new variable.</span></span>
<!-- Link to UID for superdense conceptual and example documentation. -->
<span data-ttu-id="164b6-127">Isso permite representar a computação clássica que interage com as operações Quantum em um nível baixo, como na codificação superdensa:</span><span class="sxs-lookup"><span data-stu-id="164b6-127">This allows for representing classical computation that interacts with quantum operations at a low level, such as in superdense coding:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a><span data-ttu-id="164b6-128">Transmissão functors, adjoine e controlado</span><span class="sxs-lookup"><span data-stu-id="164b6-128">Functors, adjoint and controlled</span></span>
<span data-ttu-id="164b6-129">Se uma operação implementar uma transformação unitário, será possível definir como a operação age quando *adjointed* ou *controlada*.</span><span class="sxs-lookup"><span data-stu-id="164b6-129">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="164b6-130">Uma especialização adjacente de uma operação especifica como ela funciona quando executada em ordem inversa, enquanto uma especialização controlada especifica como uma operação age quando aplicada com condição no estado de um registro Quantum.</span><span class="sxs-lookup"><span data-stu-id="164b6-130">An adjoint specialization of an operation specifies how it acts when run in reverse, while a controlled specialization specifies how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="164b6-131">A existência dessas especializações pode ser declarada como parte da assinatura da operação: `is Adj + Ctl` no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="164b6-131">The existence of these specializations can be declared as part of the operation signature: `is Adj + Ctl` in the following example.</span></span> <span data-ttu-id="164b6-132">A implementação correspondente para cada tal especialização declarada implicitamente é gerada pelo compilador.</span><span class="sxs-lookup"><span data-stu-id="164b6-132">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> <span data-ttu-id="164b6-133">Muitas operações em Q # representam Gates unitários.</span><span class="sxs-lookup"><span data-stu-id="164b6-133">Many operations in Q# represent unitary gates.</span></span>
> <span data-ttu-id="164b6-134">Se $U $ é o portão unitário representado por uma operação `U`, `Adjoint U` representa o portão unitário $U ^ \dagger $.</span><span class="sxs-lookup"><span data-stu-id="164b6-134">If $U$ is the unitary gate represented by an operation `U`, then `Adjoint U` represents the unitary gate $U^\dagger$.</span></span>

<span data-ttu-id="164b6-135">No caso em que a implementação não pode ser gerada pelo compilador, ela pode ser especificada explicitamente.</span><span class="sxs-lookup"><span data-stu-id="164b6-135">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="164b6-136">Essas declarações de especialização explícitas podem consistir em uma diretiva de geração adequada ou em uma implementação definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="164b6-136">Such explicit specialization declarations can consist of a suitable generation directive or a user defined implementation.</span></span> <span data-ttu-id="164b6-137">O código em `PrepareEntangledPair` acima, por exemplo, é equivalente ao código abaixo que contém declarações de especialização explícitas:</span><span class="sxs-lookup"><span data-stu-id="164b6-137">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="164b6-138">A palavra-chave `auto` indica que o compilador deve determinar como gerar a implementação de especialização.</span><span class="sxs-lookup"><span data-stu-id="164b6-138">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="164b6-139">Se o compilador não puder gerar a implementação para determinada especialização automaticamente ou se uma implementação mais eficiente puder ser fornecida, a implementação também poderá ser definida manualmente.</span><span class="sxs-lookup"><span data-stu-id="164b6-139">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
<span data-ttu-id="164b6-140">No exemplo acima, `adjoint invert;` indica que a especialização de adjacente deve ser gerada ao inverter a implementação do corpo e `controlled adjoint invert;` indica que a especialização adjacente controlada deve ser gerada por meio da inversão da implementação fornecida do especialização controlada.</span><span class="sxs-lookup"><span data-stu-id="164b6-140">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="164b6-141">Veremos mais exemplos disso no fluxo de [controle de ordem superior](xref:microsoft.quantum.concepts.control-flow).</span><span class="sxs-lookup"><span data-stu-id="164b6-141">We will see more examples of this in [Higher-Order Control Flow](xref:microsoft.quantum.concepts.control-flow).</span></span>

<span data-ttu-id="164b6-142">Para chamar uma especialização de uma operação, use as palavras-chave `Adjoint` ou `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="164b6-142">To call a specialization of an operation, use the `Adjoint` or `Controlled` keywords.</span></span>
<span data-ttu-id="164b6-143">Por exemplo, o exemplo de codificação superdensar acima pode ser escrito mais compactamente usando o `PrepareEntangledPair` de código para transformar o estado confusas de volta em um par unentangled de qubits:</span><span class="sxs-lookup"><span data-stu-id="164b6-143">For example, the superdense coding example above can be written more compactly by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="164b6-144">Há várias limitações importantes a serem consideradas ao criar operações para uso com o transmissão functors.</span><span class="sxs-lookup"><span data-stu-id="164b6-144">There are a number of important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="164b6-145">O mais importante é que as especializações para uma operação que usa o valor de saída de qualquer outra operação não podem ser geradas automaticamente pelo compilador, pois é ambígua como reordenar as instruções nessa operação para obter o mesmo efeito.</span><span class="sxs-lookup"><span data-stu-id="164b6-145">Most critically, specializations for an operation that uses the output value of any other operation cannot be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>


## <a name="defining-new-functions"></a><span data-ttu-id="164b6-146">Definindo novas funções</span><span class="sxs-lookup"><span data-stu-id="164b6-146">Defining New Functions</span></span>

<span data-ttu-id="164b6-147">O Q # também permite definir *funções*, que são diferentes das operações, pois não têm permissão para ter nenhum efeito além de calcular um valor de saída.</span><span class="sxs-lookup"><span data-stu-id="164b6-147">Q# also allows for defining *functions*, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="164b6-148">Em particular, as funções não podem chamar operações, agir em qubits, números aleatórios de exemplo ou depender de outro Estado além do valor de entrada para uma função.</span><span class="sxs-lookup"><span data-stu-id="164b6-148">In particular, functions cannot call operations, act on qubits, sample random numbers, or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="164b6-149">Como consequência, as funções Q # são *puras*, pois elas sempre mapeiam os mesmos valores de entrada para os mesmos valores de saída.</span><span class="sxs-lookup"><span data-stu-id="164b6-149">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="164b6-150">Isso permite que o compilador Q # reordene com segurança como e quando as funções são chamadas ao gerar especializações de operação.</span><span class="sxs-lookup"><span data-stu-id="164b6-150">This allows the Q# compiler to safely reorder how and when functions are called when generating operation specializations.</span></span>

<span data-ttu-id="164b6-151">A definição de uma função funciona de forma semelhante à definição de uma operação, exceto que nenhuma especialização adjacente ou controlada pode ser definida para uma função.</span><span class="sxs-lookup"><span data-stu-id="164b6-151">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="164b6-152">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="164b6-152">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
<span data-ttu-id="164b6-153">Sempre que for possível fazer isso, é útil escrever a lógica clássica em termos de funções em vez de operações, para que ela possa ser usada mais prontamente em operações.</span><span class="sxs-lookup"><span data-stu-id="164b6-153">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations, so that it can be more readily used from within operations.</span></span>
<span data-ttu-id="164b6-154">Se tivéssemos escrito `Square` como uma operação, por exemplo, o compilador não teria conseguido garantir que chamá-lo com a mesma entrada produzirá consistentemente as mesmas saídas.</span><span class="sxs-lookup"><span data-stu-id="164b6-154">If we had written `Square` as an operation, for example, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="164b6-155">Para enfatizar a diferença entre funções e operações, considere o problema de amostragem clássica de um número aleatório de dentro de uma operação Q #:</span><span class="sxs-lookup"><span data-stu-id="164b6-155">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="164b6-156">Cada vez que `U` for chamado, ele terá uma ação diferente em `target`.</span><span class="sxs-lookup"><span data-stu-id="164b6-156">Each time that `U` is called, it will have a different action on `target`.</span></span>
<span data-ttu-id="164b6-157">Em particular, o compilador não pode garantir que, se adicionamos uma declaração de especialização de `adjoint auto` para `U`, `U(target); Adjoint U(target);` atua como identidade (ou seja, como não operacional).</span><span class="sxs-lookup"><span data-stu-id="164b6-157">In particular, the compiler cannot guarantee that if we added an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="164b6-158">Isso viola a definição do adjoin que vimos em [vetores e matrizes](xref:microsoft.quantum.concepts.vectors), de modo que permitir a geração automática de uma especialização adjacente em uma operação em que chamamos a operação <xref:microsoft.quantum.math.randomreal> interromperia as garantias fornecidas pelo compilador ; <xref:microsoft.quantum.math.randomreal> é uma operação para a qual não existe nenhuma versão adjacente ou controlada.</span><span class="sxs-lookup"><span data-stu-id="164b6-158">This violates the definition of the adjoint that we saw in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing to auto-generate an adjoint specialization in an operation where we have called the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="164b6-159">Por outro lado, permitir chamadas de função como `Square` é seguro, pois o compilador pode ter certeza de que ele só precisa preservar a entrada para `Square` para manter sua saída estável.</span><span class="sxs-lookup"><span data-stu-id="164b6-159">On the other hand, allowing function calls such as `Square` is safe, in that the compiler can be assured that it only needs to preserve the input to `Square` in order to keep its output stable.</span></span>
<span data-ttu-id="164b6-160">Portanto, isolar o máximo de lógica clássica possível em funções facilita a reutilização dessa lógica em outras funções e operações semelhantes.</span><span class="sxs-lookup"><span data-stu-id="164b6-160">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>

## <a name="control-flow"></a><span data-ttu-id="164b6-161">Fluxo de Controlo</span><span class="sxs-lookup"><span data-stu-id="164b6-161">Control Flow</span></span>

<span data-ttu-id="164b6-162">Em uma operação ou função, cada instrução é executada em ordem, semelhante às linguagens clássicas mais comuns.</span><span class="sxs-lookup"><span data-stu-id="164b6-162">Within an operation or function, each statement executes in order, similar to most common imperative classical languages.</span></span>
<span data-ttu-id="164b6-163">No entanto, esse fluxo de controle pode ser modificado de três maneiras distintas:</span><span class="sxs-lookup"><span data-stu-id="164b6-163">This flow of control can be modified, however, in three distinct ways:</span></span>

- <span data-ttu-id="164b6-164">Instruções de `if`</span><span class="sxs-lookup"><span data-stu-id="164b6-164">`if` Statements</span></span>
- <span data-ttu-id="164b6-165">Loops de `for`</span><span class="sxs-lookup"><span data-stu-id="164b6-165">`for` Loops</span></span>
- <span data-ttu-id="164b6-166">`repeat`-loops de `until`</span><span class="sxs-lookup"><span data-stu-id="164b6-166">`repeat`-`until` Loops</span></span>

<span data-ttu-id="164b6-167">Adiamos a discussão do segundo até discutirmos a [repetição até que os circuitos de sucesso (RUS)](xref:microsoft.quantum.techniques.qubits#measurements) .</span><span class="sxs-lookup"><span data-stu-id="164b6-167">We defer discussion of the latter until we discuss [Repeat Until Success (RUS)](xref:microsoft.quantum.techniques.qubits#measurements) circuits.</span></span>
<span data-ttu-id="164b6-168">No entanto, as construções de fluxo de controle `if` e `for`, no entanto, prosseguem de forma familiar com a maioria das linguagens de programação clássicas.</span><span class="sxs-lookup"><span data-stu-id="164b6-168">The `if` and `for` control flow constructs, however, proceed in a familiar sense to most classical programming languages.</span></span>
<span data-ttu-id="164b6-169">Em particular, uma instrução `if` pode tomar uma condição, pode ser seguida por uma ou mais instruções `elif` e pode terminar com uma `else`:</span><span class="sxs-lookup"><span data-stu-id="164b6-169">In particular, an `if` statement can take a condition, may be followed by one or more `elif` statements, and may end with an `else`:</span></span>

```qsharp
if (pauli == PauliX) {
    X(qubit);
} elif (pauli == PauliY) {
    Y(qubit);
} elif (pauli == PauliZ) {
    Z(qubit);
} else {
    fail "Cannot use PauliI here.";
}
```

<span data-ttu-id="164b6-170">Da mesma forma, `for` loops indicam a iteração em um intervalo de inteiros ou sobre os elementos de uma matriz:</span><span class="sxs-lookup"><span data-stu-id="164b6-170">Similarly, `for` loops indicate iteration over a range of integers or over the elements of an array:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

<span data-ttu-id="164b6-171">Importante, `for` loops e instruções de `if` podem até ser usados em operações para as quais as especializações são geradas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="164b6-171">Importantly, `for` loops and `if` statements can even be used in operations for which specializations are auto-generated.</span></span> <span data-ttu-id="164b6-172">Nesse caso, o adjoin de um loop de `for` inverte a direção e leva o adjacente de cada iteração.</span><span class="sxs-lookup"><span data-stu-id="164b6-172">In that case the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="164b6-173">Isso segue o princípio "sapatos-and-Socks": se você deseja desfazer a colocação em SOCKS e, em seguida, os sapatos, você deve desfazer a colocação de sapatos e, em seguida, desfazer a colocação em Socks.</span><span class="sxs-lookup"><span data-stu-id="164b6-173">This follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span>
<span data-ttu-id="164b6-174">Ele funciona decididamente menos bem para tentar e retomar seus Socks enquanto você ainda estiver aproveitando seus sapatos!</span><span class="sxs-lookup"><span data-stu-id="164b6-174">It works decidedly less well to try and take your socks off while you're still wearing your shoes!</span></span>

## <a name="operations-and-functions-as-first-class-values"></a><span data-ttu-id="164b6-175">Operações e funções como valores de primeira classe</span><span class="sxs-lookup"><span data-stu-id="164b6-175">Operations and Functions as First-Class Values</span></span>

<span data-ttu-id="164b6-176">Uma técnica crítica para o raciocínio sobre o fluxo de controle e a lógica clássica usando funções em vez de operações é utilizar essas operações e funções em Q # são de *primeira classe*.</span><span class="sxs-lookup"><span data-stu-id="164b6-176">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="164b6-177">Ou seja, eles são cada um dos valores no idioma que estão no seu próprio direito.</span><span class="sxs-lookup"><span data-stu-id="164b6-177">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="164b6-178">Por exemplo, este é um código Q # perfeitamente válido, se um pouco indireto:</span><span class="sxs-lookup"><span data-stu-id="164b6-178">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="164b6-179">O valor da variável `ourH` no trecho acima é, então, a operação <xref:microsoft.quantum.intrinsic.h>, de modo que possamos chamar esse valor como qualquer outra operação.</span><span class="sxs-lookup"><span data-stu-id="164b6-179">The value of the variable `ourH` in the snippet above is then the operation <xref:microsoft.quantum.intrinsic.h>, such that we can call that value like any other operation.</span></span>
<span data-ttu-id="164b6-180">Isso nos permite escrever operações que usam operações como parte de sua entrada, formando conceitos de fluxo de controle de ordem mais alta.</span><span class="sxs-lookup"><span data-stu-id="164b6-180">This allows us to write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="164b6-181">Por exemplo, podemos imaginar que queira "quadrado" uma operação aplicando-a duas vezes ao mesmo qubit de destino.</span><span class="sxs-lookup"><span data-stu-id="164b6-181">For instance, we could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

<span data-ttu-id="164b6-182">Neste exemplo, a `=>` seta exibida no tipo `(Qubit => Unit)` denota que o campo de entrada `op` é uma operação que usa como entrada o tipo `Qubit` e produz uma tupla vazia como sua saída.</span><span class="sxs-lookup"><span data-stu-id="164b6-182">In this example, the `=>` arrow that appears in the type `(Qubit => Unit)` denotes that the input field `op` is an operation which takes as its input the type `Qubit` and produces an empty tuple as its output.</span></span>
<span data-ttu-id="164b6-183">Além disso, especificamos as características desse tipo de operação, que contêm as informações sobre quais transmissão functors têm suporte.</span><span class="sxs-lookup"><span data-stu-id="164b6-183">Additionally we specify the characteristics of that operation type, which contain the information about which functors are supported.</span></span>
<span data-ttu-id="164b6-184">Uma operação do tipo `(Qubit => Unit)` não dá suporte aos `Adjoint` nem ao `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="164b6-184">An operation of type `(Qubit => Unit)` supports neither the `Adjoint` nor the `Controlled` functor.</span></span> <span data-ttu-id="164b6-185">Se quisermos indicar que uma operação desse tipo deve dar suporte, por exemplo, a `Adjoint` functor, precisamos declará-la como sendo de adjointable.</span><span class="sxs-lookup"><span data-stu-id="164b6-185">If we want to indicate that an operation of that type has to support e.g. the `Adjoint` functor, we have to declare it as being adjointable.</span></span> <span data-ttu-id="164b6-186">Isso é feito usando a anotação `is Adj` para o tipo.</span><span class="sxs-lookup"><span data-stu-id="164b6-186">This is done by using the annotation `is Adj` to the type.</span></span> <span data-ttu-id="164b6-187">Da mesma forma, `(Qubit => Unit is Ctl)` denota que uma operação desse tipo dá suporte ao `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="164b6-187">Similarly, `(Qubit => Unit is Ctl)` denotes that an operation of that type supports the `Controlled` functor.</span></span> <span data-ttu-id="164b6-188">Exploraremos isso ainda mais quando discutimos [Types in Q #] (xref: Microsoft. Quantum. Language. Type-Model) mais geralmente.</span><span class="sxs-lookup"><span data-stu-id="164b6-188">We will explore this further when we discuss [types in Q#] (xref:microsoft.quantum.language.type-model) more generally.</span></span>

<span data-ttu-id="164b6-189">Por enquanto, enfatizamos que também podemos retornar operações como parte das saídas, de modo que possamos isolar alguns tipos de lógica condicional clássica como uma função clássica que retorna uma descrição de um programa Quantum na forma de uma operação.</span><span class="sxs-lookup"><span data-stu-id="164b6-189">For now, we emphasize that we can also return operations as a part of outputs, such that we can isolate some kinds of classical conditional logic as a classical function which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="164b6-190">Como exemplo simples, considere o exemplo de teleportação, no qual a parte que recebe uma mensagem clássica de dois bits precisa usar a mensagem para decodificar seu qubit no estado de Teleporta adequado.</span><span class="sxs-lookup"><span data-stu-id="164b6-190">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="164b6-191">Poderíamos escrever isso em termos de uma função que pega esses dois bits clássicos e retorna a operação de decodificação adequada.</span><span class="sxs-lookup"><span data-stu-id="164b6-191">We could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

<span data-ttu-id="164b6-192">Essa nova função é realmente uma função, já que, se o chamarmos com os mesmos valores de `hereBit` e `thereBit`, sempre obteremos a mesma operação.</span><span class="sxs-lookup"><span data-stu-id="164b6-192">This new function is indeed a function, in that if we call it with the same values of `hereBit` and `thereBit`, we will always get back the same operation.</span></span>
<span data-ttu-id="164b6-193">Assim, o decodificador pode ser executado com segurança dentro de operações sem ter que ter por motivo de como a lógica de decodificação interage com as definições das diferentes especializações de operação.</span><span class="sxs-lookup"><span data-stu-id="164b6-193">Thus, the decoder can be safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="164b6-194">Ou seja, isolamos a lógica clássica dentro de uma função, garantindo ao compilador que a chamada de função pode ser reordenada com impunity, desde que a entrada seja preservada.</span><span class="sxs-lookup"><span data-stu-id="164b6-194">That is, we have isolated the classical logic inside a function, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>

<span data-ttu-id="164b6-195">Também podemos tratar funções como valores de primeira classe, como veremos mais detalhadamente quando discutimos [as operações e os tipos de função](#operations-and-functions-as-first-class-values).</span><span class="sxs-lookup"><span data-stu-id="164b6-195">We can also treat functions as first-class values, as we will see in more detail when we discuss [operations and function types](#operations-and-functions-as-first-class-values).</span></span>

## <a name="partially-applying-operations-and-functions"></a><span data-ttu-id="164b6-196">Aplicação parcial de operações e funções</span><span class="sxs-lookup"><span data-stu-id="164b6-196">Partially Applying Operations and Functions</span></span>

<span data-ttu-id="164b6-197">Podemos fazer significativamente mais com funções que retornam operações usando o *aplicativo parcial*, no qual podemos fornecer uma ou mais partes da entrada a uma função ou operação sem realmente chamá-la.</span><span class="sxs-lookup"><span data-stu-id="164b6-197">We can do significantly more with functions that return operations by using *partial application*, in which we can provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="164b6-198">Por exemplo, rechamar o exemplo de `ApplyTwice` acima, podemos indicar que não queremos especificar, imediatamente, a qual qubit a operação de entrada deve ser aplicada:</span><span class="sxs-lookup"><span data-stu-id="164b6-198">For example, recalling the `ApplyTwice` example above, we can indicate that we don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="164b6-199">Nesse caso, a variável local `twiceOp` mantém a operação parcialmente aplicada `ApplyTwice(op, _)`, em que partes da entrada que ainda não foram especificadas são indicadas por `_`.</span><span class="sxs-lookup"><span data-stu-id="164b6-199">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where parts of the input that have not yet been specified are indicated by `_`.</span></span>
<span data-ttu-id="164b6-200">Quando realmente chamamos `twiceOp` na próxima linha, passamos como entrada para a operação parcialmente aplicada todas as partes restantes da entrada para a operação original.</span><span class="sxs-lookup"><span data-stu-id="164b6-200">When we actually call `twiceOp` in the next line, we pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="164b6-201">Assim, o trecho acima é efetivamente idêntico a ter chamado `ApplyTwice(op, target)` diretamente, salvar para que tenhamos introduzido uma nova variável local que nos permite atrasar a chamada enquanto fornece algumas partes da entrada.</span><span class="sxs-lookup"><span data-stu-id="164b6-201">Thus, the above snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that we have introduced a new local variable that allows us to delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="164b6-202">Como uma operação que foi parcialmente aplicada não é realmente chamada até que toda a sua entrada tenha sido fornecida, podemos aplicar operações parcialmente de forma segura, mesmo a partir de funções.</span><span class="sxs-lookup"><span data-stu-id="164b6-202">Since an operation that has been partially applied is not actually called until its entire input has been provided, we can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="164b6-203">Em princípio, a lógica clássica dentro de `SquareOperation` poderia ter sido muito mais envolvida, mas ainda é isolada do restante de uma operação pelas garantias que o compilador pode oferecer sobre as funções.</span><span class="sxs-lookup"><span data-stu-id="164b6-203">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span>
<span data-ttu-id="164b6-204">Essa abordagem será usada em toda a biblioteca padrão de Q # para expressar o fluxo de controle clássico de forma que possa ser prontamente usada em programas Quantum.</span><span class="sxs-lookup"><span data-stu-id="164b6-204">This approach will be used throughout the Q# standard library for expressing classical control flow in a way that can be readily used within quantum programs.</span></span>
