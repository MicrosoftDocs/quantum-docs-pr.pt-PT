---
title: Operações e funções - Técnicas Q# Microsoft Docs
description: Operações e funções - Técnicas Q#
uid: microsoft.quantum.techniques.opsandfunctions
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 1fca20bb44cc42008f7d25d2fc71a39b962525c2
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820781"
---
# <a name="q-operations-and-functions"></a><span data-ttu-id="f5c8a-103">Q# Operações e Funções</span><span class="sxs-lookup"><span data-stu-id="f5c8a-103">Q# Operations and Functions</span></span>

<span data-ttu-id="f5c8a-104">Os programas q# consistem em uma ou mais *operações* que descrevem os efeitos colaterais que as operações quânticas podem ter nos dados *quânticos,* e uma ou mais funções que permitem modificações a dados clássicos.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-104">Q# programs consist of one or more *operations* that describe side effects quantum operations can have on quantum data, and one or more *functions* that allow modifications to classical data.</span></span> <span data-ttu-id="f5c8a-105">Em contraste com as operações, as funções são usadas para descrever comportamentos puramente clássicos e não têm quaisquer efeitos além de calcular valores de saída clássicos.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-105">In contrast to operations, functions are used to describe purely classical behavior and do not have any effects besides computing classical output values.</span></span>

<span data-ttu-id="f5c8a-106">Cada operação definida em Q# pode então chamar qualquer número de outras operações, incluindo as operações intrínsecas incorporadas definidas pela língua.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-106">Each operation defined in Q# may then call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="f5c8a-107">A forma particular como estas operações intrínsecas são definidas depende da máquina-alvo.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-107">The particular way in which these intrinsic operations are defined depends on the target machine.</span></span> <span data-ttu-id="f5c8a-108">Quando compilado, cada operação é representada como um tipo de classe .NET que pode ser fornecido às máquinas-alvo.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-108">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="f5c8a-109">Definição de Novas Operações</span><span class="sxs-lookup"><span data-stu-id="f5c8a-109">Defining New Operations</span></span>

<span data-ttu-id="f5c8a-110">Como descrito acima, o bloco de construção mais básico de um programa quântico escrito em Q# é uma *operação*, que pode ser chamada de aplicações clássicas .NET, por exemplo, usando um simulador, ou por outras operações dentro de Q#.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-110">As described above, the most basic building block of a quantum program written in Q# is an *operation*, which can either be called from classical .NET applications, e.g., using a simulator, or by other operations within Q#.</span></span>
<span data-ttu-id="f5c8a-111">Cada operação tem uma entrada, produz uma saída e especifica a implementação para uma ou mais especializações de operação.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-111">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="f5c8a-112">Por exemplo, a operação seguinte define apenas uma especialização corporal padrão e toma um único qubit como entrada, em seguida, chama a operação de `X` incorporada nessa entrada:</span><span class="sxs-lookup"><span data-stu-id="f5c8a-112">For instance, the following operation defines only a default body specialization and takes a single qubit as its input, then calls the built-in `X` operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="f5c8a-113">A palavra-chave `operation` inicia a definição de operação, e é seguida pelo nome; aqui, `BitFlip`.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-113">The keyword `operation` begins the operation definition, and is followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="f5c8a-114">Em seguida, o tipo de entrada é definido como `Qubit`, juntamente com um nome `target` por se referir à entrada dentro da nova operação.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-114">Next, the type of the input is defined as `Qubit`, along with a name `target` for referring to the input within the new operation.</span></span>
<span data-ttu-id="f5c8a-115">Da mesma forma, o `Unit` define que a saída da operação está vazia.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-115">Similarly, the `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="f5c8a-116">Isto é usado da C# mesma forma que `void` em e F# outras línguas imperativas, e é equivalente a `unit` em e outras línguas funcionais.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-116">This is used similarly to `void` in C# and other imperative languages, and is equivalent to `unit` in F# and other functional languages.</span></span>

> [!NOTE]
> <span data-ttu-id="f5c8a-117">Vamos explorar isto com mais detalhes abaixo, mas cada operação em Q# leva exatamente uma entrada e devolve exatamente uma saída.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-117">We will explore this in more detail below, but each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="f5c8a-118">Várias inputs e saídas são então representadas usando *tuples,* que recolhem múltiplos valores juntos num único valor.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-118">Multiple inputs and outputs are then represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="f5c8a-119">Informalmente, dizemos que Q# é uma linguagem "tuple-in tuple-out".</span><span class="sxs-lookup"><span data-stu-id="f5c8a-119">Informally, we say that Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="f5c8a-120">Seguindo este conceito, `()` deve ser lido como o tuple "vazio", que tem o tipo `Unit`.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-120">Following this concept, `()` should then be read as the "empty" tuple, which has the type `Unit`.</span></span>

<span data-ttu-id="f5c8a-121">No âmbito da nova operação, a implementação pode ser especificada diretamente na declaração se apenas a implementação da especialização do organismo predefinido tiver de ser especificada explicitamente.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-121">Within the new operation, the implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to be specified explicitly.</span></span> <span data-ttu-id="f5c8a-122">Além disso, é possível definir as implementações de, por exemplo, uma ou mais operações `functor`, tal como elaborada a seguir.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-122">Additionally, it is possible to define the implementations of, for example, one or more `functor` operations, as elaborated below.</span></span> <span data-ttu-id="f5c8a-123">No exemplo acima, a única declaração é chamar a operação Q# incorporada <xref:microsoft.quantum.intrinsic.x>.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-123">In the example above, the only statement is to call the built-in Q# operation <xref:microsoft.quantum.intrinsic.x>.</span></span>

<span data-ttu-id="f5c8a-124">As operações também podem devolver tipos mais interessantes do que `Unit`.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-124">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="f5c8a-125">Por exemplo, a operação <xref:microsoft.quantum.intrinsic.m> devolve uma saída de tipo `Result`, representando ter efetuado uma medição.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-125">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span> <span data-ttu-id="f5c8a-126">Podemos passar a saída de uma operação para outra operação, ou podemos usá-la com a palavra-chave `let` para definir uma nova variável.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-126">We can either pass the output from an operation to another operation, or can use it with the `let` keyword to define a new variable.</span></span>
<!-- Link to UID for superdense conceptual and example documentation. -->
<span data-ttu-id="f5c8a-127">Isto permite representar a computação clássica que interage com operações quânticas a um nível baixo, como na codificação superdensa:</span><span class="sxs-lookup"><span data-stu-id="f5c8a-127">This allows for representing classical computation that interacts with quantum operations at a low level, such as in superdense coding:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a><span data-ttu-id="f5c8a-128">Functors, adjoint e controlado</span><span class="sxs-lookup"><span data-stu-id="f5c8a-128">Functors, adjoint and controlled</span></span>
<span data-ttu-id="f5c8a-129">Se uma operação implementar uma transformação unitária, então é possível definir como a operação funciona quando *adjoint ou* *controlada*.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-129">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="f5c8a-130">Uma especialização adjoint de uma operação especifica como age quando é executada ao contrário, enquanto uma especialização controlada especifica como uma operação funciona quando aplicada condicionada no estado de um registo quântico.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-130">An adjoint specialization of an operation specifies how it acts when run in reverse, while a controlled specialization specifies how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="f5c8a-131">A existência destas especializações pode ser declarada como parte da assinatura da operação: `is Adj + Ctl` no seguinte exemplo.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-131">The existence of these specializations can be declared as part of the operation signature: `is Adj + Ctl` in the following example.</span></span> <span data-ttu-id="f5c8a-132">A implementação correspondente para cada especialização declarada implicitamente é então gerada pelo compilador.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-132">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> <span data-ttu-id="f5c8a-133">Muitas operações em Q# representam portões unitários.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-133">Many operations in Q# represent unitary gates.</span></span>
> <span data-ttu-id="f5c8a-134">Se $U$ é o portão unitário representado por uma operação `U`, então `Adjoint U` representa o portão unitário $U^\dagger$.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-134">If $U$ is the unitary gate represented by an operation `U`, then `Adjoint U` represents the unitary gate $U^\dagger$.</span></span>

<span data-ttu-id="f5c8a-135">No caso de a implementação não poder ser gerada pelo compilador, pode ser explicitamente especificada.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-135">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="f5c8a-136">Tais declarações explícitas de especialização podem consistir numa diretiva de geração adequada ou numa aplicação definida pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-136">Such explicit specialization declarations can consist of a suitable generation directive or a user defined implementation.</span></span> <span data-ttu-id="f5c8a-137">O código em `PrepareEntangledPair` acima, por exemplo, equivale ao código abaixo contendo declarações explícitas de especialização:</span><span class="sxs-lookup"><span data-stu-id="f5c8a-137">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

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
<span data-ttu-id="f5c8a-138">A palavra-chave `auto` indica que o compilador deve determinar como gerar a implementação da especialização.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-138">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="f5c8a-139">Se o compilador não conseguir gerar automaticamente a implementação para uma determinada especialização, ou se uma implementação mais eficiente puder ser administrada, então a implementação também pode ser definida manualmente.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-139">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

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
<span data-ttu-id="f5c8a-140">No exemplo acima, `adjoint invert;` indica que a especialização adjoint deve ser gerada invertendo a implementação do corpo, e `controlled adjoint invert;` indica que a especialização adjoint controlada deve ser gerada invertendo a implementação da especialização controlada.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-140">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="f5c8a-141">Veremos mais exemplos disso no Fluxo de [Controlo de Ordem Superior.](xref:microsoft.quantum.concepts.control-flow)</span><span class="sxs-lookup"><span data-stu-id="f5c8a-141">We will see more examples of this in [Higher-Order Control Flow](xref:microsoft.quantum.concepts.control-flow).</span></span>

<span data-ttu-id="f5c8a-142">Para chamar uma especialização de uma operação, utilize as palavras-chave `Adjoint` ou `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-142">To call a specialization of an operation, use the `Adjoint` or `Controlled` keywords.</span></span>
<span data-ttu-id="f5c8a-143">Por exemplo, o exemplo de codificação superdense acima pode ser escrito mais compactamente usando a adjoint de `PrepareEntangledPair` para transformar o estado emaranhado de volta em um par de qubits sem emaranhado:</span><span class="sxs-lookup"><span data-stu-id="f5c8a-143">For example, the superdense coding example above can be written more compactly by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="f5c8a-144">Há uma série de limitações importantes a ter em conta na conceção de operações de utilização com functors.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-144">There are a number of important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="f5c8a-145">Mais criticamente, as especializações para uma operação que utilize o valor de saída de qualquer outra operação não podem ser geradas automaticamente pelo compilador, uma vez que é ambígua como reordenar as declarações numa operação deste tipo para obter o mesmo efeito.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-145">Most critically, specializations for an operation that uses the output value of any other operation cannot be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>


## <a name="defining-new-functions"></a><span data-ttu-id="f5c8a-146">Definição de novas funções</span><span class="sxs-lookup"><span data-stu-id="f5c8a-146">Defining New Functions</span></span>

<span data-ttu-id="f5c8a-147">Q# também permite definir funções , que são distintas das *operações*na medida em que não são permitidas a ter quaisquer efeitos além do cálculo de um valor de saída.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-147">Q# also allows for defining *functions*, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="f5c8a-148">Em particular, as funções não podem ligar para operações, agir sobre qubits, amostrar números aleatórios, ou depender de qualquer estado para além do valor de entrada para uma função.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-148">In particular, functions cannot call operations, act on qubits, sample random numbers, or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="f5c8a-149">Como consequência, as funções Q# são *puras,* na medida em que sempre mapeiam os mesmos valores de entrada para os mesmos valores de saída.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-149">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="f5c8a-150">Isto permite ao compilador Q# reordenar com segurança como e quando as funções são chamadas ao gerar especializações de operação.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-150">This allows the Q# compiler to safely reorder how and when functions are called when generating operation specializations.</span></span>

<span data-ttu-id="f5c8a-151">A definição de uma função funciona da mesma forma para definir uma operação, exceto que nenhuma especialização adjoint ou controlada pode ser definida para uma função.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-151">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="f5c8a-152">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f5c8a-152">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
<span data-ttu-id="f5c8a-153">Sempre que é possível fazê-lo, é útil escrever a lógica clássica em termos de funções e não de operações, para que possa ser mais facilmente utilizada a partir de dentro das operações.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-153">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations, so that it can be more readily used from within operations.</span></span>
<span data-ttu-id="f5c8a-154">Se tivéssemos escrito `Square` como operação, por exemplo, o compilador não teria sido capaz de garantir que chamá-lo com a mesma entrada produziria consistentemente as mesmas saídas.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-154">If we had written `Square` as an operation, for example, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="f5c8a-155">Para sublinhar a diferença entre funções e operações, considere o problema da amostragem clássica de um número aleatório de dentro de uma operação Q#:</span><span class="sxs-lookup"><span data-stu-id="f5c8a-155">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="f5c8a-156">De cada vez que se chama `U`, terá uma ação diferente sobre `target`.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-156">Each time that `U` is called, it will have a different action on `target`.</span></span>
<span data-ttu-id="f5c8a-157">Em particular, o compilador não pode garantir que, se adicionássemos uma declaração de especialização `adjoint auto` a `U`, então `U(target); Adjoint U(target);` atua como identidade (isto é, como uma não-operação).</span><span class="sxs-lookup"><span data-stu-id="f5c8a-157">In particular, the compiler cannot guarantee that if we added an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="f5c8a-158">Isto viola a definição da adjoint que vimos em [Vetores e Matrizes](xref:microsoft.quantum.concepts.vectors), de tal forma que permitir gerar automaticamente uma especialização adjoint numa operação em que chamámos a operação <xref:microsoft.quantum.math.randomreal> quebraria as garantias fornecidas pelo compilador; <xref:microsoft.quantum.math.randomreal> é uma operação para a qual não existe nenhuma versão adjoint ou controlada.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-158">This violates the definition of the adjoint that we saw in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing to auto-generate an adjoint specialization in an operation where we have called the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="f5c8a-159">Por outro lado, permitir chamadas de funções como `Square` é segura, na medida em que o compilador pode ter a certeza de que só precisa de preservar a entrada para `Square`, a fim de manter a sua produção estável.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-159">On the other hand, allowing function calls such as `Square` is safe, in that the compiler can be assured that it only needs to preserve the input to `Square` in order to keep its output stable.</span></span>
<span data-ttu-id="f5c8a-160">Assim, isolar o máximo de lógica clássica possível em funções facilita a reutilização dessa lógica em outras funções e operações.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-160">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>

## <a name="control-flow"></a><span data-ttu-id="f5c8a-161">Fluxo de Controlo</span><span class="sxs-lookup"><span data-stu-id="f5c8a-161">Control Flow</span></span>

<span data-ttu-id="f5c8a-162">Dentro de uma operação ou função, cada declaração executa por ordem, semelhante às línguas clássicas mais comuns imperativas.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-162">Within an operation or function, each statement executes in order, similar to most common imperative classical languages.</span></span>
<span data-ttu-id="f5c8a-163">No entanto, este fluxo de controlo pode ser modificado de três formas distintas:</span><span class="sxs-lookup"><span data-stu-id="f5c8a-163">This flow of control can be modified, however, in three distinct ways:</span></span>

- <span data-ttu-id="f5c8a-164">`if` Declarações</span><span class="sxs-lookup"><span data-stu-id="f5c8a-164">`if` Statements</span></span>
- <span data-ttu-id="f5c8a-165">`for` Loops</span><span class="sxs-lookup"><span data-stu-id="f5c8a-165">`for` Loops</span></span>
- <span data-ttu-id="f5c8a-166">`repeat`-`until` Loops</span><span class="sxs-lookup"><span data-stu-id="f5c8a-166">`repeat`-`until` Loops</span></span>

<span data-ttu-id="f5c8a-167">Adiamos a discussão deste último até discutirmos os circuitos [Repeat Until Success (RUS).](xref:microsoft.quantum.techniques.qubits#measurements)</span><span class="sxs-lookup"><span data-stu-id="f5c8a-167">We defer discussion of the latter until we discuss [Repeat Until Success (RUS)](xref:microsoft.quantum.techniques.qubits#measurements) circuits.</span></span>
<span data-ttu-id="f5c8a-168">No entanto, as construções de fluxo de `if` e `for` de controlo prosseguem num sentido familiar para a maioria das línguas clássicas de programação.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-168">The `if` and `for` control flow constructs, however, proceed in a familiar sense to most classical programming languages.</span></span>
<span data-ttu-id="f5c8a-169">Em especial, uma declaração `if` pode tomar uma condição, pode ser seguida por uma ou mais declarações `elif`, podendo terminar com um `else`:</span><span class="sxs-lookup"><span data-stu-id="f5c8a-169">In particular, an `if` statement can take a condition, may be followed by one or more `elif` statements, and may end with an `else`:</span></span>

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

<span data-ttu-id="f5c8a-170">Da mesma forma, `for` loops indicam iteração sobre uma gama de inteiros ou sobre os elementos de uma matriz:</span><span class="sxs-lookup"><span data-stu-id="f5c8a-170">Similarly, `for` loops indicate iteration over a range of integers or over the elements of an array:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

<span data-ttu-id="f5c8a-171">É importante `for` loops e `if` declarações podem mesmo ser utilizados em operações para as quais as especializações são geradas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-171">Importantly, `for` loops and `if` statements can even be used in operations for which specializations are auto-generated.</span></span> <span data-ttu-id="f5c8a-172">Nesse caso, a adjoint de um laço de `for` inverte a direção e toma a adjoint de cada iteração.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-172">In that case the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="f5c8a-173">Isto segue o princípio dos "sapatos e meias": se quiser desfazer a colocação de meias e depois sapatos, tem de desfazer calçar sapatos e depois desfazer calças.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-173">This follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span>
<span data-ttu-id="f5c8a-174">Funciona decididamente menos bem para tentar tirar as meias enquanto ainda usa os sapatos!</span><span class="sxs-lookup"><span data-stu-id="f5c8a-174">It works decidedly less well to try and take your socks off while you're still wearing your shoes!</span></span>

## <a name="operations-and-functions-as-first-class-values"></a><span data-ttu-id="f5c8a-175">Operações e Funções como Valores de Primeira Classe</span><span class="sxs-lookup"><span data-stu-id="f5c8a-175">Operations and Functions as First-Class Values</span></span>

<span data-ttu-id="f5c8a-176">Uma técnica crítica para o raciocínio sobre o fluxo de controlo e a lógica clássica usando funções em vez de operações é utilizar que as operações e funções em Q# são *de primeira classe*.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-176">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="f5c8a-177">Ou seja, são cada valores da língua por direito próprio.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-177">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="f5c8a-178">Por exemplo, o seguinte é perfeitamente válido código Q#, se um pouco indireto:</span><span class="sxs-lookup"><span data-stu-id="f5c8a-178">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="f5c8a-179">O valor da variável `ourH` no corte acima é então a operação <xref:microsoft.quantum.intrinsic.h>, de modo a que possamos chamar esse valor como qualquer outra operação.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-179">The value of the variable `ourH` in the snippet above is then the operation <xref:microsoft.quantum.intrinsic.h>, such that we can call that value like any other operation.</span></span>
<span data-ttu-id="f5c8a-180">Isto permite-nos escrever operações que tomam as operações como parte da sua entrada, formando conceitos de fluxo de controlo de maior ordem.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-180">This allows us to write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="f5c8a-181">Por exemplo, podemos imaginar querer "quadrar" uma operação aplicando-a duas vezes ao mesmo qubit alvo.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-181">For instance, we could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

<span data-ttu-id="f5c8a-182">Neste exemplo, a seta `=>` que aparece no tipo `(Qubit => Unit)` denota que o campo de entrada `op` é uma operação que toma como entrada o tipo `Qubit` e produz uma tuple vazia como sua saída.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-182">In this example, the `=>` arrow that appears in the type `(Qubit => Unit)` denotes that the input field `op` is an operation which takes as its input the type `Qubit` and produces an empty tuple as its output.</span></span>
<span data-ttu-id="f5c8a-183">Além disso, especificamos as características desse tipo de operação, que contêm as informações sobre as quais os functores são suportados.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-183">Additionally we specify the characteristics of that operation type, which contain the information about which functors are supported.</span></span>
<span data-ttu-id="f5c8a-184">Uma operação de tipo `(Qubit => Unit)` não suporta nem o `Adjoint` nem o functor `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-184">An operation of type `(Qubit => Unit)` supports neither the `Adjoint` nor the `Controlled` functor.</span></span> <span data-ttu-id="f5c8a-185">Se quisermos indicar que uma operação desse tipo tem de suportar, por exemplo, o functor `Adjoint`, temos de o declarar como sendo adjointable.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-185">If we want to indicate that an operation of that type has to support e.g. the `Adjoint` functor, we have to declare it as being adjointable.</span></span> <span data-ttu-id="f5c8a-186">Isto é feito utilizando a anotação `is Adj` ao tipo.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-186">This is done by using the annotation `is Adj` to the type.</span></span> <span data-ttu-id="f5c8a-187">Da mesma forma, `(Qubit => Unit is Ctl)` denota que uma operação deste tipo suporta o functor `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-187">Similarly, `(Qubit => Unit is Ctl)` denotes that an operation of that type supports the `Controlled` functor.</span></span> <span data-ttu-id="f5c8a-188">Vamos explorar isto ainda mais quando discutirmos [tipos em Q#] (xref:microsoft.quantum.language.type-model) de uma forma mais geral.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-188">We will explore this further when we discuss [types in Q#] (xref:microsoft.quantum.language.type-model) more generally.</span></span>

<span data-ttu-id="f5c8a-189">Por enquanto, sublinhamos que também podemos devolver as operações como parte de saídas, de modo a podermos isolar alguns tipos de lógica condicional clássica como função clássica que devolve uma descrição de um programa quântico sob a forma de uma operação.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-189">For now, we emphasize that we can also return operations as a part of outputs, such that we can isolate some kinds of classical conditional logic as a classical function which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="f5c8a-190">Como exemplo simples, considere o exemplo da teletransporte, em que o partido que recebe uma mensagem clássica de dois bits precisa de usar a mensagem para descodificar o seu qubit no estado teletransportado adequado.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-190">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="f5c8a-191">Poderíamos escrever isto em termos de uma função que pega nessas duas partes clássicas e devolve a operação de descodificação adequada.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-191">We could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

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

<span data-ttu-id="f5c8a-192">Esta nova função é, de facto, uma função, na forma de a chamarmos com os mesmos valores de `hereBit` e `thereBit`, teremos sempre de volta a mesma operação.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-192">This new function is indeed a function, in that if we call it with the same values of `hereBit` and `thereBit`, we will always get back the same operation.</span></span>
<span data-ttu-id="f5c8a-193">Assim, o descodificador pode ser executado com segurança dentro de operações sem ter de raciocinar sobre como a lógica de descodificação interage com as definições das diferentes especializações de operação.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-193">Thus, the decoder can be safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="f5c8a-194">Ou seja, isolamos a lógica clássica dentro de uma função, garantindo ao compilador que a chamada de função pode ser reordenada impunemente enquanto a entrada for preservada.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-194">That is, we have isolated the classical logic inside a function, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>

<span data-ttu-id="f5c8a-195">Também podemos tratar as funções como valores de primeira classe, como veremos mais detalhadamente quando discutirmos os tipos de [operações e funções.](#operations-and-functions-as-first-class-values)</span><span class="sxs-lookup"><span data-stu-id="f5c8a-195">We can also treat functions as first-class values, as we will see in more detail when we discuss [operations and function types](#operations-and-functions-as-first-class-values).</span></span>

## <a name="partially-applying-operations-and-functions"></a><span data-ttu-id="f5c8a-196">Aplicação parcial de operações e funções</span><span class="sxs-lookup"><span data-stu-id="f5c8a-196">Partially Applying Operations and Functions</span></span>

<span data-ttu-id="f5c8a-197">Podemos fazer significativamente mais com funções que devolvem as operações utilizando *aplicações parciais,* nas quais podemos fornecer uma ou mais partes da entrada a uma função ou operação sem realmente chamá-lo.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-197">We can do significantly more with functions that return operations by using *partial application*, in which we can provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="f5c8a-198">Por exemplo, recordando o exemplo `ApplyTwice` acima, podemos indicar que não queremos especificar, imediatamente, a que qubit a operação de entrada deve aplicar:</span><span class="sxs-lookup"><span data-stu-id="f5c8a-198">For example, recalling the `ApplyTwice` example above, we can indicate that we don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="f5c8a-199">Neste caso, a variável local `twiceOp` detém a operação parcialmente aplicada `ApplyTwice(op, _)`, onde partes da entrada que ainda não foram especificadas são indicadas por `_`.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-199">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where parts of the input that have not yet been specified are indicated by `_`.</span></span>
<span data-ttu-id="f5c8a-200">Quando realmente chamamos `twiceOp` na linha seguinte, passamos como entrada para a operação parcialmente aplicada todas as partes restantes da entrada para a operação original.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-200">When we actually call `twiceOp` in the next line, we pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="f5c8a-201">Assim, o corte acima é efetivamente idêntico ao de ter chamado `ApplyTwice(op, target)` diretamente, salvo para isso introduzimos uma nova variável local que nos permite atrasar a chamada, fornecendo algumas partes da entrada.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-201">Thus, the above snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that we have introduced a new local variable that allows us to delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="f5c8a-202">Uma vez que uma operação que foi parcialmente aplicada não é realmente chamada até que toda a sua entrada tenha sido fornecida, podemos aplicar parcialmente as operações mesmo a partir de funções.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-202">Since an operation that has been partially applied is not actually called until its entire input has been provided, we can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="f5c8a-203">Em princípio, a lógica clássica dentro `SquareOperation` poderia ter sido muito mais envolvida, mas continua isolada do resto de uma operação pelas garantias que o compilador pode oferecer sobre funções.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-203">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span>
<span data-ttu-id="f5c8a-204">Esta abordagem será usada em toda a biblioteca padrão Q# para expressar o fluxo de controlo clássico de uma forma que pode ser facilmente usada dentro de programas quânticos.</span><span class="sxs-lookup"><span data-stu-id="f5c8a-204">This approach will be used throughout the Q# standard library for expressing classical control flow in a way that can be readily used within quantum programs.</span></span>
