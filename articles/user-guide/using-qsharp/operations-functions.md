---
title: Operações e funções emQ#
description: Como definir e chamar operações e funções, bem como as especializações de operação controladas e adjacentes.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
no-loc:
- Q#
- $$v
ms.openlocfilehash: 76437c83df894fa86409e680f961d97e267c6869
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867884"
---
# <a name="operations-and-functions-in-no-locq"></a><span data-ttu-id="f6424-103">Operações e Funções emQ#</span><span class="sxs-lookup"><span data-stu-id="f6424-103">Operations and Functions in Q#</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="f6424-104">Definição de Novas Operações</span><span class="sxs-lookup"><span data-stu-id="f6424-104">Defining New Operations</span></span>

<span data-ttu-id="f6424-105">As operações são o núcleo Q# de.</span><span class="sxs-lookup"><span data-stu-id="f6424-105">Operations are the core of Q#.</span></span>
<span data-ttu-id="f6424-106">Uma vez declarados, podem ser chamados a partir de aplicações clássicas .NET, por exemplo, utilizando um simulador ou por outras operações no seu interior Q# .</span><span class="sxs-lookup"><span data-stu-id="f6424-106">Once declared, they can either be called from classical .NET applications, for example, using a simulator or by other operations within Q#.</span></span>
<span data-ttu-id="f6424-107">Cada operação definida Q# pode chamar qualquer número de outras operações, incluindo as operações intrínsecas incorporadas definidas pela língua.</span><span class="sxs-lookup"><span data-stu-id="f6424-107">Each operation defined in Q# can call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="f6424-108">A forma particular como Q# define estas operações intrínsecas depende da máquina-alvo.</span><span class="sxs-lookup"><span data-stu-id="f6424-108">The particular way in which Q# defines these intrinsic operations depends on the target machine.</span></span>
<span data-ttu-id="f6424-109">Quando compilado, cada operação é representada como um tipo de classe .NET que pode ser fornecido às máquinas-alvo.</span><span class="sxs-lookup"><span data-stu-id="f6424-109">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="f6424-110">Cada Q# ficheiro de origem pode definir qualquer número de operações.</span><span class="sxs-lookup"><span data-stu-id="f6424-110">Each Q# source file can define any number of operations.</span></span>
<span data-ttu-id="f6424-111">Os nomes de operação devem ser únicos dentro de um espaço de nome e não podem entrar em conflito com nomes de tipo ou função.</span><span class="sxs-lookup"><span data-stu-id="f6424-111">Operation names must be unique within a namespace and can not conflict with type or function names.</span></span>

<span data-ttu-id="f6424-112">Uma declaração de operação consiste na palavra-chave, `operation` seguida do símbolo que é o nome da operação, um tuple identificador dactilografado que define os argumentos para a operação, um `:` cólon, um tipo de anotação que descreve o tipo de resultado da operação, opcionalmente uma anotação com as características de funcionamento, uma cinta aberta e, em seguida, o corpo da declaração de operação, em `{ }` anexo.</span><span class="sxs-lookup"><span data-stu-id="f6424-112">An operation declaration consists of the keyword `operation`, followed by the symbol that is the operation's name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation's result type, optionally an annotation with the operation characteristics, an open brace, and then the body of the operation declaration, enclosed in braces `{ }`.</span></span>

<span data-ttu-id="f6424-113">Cada operação leva uma entrada, produz uma saída, e especifica a implementação para uma ou mais especializações de operação.</span><span class="sxs-lookup"><span data-stu-id="f6424-113">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="f6424-114">As possíveis especializações, e como defini-las e chamá-las, são detalhadas nas diferentes secções deste artigo.</span><span class="sxs-lookup"><span data-stu-id="f6424-114">The possible specializations, and how to define and call them, are detailed in the different sections of this article.</span></span>
<span data-ttu-id="f6424-115">Por enquanto, considere a seguinte operação, que define apenas uma especialização do corpo predefinido e toma um único qubit como sua entrada, em seguida, chama a operação incorporada <xref:microsoft.quantum.intrinsic.x> nessa entrada:</span><span class="sxs-lookup"><span data-stu-id="f6424-115">For now, consider the following operation, which defines only a default body specialization and takes a single qubit as its input, then calls the built-in <xref:microsoft.quantum.intrinsic.x> operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="f6424-116">A palavra-chave `operation` começa a definição de operação, seguida do nome; aqui, `BitFlip` .</span><span class="sxs-lookup"><span data-stu-id="f6424-116">The keyword `operation` begins the operation definition, followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="f6424-117">Em seguida, o tipo de entrada é definido `Qubit` (), juntamente com um nome, `target` para se referir à entrada dentro da nova operação.</span><span class="sxs-lookup"><span data-stu-id="f6424-117">Next, the type of input is defined (`Qubit`), along with a name, `target`, for referring to the input within the new operation.</span></span>
<span data-ttu-id="f6424-118">Por último, `Unit` define que a saída da operação está vazia.</span><span class="sxs-lookup"><span data-stu-id="f6424-118">Lastly, `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="f6424-119">`Unit`é usado da mesma forma `void` em C# e outras línguas imperativas e é equivalente `unit` a em F# e outras línguas funcionais.</span><span class="sxs-lookup"><span data-stu-id="f6424-119">`Unit` is used similarly to `void` in C# and other imperative languages and is equivalent to `unit` in F# and other functional languages.</span></span>

<span data-ttu-id="f6424-120">As operações também podem devolver tipos mais interessantes do que `Unit` .</span><span class="sxs-lookup"><span data-stu-id="f6424-120">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="f6424-121">Por exemplo, a <xref:microsoft.quantum.intrinsic.m> operação devolve uma saída do `Result` tipo, representando ter efetuado uma medição.</span><span class="sxs-lookup"><span data-stu-id="f6424-121">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span>  <span data-ttu-id="f6424-122">Pode passá-lo de uma operação para outra operação ou usá-la com a `let` palavra-chave para definir uma nova variável.</span><span class="sxs-lookup"><span data-stu-id="f6424-122">You can pass it from an operation to another operation or use it with the `let` keyword to define a new variable.</span></span>

<span data-ttu-id="f6424-123">Esta abordagem permite representar a computação clássica que interage com operações quânticas a um nível baixo, como na [codificação superdense:](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)</span><span class="sxs-lookup"><span data-stu-id="f6424-123">This approach allows for representing classical computation that interacts with quantum operations at a low level, such as in [superdense coding](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):</span></span>

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
> <span data-ttu-id="f6424-124">Cada operação Q# requer exatamente uma entrada e devolve exatamente uma saída.</span><span class="sxs-lookup"><span data-stu-id="f6424-124">Each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="f6424-125">Várias entradas e saídas são representadas usando *tuples,* que recolhem múltiplos valores juntos num único valor.</span><span class="sxs-lookup"><span data-stu-id="f6424-125">Multiple inputs and outputs are represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="f6424-126">A este respeito, Q# é uma linguagem "tuple-in tuple-out".</span><span class="sxs-lookup"><span data-stu-id="f6424-126">In this regard, Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="f6424-127">Seguindo este conceito, um conjunto de parênteses vazios, `()` deve então ser lido como o tuple "vazio", que tem o tipo `Unit` .</span><span class="sxs-lookup"><span data-stu-id="f6424-127">Following this concept, a set of empty parentheses, `()`, should then be read as the "empty" tuple, which has the type `Unit`.</span></span>

## <a name="controlled-and-adjoint-operations"></a><span data-ttu-id="f6424-128">Operações controladas e adjacentes</span><span class="sxs-lookup"><span data-stu-id="f6424-128">Controlled and Adjoint Operations</span></span>

<span data-ttu-id="f6424-129">Se uma operação implementar uma transformação unitária, como é o caso de muitas operações em Q# , então é possível definir como a operação age quando *contígua* ou *controlada*.</span><span class="sxs-lookup"><span data-stu-id="f6424-129">If an operation implements a unitary transformation, as is the case for many operations in Q#, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="f6424-130">Uma especialização *adjacente* de uma operação especifica como o "inverso" da operação atua, enquanto uma especialização *controlada* especifica como uma operação age quando a sua aplicação está condicionada ao estado de um determinado registo quântico.</span><span class="sxs-lookup"><span data-stu-id="f6424-130">An *adjoint* specialization of an operation specifies how the "inverse" of the operation acts, while a *controlled* specialization specifies how an operation acts when its application is conditioned on the state of a particular quantum register.</span></span>

<span data-ttu-id="f6424-131">Os contíguos das operações quânticas são cruciais para muitos aspetos da computação quântica.</span><span class="sxs-lookup"><span data-stu-id="f6424-131">Adjoints of quantum operations are crucial to many aspects of quantum computing.</span></span> <span data-ttu-id="f6424-132">Para um exemplo de uma dessas situações discutidas ao lado de uma técnica de Q# programação útil, consulte [Conjugações](#conjugations) neste artigo.</span><span class="sxs-lookup"><span data-stu-id="f6424-132">For an example of one such situation discussed alongside a useful Q# programming technique, see [Conjugations](#conjugations) in this article.</span></span> 

<span data-ttu-id="f6424-133">A versão controlada de uma operação é uma nova operação que aplica efetivamente a operação base apenas se todos os qubits de controlo estiverem num estado especificado.</span><span class="sxs-lookup"><span data-stu-id="f6424-133">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="f6424-134">Se os qubits de controlo estiverem em sobreposição, então a operação de base é aplicada de forma coerente à parte apropriada da sobreposição.</span><span class="sxs-lookup"><span data-stu-id="f6424-134">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="f6424-135">Assim, as operações controladas são frequentemente usadas para gerar emaranhados.</span><span class="sxs-lookup"><span data-stu-id="f6424-135">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="f6424-136">Naturalmente, também poderia existir uma especialização *adjacente controlada,* especificando a aplicação controlada do adjacente de uma operação.</span><span class="sxs-lookup"><span data-stu-id="f6424-136">Naturally, a *controlled adjoint* specialization could exist as well, specifying the controlled application of an operation's adjoint.</span></span>

> [!NOTE]
> <span data-ttu-id="f6424-137">Se $U$ é a transformação unitária implementada por uma `U` operação, então `Adjoint U` representa a transformação unitária $U^\dagger$, que é a transposição conjugada complexa.</span><span class="sxs-lookup"><span data-stu-id="f6424-137">If $U$ is the unitary transformation implemented by an operation `U`, then `Adjoint U` represents the unitary transformation $U^\dagger$, which is the complex conjugate transpose.</span></span>
> <span data-ttu-id="f6424-138">Aplicar sucessivamente uma operação e, em seguida, o seu contíguo a um estado deixa o estado inalterado, como ilustrado pelo facto de $UU^\dagger = U^\dagger U = \id$, a matriz de identidade.</span><span class="sxs-lookup"><span data-stu-id="f6424-138">Successively applying an operation and then its adjoint to a state leaves the state unchanged, as illustrated by the fact that $UU^\dagger = U^\dagger U = \id$, the identity matrix.</span></span>
> <span data-ttu-id="f6424-139">A representação unitária de uma operação controlada é um pouco mais matizada, mas pode encontrar mais detalhes em [conceitos de computação quântica: múltiplos qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span><span class="sxs-lookup"><span data-stu-id="f6424-139">The unitary representation of a controlled operation is slightly more nuanced, but you can find more details at [Quantum computing concepts: multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

<span data-ttu-id="f6424-140">A secção seguinte descreve como chamar estas várias especializações no seu Q# código e como definir operações para as suportar.</span><span class="sxs-lookup"><span data-stu-id="f6424-140">The following section describes how to call these various specializations in your Q# code, and how to define operations to support them.</span></span>

### <a name="calling-operation-specializations"></a><span data-ttu-id="f6424-141">Especializações de operação de chamada</span><span class="sxs-lookup"><span data-stu-id="f6424-141">Calling operation specializations</span></span>

<span data-ttu-id="f6424-142">Um *functor* Q# é uma fábrica que define uma nova operação a partir de outra operação.</span><span class="sxs-lookup"><span data-stu-id="f6424-142">A *functor* in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="f6424-143">Os dois funtores padrão Q# são `Adjoint` `Controlled` e.</span><span class="sxs-lookup"><span data-stu-id="f6424-143">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

<span data-ttu-id="f6424-144">Os funtores têm acesso à implementação da operação base ao definir a implementação da nova operação.</span><span class="sxs-lookup"><span data-stu-id="f6424-144">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="f6424-145">Assim, os funtores podem desempenhar funções mais complexas do que as funções tradicionais de alto nível.</span><span class="sxs-lookup"><span data-stu-id="f6424-145">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span> <span data-ttu-id="f6424-146">Os functors não têm representação no Q# sistema de tipo.</span><span class="sxs-lookup"><span data-stu-id="f6424-146">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="f6424-147">Não é, portanto, atualmente possível ligá-los a uma variável ou passá-las como argumentos.</span><span class="sxs-lookup"><span data-stu-id="f6424-147">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="f6424-148">Use um functor aplicando-o a uma operação, que devolve uma nova operação.</span><span class="sxs-lookup"><span data-stu-id="f6424-148">Use a functor by applying it to an operation, which returns a new operation.</span></span>
<span data-ttu-id="f6424-149">Por exemplo, a aplicação do `Adjoint` functor à `Y` operação devolve a nova operação `Adjoint Y` .</span><span class="sxs-lookup"><span data-stu-id="f6424-149">For example, applying the `Adjoint` functor to the `Y` operation returns the new operation `Adjoint Y`.</span></span> <span data-ttu-id="f6424-150">Pode invocar a nova operação como qualquer outra operação.</span><span class="sxs-lookup"><span data-stu-id="f6424-150">You can invoke the new operation like any other operation.</span></span>
<span data-ttu-id="f6424-151">Para uma operação de apoio à aplicação dos `Adjoint` `Controlled` ou funtores, o seu tipo de devolução tem necessariamente de ser `Unit` .</span><span class="sxs-lookup"><span data-stu-id="f6424-151">For an operation to support the application of the `Adjoint` or `Controlled` functors, its return type necessarily needs to be `Unit`.</span></span> 

#### <a name="adjoint-functor"></a><span data-ttu-id="f6424-152">`Adjoint`functor</span><span class="sxs-lookup"><span data-stu-id="f6424-152">`Adjoint` functor</span></span>

<span data-ttu-id="f6424-153">Assim, `Adjoint Y(q1)` aplica o `Adjoint` functor à `Y` operação para gerar uma nova operação, e aplica essa nova operação a `q1` .</span><span class="sxs-lookup"><span data-stu-id="f6424-153">Thus, `Adjoint Y(q1)` applies the `Adjoint` functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>
<span data-ttu-id="f6424-154">A nova operação tem a mesma assinatura e tipo que a operação `Y` base.</span><span class="sxs-lookup"><span data-stu-id="f6424-154">The new operation has the same signature and type as the base operation `Y`.</span></span>
<span data-ttu-id="f6424-155">Em particular, a nova operação também apoia `Adjoint` , e suporta se e só se a `Controlled` operação de base o fez.</span><span class="sxs-lookup"><span data-stu-id="f6424-155">In particular, the new operation also supports `Adjoint`, and supports `Controlled` if and only if the base operation did.</span></span>
<span data-ttu-id="f6424-156">O `Adjoint` functor é o seu próprio inverso; ou seja, é sempre o mesmo que `Adjoint Adjoint Op` `Op` .</span><span class="sxs-lookup"><span data-stu-id="f6424-156">The `Adjoint` functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled-functor"></a><span data-ttu-id="f6424-157">`Controlled`functor</span><span class="sxs-lookup"><span data-stu-id="f6424-157">`Controlled` functor</span></span>

<span data-ttu-id="f6424-158">Da mesma forma, `Controlled X(controls, target)` aplica o `Controlled` functor à `X` operação para gerar uma nova operação, e aplica essa nova operação a `controls` e `target` .</span><span class="sxs-lookup"><span data-stu-id="f6424-158">Similarly, `Controlled X(controls, target)` applies the `Controlled` functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

> [!NOTE]
> <span data-ttu-id="f6424-159">Em Q# , versões controladas sempre tomam uma série de qubits de controlo, e o controlo é sempre baseado em todos os qubits de controlo que estão no estado computacional `PauliZ` , `One` $\ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="f6424-159">In Q#, controlled versions always take an array of control qubits, and the controlling is always based on all of the control qubits being in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
> <span data-ttu-id="f6424-160">O controlo baseado noutros Estados é conseguido aplicando a operação unitária adequada aos qubits de controlo antes da operação controlada e, em seguida, aplicando os inversos da operação unitária após a operação controlada.</span><span class="sxs-lookup"><span data-stu-id="f6424-160">Controlling based on other states is achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
> <span data-ttu-id="f6424-161">Por exemplo, aplicar uma `X` operação a um qubit de controlo antes e depois de uma operação controlada faz com que a `Zero` operação controle o estado ($\ket {0} $) para esse qubit; aplicando uma `H` operação antes e depois dos controlos sobre o `PauliX` `One` estado, ou seja , -1 egenvalue de Pauli X, $\ket {-} \mathrel{:=} (\ket {0} - \ket {1} ) / \sqrt {2} $ em vez do `PauliZ` `One` estado.</span><span class="sxs-lookup"><span data-stu-id="f6424-161">For example, applying an `X` operation to a control qubit before and after a controlled operation causes the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after controls on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="f6424-162">Dada a expressão de operação, pode formar uma nova expressão de operação utilizando o `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="f6424-162">Given an operation expression, you can form a new operation expression by using the `Controlled` functor.</span></span>
<span data-ttu-id="f6424-163">A assinatura da nova operação baseia-se na assinatura da operação original.</span><span class="sxs-lookup"><span data-stu-id="f6424-163">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="f6424-164">O tipo de resultado é o mesmo, mas o tipo de entrada é um dois tuple com uma matriz qubit que mantém o(s) qubit de controlo como primeiro elemento e os argumentos da operação original como segundo elemento.</span><span class="sxs-lookup"><span data-stu-id="f6424-164">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="f6424-165">A nova operação suporta `Controlled` , e irá suportar se e `Adjoint` somente se a operação original o fizer.</span><span class="sxs-lookup"><span data-stu-id="f6424-165">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="f6424-166">Se a operação original teve apenas um argumento, então [a equivalência de tuple singleton](xref:microsoft.quantum.guide.types) entra em jogo aqui.</span><span class="sxs-lookup"><span data-stu-id="f6424-166">If the original operation took only a single argument, then [singleton tuple equivalence](xref:microsoft.quantum.guide.types) comes into play here.</span></span>
<span data-ttu-id="f6424-167">Por exemplo, `Controlled X` é a versão controlada da `X` operação.</span><span class="sxs-lookup"><span data-stu-id="f6424-167">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span> 
<span data-ttu-id="f6424-168">`X`tem `(Qubit => Unit is Adj + Ctl)` tipo, assim `Controlled X` tem `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` tipo; por causa da equivalência de tuple singleton, este é o mesmo que `((Qubit[], Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="f6424-168">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="f6424-169">Se a operação base levou vários argumentos, lembre-se de incluir os argumentos correspondentes da versão controlada da operação em parênteses para convertê-los em tuple.</span><span class="sxs-lookup"><span data-stu-id="f6424-169">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="f6424-170">Por exemplo, `Controlled Rz` é a versão controlada da `Rz` operação.</span><span class="sxs-lookup"><span data-stu-id="f6424-170">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span> 
<span data-ttu-id="f6424-171">`Rz`tem `((Double, Qubit) => Unit is Adj + Ctl)` tipo, assim `Controlled Rz` como o tipo `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="f6424-171">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="f6424-172">Assim, `Controlled Rz(controls, (0.1, target))` seria uma invocação válida de `Controlled Rz` (note os parênteses em torno `0.1, target` de ).</span><span class="sxs-lookup"><span data-stu-id="f6424-172">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="f6424-173">Como outro exemplo, `CNOT(control, target)` pode ser implementado como `Controlled X([control], target)` .</span><span class="sxs-lookup"><span data-stu-id="f6424-173">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="f6424-174">Se um alvo deve ser controlado por dois qubits de controlo (CCNOT), utilize uma `Controlled X([control1, control2], target)` declaração.</span><span class="sxs-lookup"><span data-stu-id="f6424-174">If a target should be controlled by two control qubits (CCNOT), use a `Controlled X([control1, control2], target)` statement.</span></span>

#### `Controlled Adjoint` 

<span data-ttu-id="f6424-175">Os `Controlled` `Adjoint` funtores e funtores viajam, por isso não há diferença entre a aplicação `Controlled Adjoint Op` ou `Adjoint Controlled Op` .</span><span class="sxs-lookup"><span data-stu-id="f6424-175">The `Controlled` and `Adjoint` functors commute, so there is no difference between applying `Controlled Adjoint Op` or `Adjoint Controlled Op`.</span></span>


## <a name="defining-controlled-and-adjoint-implementations"></a><span data-ttu-id="f6424-176">Definição de implementações controladas e adjacentes</span><span class="sxs-lookup"><span data-stu-id="f6424-176">Defining Controlled and Adjoint Implementations</span></span>

<span data-ttu-id="f6424-177">Na primeira declaração de operação nos exemplos anteriores, as operações `BitFlip` `DecodeSuperdense` foram definidas com assinaturas `(Qubit => Unit)` `((Qubit, Qubit) => (Result, Result))` e, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="f6424-177">In the first operation declaration in the previous examples, the operations `BitFlip` and `DecodeSuperdense` were defined with signatures `(Qubit => Unit)` and `((Qubit, Qubit) => (Result, Result))`, respectively.</span></span>
<span data-ttu-id="f6424-178">Tal como `DecodeSuperdense` as medições, não se trata de uma operação unitária e, portanto, não podem existir especializações não adjacentes controladas (recorde-se a exigência de tal operação `Unit` de devolução).</span><span class="sxs-lookup"><span data-stu-id="f6424-178">As `DecodeSuperdense` includes measurements, it is not a unitary operation, and therefore neither controlled not adjoint specializations could exist (recall the related requirement that such an operation return `Unit`).</span></span>
<span data-ttu-id="f6424-179">No entanto, como `BitFlip` simplesmente executa a operação unitária, <xref:microsoft.quantum.intrinsic.x> poderia tê-lo definido com ambas as especializações.</span><span class="sxs-lookup"><span data-stu-id="f6424-179">However, as `BitFlip` simply performs the unitary <xref:microsoft.quantum.intrinsic.x> operation, you could have defined it with both specializations.</span></span>

<span data-ttu-id="f6424-180">Esta secção detalha como incluir a existência de especializações nas suas declarações de Q# operação, dando-lhes assim a capacidade de chamar em conjunto com os `Adjoint` ou `Controlled` funtores.</span><span class="sxs-lookup"><span data-stu-id="f6424-180">This section details how to include the existence of specializations in your Q# operation declarations, hence giving them the ability to called in conjunction with the `Adjoint` or `Controlled` functors.</span></span>
<span data-ttu-id="f6424-181">Para obter mais informações sobre algumas das situações em que é válido ou não é válido declarar determinadas especializações, consulte [Circunstâncias para definir validamente as especializações](#circumstances-for-validly-defining-specializations) neste artigo.</span><span class="sxs-lookup"><span data-stu-id="f6424-181">For more information about some of the situations in which it is either valid or not valid to declare certain specializations, see [Circumstances for validly defining specializations](#circumstances-for-validly-defining-specializations) in this article.</span></span>

<span data-ttu-id="f6424-182">As características de operação definem que tipos de funtores pode aplicar à operação declarada e que efeito têm.</span><span class="sxs-lookup"><span data-stu-id="f6424-182">Operation characteristics define what kinds of functors you can apply to the declared operation, and what effect they have.</span></span> <span data-ttu-id="f6424-183">A existência destas especializações pode ser declarada como parte da assinatura da operação, nomeadamente através de uma anotação com as características de funcionamento: `is Adj` `is Ctl` ou, ou `is Adj + Ctl` .</span><span class="sxs-lookup"><span data-stu-id="f6424-183">The existence of these specializations can be declared as part of the operation signature, specifically through an annotation with the operation characteristics: either `is Adj`, `is Ctl`, or `is Adj + Ctl`.</span></span>
<span data-ttu-id="f6424-184">A implementação real de cada especialização pode ser *definida implicitamente* ou *explicitamente.*</span><span class="sxs-lookup"><span data-stu-id="f6424-184">The actual implementation of each specialization can either be *implicitly* or *explicitly* defined.</span></span>

### <a name="implicitly-specifying-implementations"></a><span data-ttu-id="f6424-185">Especificar implicitamente implementações</span><span class="sxs-lookup"><span data-stu-id="f6424-185">Implicitly specifying implementations</span></span>

<span data-ttu-id="f6424-186">Neste caso, o corpo da declaração de operação consiste exclusivamente na implementação por defeito.</span><span class="sxs-lookup"><span data-stu-id="f6424-186">In this case, the body of the operation declaration consists solely of the default implementation.</span></span> <span data-ttu-id="f6424-187">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f6424-187">For example:</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
<span data-ttu-id="f6424-188">Aqui, a implementação correspondente para cada uma dessas especializações implicitamente declaradas é gerada automaticamente pelo compilador, a ser realizada se os `Adjoint` `Controlled` ou funtores forem utilizados.</span><span class="sxs-lookup"><span data-stu-id="f6424-188">Here, the corresponding implementation for each such implicitly declared specialization is automatically generated by the compiler, to be performed if the `Adjoint` or `Controlled` functors are used.</span></span>

<span data-ttu-id="f6424-189">Assim, uma chamada de `Adjoint PrepareEntangledPair` resultaria na implementação do compilador adjacente `CNOT` e, em seguida, do adjacente de `H` .</span><span class="sxs-lookup"><span data-stu-id="f6424-189">So, a call of `Adjoint PrepareEntangledPair` would result in the compiler implementing the adjoint of `CNOT` and then the adjoint of `H`.</span></span>
<span data-ttu-id="f6424-190">Estas operações individuais são ambas auto-adjacentes, pelo que a operação resultante `Adjoint PrepareEntangledPair` consistiria simplesmente em aplicar `CNOT(here, there)` e, em `H(here)` seguida, .</span><span class="sxs-lookup"><span data-stu-id="f6424-190">These individual operations are both self-adjoint, so the resulting `Adjoint PrepareEntangledPair` operation would simply consist of applying `CNOT(here, there)` and then `H(here)`.</span></span>
<span data-ttu-id="f6424-191">Assim, pode usar isto para escrever `DecodeSuperdense` o exemplo anterior de forma mais compacta, utilizando o adjacente de transformar o estado emaranhado de volta num par de `PrepareEntangledPair` qubits não emaranhados:</span><span class="sxs-lookup"><span data-stu-id="f6424-191">Hence you can use this to write the `DecodeSuperdense` in the previous example more compactly, by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="f6424-192">A anotação com as características de funcionamento na declaração é útil para garantir que o compilador gera automaticamente outras especializações com base na implementação padrão.</span><span class="sxs-lookup"><span data-stu-id="f6424-192">The annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="f6424-193">Existem várias limitações importantes a considerar ao conceber operações para uso com funtores.</span><span class="sxs-lookup"><span data-stu-id="f6424-193">There are several important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="f6424-194">Mais criticamente, as especializações para uma operação que utiliza o valor de saída de qualquer outra operação *não podem* ser geradas automaticamente pelo compilador, uma vez que é ambíguo como reordenar as declarações de tal operação para obter o mesmo efeito.</span><span class="sxs-lookup"><span data-stu-id="f6424-194">Most critically, specializations for an operation that uses the output value of any other operation *cannot* be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>

<span data-ttu-id="f6424-195">Por conseguinte, muitas vezes é útil especificar explicitamente as várias implementações.</span><span class="sxs-lookup"><span data-stu-id="f6424-195">Therefore, it is often useful to explicitly specify the various implementations.</span></span>

### <a name="explicitly-specifying-implementations"></a><span data-ttu-id="f6424-196">Especificar explicitamente implementações</span><span class="sxs-lookup"><span data-stu-id="f6424-196">Explicitly specifying implementations</span></span>

<span data-ttu-id="f6424-197">No caso de o compilador não conseguir gerar a implementação, pode especirá-la explicitamente.</span><span class="sxs-lookup"><span data-stu-id="f6424-197">In the case where the compiler cannot generate the implementation, you can specify it explicitly.</span></span> <span data-ttu-id="f6424-198">Tais declarações explícitas de especialização podem consistir numa diretiva de *geração* adequada ou numa implementação definida pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="f6424-198">Such explicit specialization declarations can consist of a suitable *generation directive* or a user-defined implementation.</span></span>
<span data-ttu-id="f6424-199">Seguem-se toda a gama de possibilidades, com alguns exemplos de especialização explícita.</span><span class="sxs-lookup"><span data-stu-id="f6424-199">Following are the full range of possibilities, with some examples of explicit specialization.</span></span> 


#### <a name="explicit-specialization-declarations"></a><span data-ttu-id="f6424-200">Declarações explícitas de especialização</span><span class="sxs-lookup"><span data-stu-id="f6424-200">Explicit specialization declarations</span></span>

<span data-ttu-id="f6424-201">Q#As operações podem conter as seguintes declarações explícitas de especialização:</span><span class="sxs-lookup"><span data-stu-id="f6424-201">Q# operations can contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="f6424-202">A `body` especialização especifica a implementação da operação sem funtores aplicados.</span><span class="sxs-lookup"><span data-stu-id="f6424-202">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="f6424-203">A `adjoint` especialização especifica a implementação da operação com o `Adjoint` functor aplicado.</span><span class="sxs-lookup"><span data-stu-id="f6424-203">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="f6424-204">A `controlled` especialização especifica a implementação da operação com o `Controlled` functor aplicado.</span><span class="sxs-lookup"><span data-stu-id="f6424-204">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="f6424-205">A `controlled adjoint` especialização especifica a implementação da operação com os `Adjoint` funtores e `Controlled` funtores aplicados.</span><span class="sxs-lookup"><span data-stu-id="f6424-205">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="f6424-206">Esta especialização também pode ser `adjoint controlled` nomeada, uma vez que os dois funtores viajam.</span><span class="sxs-lookup"><span data-stu-id="f6424-206">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="f6424-207">Uma especialização de operação consiste na etiqueta de especialização (por exemplo, `body` `adjoint` ou) seguida de um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="f6424-207">An operation specialization consists of the specialization tag (for example, `body` or `adjoint`) followed by one of:</span></span>

- <span data-ttu-id="f6424-208">Uma declaração explícita, tal como descrita no seguinte.</span><span class="sxs-lookup"><span data-stu-id="f6424-208">An explicit declaration as described in the following.</span></span>
- <span data-ttu-id="f6424-209">Uma *diretiva* que diz ao compilador *como* gerar a especialização, uma das seguintes:</span><span class="sxs-lookup"><span data-stu-id="f6424-209">A *directive* that tells the compiler *how* to generate the specialization, one of:</span></span>
  - <span data-ttu-id="f6424-210">`intrinsic`, o que indica que a máquina-alvo fornece a especialização.</span><span class="sxs-lookup"><span data-stu-id="f6424-210">`intrinsic`, which indicates that the target machine provides the specialization.</span></span>
  - <span data-ttu-id="f6424-211">`distribute`, usado com as `controlled` `controlled adjoint` especializações.</span><span class="sxs-lookup"><span data-stu-id="f6424-211">`distribute`, used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="f6424-212">Quando utilizado `controlled` com , indica que o compilador deve calcular a especialização aplicando-se a todas as `Controlled` operações no `body` .</span><span class="sxs-lookup"><span data-stu-id="f6424-212">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="f6424-213">Quando utilizado `controlled adjoint` com , indica que o compilador deve calcular a especialização aplicando-se a todas as `Controlled` operações da `adjoint` especialização.</span><span class="sxs-lookup"><span data-stu-id="f6424-213">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="f6424-214">`invert`, o que indica que o compilador deve calcular a `adjoint` especialização invertendo a `body` , por exemplo, invertendo a ordem de operações e aplicando o adjacente a cada um.</span><span class="sxs-lookup"><span data-stu-id="f6424-214">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, for example, reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="f6424-215">Quando `adjoint controlled` utilizado, isto indica que o compilador deve calcular a especialização invertendo a `controlled` especialização.</span><span class="sxs-lookup"><span data-stu-id="f6424-215">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="f6424-216">`self`, para indicar que a especialização adjacente é a mesma que a `body` especialização.</span><span class="sxs-lookup"><span data-stu-id="f6424-216">`self`, to indicate that the adjoint specialization is the same as the `body` specialization.</span></span>
    <span data-ttu-id="f6424-217">A utilização `self` é legal para as `adjoint` `adjoint controlled` especializações.</span><span class="sxs-lookup"><span data-stu-id="f6424-217">Using `self` is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="f6424-218">Pois, `adjoint controlled` `self` implica que a `adjoint controlled` especialização é a mesma que a `controlled` especialização.</span><span class="sxs-lookup"><span data-stu-id="f6424-218">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="f6424-219">`auto`, para indicar que o compilador deve selecionar uma diretiva adequada a aplicar.</span><span class="sxs-lookup"><span data-stu-id="f6424-219">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="f6424-220">Não pode usar `auto` para a `body` especialização.</span><span class="sxs-lookup"><span data-stu-id="f6424-220">You cannot use`auto` for the `body` specialization.</span></span>

<span data-ttu-id="f6424-221">As diretivas e `auto` todos requerem um fecho do ponto de souco. `;`</span><span class="sxs-lookup"><span data-stu-id="f6424-221">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="f6424-222">A `auto` diretiva resolve a seguinte diretiva gerada se for fornecida uma declaração `body` explícita:</span><span class="sxs-lookup"><span data-stu-id="f6424-222">The `auto` directive resolves to the following generated directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="f6424-223">A `adjoint` especialização gera de acordo com a `invert` diretiva.</span><span class="sxs-lookup"><span data-stu-id="f6424-223">The `adjoint` specialization generates according to the directive `invert`.</span></span>
- <span data-ttu-id="f6424-224">A `controlled` especialização gera de acordo com a `distribute` diretiva.</span><span class="sxs-lookup"><span data-stu-id="f6424-224">The `controlled` specialization generates according to the directive `distribute`.</span></span>
- <span data-ttu-id="f6424-225">A `adjoint controlled` especialização gera de acordo com a diretiva `invert` se for dada uma declaração `controlled` explícita, mas não uma para , e não para `adjoint` `distribute` outras.</span><span class="sxs-lookup"><span data-stu-id="f6424-225">The `adjoint controlled` specialization  generates according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="f6424-226">Se uma operação for auto-adjacente, especifique explicitamente a especialização adjacente ou a especialização adjacente controlada através da diretiva `self` de geração, a fim de permitir que o compilador utilize essa informação para fins de otimização.</span><span class="sxs-lookup"><span data-stu-id="f6424-226">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="f6424-227">Uma declaração de especialização contendo uma implementação definida pelo utilizador consiste num tuple de argumento seguido de um bloco de declaração com o Q# código que implementa a especialização.</span><span class="sxs-lookup"><span data-stu-id="f6424-227">A specialization declaration containing a user-defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="f6424-228">Na lista de argumentos, `...` é usado para representar os argumentos declarados para a operação como um todo.</span><span class="sxs-lookup"><span data-stu-id="f6424-228">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="f6424-229">Para `body` `adjoint` e, a lista de argumentos deve ser `(...)` sempre; para `controlled` `adjoint controlled` e, a lista de argumentos deve ser um símbolo que represente a matriz de qubits de controlo, seguido `...` de, incluído em parênteses; por exemplo, `(controls,...)` .</span><span class="sxs-lookup"><span data-stu-id="f6424-229">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

### <a name="examples"></a><span data-ttu-id="f6424-230">Exemplos</span><span class="sxs-lookup"><span data-stu-id="f6424-230">Examples</span></span>

<span data-ttu-id="f6424-231">Uma declaração de operação pode ser tão simples como a seguinte, que define a operação primitiva pauli X:</span><span class="sxs-lookup"><span data-stu-id="f6424-231">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
<span data-ttu-id="f6424-232">Note-se que o ponto adísquio da operação Pauli X é definido com a diretiva `self` porque, por definição, `X` é o seu próprio inverso.</span><span class="sxs-lookup"><span data-stu-id="f6424-232">Note that the adjoint of the Pauli X operation is defined with the directive `self` because by definition `X` is its own inverse.</span></span>

<span data-ttu-id="f6424-233">No exemplo `PrepareEntangledPair` anterior, o código é equivalente ao seguinte código que contém declarações explícitas de especialização:</span><span class="sxs-lookup"><span data-stu-id="f6424-233">In the earlier `PrepareEntangledPair` example, the code is equivalent to the following code containing explicit specialization declarations:</span></span> 

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
<span data-ttu-id="f6424-234">A palavra-chave `auto` indica que o compilador deve determinar como gerar a implementação da especialização.</span><span class="sxs-lookup"><span data-stu-id="f6424-234">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>

#### <a name="user-defined-specialization-implementation"></a><span data-ttu-id="f6424-235">Implementação de especialização definida pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="f6424-235">User-defined specialization implementation</span></span>

<span data-ttu-id="f6424-236">Se o compilador não conseguir gerar automaticamente a implementação para uma determinada especialização, ou se uma implementação mais eficiente puder ser dada, então pode definir manualmente a implementação.</span><span class="sxs-lookup"><span data-stu-id="f6424-236">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then you can manually define the implementation.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user-defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
<span data-ttu-id="f6424-237">No exemplo anterior, `adjoint invert;` indica que a especialização adjacente deve ser gerada invertendo a implementação do corpo, e `controlled adjoint invert;` indica que a especialização adjacente controlada deve ser gerada invertendo a implementação dada da especialização controlada.</span><span class="sxs-lookup"><span data-stu-id="f6424-237">In the previous example, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="f6424-238">Se uma ou mais especializações para além do corpo predefinido precisar de ser explicitamente declarada, então a implementação do corpo predefinido também deve ser incluída numa declaração de especialização adequada:</span><span class="sxs-lookup"><span data-stu-id="f6424-238">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

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

### <a name="circumstances-for-validly-defining-specializations"></a><span data-ttu-id="f6424-239">Circunstâncias para a definição válida de especializações</span><span class="sxs-lookup"><span data-stu-id="f6424-239">Circumstances for validly defining specializations</span></span>

#### <a name="operation-declarations-with-adjointcontrolled"></a><span data-ttu-id="f6424-240">Declarações de operação com adjacentes/controladas</span><span class="sxs-lookup"><span data-stu-id="f6424-240">Operation declarations with adjoint/controlled</span></span>

<span data-ttu-id="f6424-241">É legal especificar uma operação sem versões adjacentes ou controladas.</span><span class="sxs-lookup"><span data-stu-id="f6424-241">It is legal to specify an operation with no adjoint or controlled versions.</span></span> <span data-ttu-id="f6424-242">Por exemplo, as operações de medição não têm, por não serem invertíveis ou controláveis.</span><span class="sxs-lookup"><span data-stu-id="f6424-242">For instance, measurement operations have neither because they are not invertible or controllable.</span></span>

<span data-ttu-id="f6424-243">Uma operação apoia os `Adjoint` e `Controlled` functors se a sua declaração contiver uma declaração implícita ou explícita das respetivas especializações.</span><span class="sxs-lookup"><span data-stu-id="f6424-243">An operation supports the `Adjoint` and `Controlled` functors if its declaration contains an implicit or explicit declaration of the respective specializations.</span></span>

<span data-ttu-id="f6424-244">Uma especialização explicitamente declarada adjacente/controlada implica a existência de uma especialização adjacente/controlada.</span><span class="sxs-lookup"><span data-stu-id="f6424-244">An explicitly declared adjoint/controlled specialization implies the existence of an adjoint/controlled specialization.</span></span> 

<span data-ttu-id="f6424-245">Para uma operação cujo corpo contenha ciclos de repetição até ao sucesso, desemote declarações, medições, declarações de devolução ou chamadas para outras operações que não suportem o `Adjoint` functor, gerando automaticamente uma especialização adjacente seguindo a `invert` diretiva ou `auto` diretiva não é possível.</span><span class="sxs-lookup"><span data-stu-id="f6424-245">For an operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

<span data-ttu-id="f6424-246">Para uma operação cujo corpo contenha chamadas para outras operações que não suportem o `Controlled` functor, não é possível gerar automaticamente uma especialização controlada seguindo a `distribute` diretiva ou `auto` diretiva.</span><span class="sxs-lookup"><span data-stu-id="f6424-246">For an operation whose body contains calls to other operations that do not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

#### <a name="controlled-adjoint"></a><span data-ttu-id="f6424-247">Controlado adjacente</span><span class="sxs-lookup"><span data-stu-id="f6424-247">Controlled Adjoint</span></span>

<span data-ttu-id="f6424-248">A versão adjacente controlada de uma operação especifica como implementar uma versão com controlo quântico do adjacente da operação.</span><span class="sxs-lookup"><span data-stu-id="f6424-248">The controlled adjoint version of an operation specifies how to implement a quantum-controlled version of the adjoint of the operation.</span></span>
<span data-ttu-id="f6424-249">É legal especificar uma operação sem versão adjacente controlada; por exemplo, as operações de medição não têm versão adjacente controlada porque não são controláveis nem invertíveis.</span><span class="sxs-lookup"><span data-stu-id="f6424-249">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="f6424-250">Uma especialização adjacente controlada para uma operação tem de existir se e somente se existir uma especialização adjacente e controlada.</span><span class="sxs-lookup"><span data-stu-id="f6424-250">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="f6424-251">Nesse caso, é deduzida a existência da especialização adjacente controlada.</span><span class="sxs-lookup"><span data-stu-id="f6424-251">In that case, the existence of the controlled adjoint specialization is inferred.</span></span> <span data-ttu-id="f6424-252">Se nenhuma implementação for explicitamente definida, o compile gera uma especialização adequada.</span><span class="sxs-lookup"><span data-stu-id="f6424-252">If no implementation is explicitly defined, the compile generates an appropriate specialization.</span></span>

<span data-ttu-id="f6424-253">Para uma operação cujo corpo contenha chamadas para outras operações que não tenham uma versão adjacente controlada, não é possível gerar automaticamente uma especialização adjacente na sequência do `invert` `distribute` , ou `auto` diretiva.</span><span class="sxs-lookup"><span data-stu-id="f6424-253">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute`, or `auto` directive is not possible.</span></span>


### <a name="type-compatibility"></a><span data-ttu-id="f6424-254">Compatibilidade tipo</span><span class="sxs-lookup"><span data-stu-id="f6424-254">Type Compatibility</span></span>

<span data-ttu-id="f6424-255">Utilize uma operação com funtores adicionais suportados em qualquer lugar que utilize uma operação com menos funtores, mas a mesma assinatura.</span><span class="sxs-lookup"><span data-stu-id="f6424-255">Use an operation with additional functors supported anywhere you use an operation with fewer functors but the same signature.</span></span> <span data-ttu-id="f6424-256">Por exemplo, utilize uma operação do tipo `(Qubit => Unit is Adj)` em qualquer lugar que utilize uma operação do tipo `(Qubit => Unit)` .</span><span class="sxs-lookup"><span data-stu-id="f6424-256">For instance, use an operation of type `(Qubit => Unit is Adj)` anywhere you use an operation of type `(Qubit => Unit)`.</span></span>

<span data-ttu-id="f6424-257">Q#é *covariante* no que diz respeito aos tipos de retorno callable: uma chamada que devolve um tipo `'A` é compatível com uma chamada com o mesmo tipo de entrada e um tipo de resultado que é compatível com `'A` .</span><span class="sxs-lookup"><span data-stu-id="f6424-257">Q# is *covariant* with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that is compatible with `'A` .</span></span>

<span data-ttu-id="f6424-258">Q#é *contravariante* no que diz respeito aos tipos de entrada: uma chamada que toma um tipo `'A` como entrada é compatível com uma chamada com o mesmo tipo de resultado e um tipo de entrada compatível com `'A` .</span><span class="sxs-lookup"><span data-stu-id="f6424-258">Q# is *contravariant* with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="f6424-259">Isto é, dadas as seguintes definições,</span><span class="sxs-lookup"><span data-stu-id="f6424-259">That is, given the following definitions,</span></span>

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

<span data-ttu-id="f6424-260">É possível</span><span class="sxs-lookup"><span data-stu-id="f6424-260">you can</span></span>

- <span data-ttu-id="f6424-261">Invocar a `ConjugateInvertWith` função com um `inner` argumento de um ou `Invert` `ApplyUnitary` .</span><span class="sxs-lookup"><span data-stu-id="f6424-261">Invoke the function `ConjugateInvertWith` with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="f6424-262">Invoque a `ConjugateUnitaryWith` função com um `inner` argumento `ApplyUnitary` de, mas não `Invert` .</span><span class="sxs-lookup"><span data-stu-id="f6424-262">Invoke the function `ConjugateUnitaryWith` with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="f6424-263">Devolva um valor de tipo `(Qubit[] => Unit is Adj + Ctl)` a partir de `ConjugateInvertWith` .</span><span class="sxs-lookup"><span data-stu-id="f6424-263">Return a value of type `(Qubit[] => Unit is Adj + Ctl)` from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6424-264">Q#0.3 introduziu uma diferença significativa no comportamento dos tipos definidos pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="f6424-264">Q# 0.3 introduced a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="f6424-265">Os tipos definidos pelo utilizador são tratados como uma versão embrulhada do tipo subjacente, em vez de como um subtipo.</span><span class="sxs-lookup"><span data-stu-id="f6424-265">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="f6424-266">Isto significa que um valor de um tipo definido pelo utilizador não é utilizável onde se espera que seja um valor do tipo subjacente.</span><span class="sxs-lookup"><span data-stu-id="f6424-266">This means that a value of a user-defined type is not usable where you expect a value of the underlying type is.</span></span>


### <a name="conjugations"></a><span data-ttu-id="f6424-267">Conjugações</span><span class="sxs-lookup"><span data-stu-id="f6424-267">Conjugations</span></span>

<span data-ttu-id="f6424-268">Em contraste com os bits clássicos, a libertação da memória quântica é um pouco mais envolvida, uma vez que os qubits de reposição cega podem ter efeitos indesejáveis na computação restante se os qubits ainda estiverem emaranhados.</span><span class="sxs-lookup"><span data-stu-id="f6424-268">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="f6424-269">Estes efeitos podem ser evitados "desfazendo" os cálculos realizados corretamente antes de libertar a memória.</span><span class="sxs-lookup"><span data-stu-id="f6424-269">These effects can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="f6424-270">Um padrão comum na computação quântica é, por conseguinte, o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f6424-270">A common pattern in quantum computing is hence the following:</span></span> 

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

<span data-ttu-id="f6424-271">Começando com o nosso lançamento 0.9, Q# apoia uma declaração de conjugação que implementa a transformação anterior.</span><span class="sxs-lookup"><span data-stu-id="f6424-271">Starting with our 0.9 release, Q# supports a conjugation statement that implements the preceding transformation.</span></span> <span data-ttu-id="f6424-272">Utilizando esta declaração, a operação `ApplyWith` pode ser implementada da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="f6424-272">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

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
<span data-ttu-id="f6424-273">Tal declaração de conjugação torna-se muito mais útil se as transformações exteriores e interiores não estiverem prontamente disponíveis como operações, mas são mais convenientes para descrever por um bloco composto por várias declarações.</span><span class="sxs-lookup"><span data-stu-id="f6424-273">Such a conjugation statement becomes far more useful if the outer and inner transformations are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="f6424-274">A transformação inversa para as declarações definidas no bloco interior é gerada automaticamente pelo compilador e executada após o fim do bloco de aplicação.</span><span class="sxs-lookup"><span data-stu-id="f6424-274">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and run after the apply-block completes.</span></span>
<span data-ttu-id="f6424-275">Uma vez que quaisquer variáveis mutáveis utilizadas como parte do bloco interior não podem ser recuperadas no bloco de aplicação, a transformação gerada é garantidamente o adjacente do cálculo no bloco interior.</span><span class="sxs-lookup"><span data-stu-id="f6424-275">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 


## <a name="defining-new-functions"></a><span data-ttu-id="f6424-276">Definição de Novas Funções</span><span class="sxs-lookup"><span data-stu-id="f6424-276">Defining New Functions</span></span>

<span data-ttu-id="f6424-277">As funções são puramente determinísticas, rotinas clássicas Q# em, que são distintas das operações na qual não são permitidas a ter quaisquer efeitos além do cálculo de um valor de saída.</span><span class="sxs-lookup"><span data-stu-id="f6424-277">Functions are purely deterministic, classical routines in Q#, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="f6424-278">Em especial, as funções não podem convocar operações; agir, alocar ou pedir qubits emprestados; amostra de números aleatórios; ou de outra forma dependem do estado para além do valor de entrada para uma função.</span><span class="sxs-lookup"><span data-stu-id="f6424-278">In particular, functions cannot call operations; act on, allocate, or borrow qubits; sample random numbers; or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="f6424-279">Como consequência, Q# as funções são *puras,* na medida em que mapeiam sempre os mesmos valores de entrada para os mesmos valores de saída.</span><span class="sxs-lookup"><span data-stu-id="f6424-279">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="f6424-280">Este comportamento permite ao Q# compilador reencomendar com segurança como e quando chamar funções ao gerar especializações de operação.</span><span class="sxs-lookup"><span data-stu-id="f6424-280">This behavior allows the Q# compiler to safely reorder how and when to call functions when generating operation specializations.</span></span>

<span data-ttu-id="f6424-281">Cada Q# ficheiro de origem pode definir qualquer número de funções.</span><span class="sxs-lookup"><span data-stu-id="f6424-281">Each Q# source file can define any number of functions.</span></span>
<span data-ttu-id="f6424-282">Os nomes das funções devem ser únicos dentro de um espaço de nome e não podem entrar em conflito com o funcionamento ou os nomes do tipo.</span><span class="sxs-lookup"><span data-stu-id="f6424-282">Function names must be unique within a namespace and cannot conflict with operation or type names.</span></span>

<span data-ttu-id="f6424-283">A definição de uma função funciona da mesma forma para definir uma operação, exceto que não podem ser definidas especializações adjacentes ou controladas para uma função.</span><span class="sxs-lookup"><span data-stu-id="f6424-283">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="f6424-284">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f6424-284">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

<span data-ttu-id="f6424-285">ou</span><span class="sxs-lookup"><span data-stu-id="f6424-285">or</span></span> 

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

### <a name="classical-logic-in-functions--good"></a><span data-ttu-id="f6424-286">Lógica clássica em funções == bom</span><span class="sxs-lookup"><span data-stu-id="f6424-286">Classical logic in functions == good</span></span>

<span data-ttu-id="f6424-287">Sempre que é possível fazê-lo, é útil escrever a lógica clássica em termos de funções em vez de operações para que as operações possam usá-la mais facilmente.</span><span class="sxs-lookup"><span data-stu-id="f6424-287">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations so that operations can more readily use it.</span></span> <span data-ttu-id="f6424-288">Por exemplo, se tivesse escrito a declaração anterior `Square` como *uma operação*, então o compilador não teria sido capaz de garantir que chamá-lo com a mesma entrada produziria consistentemente as mesmas saídas.</span><span class="sxs-lookup"><span data-stu-id="f6424-288">For example, if you had written the earlier `Square` declaration as an *operation*, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="f6424-289">Para sublinhar a diferença entre funções e operações, considere o problema da amostragem clássica de um número aleatório de dentro de uma Q# operação:</span><span class="sxs-lookup"><span data-stu-id="f6424-289">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="f6424-290">Cada vez que `U` se chama, tem uma ação `target` diferente.</span><span class="sxs-lookup"><span data-stu-id="f6424-290">Each time that `U` is called, it has a different action on `target`.</span></span>
<span data-ttu-id="f6424-291">Em particular, o compilador não pode garantir que, se adicionar uma `adjoint auto` declaração de `U` especialização, age como identidade `U(target); Adjoint U(target);` (isto é, como um não-op).</span><span class="sxs-lookup"><span data-stu-id="f6424-291">In particular, the compiler cannot guarantee that if you add an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="f6424-292">Isto viola a definição do adjacente definido em [Vetores e Matrizes,](xref:microsoft.quantum.concepts.vectors)de modo que permitir que o compilador gere automaticamente uma especialização adjacente numa operação em que você chama a operação <xref:microsoft.quantum.math.randomreal> quebraria as garantias fornecidas pelo compilador; é uma operação para a <xref:microsoft.quantum.math.randomreal> qual não existe nenhuma versão adjacente ou controlada.</span><span class="sxs-lookup"><span data-stu-id="f6424-292">This violates the definition of the adjoint defined in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing the compiler to auto-generate an adjoint specialization in an operation where you call the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="f6424-293">Por outro lado, permitir chamadas de funções como `Square` é seguro, e assegura ao compilador que só precisa de preservar a entrada `Square` para manter a sua saída estável.</span><span class="sxs-lookup"><span data-stu-id="f6424-293">On the other hand, allowing function calls such as `Square` is safe, and assures the compiler that it only needs to preserve the input to `Square` to keep its output stable.</span></span>
<span data-ttu-id="f6424-294">Assim, isolar o máximo de lógica clássica possível em funções torna fácil a reutilização dessa lógica noutras funções e operações.</span><span class="sxs-lookup"><span data-stu-id="f6424-294">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>


## <a name="generic-type-parameterized-callables"></a><span data-ttu-id="f6424-295">Caláveis genéricos (tipo-parametrizados)</span><span class="sxs-lookup"><span data-stu-id="f6424-295">Generic (Type-Parameterized) Callables</span></span>

<span data-ttu-id="f6424-296">Muitas funções e operações que você pode desejar definir não dependem fortemente dos tipos de suas entradas, mas apenas implicitamente usar os seus tipos através de qualquer outra função ou funcionamento.</span><span class="sxs-lookup"><span data-stu-id="f6424-296">Many functions and operations that you might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="f6424-297">Por exemplo, considere o conceito de *mapa* comum a muitas línguas funcionais; dada uma função $f(x)$ e uma coleção de valores $ \{ x_1, x_2, \dots, x_n \} $, o mapa devolve uma nova coleção $ \{ f(x_1), f(x_2), \dots, f(x_n) \} $.</span><span class="sxs-lookup"><span data-stu-id="f6424-297">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="f6424-298">Para implementar isto Q# em , aproveite o facto de que as funções são de primeira classe.</span><span class="sxs-lookup"><span data-stu-id="f6424-298">To implement this in Q#, take advantage of the fact that functions are first class.</span></span>
<span data-ttu-id="f6424-299">Aqui está um exemplo rápido de `Map` , usando `T` como espaço reservado enquanto você descobre que tipos você precisa.</span><span class="sxs-lookup"><span data-stu-id="f6424-299">Here is a quick example of `Map`, using `T` as a placeholder while you figure out what types you need.</span></span>

```qsharp
function Map(fn : (T -> T), values : T[]) : T[] {
    mutable mappedValues = new T[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="f6424-300">Note que esta função parece muito igual independentemente dos tipos reais que substitua.</span><span class="sxs-lookup"><span data-stu-id="f6424-300">Note that this function looks very much the same no matter what actual types you substitute in.</span></span>
<span data-ttu-id="f6424-301">Um mapa de inteiros a Paulis, por exemplo, parece muito parecido com um mapa de números flutuantes a cordas:</span><span class="sxs-lookup"><span data-stu-id="f6424-301">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

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

<span data-ttu-id="f6424-302">Em princípio, pode escrever uma versão `Map` de todos os tipos que encontrar, mas isto introduz várias dificuldades.</span><span class="sxs-lookup"><span data-stu-id="f6424-302">In principle, you could write a version of `Map` for every pair of types that you encounter, but this introduces several difficulties.</span></span>
<span data-ttu-id="f6424-303">Por exemplo, se encontrar um `Map` bug, deve certificar-se de que a correção é aplicada uniformemente em todas as versões de `Map` .</span><span class="sxs-lookup"><span data-stu-id="f6424-303">For instance, if you find a bug in `Map`, then you must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="f6424-304">Além disso, se você constrói um novo tuple ou UDT, então você deve agora também construir um novo `Map` para acompanhar o novo tipo.</span><span class="sxs-lookup"><span data-stu-id="f6424-304">Moreover, if you construct a new tuple or UDT, then you must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="f6424-305">Embora isto seja tratável para um pequeno número de tais funções, à medida que recolhe cada vez mais funções da mesma forma `Map` que, o custo de introdução de novos tipos torna-se irracionalmente grande em ordem bastante curta.</span><span class="sxs-lookup"><span data-stu-id="f6424-305">While this is tractable for a small number of such functions, as you collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="f6424-306">No entanto, grande parte desta dificuldade resulta do facto de não ter dado ao compilador a informação de que necessita para reconhecer como as diferentes versões `Map` estão relacionadas.</span><span class="sxs-lookup"><span data-stu-id="f6424-306">However, much of this difficulty results from the fact that you have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="f6424-307">Efetivamente, pretende-se que o compilador trate `Map` como uma espécie de função matemática, desde Q# *tipos* a Q# funções.</span><span class="sxs-lookup"><span data-stu-id="f6424-307">Effectively, you want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>

<span data-ttu-id="f6424-308">Q#formaliza esta noção permitindo que funções e operações tenham *parâmetros de tipo,* bem como os seus parâmetros comuns de tuple.</span><span class="sxs-lookup"><span data-stu-id="f6424-308">Q# formalizes this notion by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="f6424-309">Nos exemplos anteriores, pretende-se pensar em ter parâmetros de `Map` tipo no primeiro caso e no segundo `Int, Pauli` `Double, String` caso.</span><span class="sxs-lookup"><span data-stu-id="f6424-309">In the previous examples, you wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="f6424-310">Na maior parte das vezes, utilize estes parâmetros de tipo como se fossem tipos comuns.</span><span class="sxs-lookup"><span data-stu-id="f6424-310">For the most part, use these type parameters as though they were ordinary types.</span></span> <span data-ttu-id="f6424-311">Utilize valores de parâmetros de tipo para fazer matrizes e tuples, funções de chamada e operações, e atribuir a variáveis comuns ou mutáveis.</span><span class="sxs-lookup"><span data-stu-id="f6424-311">Use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="f6424-312">O caso mais extremo de dependência indireta é o dos qubits, onde um Q# programa não pode depender diretamente da estrutura do `Qubit` tipo, mas **deve** passar esses tipos para outras operações e funções.</span><span class="sxs-lookup"><span data-stu-id="f6424-312">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="f6424-313">Voltando ao exemplo anterior, então, você vê que `Map` precisa ter parâmetros de tipo, um para representar a entrada `fn` e outro para representar a saída de `fn` .</span><span class="sxs-lookup"><span data-stu-id="f6424-313">Returning to the earlier example, then, you see that `Map` needs to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="f6424-314">Em Q# , isto é escrito adicionando suportes de ângulo (isto `<>` é, não travões $\braket {} $!) após o nome de uma função ou operação na sua declaração, e enumerando cada parâmetro do tipo.</span><span class="sxs-lookup"><span data-stu-id="f6424-314">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="f6424-315">O nome de cada parâmetro do tipo deve começar com um `'` carrapato, indicando que se trata de um parâmetro do tipo e não de um tipo comum (também conhecido como tipo *de betão).*</span><span class="sxs-lookup"><span data-stu-id="f6424-315">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="f6424-316">Assim, `Map` está escrito:</span><span class="sxs-lookup"><span data-stu-id="f6424-316">Thus, `Map`, is written:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="f6424-317">Note que a definição de `Map<'Input, 'Output>` parece extremamente semelhante às versões previoius.</span><span class="sxs-lookup"><span data-stu-id="f6424-317">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the previoius versions.</span></span>
<span data-ttu-id="f6424-318">A única diferença é que informou explicitamente o compilador que `Map` não depende diretamente do que e do que `'Input` `'Output` são, mas funciona para qualquer dois tipos, utilizando-os indiretamente através `fn` de .</span><span class="sxs-lookup"><span data-stu-id="f6424-318">The only difference is that you have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="f6424-319">Uma vez definido `Map<'Input, 'Output>` desta forma, pode chamá-lo como se fosse uma função comum:</span><span class="sxs-lookup"><span data-stu-id="f6424-319">Once you have defined `Map<'Input, 'Output>` in this way, you can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="f6424-320">Escrever funções genéricas e operações é um lugar onde "tuple-in tuple-out" é uma forma muito útil de pensar sobre Q# funções e operações.</span><span class="sxs-lookup"><span data-stu-id="f6424-320">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="f6424-321">Uma vez que cada função requer exatamente uma entrada e devolve exatamente uma saída, uma entrada de tipo `'T -> 'U` corresponde a *qualquer* Q# função.</span><span class="sxs-lookup"><span data-stu-id="f6424-321">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="f6424-322">Da mesma forma, pode passar qualquer operação a uma entrada do tipo `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="f6424-322">Similarly, you can pass any operation to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="f6424-323">Como segundo exemplo, considere o desafio de escrever uma função que devolve a composição de duas outras funções:</span><span class="sxs-lookup"><span data-stu-id="f6424-323">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="f6424-324">Aqui, você deve especificar exatamente o que `A` `B` , e `C` estão, portanto, severamente limitando a utilidade da nossa nova `Compose` função.</span><span class="sxs-lookup"><span data-stu-id="f6424-324">Here, you must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="f6424-325">Afinal, `Compose` só depende `A` de `B` , e `C` *via* `innerFn` e `outerFn` .</span><span class="sxs-lookup"><span data-stu-id="f6424-325">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="f6424-326">Como alternativa, então, pode adicionar parâmetros de tipo `Compose` a que indicam que funciona para *qualquer* , e , desde que `A` estes `B` `C` parâmetros correspondam aos esperados por `innerFn` `outerFn` e:</span><span class="sxs-lookup"><span data-stu-id="f6424-326">As an alternative, then, you can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="f6424-327">As Q# bibliotecas-padrão fornecem uma gama de operações e funções por tipo-parametrizadas para facilitar a expressão do fluxo de controlo de ordem superior.</span><span class="sxs-lookup"><span data-stu-id="f6424-327">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="f6424-328">Estes são discutidos mais adiante no [ Q# guia padrão](xref:microsoft.quantum.libraries.standard.intro)da biblioteca.</span><span class="sxs-lookup"><span data-stu-id="f6424-328">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>


## <a name="callables-as-first-class-values"></a><span data-ttu-id="f6424-329">Calíveis como Valores de Primeira Classe</span><span class="sxs-lookup"><span data-stu-id="f6424-329">Callables as First-Class Values</span></span>

<span data-ttu-id="f6424-330">Uma técnica crítica para o raciocínio sobre o fluxo de controlo e a lógica clássica utilizando funções em vez de operações é utilizar que as operações e as funções Q# são de primeira *classe*.</span><span class="sxs-lookup"><span data-stu-id="f6424-330">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="f6424-331">Ou seja, são valores cada um na língua por direito próprio.</span><span class="sxs-lookup"><span data-stu-id="f6424-331">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="f6424-332">Por exemplo, o seguinte é um código perfeitamente Q# válido, se um pouco indireto:</span><span class="sxs-lookup"><span data-stu-id="f6424-332">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="f6424-333">O valor da variável `ourH` no corte anterior é então a operação , de modo a que possa chamar esse valor como qualquer outra <xref:microsoft.quantum.intrinsic.h> operação.</span><span class="sxs-lookup"><span data-stu-id="f6424-333">The value of the variable `ourH` in the previous snippet is then the operation <xref:microsoft.quantum.intrinsic.h>, such that you can call that value like any other operation.</span></span>
<span data-ttu-id="f6424-334">Com esta capacidade, pode escrever operações que tomem operações como parte da sua entrada, formando conceitos de fluxo de controlo de ordem superior.</span><span class="sxs-lookup"><span data-stu-id="f6424-334">With this ability, you can write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="f6424-335">Por exemplo, pode imaginar querer "quadrar" uma operação aplicando-a duas vezes ao mesmo qubit alvo.</span><span class="sxs-lookup"><span data-stu-id="f6424-335">For instance, you could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a><span data-ttu-id="f6424-336">Operações de regresso de uma função</span><span class="sxs-lookup"><span data-stu-id="f6424-336">Returning operations from a function</span></span>

<span data-ttu-id="f6424-337">É importante enfatizar que também pode devolver operações como parte das saídas, de modo a que possa isolar alguns tipos de lógica condicional clássica como uma função clássica, que devolve uma descrição de um programa quântico sob a forma de uma operação.</span><span class="sxs-lookup"><span data-stu-id="f6424-337">It's important to emphasize that you can also return operations as a part of outputs, such that you can isolate some kinds of classical conditional logic as a classical function, which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="f6424-338">Como exemplo simples, considere o exemplo de teletransporte, no qual o partido que recebe uma mensagem clássica de duas partes precisa de usar a mensagem para descodificar o seu qubit no estado teletransportado adequado.</span><span class="sxs-lookup"><span data-stu-id="f6424-338">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="f6424-339">Você poderia escrever isto em termos de uma função que pega nessas duas partes clássicas e devolve a operação de descodição adequada.</span><span class="sxs-lookup"><span data-stu-id="f6424-339">You could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

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

<span data-ttu-id="f6424-340">Esta nova função é de facto uma função, na qual se lhe chamarmos com os mesmos valores `hereBit` de `thereBit` e, você sempre recebe de volta a mesma operação.</span><span class="sxs-lookup"><span data-stu-id="f6424-340">This new function is indeed a function, in that if you call it with the same values of `hereBit` and `thereBit`, you always get back the same operation.</span></span>
<span data-ttu-id="f6424-341">Assim, o descodificador pode executar com segurança operações internas sem ter de raciocinar sobre como a lógica de descodificante interage com as definições das diferentes especializações de operação.</span><span class="sxs-lookup"><span data-stu-id="f6424-341">Thus, the decoder can safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="f6424-342">Ou seja, a lógica clássica dentro de uma função é isolada, garantindo ao compilador que a chamada de função pode ser reordenada com impunidade enquanto a entrada for preservada.</span><span class="sxs-lookup"><span data-stu-id="f6424-342">That is, the classical logic inside a function is isolated, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>


## <a name="partial-application"></a><span data-ttu-id="f6424-343">Aplicação Parcial</span><span class="sxs-lookup"><span data-stu-id="f6424-343">Partial Application</span></span>

<span data-ttu-id="f6424-344">Pode fazer significativamente mais com funções que devolvem as operações utilizando *uma aplicação parcial,* na qual fornece uma ou mais partes da entrada para uma função ou funcionamento sem realmente chamá-la.</span><span class="sxs-lookup"><span data-stu-id="f6424-344">You can do significantly more with functions that return operations by using *partial application*, in which you provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="f6424-345">No exemplo `ApplyTwice` anterior, pode indicar que não pretende especificar, de imediato, qual o qubit da operação de entrada:</span><span class="sxs-lookup"><span data-stu-id="f6424-345">In the earlier `ApplyTwice` example, you can indicate that you don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="f6424-346">Neste caso, a variável local `twiceOp` detém a operação parcialmente `ApplyTwice(op, _)` aplicada, onde `_` indica partes da entrada que ainda não foram especificadas.</span><span class="sxs-lookup"><span data-stu-id="f6424-346">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where `_` indicates parts of the input that have not yet been specified.</span></span>
<span data-ttu-id="f6424-347">Quando ligar `twiceOp` na linha seguinte, passa como entrada para a operação parcialmente aplicada todas as partes restantes da entrada para a operação original.</span><span class="sxs-lookup"><span data-stu-id="f6424-347">When you call `twiceOp` in the next line, you pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="f6424-348">Assim, o corte anterior é efetivamente idêntico a ter chamado `ApplyTwice(op, target)` diretamente, salvo para que tenha introduzido uma nova variável local para que possa atrasar a chamada enquanto fornece algumas partes da entrada.</span><span class="sxs-lookup"><span data-stu-id="f6424-348">Thus, the previous snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that you have introduced a new local variable so you can delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="f6424-349">Uma vez que uma operação que foi parcialmente aplicada não é realmente chamada até que toda a sua entrada tenha sido fornecida, você pode aplicar parcialmente as operações mesmo a partir de funções.</span><span class="sxs-lookup"><span data-stu-id="f6424-349">Since an operation that has been partially applied is not actually called until its entire input has been provided, you can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="f6424-350">Em princípio, a lógica clássica dentro de si `SquareOperation` poderia ter sido muito mais envolvida, mas ainda está isolada do resto de uma operação pelas garantias que o compilador pode oferecer sobre funções.</span><span class="sxs-lookup"><span data-stu-id="f6424-350">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span> <span data-ttu-id="f6424-351">A Q# biblioteca padrão usa esta abordagem ao longo de todo para expressar o fluxo de controlo clássico de uma forma que os programas quânticos podem facilmente usar.</span><span class="sxs-lookup"><span data-stu-id="f6424-351">The Q# standard library uses this approach throughout for expressing classical control flow in a way that quantum programs can readily use.</span></span>


## <a name="recursion"></a><span data-ttu-id="f6424-352">Recursão</span><span class="sxs-lookup"><span data-stu-id="f6424-352">Recursion</span></span>

<span data-ttu-id="f6424-353">Q#as calções podem ser direta ou indiretamente recursivas.</span><span class="sxs-lookup"><span data-stu-id="f6424-353">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="f6424-354">Ou seja, uma operação ou função pode chamar-se a si mesma, ou pode chamar outra chamada que, direta ou indiretamente, chama a operação callable.</span><span class="sxs-lookup"><span data-stu-id="f6424-354">That is, an operation or function can call itself, or it can call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="f6424-355">No entanto, existem dois comentários importantes sobre a utilização da recursão:</span><span class="sxs-lookup"><span data-stu-id="f6424-355">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="f6424-356">A utilização de recursões nas operações é suscetível de interferir com determinadas otimizações.</span><span class="sxs-lookup"><span data-stu-id="f6424-356">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="f6424-357">Esta interferência pode ter um impacto substancial no tempo de execução do algoritmo.</span><span class="sxs-lookup"><span data-stu-id="f6424-357">This interference can have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="f6424-358">Ao correr num dispositivo quântico real, o espaço da pilha pode ser limitado, e assim a recursão profunda pode levar a um erro de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="f6424-358">When running on an actual quantum device, stack space might be limited, and so deep recursion can lead to a runtime error.</span></span>
  <span data-ttu-id="f6424-359">Em particular, o compilador e o Q# tempo de execução não identificam e otimizam a recursão da cauda.</span><span class="sxs-lookup"><span data-stu-id="f6424-359">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f6424-360">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="f6424-360">Next steps</span></span>

<span data-ttu-id="f6424-361">Saiba mais sobre [variáveis](xref:microsoft.quantum.guide.variables) em Q# .</span><span class="sxs-lookup"><span data-stu-id="f6424-361">Learn about [Variables](xref:microsoft.quantum.guide.variables) in Q#.</span></span>