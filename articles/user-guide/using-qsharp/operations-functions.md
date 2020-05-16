---
title: 'Operações e funções em Q #'
description: Como definir e chamar operações e funções, bem como as especializações de operação controlada e adjoint.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: bc9695b85b68807801225ccbc903a4622b450768
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431075"
---
# <a name="operations-and-functions-in-q"></a><span data-ttu-id="45eb1-103">Operações e Funções em Q #</span><span class="sxs-lookup"><span data-stu-id="45eb1-103">Operations and Functions in Q#</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="45eb1-104">Definição de Novas Operações</span><span class="sxs-lookup"><span data-stu-id="45eb1-104">Defining New Operations</span></span>

<span data-ttu-id="45eb1-105">As operações são o núcleo do Q#.</span><span class="sxs-lookup"><span data-stu-id="45eb1-105">Operations are the core of Q#.</span></span>
<span data-ttu-id="45eb1-106">Uma vez declarados, podem ser chamados de aplicações clássicas .NET, por exemplo, utilizando um simulador, ou por outras operações dentro do Q#.</span><span class="sxs-lookup"><span data-stu-id="45eb1-106">Once declared, they can either be called from classical .NET applications, e.g., using a simulator, or by other operations within Q#.</span></span>
<span data-ttu-id="45eb1-107">Cada operação definida em Q# pode então chamar qualquer número de outras operações, incluindo as operações intrínsecas incorporadas definidas pela língua.</span><span class="sxs-lookup"><span data-stu-id="45eb1-107">Each operation defined in Q# may then call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="45eb1-108">A forma particular como estas operações intrínsecas são definidas depende da máquina-alvo.</span><span class="sxs-lookup"><span data-stu-id="45eb1-108">The particular way in which these intrinsic operations are defined depends on the target machine.</span></span>
<span data-ttu-id="45eb1-109">Quando compilado, cada operação é representada como um tipo de classe .NET que pode ser fornecido às máquinas-alvo.</span><span class="sxs-lookup"><span data-stu-id="45eb1-109">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="45eb1-110">Cada ficheiro de origem Q# pode definir qualquer número de operações.</span><span class="sxs-lookup"><span data-stu-id="45eb1-110">Each Q# source file may define any number of operations.</span></span>
<span data-ttu-id="45eb1-111">Os nomes de funcionamento devem ser únicos dentro de um espaço de nome e não podem entrar em conflito com nomes de tipo ou função.</span><span class="sxs-lookup"><span data-stu-id="45eb1-111">Operation names must be unique within a namespace and may not conflict with type or function names.</span></span>

<span data-ttu-id="45eb1-112">Uma declaração de operação consiste na palavra-chave, `operation` seguida do símbolo que é o nome da operação, de uma túnica identificada dactilografada que define os argumentos da operação, de um `:` cólon, de uma anotação tipo que descreve o tipo de resultado da operação, opcionalmente uma anotação com as características de funcionamento, uma cinta `{` aberta, o corpo da declaração de funcionamento e um aparelho de fecho `}` final.</span><span class="sxs-lookup"><span data-stu-id="45eb1-112">An operation declaration consists of the keyword `operation`, followed by the symbol that is the operation's name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation's result type, optionally an annotation with the operation characteristics, an open brace `{`, the body of the operation declaration, and a final closing brace `}`.</span></span>

<span data-ttu-id="45eb1-113">Cada operação tem uma entrada, produz uma saída e especifica a implementação para uma ou mais especializações de operação.</span><span class="sxs-lookup"><span data-stu-id="45eb1-113">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="45eb1-114">As possíveis especializações, e como defini-las/chamá-las, são detalhadas mais abaixo.</span><span class="sxs-lookup"><span data-stu-id="45eb1-114">The possible specializations, and how to define/call them, are detailed further below.</span></span>
<span data-ttu-id="45eb1-115">Para já, considere a seguinte operação, que define apenas uma especialização corporal padrão e toma um único qubit como entrada, e depois chama a operação incorporada <xref:microsoft.quantum.intrinsic.x> nessa entrada:</span><span class="sxs-lookup"><span data-stu-id="45eb1-115">For now, consider the following operation, which defines only a default body specialization and takes a single qubit as its input, then calls the built-in <xref:microsoft.quantum.intrinsic.x> operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="45eb1-116">A palavra-chave começa a definição de `operation` operação, e é seguida pelo nome; aqui, `BitFlip` .</span><span class="sxs-lookup"><span data-stu-id="45eb1-116">The keyword `operation` begins the operation definition, and is followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="45eb1-117">Em seguida, o tipo de entrada é definido `Qubit` como, juntamente com um nome `target` para se referir à entrada dentro da nova operação.</span><span class="sxs-lookup"><span data-stu-id="45eb1-117">Next, the type of the input is defined as `Qubit`, along with a name `target` for referring to the input within the new operation.</span></span>
<span data-ttu-id="45eb1-118">Da mesma forma, os `Unit` definidos definem que a saída da operação está vazia.</span><span class="sxs-lookup"><span data-stu-id="45eb1-118">Similarly, the `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="45eb1-119">Isto é usado da mesma forma `void` em C# e outras línguas imperativas, e é equivalente a `unit` F# e outras línguas funcionais.</span><span class="sxs-lookup"><span data-stu-id="45eb1-119">This is used similarly to `void` in C# and other imperative languages, and is equivalent to `unit` in F# and other functional languages.</span></span>

<span data-ttu-id="45eb1-120">As operações também podem devolver tipos mais interessantes do que `Unit` .</span><span class="sxs-lookup"><span data-stu-id="45eb1-120">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="45eb1-121">Por exemplo, a <xref:microsoft.quantum.intrinsic.m> operação devolve uma saída de `Result` tipo, representando ter efetuado uma medição.</span><span class="sxs-lookup"><span data-stu-id="45eb1-121">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span> <span data-ttu-id="45eb1-122">Podemos passar a saída de uma operação para outra operação, ou podemos usá-la com a `let` palavra-chave para definir uma nova variável.</span><span class="sxs-lookup"><span data-stu-id="45eb1-122">We can either pass the output from an operation to another operation, or can use it with the `let` keyword to define a new variable.</span></span>

<span data-ttu-id="45eb1-123">Isto permite representar a computação clássica que interage com operações quânticas a um nível baixo, como na [codificação superdensa:](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)</span><span class="sxs-lookup"><span data-stu-id="45eb1-123">This allows for representing classical computation that interacts with quantum operations at a low level, such as in [superdense coding](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

> [!NOTE]
> <span data-ttu-id="45eb1-124">Cada operação em Q# leva exatamente uma entrada e devolve exatamente uma saída.</span><span class="sxs-lookup"><span data-stu-id="45eb1-124">Each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="45eb1-125">Várias inputs e saídas são então representadas usando *tuples,* que recolhem múltiplos valores juntos num único valor.</span><span class="sxs-lookup"><span data-stu-id="45eb1-125">Multiple inputs and outputs are then represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="45eb1-126">Informalmente, dizemos que Q# é uma linguagem "tuple-in tuple-out".</span><span class="sxs-lookup"><span data-stu-id="45eb1-126">Informally, we say that Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="45eb1-127">Seguindo este conceito, `()` deve então ser lido como o tuple "vazio", que tem o tipo `Unit` .</span><span class="sxs-lookup"><span data-stu-id="45eb1-127">Following this concept, `()` should then be read as the "empty" tuple, which has the type `Unit`.</span></span>


## <a name="controlled-and-adjoint-operations"></a><span data-ttu-id="45eb1-128">Operações controladas e adjoint</span><span class="sxs-lookup"><span data-stu-id="45eb1-128">Controlled and Adjoint Operations</span></span>

<span data-ttu-id="45eb1-129">Se uma operação implementar uma transformação unitária, como é o caso de muitas operações em Q#, então é possível definir como a operação funciona quando *adjoint ou* *controlada*.</span><span class="sxs-lookup"><span data-stu-id="45eb1-129">If an operation implements a unitary transformation, as is the case for many operations in Q#, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="45eb1-130">Uma especialização *conjunta* de uma operação especifica como funciona o "inverso" da operação, enquanto uma especialização *controlada* especifica como uma operação funciona quando a sua aplicação está condicionada no estado de um determinado registo quântico.</span><span class="sxs-lookup"><span data-stu-id="45eb1-130">An *adjoint* specialization of an operation specifies how the "inverse" of the operation acts, while a *controlled* specialization specifies how an operation acts when its application is conditioned on the state of a particular quantum register.</span></span>

<span data-ttu-id="45eb1-131">As articulações de operações quânticas são cruciais para muitos aspetos da computação quântica.</span><span class="sxs-lookup"><span data-stu-id="45eb1-131">Adjoints of quantum operations are crucial to many aspects of quantum computing.</span></span> <span data-ttu-id="45eb1-132">Mais abaixo, na secção [Conjugações,](#conjugations) encontrará uma dessas situações discutida seletivamente ao lado de uma técnica de programação Q# útil.</span><span class="sxs-lookup"><span data-stu-id="45eb1-132">Further below, in the [Conjugations](#conjugations) section, you will find one such situation discussed alongside a useful Q# programming technique.</span></span>

<span data-ttu-id="45eb1-133">A versão controlada de uma operação é uma nova operação que aplica eficazmente o funcionamento da base apenas se todos os qubits de controlo estiverem num estado determinado.</span><span class="sxs-lookup"><span data-stu-id="45eb1-133">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="45eb1-134">Se os qubits de controlo estiverem em sobreposição, então o funcionamento da base é aplicado de forma coerente à parte adequada da superposição.</span><span class="sxs-lookup"><span data-stu-id="45eb1-134">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="45eb1-135">Assim, as operações controladas são frequentemente usadas para gerar emaranhado.</span><span class="sxs-lookup"><span data-stu-id="45eb1-135">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="45eb1-136">Naturalmente, também poderia existir uma especialização *adjoint controlada,* especificando a aplicação controlada do adjoint de uma operação.</span><span class="sxs-lookup"><span data-stu-id="45eb1-136">Naturally, a *controlled adjoint* specialization could exist as well, specifying the controlled application of an operation's adjoint.</span></span>

> [!NOTE]
> <span data-ttu-id="45eb1-137">Se $U$ é a transformação unitária implementada por uma `U` operação, então `Adjoint U` representa a transformação unitária $U^\dagger$, que é o complexo conjugado transpor.</span><span class="sxs-lookup"><span data-stu-id="45eb1-137">If $U$ is the unitary transformation implemented by an operation `U`, then `Adjoint U` represents the unitary transformation $U^\dagger$, which is the complex conjugate transpose.</span></span>
> <span data-ttu-id="45eb1-138">Sucessivamente aplicando uma operação e, em seguida, o seu adjoint a um estado deixa o Estado inalterado, como ilustrado pelo facto de $UU^\dagger = U^\dagger U = \id$, a matriz de identidade.</span><span class="sxs-lookup"><span data-stu-id="45eb1-138">Successively applying an operation and then its adjoint to a state leaves the state unchanged, as illustrated by the fact that $UU^\dagger = U^\dagger U = \id$, the identity matrix.</span></span>
> <span data-ttu-id="45eb1-139">A representação unitária de uma operação controlada é um pouco mais matizada, mas pode encontrar mais detalhes nos [conceitos de computação quântica: múltiplos qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span><span class="sxs-lookup"><span data-stu-id="45eb1-139">The unitary representation of a controlled operation is slightly more nuanced, but you can find more details at [Quantum computing concepts: multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

<span data-ttu-id="45eb1-140">A secção seguinte descreve como chamar estas várias especializações no seu código Q#.</span><span class="sxs-lookup"><span data-stu-id="45eb1-140">The following section describes how to call these various specializations in your Q# code.</span></span>
<span data-ttu-id="45eb1-141">Abaixo, detalhamos como definir operações para apoiá-las.</span><span class="sxs-lookup"><span data-stu-id="45eb1-141">Below, we detail how to define operations to support them.</span></span>

### <a name="calling-operation-specializations"></a><span data-ttu-id="45eb1-142">Call operation especializações</span><span class="sxs-lookup"><span data-stu-id="45eb1-142">Calling operation specializations</span></span>

<span data-ttu-id="45eb1-143">Um *functor* em Q# é uma fábrica que define uma nova operação a partir de outra operação.</span><span class="sxs-lookup"><span data-stu-id="45eb1-143">A *functor* in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="45eb1-144">Os dois functores padrão em Q# são `Adjoint` e `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="45eb1-144">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

<span data-ttu-id="45eb1-145">Os functores têm acesso à implementação da operação base na definição da implementação da nova operação.</span><span class="sxs-lookup"><span data-stu-id="45eb1-145">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="45eb1-146">Assim, os functores podem desempenhar funções mais complexas do que as funções tradicionais de alto nível.</span><span class="sxs-lookup"><span data-stu-id="45eb1-146">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span> <span data-ttu-id="45eb1-147">Os functores não têm representação no sistema do tipo Q#.</span><span class="sxs-lookup"><span data-stu-id="45eb1-147">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="45eb1-148">Por conseguinte, não é atualmente possível ligá-los a uma variável ou aprová-los como argumentos.</span><span class="sxs-lookup"><span data-stu-id="45eb1-148">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="45eb1-149">Um functor é utilizado aplicando-o a uma operação, devolvendo uma nova operação.</span><span class="sxs-lookup"><span data-stu-id="45eb1-149">A functor is used by applying it to an operation, returning a new operation.</span></span>
<span data-ttu-id="45eb1-150">Por exemplo, a operação que resulta da aplicação do `Adjoint` functor à `Y` operação é escrita como `Adjoint Y` .</span><span class="sxs-lookup"><span data-stu-id="45eb1-150">For example, the operation that results from applying the `Adjoint` functor to the `Y` operation is written as `Adjoint Y`.</span></span>
<span data-ttu-id="45eb1-151">A nova operação pode então ser invocada como qualquer outra operação.</span><span class="sxs-lookup"><span data-stu-id="45eb1-151">The new operation may then be invoked like any other operation.</span></span>
<span data-ttu-id="45eb1-152">Para uma operação de apoio à aplicação dos `Adjoint` functores e/ou `Controlled` functores, o seu tipo de devolução precisa necessariamente de ser `Unit` .</span><span class="sxs-lookup"><span data-stu-id="45eb1-152">For an operation to support application of the `Adjoint` and/or `Controlled` functors, its return type necessarily needs to be `Unit`.</span></span> 

#### <a name="adjoint-functor"></a><span data-ttu-id="45eb1-153">`Adjoint`functor</span><span class="sxs-lookup"><span data-stu-id="45eb1-153">`Adjoint` functor</span></span>

<span data-ttu-id="45eb1-154">Assim, `Adjoint Y(q1)` aplica-se o functor Adjoint à `Y` operação para gerar uma nova operação, e aplica-se essa nova operação a `q1` .</span><span class="sxs-lookup"><span data-stu-id="45eb1-154">Thus, `Adjoint Y(q1)` applies the Adjoint functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>
<span data-ttu-id="45eb1-155">A nova operação tem a mesma assinatura e tipo que o funcionamento da base `Y` .</span><span class="sxs-lookup"><span data-stu-id="45eb1-155">The new operation has the same signature and type as the base operation `Y`.</span></span>
<span data-ttu-id="45eb1-156">Em particular, a nova operação também `Adjoint` permite, e permitirá `Controlled` se e apenas se a operação base o fez.</span><span class="sxs-lookup"><span data-stu-id="45eb1-156">In particular, the new operation also allows `Adjoint`, and will allow `Controlled` if and only if the base operation did.</span></span>
<span data-ttu-id="45eb1-157">O functor Adjoint é o seu próprio inverso; isto é, `Adjoint Adjoint Op` é sempre o mesmo `Op` que.</span><span class="sxs-lookup"><span data-stu-id="45eb1-157">The Adjoint functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled-functor"></a><span data-ttu-id="45eb1-158">`Controlled`functor</span><span class="sxs-lookup"><span data-stu-id="45eb1-158">`Controlled` functor</span></span>

<span data-ttu-id="45eb1-159">Da mesma forma, `Controlled X(controls, target)` aplica-se o functor controlado à `X` operação para gerar uma nova operação, e aplica essa nova operação para e `controls` `target` .</span><span class="sxs-lookup"><span data-stu-id="45eb1-159">Similarly, `Controlled X(controls, target)` applies the Controlled functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

> [!NOTE]
> <span data-ttu-id="45eb1-160">Em Q#, as versões controladas tomam sempre uma série de qubits de controlo, e o estado especificado é sempre para todos os qubits de controlo estarem no estado computacional , `PauliZ` `One` $\ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="45eb1-160">In Q#, controlled versions always take an array of control qubits, and the specified state is always for all of the control qubits to be in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
> <span data-ttu-id="45eb1-161">O controlo baseado noutros Estados pode ser alcançado aplicando a operação unitária adequada aos qubits de controlo antes da operação controlada e aplicando os inversos da operação unitária após a operação controlada.</span><span class="sxs-lookup"><span data-stu-id="45eb1-161">Controlling based on other states may be achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
> <span data-ttu-id="45eb1-162">Por exemplo, aplicar uma operação a um qubit de controlo antes e depois de uma operação controlada fará com que `X` a operação controle o `Zero` estado ($\ket {0} $) para esse qubit; aplicação de uma `H` operação antes e depois controlará o `PauliX` `One` estado, ou seja, -1 eigenvalue de Pauli X, $\ket {-} \mathrel{:=} {0} (\ket - \ket {1} ) / \sqrt {2} $ em vez do `PauliZ` `One` estado.</span><span class="sxs-lookup"><span data-stu-id="45eb1-162">For example, applying an `X` operation to a control qubit before and after a controlled operation will cause the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after will control on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="45eb1-163">Dada a expressão de operação, pode ser formada uma nova expressão de operação utilizando o `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="45eb1-163">Given an operation expression, a new operation expression may be formed using the `Controlled` functor.</span></span>
<span data-ttu-id="45eb1-164">A assinatura da nova operação baseia-se na assinatura da operação original.</span><span class="sxs-lookup"><span data-stu-id="45eb1-164">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="45eb1-165">O tipo de resultado é o mesmo, mas o tipo de entrada é um dois tuple com uma matriz qubit que detém o qubit de controlo como primeiro elemento e os argumentos da operação original como segundo elemento.</span><span class="sxs-lookup"><span data-stu-id="45eb1-165">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="45eb1-166">A nova operação apoia `Controlled` , e apoiará `Adjoint` se e apenas se a operação original o fizer.</span><span class="sxs-lookup"><span data-stu-id="45eb1-166">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="45eb1-167">Se a operação original teve apenas um único argumento, então a equivalência de tuple singleton entrará em jogo aqui.</span><span class="sxs-lookup"><span data-stu-id="45eb1-167">If the original operation took only a single argument, then singleton tuple equivalence will come into play here.</span></span>
<span data-ttu-id="45eb1-168">Por exemplo, `Controlled X` é a versão controlada da `X` operação.</span><span class="sxs-lookup"><span data-stu-id="45eb1-168">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span> 
<span data-ttu-id="45eb1-169">`X`tem `(Qubit => Unit is Adj + Ctl)` tipo, assim `Controlled X` como tem `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` tipo; por causa da equivalência de tuple singleton, este é o mesmo que `((Qubit[], Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="45eb1-169">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="45eb1-170">Se a operação base tomou vários argumentos, lembre-se de encerrar os argumentos correspondentes da versão controlada da operação em parênteses para convertê-los em um tuple.</span><span class="sxs-lookup"><span data-stu-id="45eb1-170">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="45eb1-171">Por exemplo, `Controlled Rz` é a versão controlada da `Rz` operação.</span><span class="sxs-lookup"><span data-stu-id="45eb1-171">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span> 
<span data-ttu-id="45eb1-172">`Rz`tem `((Double, Qubit) => Unit is Adj + Ctl)` tipo, assim `Controlled Rz` tem tipo `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="45eb1-172">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="45eb1-173">Assim, `Controlled Rz(controls, (0.1, target))` seria uma invocação válida de `Controlled Rz` (note os parênteses ao `0.1, target` redor).</span><span class="sxs-lookup"><span data-stu-id="45eb1-173">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="45eb1-174">Como outro exemplo, `CNOT(control, target)` pode ser implementado como `Controlled X([control], target)` .</span><span class="sxs-lookup"><span data-stu-id="45eb1-174">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="45eb1-175">Se um alvo deve ser controlado por 2 qubits de controlo (CCNOT), podemos utilizar `Controlled X([control1, control2], target)` a declaração.</span><span class="sxs-lookup"><span data-stu-id="45eb1-175">If a target should be controlled by 2 control qubits (CCNOT), we can use `Controlled X([control1, control2], target)` statement.</span></span>

#### `Controlled Adjoint` 

<span data-ttu-id="45eb1-176">Os `Controlled` `Adjoint` functores e functores viajam, pelo que não há diferença entre candidatar `Controlled Adjoint Op` ou `Adjoint Controlled Op` .</span><span class="sxs-lookup"><span data-stu-id="45eb1-176">The `Controlled` and `Adjoint` functors commute, so there is no difference between applying `Controlled Adjoint Op` or `Adjoint Controlled Op`.</span></span>


## <a name="defining-controlled-and-adjoint-implementations"></a><span data-ttu-id="45eb1-177">Definição de implementações controladas e adjoint</span><span class="sxs-lookup"><span data-stu-id="45eb1-177">Defining Controlled and Adjoint Implementations</span></span>

<span data-ttu-id="45eb1-178">Na primeira declaração de operação, os exemplos acima referidos, as operações `BitFlip` foram `DecodeSuperdense` definidas com assinaturas `(Qubit => Unit)` `((Qubit, Qubit) => (Result, Result))` e, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="45eb1-178">In the first operation declaration examples above, the operations `BitFlip` and `DecodeSuperdense` were defined with signatures `(Qubit => Unit)` and `((Qubit, Qubit) => (Result, Result))`, respectively.</span></span>
<span data-ttu-id="45eb1-179">Como `DecodeSuperdense` inclui medições, não se trata de uma operação unitária e, por conseguinte, não poderia existir especializações adjoint não controladas (recorde-se a exigência conexa de que tal operação devolução `Unit` ).</span><span class="sxs-lookup"><span data-stu-id="45eb1-179">As `DecodeSuperdense` includes measurements, it is not a unitary operation, and therefore neither controlled not adjoint specializations could exist (recall the related requirement that such an operation return `Unit`).</span></span>
<span data-ttu-id="45eb1-180">No entanto, como `BitFlip` simplesmente executa a operação unitária, <xref:microsoft.quantum.intrinsic.x> poderíamos tê-la definido com ambas as especializações.</span><span class="sxs-lookup"><span data-stu-id="45eb1-180">However, as `BitFlip` simply performs the unitary <xref:microsoft.quantum.intrinsic.x> operation, we could have defined it with both specializations.</span></span>

<span data-ttu-id="45eb1-181">Aqui, detalhamos como incluir a existência de especializações nas suas declarações de operação Q#, dando-lhes assim a capacidade de ligar em conjunto com os `Adjoint` e/ou `Controlled` functors.</span><span class="sxs-lookup"><span data-stu-id="45eb1-181">Here, we detail how to include the existence of specializations in your Q# operation declarations, hence giving them the ability to called in conjunction with the `Adjoint` and/or `Controlled` functors.</span></span>
<span data-ttu-id="45eb1-182">Mais [abaixo,](#circumstances-for-validly-defining-specializations)descrevemos algumas das situações em que é válida ou não válida para declarar determinadas especializações.</span><span class="sxs-lookup"><span data-stu-id="45eb1-182">Further [below](#circumstances-for-validly-defining-specializations), we describe some of the situations in which it is either valid or not valid to declare certain specializations.</span></span>

<span data-ttu-id="45eb1-183">As características de funcionamento definem que tipos de functores podem ser aplicados à operação declarada e que efeito têm.</span><span class="sxs-lookup"><span data-stu-id="45eb1-183">Operation characteristics define what kinds of functors can be applied to the declared operation, and what effect they have.</span></span> <span data-ttu-id="45eb1-184">A existência destas especializações pode ser declarada como parte da assinatura da operação, especificamente através de uma anotação com as características de funcionamento: `is Adj` ou, `is Ctl` ou `is Adj + Ctl` .</span><span class="sxs-lookup"><span data-stu-id="45eb1-184">The existence of these specializations can be declared as part of the operation signature, specifically through an annotation with the operation characteristics: either `is Adj`, `is Ctl`, or `is Adj + Ctl`.</span></span>
<span data-ttu-id="45eb1-185">A implementação real de cada especialização pode ser *definida implicitamente* ou *explicitamente.*</span><span class="sxs-lookup"><span data-stu-id="45eb1-185">The actual implementation of each specialization can either be *implicitly* or *explicitly* defined.</span></span>

### <a name="implicitly-specifying-implementations"></a><span data-ttu-id="45eb1-186">Especificando implicitamente as implementações</span><span class="sxs-lookup"><span data-stu-id="45eb1-186">Implicitly specifying implementations</span></span>

<span data-ttu-id="45eb1-187">Neste caso, o organismo da declaração de operação consiste exclusivamente na aplicação por defeito.</span><span class="sxs-lookup"><span data-stu-id="45eb1-187">In this case, the body of the operation declaration consists solely of the default implementation.</span></span> <span data-ttu-id="45eb1-188">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="45eb1-188">For example:</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
<span data-ttu-id="45eb1-189">Aqui, a implementação correspondente para cada uma dessas especialização declarada sem fim é automaticamente gerada pelo compilador, a ser realizada se os `Adjoint` `Controlled` functores ou functores forem utilizados.</span><span class="sxs-lookup"><span data-stu-id="45eb1-189">Here, the corresponding implementation for each such implicitly declared specialization is automatically generated by the compiler, to be performed if the `Adjoint` or `Controlled` functors are used.</span></span>

<span data-ttu-id="45eb1-190">Assim, uma chamada resultaria `Adjoint PrepareEntangledPair` na implementação do compilador da adjoint de `CNOT` e, em seguida, do adjoint de `H` .</span><span class="sxs-lookup"><span data-stu-id="45eb1-190">So, a call of `Adjoint PrepareEntangledPair` would result in the compiler implementing the adjoint of `CNOT` and then the adjoint of `H`.</span></span>
<span data-ttu-id="45eb1-191">Estas operações individuais são simultaneamente auto-adjoint, pelo que a operação resultante `Adjoint PrepareEntangledPair` consistiria simplesmente na aplicação `CNOT(here, there)` `H(here)` e, em seguida, em .</span><span class="sxs-lookup"><span data-stu-id="45eb1-191">These individual operations are both self-adjoint, so the resulting `Adjoint PrepareEntangledPair` operation would simply consist of applying `CNOT(here, there)` and then `H(here)`.</span></span>
<span data-ttu-id="45eb1-192">Assim, podemos usá-lo para escrever o `DecodeSuperdense` exemplo acima de forma mais compacta, usando a adjoint de transformar o estado emaranhado de volta em um par de `PrepareEntangledPair` qubits sem emaranhado:</span><span class="sxs-lookup"><span data-stu-id="45eb1-192">Hence we can use this to write the `DecodeSuperdense` example above more compactly, by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="45eb1-193">A anotação com as características de funcionamento na declaração é útil para garantir que o compilador gera automaticamente outras especializações com base na implementação padrão.</span><span class="sxs-lookup"><span data-stu-id="45eb1-193">The annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="45eb1-194">Há uma série de limitações importantes a ter em conta na conceção de operações de utilização com functors.</span><span class="sxs-lookup"><span data-stu-id="45eb1-194">There are a number of important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="45eb1-195">Mais criticamente, as especializações para uma operação que utilize o valor de saída de qualquer outra operação *não podem* ser geradas automaticamente pelo compilador, uma vez que é ambígua como reordenar as declarações numa operação deste tipo para obter o mesmo efeito.</span><span class="sxs-lookup"><span data-stu-id="45eb1-195">Most critically, specializations for an operation that uses the output value of any other operation *cannot* be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>

<span data-ttu-id="45eb1-196">Por conseguinte, é muitas vezes útil especificar explicitamente as várias implementações.</span><span class="sxs-lookup"><span data-stu-id="45eb1-196">Therefore, it is often useful to explicitly specify the various implementations.</span></span>

### <a name="explicitly-specifying-implementations"></a><span data-ttu-id="45eb1-197">Especificação explícita das implementações</span><span class="sxs-lookup"><span data-stu-id="45eb1-197">Explicitly specifying implementations</span></span>

<span data-ttu-id="45eb1-198">No caso de a implementação não poder ser gerada pelo compilador, pode ser explicitamente especificada.</span><span class="sxs-lookup"><span data-stu-id="45eb1-198">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="45eb1-199">Tais declarações explícitas de especialização podem consistir numa diretiva de *geração* adequada ou numa aplicação definida pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="45eb1-199">Such explicit specialization declarations can consist of a suitable *generation directive* or a user-defined implementation.</span></span>
<span data-ttu-id="45eb1-200">Aqui fornecemos toda a gama de possibilidades, com exemplos a seguir abaixo.</span><span class="sxs-lookup"><span data-stu-id="45eb1-200">Here we provide the full range of possibilities, with examples following below.</span></span>


#### <a name="explicit-specialization-declarations"></a><span data-ttu-id="45eb1-201">Declarações explícitas de especialização</span><span class="sxs-lookup"><span data-stu-id="45eb1-201">Explicit specialization declarations</span></span>

<span data-ttu-id="45eb1-202">Q# as operações podem conter as seguintes declarações explícitas de especialização:</span><span class="sxs-lookup"><span data-stu-id="45eb1-202">Q# operations may contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="45eb1-203">A `body` especialização especifica a implementação da operação sem functores aplicados.</span><span class="sxs-lookup"><span data-stu-id="45eb1-203">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="45eb1-204">A `adjoint` especialização especifica a implementação da operação com o `Adjoint` functor aplicado.</span><span class="sxs-lookup"><span data-stu-id="45eb1-204">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="45eb1-205">A `controlled` especialização especifica a implementação da operação com o `Controlled` functor aplicado.</span><span class="sxs-lookup"><span data-stu-id="45eb1-205">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="45eb1-206">A `controlled adjoint` especialização especifica a implementação da operação com os `Adjoint` functores e os `Controlled` functors aplicados.</span><span class="sxs-lookup"><span data-stu-id="45eb1-206">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="45eb1-207">Esta especialização também pode ser `adjoint controlled` nomeada, uma vez que os dois functors viajam.</span><span class="sxs-lookup"><span data-stu-id="45eb1-207">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="45eb1-208">Uma especialização de operação consiste na etiqueta de especialização (por `body` exemplo, `adjoint` ou, etc.) seguida de uma das:</span><span class="sxs-lookup"><span data-stu-id="45eb1-208">An operation specialization consists of the specialization tag (e.g. `body`, or `adjoint`, etc.) followed by one of:</span></span>

- <span data-ttu-id="45eb1-209">Uma declaração explícita, como descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="45eb1-209">An explicit declaration as described below.</span></span>
- <span data-ttu-id="45eb1-210">Uma *diretiva* que diz ao compilador *como* gerar a especialização, uma das:</span><span class="sxs-lookup"><span data-stu-id="45eb1-210">A *directive* that tells the compiler *how* to generate the specialization, one of:</span></span>
  - <span data-ttu-id="45eb1-211">`intrinsic`, o que indica que a especialização é fornecida pela máquina-alvo.</span><span class="sxs-lookup"><span data-stu-id="45eb1-211">`intrinsic`, which indicates that the specialization is provided by the target machine.</span></span>
  - <span data-ttu-id="45eb1-212">`distribute`, que pode ser utilizado com `controlled` e `controlled adjoint` especializações.</span><span class="sxs-lookup"><span data-stu-id="45eb1-212">`distribute`, which may be used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="45eb1-213">Quando utilizado `controlled` com, indica que o compilador deve calcular a especialização aplicando-se `Controlled` a todas as operações na `body` .</span><span class="sxs-lookup"><span data-stu-id="45eb1-213">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="45eb1-214">Quando utilizado `controlled adjoint` com, indica que o compilador deve calcular a especialização aplicando-se `Controlled` a todas as operações na `adjoint` especialização.</span><span class="sxs-lookup"><span data-stu-id="45eb1-214">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="45eb1-215">`invert`, o que indica que o compilador deve calcular a `adjoint` especialização invertendo a `body` ordem de operações e aplicando o adjoint a cada um.</span><span class="sxs-lookup"><span data-stu-id="45eb1-215">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, i.e. reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="45eb1-216">Quando utilizado `adjoint controlled` com, isto indica que o compilador deve calcular a especialização invertendo a `controlled` especialização.</span><span class="sxs-lookup"><span data-stu-id="45eb1-216">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="45eb1-217">`self`, para indicar que a especialização adjoint é a mesma que a `body` especialização.</span><span class="sxs-lookup"><span data-stu-id="45eb1-217">`self`, to indicate that the adjoint specialization is the the same as the `body` specialization.</span></span>
    <span data-ttu-id="45eb1-218">Isto é legal para as `adjoint` `adjoint controlled` e especializações.</span><span class="sxs-lookup"><span data-stu-id="45eb1-218">This is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="45eb1-219">Pois, `adjoint controlled` `self` implica que a `adjoint controlled` especialização é a mesma que a `controlled` especialização.</span><span class="sxs-lookup"><span data-stu-id="45eb1-219">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="45eb1-220">`auto`, para indicar que o compilador deve selecionar uma diretiva adequada a aplicar.</span><span class="sxs-lookup"><span data-stu-id="45eb1-220">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="45eb1-221">`auto`não pode ser utilizado para a `body` especialização.</span><span class="sxs-lookup"><span data-stu-id="45eb1-221">`auto` may not be used for the `body` specialization.</span></span>

<span data-ttu-id="45eb1-222">As diretivas e `auto` todos exigem um fecho do ponto-de-vírgula. `;`</span><span class="sxs-lookup"><span data-stu-id="45eb1-222">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="45eb1-223">A `auto` diretiva resolve-se com a seguinte diretiva de geração se for fornecida uma declaração `body` explícita:</span><span class="sxs-lookup"><span data-stu-id="45eb1-223">The `auto` directive resolves to the following generation directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="45eb1-224">A `adjoint` especialização é gerada de acordo com a `invert` diretiva.</span><span class="sxs-lookup"><span data-stu-id="45eb1-224">The `adjoint` specialization is generated according to the directive `invert`.</span></span>
- <span data-ttu-id="45eb1-225">A `controlled` especialização é gerada de acordo com a `distribute` diretiva.</span><span class="sxs-lookup"><span data-stu-id="45eb1-225">The `controlled` specialization is generated according to the directive `distribute`.</span></span>
- <span data-ttu-id="45eb1-226">A `adjoint controlled` especialização é gerada de acordo com a diretiva `invert` se for dada uma declaração explícita, mas não uma para , e de outra `controlled` `adjoint` `distribute` forma.</span><span class="sxs-lookup"><span data-stu-id="45eb1-226">The `adjoint controlled` specialization is generated according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="45eb1-227">Se uma operação for auto-adjoint, especifique explicitamente a adjoint ou a especialização adjoint controlada através da diretiva de geração, a fim de `self` permitir que o compilador utilize essa informação para fins de otimização.</span><span class="sxs-lookup"><span data-stu-id="45eb1-227">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="45eb1-228">Uma declaração de especialização contendo uma implementação definida pelo utilizador consiste num argumento de tuple seguido de um bloco de declaração com o código Q# que implementa a especialização.</span><span class="sxs-lookup"><span data-stu-id="45eb1-228">A specialization declaration containing a user defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="45eb1-229">Na lista de argumentos, `...` é utilizado para representar os argumentos declarados para a operação como um todo.</span><span class="sxs-lookup"><span data-stu-id="45eb1-229">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="45eb1-230">Pois e , a lista de argumentos deve ser sempre - para e , a lista de `body` argumentos deve ser um símbolo que `adjoint` `(...)` `controlled` `adjoint controlled` represente o conjunto de qubits de controlo, seguidos por `...` , fechados em parênteses; por exemplo, `(controls,...)` .</span><span class="sxs-lookup"><span data-stu-id="45eb1-230">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

### <a name="examples"></a><span data-ttu-id="45eb1-231">Exemplos</span><span class="sxs-lookup"><span data-stu-id="45eb1-231">Examples</span></span>

<span data-ttu-id="45eb1-232">Uma declaração de operação pode ser tão simples como a seguinte, que define a operação primitiva Pauli X:</span><span class="sxs-lookup"><span data-stu-id="45eb1-232">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
<span data-ttu-id="45eb1-233">Note-se que o adjoint da operação Pauli X é definido com a diretiva `self` porque, por `X` definição, é o seu próprio inverso.</span><span class="sxs-lookup"><span data-stu-id="45eb1-233">Note that the adjoint of the Pauli X operation is defined with the directive `self` because by definition `X` is its own inverse.</span></span>

<span data-ttu-id="45eb1-234">O código `PrepareEntangledPair` acima, por exemplo, equivale ao código abaixo contendo declarações explícitas de especialização:</span><span class="sxs-lookup"><span data-stu-id="45eb1-234">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="45eb1-235">A palavra-chave `auto` indica que o compilador deve determinar como gerar a implementação da especialização.</span><span class="sxs-lookup"><span data-stu-id="45eb1-235">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>

#### <a name="user-defined-specialization-implementation"></a><span data-ttu-id="45eb1-236">Implementação da especialização definida pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="45eb1-236">User-defined specialization implementation</span></span>

<span data-ttu-id="45eb1-237">Se o compilador não conseguir gerar automaticamente a implementação para uma determinada especialização, ou se uma implementação mais eficiente puder ser administrada, então a implementação também pode ser definida manualmente.</span><span class="sxs-lookup"><span data-stu-id="45eb1-237">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

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
<span data-ttu-id="45eb1-238">No exemplo acima, `adjoint invert;` indica que a especialização adjoint deve ser gerada invertendo a implementação do corpo, e `controlled adjoint invert;` indica que a especialização adjoint controlada deve ser gerada invertendo a implementação da especialização controlada.</span><span class="sxs-lookup"><span data-stu-id="45eb1-238">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="45eb1-239">Se uma ou mais especializações para além do corpo padrão precisarde matem explicitamente, então a implementação do organismo predefinido deve ser embrulhada numa declaração de especialização adequada:</span><span class="sxs-lookup"><span data-stu-id="45eb1-239">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="circumstances-for-validly-defining-specializations"></a><span data-ttu-id="45eb1-240">Circunstâncias para definir validamente especializações</span><span class="sxs-lookup"><span data-stu-id="45eb1-240">Circumstances for validly defining specializations</span></span>

#### <a name="operation-declarations-with-adjointcontrolled"></a><span data-ttu-id="45eb1-241">Declarações de operação com adjoint/controlada</span><span class="sxs-lookup"><span data-stu-id="45eb1-241">Operation declarations with adjoint/controlled</span></span>

<span data-ttu-id="45eb1-242">É legal especificar uma operação sem versões adjoint ou controlada.</span><span class="sxs-lookup"><span data-stu-id="45eb1-242">It is legal to specify an operation with no adjoint or controlled versions.</span></span> <span data-ttu-id="45eb1-243">Por exemplo, as operações de medição não têm nenhuma, porque não são invertáveis ou controláveis.</span><span class="sxs-lookup"><span data-stu-id="45eb1-243">For instance, measurement operations have neither, because they are not invertible or controllable.</span></span>

<span data-ttu-id="45eb1-244">Uma operação apoia os `Adjoint` e/ou `Controlled` functores se a sua declaração contiver uma declaração implícita ou explícita das respetivas especializações.</span><span class="sxs-lookup"><span data-stu-id="45eb1-244">An operation supports the `Adjoint` and/or `Controlled` functors if its declaration contains an implicit or explicit declaration of the respective specializations.</span></span>

<span data-ttu-id="45eb1-245">Uma especialização adjoint/controlada explicitamente declarada implica a existência de uma especialização adjoint/controlada.</span><span class="sxs-lookup"><span data-stu-id="45eb1-245">An explicitly declared adjoint/controlled specialization implies the existence of an adjoint/controlled specialization.</span></span> 

<span data-ttu-id="45eb1-246">Para uma operação cujo corpo contenha ciclos de repetição até ao sucesso, definir declarações, medições, declarações de devolução ou chamadas para outras operações que não suportem o `Adjoint` functor, gerando automaticamente uma especialização adjoint seguindo a ou diretiva `invert` `auto` não é possível.</span><span class="sxs-lookup"><span data-stu-id="45eb1-246">For an operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

<span data-ttu-id="45eb1-247">Para uma operação cujo corpo contenha chamadas para outras operações que não suportem o `Controlled` functor, não é possível gerar automaticamente uma especialização controlada na sequência da `distribute` ou `auto` diretiva.</span><span class="sxs-lookup"><span data-stu-id="45eb1-247">For an operation whose body contains calls to other operations that does not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

#### <a name="controlled-adjoint"></a><span data-ttu-id="45eb1-248">Adjoint controlado</span><span class="sxs-lookup"><span data-stu-id="45eb1-248">Controlled Adjoint</span></span>

<span data-ttu-id="45eb1-249">A versão adjoint controlada de uma operação especifica como é implementada uma versão quântica da adjoint da operação.</span><span class="sxs-lookup"><span data-stu-id="45eb1-249">The controlled adjoint version of an operation specifies how a quantum-controlled version of the adjoint of the operation is implemented.</span></span>
<span data-ttu-id="45eb1-250">É legal especificar uma operação sem versão adjoint controlada; por exemplo, as operações de medição não têm versão adjoint controlada porque não são controláveis nem invertíveis.</span><span class="sxs-lookup"><span data-stu-id="45eb1-250">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="45eb1-251">Uma especialização adjoint controlada para uma operação precisa de existir se e apenas se existir uma especialização adjoint e controlada.</span><span class="sxs-lookup"><span data-stu-id="45eb1-251">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="45eb1-252">Nesse caso, a existência da especialização adjoint controlada é inferida e uma especialização adequada é gerada pelo compilador se não tiver sido definida explicitamente nenhuma implementação.</span><span class="sxs-lookup"><span data-stu-id="45eb1-252">In that case, the existence of the controlled adjoint specialization is inferred and an appropriate specialization is generated by the compiler if no implementation has been defined explicitly.</span></span> 

<span data-ttu-id="45eb1-253">Para uma operação cujo corpo contenha chamadas para outras operações que não tenham uma versão adjoint controlada, não é possível gerar automaticamente uma especialização adjoint na sequência da `invert` diretiva `distribute` ou `auto` diretiva.</span><span class="sxs-lookup"><span data-stu-id="45eb1-253">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute` or `auto` directive is not possible.</span></span>


### <a name="type-compatibility"></a><span data-ttu-id="45eb1-254">Compatibilidade tipo</span><span class="sxs-lookup"><span data-stu-id="45eb1-254">Type Compatibility</span></span>

<span data-ttu-id="45eb1-255">Uma operação com functores adicionais suportados pode ser usada em qualquer lugar de uma operação com menos functores, mas a mesma assinatura é esperada.</span><span class="sxs-lookup"><span data-stu-id="45eb1-255">An operation with additional functors supported may be used anywhere an operation with fewer functors but the same signature is expected.</span></span>
<span data-ttu-id="45eb1-256">Por exemplo, pode ser utilizada uma operação de tipo `(Qubit => Unit is Adj)` em qualquer lugar que se espere uma operação de `(Qubit => Unit)` tipo.</span><span class="sxs-lookup"><span data-stu-id="45eb1-256">For instance, an operation of type `(Qubit => Unit is Adj)` may be used anywhere an operation of type `(Qubit => Unit)` is expected.</span></span>

<span data-ttu-id="45eb1-257">Q# é *covariante* em relação aos tipos de retorno caltáveis: um callable que devolve um tipo é compatível com um callable com o mesmo tipo de entrada e um tipo de `'A` resultado compatível `'A` com.</span><span class="sxs-lookup"><span data-stu-id="45eb1-257">Q# is *covariant* with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that `'A` is compatible with.</span></span>

<span data-ttu-id="45eb1-258">Q# é *contravariante* em relação aos tipos de entrada: um callable que toma um tipo `'A` como entrada é compatível com um callable com o mesmo tipo de resultado e um tipo de entrada compatível com `'A` .</span><span class="sxs-lookup"><span data-stu-id="45eb1-258">Q# is *contravariant* with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="45eb1-259">Ou seja, dadas as seguintes definições:</span><span class="sxs-lookup"><span data-stu-id="45eb1-259">That is, given the following definitions:</span></span>

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

<span data-ttu-id="45eb1-260">os seguintes são verdadeiros:</span><span class="sxs-lookup"><span data-stu-id="45eb1-260">the following are true:</span></span>

- <span data-ttu-id="45eb1-261">A função `ConjugateInvertWith` pode ser invocada com um `inner` argumento de qualquer um ou `Invert` `ApplyUnitary` .</span><span class="sxs-lookup"><span data-stu-id="45eb1-261">The function `ConjugateInvertWith` may be invoked with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="45eb1-262">A função `ConjugateUnitaryWith` pode ser invocada com um `inner` argumento `ApplyUnitary` de, mas `Invert` não.</span><span class="sxs-lookup"><span data-stu-id="45eb1-262">The function `ConjugateUnitaryWith` may be invoked with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="45eb1-263">Um valor de tipo `(Qubit[] => Unit is Adj + Ctl)` pode ser devolvido a partir de `ConjugateInvertWith` .</span><span class="sxs-lookup"><span data-stu-id="45eb1-263">A value of type `(Qubit[] => Unit is Adj + Ctl)` may be returned from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="45eb1-264">Q# 0.3 introduziu uma diferença significativa no comportamento dos tipos definidos pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="45eb1-264">Q# 0.3 introduced a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="45eb1-265">Os tipos definidos pelo utilizador são tratados como uma versão embrulhada do tipo subjacente, em vez de como um subtipo.</span><span class="sxs-lookup"><span data-stu-id="45eb1-265">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="45eb1-266">Isto significa que um valor de um tipo definido pelo utilizador não é utilizável quando se espera um valor do tipo subjacente.</span><span class="sxs-lookup"><span data-stu-id="45eb1-266">This means that a value of a user-defined type is not usable where a value of the underlying type is expected.</span></span>


### <a name="conjugations"></a><span data-ttu-id="45eb1-267">Conjugações</span><span class="sxs-lookup"><span data-stu-id="45eb1-267">Conjugations</span></span>

<span data-ttu-id="45eb1-268">Em contraste com as partes clássicas, a libertação da memória quântica é um pouco mais envolvida, uma vez que os qubits de reposição cega podem ter efeitos indesejados no restante cálculo se os qubits ainda estiverem emaranhados.</span><span class="sxs-lookup"><span data-stu-id="45eb1-268">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="45eb1-269">Isto pode ser evitado por "desfazer" corretamente as computações realizadas antes de libertar a memória.</span><span class="sxs-lookup"><span data-stu-id="45eb1-269">This can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="45eb1-270">Um padrão comum na computação quântica é, portanto, o seguinte:</span><span class="sxs-lookup"><span data-stu-id="45eb1-270">A common pattern in quantum computing is hence the following:</span></span> 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

<span data-ttu-id="45eb1-271">A partir do nosso lançamento 0.9, apoiamos uma declaração de conjugação que implementa a transformação acima.</span><span class="sxs-lookup"><span data-stu-id="45eb1-271">Starting with our 0.9 release, we support a conjugation statement that implements the transformation above.</span></span> <span data-ttu-id="45eb1-272">Utilizando esta declaração, a operação `ApplyWith` pode ser implementada da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="45eb1-272">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
<span data-ttu-id="45eb1-273">Tal declaração de conjugação torna-se obviamente muito mais útil se a transformação exterior e interior não estiver prontamente disponível como operações, mas em vez disso são mais convenientes para descrever por um bloco composto por várias declarações.</span><span class="sxs-lookup"><span data-stu-id="45eb1-273">Such a conjugation statement obviously becomes far more useful if the outer and inner transformation are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="45eb1-274">A transformação inversa para as declarações definidas no bloco interior é automaticamente gerada pelo compilador e executada após a conclusão do bloco de aplicação.</span><span class="sxs-lookup"><span data-stu-id="45eb1-274">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and executed after the apply-block completes.</span></span>
<span data-ttu-id="45eb1-275">Uma vez que quaisquer variáveis mutáveis utilizadas como parte do bloco interior não podem ser recuperadas no bloco de aplicação, a transformação gerada é garantidamente a adjoint do cálculo no bloco interior.</span><span class="sxs-lookup"><span data-stu-id="45eb1-275">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 


## <a name="defining-new-functions"></a><span data-ttu-id="45eb1-276">Definição de novas funções</span><span class="sxs-lookup"><span data-stu-id="45eb1-276">Defining New Functions</span></span>

<span data-ttu-id="45eb1-277">As funções são puramente deterministas, rotinas clássicas em Q#, que são distintas das operações na medida em que não estão autorizadas a ter quaisquer efeitos além do cálculo de um valor de saída.</span><span class="sxs-lookup"><span data-stu-id="45eb1-277">Functions are purely deterministic, classical routines in Q#, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="45eb1-278">Em especial, as funções não podem chamar operações; Agir sobre, atribuir ou emprestar qubits; números aleatórios de amostra; ou depender do estado para além do valor de entrada para uma função.</span><span class="sxs-lookup"><span data-stu-id="45eb1-278">In particular, functions cannot call operations; act on, allocate, or borrow qubits; sample random numbers; or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="45eb1-279">Como consequência, as funções Q# são *puras,* na medida em que sempre mapeiam os mesmos valores de entrada para os mesmos valores de saída.</span><span class="sxs-lookup"><span data-stu-id="45eb1-279">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="45eb1-280">Isto permite ao compilador Q# reordenar com segurança como e quando as funções são chamadas ao gerar especializações de operação.</span><span class="sxs-lookup"><span data-stu-id="45eb1-280">This allows the Q# compiler to safely reorder how and when functions are called when generating operation specializations.</span></span>

<span data-ttu-id="45eb1-281">Cada ficheiro de origem Q# pode definir qualquer número de funções.</span><span class="sxs-lookup"><span data-stu-id="45eb1-281">Each Q# source file may define any number of functions.</span></span>
<span data-ttu-id="45eb1-282">Os nomes de funções devem ser únicos dentro de um espaço de nome e não podem entrar em conflito com nomes de funcionamento ou tipo.</span><span class="sxs-lookup"><span data-stu-id="45eb1-282">Function names must be unique within a namespace and may not conflict with operation or type names.</span></span>

<span data-ttu-id="45eb1-283">A definição de uma função funciona da mesma forma para definir uma operação, exceto que nenhuma especialização adjoint ou controlada pode ser definida para uma função.</span><span class="sxs-lookup"><span data-stu-id="45eb1-283">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="45eb1-284">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="45eb1-284">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

<span data-ttu-id="45eb1-285">ou</span><span class="sxs-lookup"><span data-stu-id="45eb1-285">or</span></span> 

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```

### <a name="classical-logic-in-functions--good"></a><span data-ttu-id="45eb1-286">Lógica clássica em funções == bom</span><span class="sxs-lookup"><span data-stu-id="45eb1-286">Classical logic in functions == good</span></span>

<span data-ttu-id="45eb1-287">Sempre que é possível fazê-lo, é útil escrever a lógica clássica em termos de funções e não de operações, para que possa ser mais facilmente utilizada a partir de dentro das operações.</span><span class="sxs-lookup"><span data-stu-id="45eb1-287">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations, so that it can be more readily used from within operations.</span></span>
<span data-ttu-id="45eb1-288">Por exemplo, se tivéssemos escrito a `Square` declaração acima como *operação,* então o compilador não teria podido garantir que chamá-la com a mesma entrada produziria consistentemente as mesmas saídas.</span><span class="sxs-lookup"><span data-stu-id="45eb1-288">For example, if we had written the `Square` declaration above as an *operation*, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="45eb1-289">Para sublinhar a diferença entre funções e operações, considere o problema da amostragem clássica de um número aleatório de dentro de uma operação Q#:</span><span class="sxs-lookup"><span data-stu-id="45eb1-289">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="45eb1-290">Cada vez que `U` for chamado, terá uma ação `target` diferente.</span><span class="sxs-lookup"><span data-stu-id="45eb1-290">Each time that `U` is called, it will have a different action on `target`.</span></span>
<span data-ttu-id="45eb1-291">Em particular, o compilador não pode garantir que, se adicionássemos uma declaração de `adjoint auto` especialização, `U` `U(target); Adjoint U(target);` então atua como identidade (isto é, como uma não-operação).</span><span class="sxs-lookup"><span data-stu-id="45eb1-291">In particular, the compiler cannot guarantee that if we added an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="45eb1-292">Isto viola a definição da adjoint que vimos em [Vetores e Matrizes](xref:microsoft.quantum.concepts.vectors), de tal forma que permitir gerar automaticamente uma especialização adjoint numa operação em que chamámos operação <xref:microsoft.quantum.math.randomreal> quebraria as garantias fornecidas pelo compilador; é uma operação para a qual não existe nenhuma <xref:microsoft.quantum.math.randomreal> versão adjoint ou controlada.</span><span class="sxs-lookup"><span data-stu-id="45eb1-292">This violates the definition of the adjoint that we saw in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing to auto-generate an adjoint specialization in an operation where we have called the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="45eb1-293">Por outro lado, permitir chamadas de funções como `Square` é segura, na medida em que o compilador pode ter a certeza de que só precisa de preservar a entrada `Square` para manter a sua produção estável.</span><span class="sxs-lookup"><span data-stu-id="45eb1-293">On the other hand, allowing function calls such as `Square` is safe, in that the compiler can be assured that it only needs to preserve the input to `Square` in order to keep its output stable.</span></span>
<span data-ttu-id="45eb1-294">Assim, isolar o máximo de lógica clássica possível em funções facilita a reutilização dessa lógica em outras funções e operações.</span><span class="sxs-lookup"><span data-stu-id="45eb1-294">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>


## <a name="generic-type-parameterized-callables"></a><span data-ttu-id="45eb1-295">Callables genéricos (tipo-parametrizados)</span><span class="sxs-lookup"><span data-stu-id="45eb1-295">Generic (Type-Parameterized) Callables</span></span>

<span data-ttu-id="45eb1-296">Muitas funções e operações que podemos querer definir não dependem muito dos tipos das suas inputs, mas apenas utilizam implicitamente os seus tipos através de outra função ou operação.</span><span class="sxs-lookup"><span data-stu-id="45eb1-296">Many functions and operations that we might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="45eb1-297">Por exemplo, considere o conceito de *mapa* comum a muitas línguas funcionais; dada uma função $f(x)$ e uma coleção de valores $ \{ x_1, x_2, \dots, x_n \} $, mapa devolve uma nova coleção $ \{ f(x_1), f(x_2), \dots, f(x_n) \} $.</span><span class="sxs-lookup"><span data-stu-id="45eb1-297">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="45eb1-298">Para implementar isto em Q#, podemos tirar partido dessas funções são de primeira classe.</span><span class="sxs-lookup"><span data-stu-id="45eb1-298">To implement this in Q#, we can take advantage of that functions are first class.</span></span>
<span data-ttu-id="45eb1-299">Vamos escrever um exemplo rápido `Map` de, usando ★ como espaço reservado enquanto descobrimos que tipos precisamos.</span><span class="sxs-lookup"><span data-stu-id="45eb1-299">Let's write out a quick example of `Map`, using ★ as a placeholder while we figure out what types we need.</span></span>

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="45eb1-300">Note que esta função parece muito a mesma, independentemente dos tipos reais em que substituímos.</span><span class="sxs-lookup"><span data-stu-id="45eb1-300">Note this function looks very much the same no matter what actual types we substitute in.</span></span>
<span data-ttu-id="45eb1-301">Um mapa de inteiros a Paulis, por exemplo, parece muito parecido com um mapa de números de pontos flutuantes a cordas:</span><span class="sxs-lookup"><span data-stu-id="45eb1-301">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="45eb1-302">Em princípio, poderíamos escrever uma versão de `Map` cada par de tipos que encontramos, mas isso introduz uma série de dificuldades.</span><span class="sxs-lookup"><span data-stu-id="45eb1-302">In principle, we could write a version of `Map` for every pair of types that we encounter, but this introduces a number of difficulties.</span></span>
<span data-ttu-id="45eb1-303">Por exemplo, se encontrarmos um `Map` bug, então temos de garantir que a correção é aplicada uniformemente em todas as versões de `Map` .</span><span class="sxs-lookup"><span data-stu-id="45eb1-303">For instance, if we find a bug in `Map`, then we must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="45eb1-304">Além disso, se construirmos um novo tuple ou UDT, então temos agora também de construir um novo `Map` para acompanhar o novo tipo.</span><span class="sxs-lookup"><span data-stu-id="45eb1-304">Moreover, if we construct a new tuple or UDT, then we must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="45eb1-305">Embora isto seja tratável para um pequeno número de tais funções, à medida que recolhemos cada vez mais funções da mesma forma `Map` que, o custo de introdução de novos tipos torna-se irracionalmente grande em ordem bastante curta.</span><span class="sxs-lookup"><span data-stu-id="45eb1-305">While this is tractable for a small number of such functions, as we collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="45eb1-306">Grande parte desta dificuldade resulta, no entanto, do facto de não termos dado ao compilador a informação de que necessita para reconhecer como as diferentes versões `Map` estão relacionadas.</span><span class="sxs-lookup"><span data-stu-id="45eb1-306">Much of this difficulty results, however, from that the we have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="45eb1-307">Efetivamente, queremos que o compilador trate `Map` como uma espécie de função matemática dos *tipos* Q# para as funções Q#.</span><span class="sxs-lookup"><span data-stu-id="45eb1-307">Effectively, we want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>

<span data-ttu-id="45eb1-308">Esta noção é formalizada permitindo que funções e operações tenham *parâmetros de tipo,* bem como os seus parâmetros normais de tuple.</span><span class="sxs-lookup"><span data-stu-id="45eb1-308">This notion is formalized by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="45eb1-309">Nos exemplos acima referidos, queremos pensar `Map` que têm parâmetros de tipo `Int, Pauli` no primeiro caso e no segundo `Double, String` caso.</span><span class="sxs-lookup"><span data-stu-id="45eb1-309">In the examples above, we wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="45eb1-310">Na maior parte dos casos, estes parâmetros de tipo podem então ser usados como se fossem tipos comuns: usamos valores de parâmetros de tipo para fazer matrizes e tuples, funções de chamada e operações, e atribuir a variáveis ordinárias ou mutáveis.</span><span class="sxs-lookup"><span data-stu-id="45eb1-310">For the most part, these type parameters can then be used as though they were ordinary types: we use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="45eb1-311">O caso mais extremo de dependência indireta é o dos qubits, onde um programa Q# não pode depender diretamente da estrutura do `Qubit` tipo, mas **deve** passar esses tipos para outras operações e funções.</span><span class="sxs-lookup"><span data-stu-id="45eb1-311">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type, but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="45eb1-312">Voltando ao exemplo acima, podemos ver que precisamos de `Map` ter parâmetros de tipo, um para representar a entrada `fn` e um para representar a saída de `fn` .</span><span class="sxs-lookup"><span data-stu-id="45eb1-312">Returning to the example above, then, we can see that we need `Map` to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="45eb1-313">Em Q#, isto é escrito adicionando suportes de ângulo (isto `<>` é, não travões $\travão {} $!) após o nome de uma função ou operação na sua declaração, e listando cada parâmetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="45eb1-313">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="45eb1-314">O nome de cada parâmetro de tipo deve começar com um `'` carrapato, indicando que se trata de um parâmetro tipo e não de um tipo ordinário (também conhecido como tipo *de concreto).*</span><span class="sxs-lookup"><span data-stu-id="45eb1-314">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="45eb1-315">Pois, `Map` nós assim escrevemos:</span><span class="sxs-lookup"><span data-stu-id="45eb1-315">For `Map`, we thus write:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="45eb1-316">Note que a definição de `Map<'Input, 'Output>` é extremamente semelhante às versões que escrevemos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="45eb1-316">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the versions we wrote out before.</span></span>
<span data-ttu-id="45eb1-317">A única diferença é que informamos explicitamente o compilador que `Map` não depende diretamente do que `'Input` e `'Output` são, mas funciona para qualquer dois tipos, utilizando-os indiretamente através `fn` de .</span><span class="sxs-lookup"><span data-stu-id="45eb1-317">The only difference is that we have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="45eb1-318">Uma vez `Map<'Input, 'Output>` definidos desta forma, podemos chamá-lo como se fosse uma função comum:</span><span class="sxs-lookup"><span data-stu-id="45eb1-318">Once we have defined `Map<'Input, 'Output>` in this way, we can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="45eb1-319">Escrever funções e operações genéricas é um lugar onde "tuple-in tuple-out" é uma forma muito útil de pensar sobre as funções e operações q#.</span><span class="sxs-lookup"><span data-stu-id="45eb1-319">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="45eb1-320">Uma vez que cada função requer exatamente uma entrada e devolve exatamente uma saída, uma entrada de tipo `'T -> 'U` corresponde a *qualquer* função Q# qualquer.</span><span class="sxs-lookup"><span data-stu-id="45eb1-320">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="45eb1-321">Da mesma forma, qualquer operação pode ser passada para uma entrada de tipo `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="45eb1-321">Similarly, any operation can be passed to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="45eb1-322">Como segundo exemplo, considere o desafio de escrever uma função que retorne a composição de duas outras funções:</span><span class="sxs-lookup"><span data-stu-id="45eb1-322">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="45eb1-323">Aqui, temos de especificar exatamente o `A` `B` que, e `C` estamos, portanto, a limitar severamente a utilidade da nossa nova `Compose` função.</span><span class="sxs-lookup"><span data-stu-id="45eb1-323">Here, we must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="45eb1-324">Afinal, `Compose` só depende `A` de, e `B` `C` *via* `innerFn` e `outerFn` .</span><span class="sxs-lookup"><span data-stu-id="45eb1-324">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="45eb1-325">Como alternativa, então, podemos adicionar parâmetros de tipo `Compose` que indicam que funciona para *qualquer,* e , desde que `A` estes `B` `C` parâmetros correspondam aos esperados por `innerFn` `outerFn` e:</span><span class="sxs-lookup"><span data-stu-id="45eb1-325">As an alternative, then, we can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="45eb1-326">As bibliotecas padrão Q# fornecem uma gama dessas operações e funções paramétricas tipo para facilitar o fluxo de controlo de ordem mais fácil de expressar.</span><span class="sxs-lookup"><span data-stu-id="45eb1-326">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="45eb1-327">Estes são discutidos mais no guia padrão da [biblioteca Q#](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="45eb1-327">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>


## <a name="callables-as-first-class-values"></a><span data-ttu-id="45eb1-328">Callables como Valores de Primeira Classe</span><span class="sxs-lookup"><span data-stu-id="45eb1-328">Callables as First-Class Values</span></span>

<span data-ttu-id="45eb1-329">Uma técnica crítica para o raciocínio sobre o fluxo de controlo e a lógica clássica usando funções em vez de operações é utilizar que as operações e funções em Q# são *de primeira classe*.</span><span class="sxs-lookup"><span data-stu-id="45eb1-329">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="45eb1-330">Ou seja, são cada valores da língua por direito próprio.</span><span class="sxs-lookup"><span data-stu-id="45eb1-330">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="45eb1-331">Por exemplo, o seguinte é perfeitamente válido código Q#, se um pouco indireto:</span><span class="sxs-lookup"><span data-stu-id="45eb1-331">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="45eb1-332">O valor da variável `ourH` no corte acima é então a operação , de modo a que <xref:microsoft.quantum.intrinsic.h> possamos chamar esse valor como qualquer outra operação.</span><span class="sxs-lookup"><span data-stu-id="45eb1-332">The value of the variable `ourH` in the snippet above is then the operation <xref:microsoft.quantum.intrinsic.h>, such that we can call that value like any other operation.</span></span>
<span data-ttu-id="45eb1-333">Isto permite-nos escrever operações que tomam as operações como parte da sua entrada, formando conceitos de fluxo de controlo de maior ordem.</span><span class="sxs-lookup"><span data-stu-id="45eb1-333">This allows us to write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="45eb1-334">Por exemplo, podemos imaginar querer "quadrar" uma operação aplicando-a duas vezes ao mesmo qubit alvo.</span><span class="sxs-lookup"><span data-stu-id="45eb1-334">For instance, we could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a><span data-ttu-id="45eb1-335">Operações de devolução de uma função</span><span class="sxs-lookup"><span data-stu-id="45eb1-335">Returning operations from a function</span></span>

<span data-ttu-id="45eb1-336">Sublinhamos que também podemos devolver as operações como parte das saídas, de modo a que possamos isolar alguns tipos de lógica condicional clássica como função clássica que devolve uma descrição de um programa quântico sob a forma de uma operação.</span><span class="sxs-lookup"><span data-stu-id="45eb1-336">We emphasize that we can also return operations as a part of outputs, such that we can isolate some kinds of classical conditional logic as a classical function which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="45eb1-337">Como exemplo simples, considere o exemplo da teletransporte, em que o partido que recebe uma mensagem clássica de dois bits precisa de usar a mensagem para descodificar o seu qubit no estado teletransportado adequado.</span><span class="sxs-lookup"><span data-stu-id="45eb1-337">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="45eb1-338">Poderíamos escrever isto em termos de uma função que pega nessas duas partes clássicas e devolve a operação de descodificação adequada.</span><span class="sxs-lookup"><span data-stu-id="45eb1-338">We could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

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

<span data-ttu-id="45eb1-339">Esta nova função é, de facto, uma função, na forma de a chamarmos com os mesmos valores `hereBit` de `thereBit` e, teremos sempre de volta a mesma operação.</span><span class="sxs-lookup"><span data-stu-id="45eb1-339">This new function is indeed a function, in that if we call it with the same values of `hereBit` and `thereBit`, we will always get back the same operation.</span></span>
<span data-ttu-id="45eb1-340">Assim, o descodificador pode ser executado com segurança dentro de operações sem ter de raciocinar sobre como a lógica de descodificação interage com as definições das diferentes especializações de operação.</span><span class="sxs-lookup"><span data-stu-id="45eb1-340">Thus, the decoder can be safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="45eb1-341">Ou seja, isolamos a lógica clássica dentro de uma função, garantindo ao compilador que a chamada de função pode ser reordenada impunemente enquanto a entrada for preservada.</span><span class="sxs-lookup"><span data-stu-id="45eb1-341">That is, we have isolated the classical logic inside a function, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>


## <a name="partial-application"></a><span data-ttu-id="45eb1-342">Aplicação parcial</span><span class="sxs-lookup"><span data-stu-id="45eb1-342">Partial Application</span></span>

<span data-ttu-id="45eb1-343">Podemos fazer significativamente mais com funções que devolvem as operações utilizando *aplicações parciais,* nas quais podemos fornecer uma ou mais partes da entrada a uma função ou operação sem realmente chamá-lo.</span><span class="sxs-lookup"><span data-stu-id="45eb1-343">We can do significantly more with functions that return operations by using *partial application*, in which we can provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="45eb1-344">Por exemplo, recordando o `ApplyTwice` exemplo acima, podemos indicar que não queremos especificar, imediatamente, a que qubit a operação de entrada deve aplicar:</span><span class="sxs-lookup"><span data-stu-id="45eb1-344">For example, recalling the `ApplyTwice` example above, we can indicate that we don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="45eb1-345">Neste caso, a variável local `twiceOp` detém o funcionamento parcialmente `ApplyTwice(op, _)` aplicado, onde partes da entrada que ainda não foram especificadas são indicadas por `_` .</span><span class="sxs-lookup"><span data-stu-id="45eb1-345">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where parts of the input that have not yet been specified are indicated by `_`.</span></span>
<span data-ttu-id="45eb1-346">Quando realmente ligamos `twiceOp` para a linha seguinte, passamos como entrada para a operação parcialmente aplicada todas as partes restantes da entrada para a operação original.</span><span class="sxs-lookup"><span data-stu-id="45eb1-346">When we actually call `twiceOp` in the next line, we pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="45eb1-347">Assim, o corte acima é efetivamente idêntico ao de ter chamado `ApplyTwice(op, target)` diretamente, salvo para isso introduzimos uma nova variável local que nos permite atrasar a chamada, fornecendo algumas partes da entrada.</span><span class="sxs-lookup"><span data-stu-id="45eb1-347">Thus, the above snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that we have introduced a new local variable that allows us to delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="45eb1-348">Uma vez que uma operação que foi parcialmente aplicada não é realmente chamada até que toda a sua entrada tenha sido fornecida, podemos aplicar parcialmente as operações mesmo a partir de funções.</span><span class="sxs-lookup"><span data-stu-id="45eb1-348">Since an operation that has been partially applied is not actually called until its entire input has been provided, we can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="45eb1-349">Em princípio, a lógica clássica no seu interior `SquareOperation` poderia ter sido muito mais envolvida, mas continua isolada do resto de uma operação pelas garantias que o compilador pode oferecer sobre funções.</span><span class="sxs-lookup"><span data-stu-id="45eb1-349">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span>
<span data-ttu-id="45eb1-350">Esta abordagem será usada em toda a biblioteca padrão Q# para expressar o fluxo de controlo clássico de uma forma que pode ser facilmente usada dentro de programas quânticos.</span><span class="sxs-lookup"><span data-stu-id="45eb1-350">This approach will be used throughout the Q# standard library for expressing classical control flow in a way that can be readily used within quantum programs.</span></span>


## <a name="recursion"></a><span data-ttu-id="45eb1-351">Recursão</span><span class="sxs-lookup"><span data-stu-id="45eb1-351">Recursion</span></span>

<span data-ttu-id="45eb1-352">Q# os callables são permitidos ser direta ou indiretamente recursivos.</span><span class="sxs-lookup"><span data-stu-id="45eb1-352">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="45eb1-353">Ou seja, uma operação ou função pode chamar-se a si mesma, ou pode chamar outra chamada que, direta ou indiretamente, chama a operação de chamada.</span><span class="sxs-lookup"><span data-stu-id="45eb1-353">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="45eb1-354">No entanto, existem dois comentários importantes sobre a recura:</span><span class="sxs-lookup"><span data-stu-id="45eb1-354">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="45eb1-355">A utilização da recursição nas operações é suscetível de interferir com determinadas otimizações.</span><span class="sxs-lookup"><span data-stu-id="45eb1-355">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="45eb1-356">Isto pode ter um impacto substancial no tempo de execução do algoritmo.</span><span class="sxs-lookup"><span data-stu-id="45eb1-356">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="45eb1-357">Ao executar um dispositivo quântico real, o espaço da pilha pode ser limitado, e assim a recursão profunda pode levar a um erro de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="45eb1-357">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="45eb1-358">Em particular, o compilador Q# e o tempo de execução não identificam e otimizam a recursão da cauda.</span><span class="sxs-lookup"><span data-stu-id="45eb1-358">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="whats-next"></a><span data-ttu-id="45eb1-359">O que se segue?</span><span class="sxs-lookup"><span data-stu-id="45eb1-359">What's Next?</span></span>
<span data-ttu-id="45eb1-360">Saiba mais sobre [Variáveis](xref:microsoft.quantum.guide.variables) em Q#.</span><span class="sxs-lookup"><span data-stu-id="45eb1-360">Learn about [Variables](xref:microsoft.quantum.guide.variables) in Q#.</span></span>