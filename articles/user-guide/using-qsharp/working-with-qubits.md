---
title: Trabalhar com qubits
description: Saiba como trabalhar com qubits em Q#
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: aa942a61280553ae4e51cd5ddcc85c0df935dab1
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835864"
---
# <a name="working-with-qubits"></a><span data-ttu-id="fedaf-103">Trabalhar com qubits</span><span class="sxs-lookup"><span data-stu-id="fedaf-103">Working with qubits</span></span>

<span data-ttu-id="fedaf-104">Qubits são o objeto fundamental da informação na computação quântica.</span><span class="sxs-lookup"><span data-stu-id="fedaf-104">Qubits are the fundamental object of information in quantum computing.</span></span> <span data-ttu-id="fedaf-105">Para uma introdução geral aos qubits, consulte [a computação quântica,](xref:microsoft.quantum.overview.understanding)e mergulhe mais profundamente na sua representação matemática, consulte [O Qubit](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="fedaf-105">For a general introduction to qubits, see [Understanding quantum computing](xref:microsoft.quantum.overview.understanding), and to dive deeper into their mathematical representation, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span> 

<span data-ttu-id="fedaf-106">Este artigo explora como usar e trabalhar com qubits num Q# programa.</span><span class="sxs-lookup"><span data-stu-id="fedaf-106">This article explores how to use and work with qubits in a Q# program.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="fedaf-107">Nenhuma das declarações discutidas neste artigo é válida dentro do corpo de uma função.</span><span class="sxs-lookup"><span data-stu-id="fedaf-107">None of the statements discussed in this article are valid within the body of a function.</span></span> <span data-ttu-id="fedaf-108">Só são válidos dentro das operações.</span><span class="sxs-lookup"><span data-stu-id="fedaf-108">They are only valid within operations.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="fedaf-109">Atribuição de Qubits</span><span class="sxs-lookup"><span data-stu-id="fedaf-109">Allocating Qubits</span></span>

<span data-ttu-id="fedaf-110">Como os qubits físicos são um recurso precioso num computador quântico, parte do trabalho do compilador é garantir que estão a ser usados o mais eficientemente possível.</span><span class="sxs-lookup"><span data-stu-id="fedaf-110">Because physical qubits are a precious resource in a quantum computer, part of the compiler's job is to make sure they are being used as efficiently as possible.</span></span>
<span data-ttu-id="fedaf-111">Como tal, tem de dizer Q# para *alocar* qubits para utilização dentro de um determinado bloco de declaração.</span><span class="sxs-lookup"><span data-stu-id="fedaf-111">As such, you need to tell Q# to *allocate* qubits for use within a particular statement block.</span></span>
<span data-ttu-id="fedaf-112">Você pode alocar qubits como um único qubit, ou como uma variedade de qubits, conhecido como um *registo*.</span><span class="sxs-lookup"><span data-stu-id="fedaf-112">You can allocate qubits as a single qubit, or as an array of qubits, known as a *register*.</span></span> 

### <a name="clean-qubits"></a><span data-ttu-id="fedaf-113">Qubits limpos</span><span class="sxs-lookup"><span data-stu-id="fedaf-113">Clean qubits</span></span>

<span data-ttu-id="fedaf-114">Utilize a `using` declaração para alocar novos qubits para utilização durante um bloco de declaração.</span><span class="sxs-lookup"><span data-stu-id="fedaf-114">Use the `using` statement to allocate new qubits for use during a statement block.</span></span>

<span data-ttu-id="fedaf-115">A declaração consiste na `using` palavra-chave, seguida de uma ligação em parênteses e do bloco de declaração dentro do qual os `( )` qubits estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="fedaf-115">The statement consists of the keyword `using`, followed by a binding enclosed in parentheses `( )` and the statement block within which the qubits are available.</span></span>
<span data-ttu-id="fedaf-116">A ligação segue o mesmo padrão que `let` as declarações: ou um único símbolo ou um tuple de símbolos, seguido de um sinal de iguais `=` , e um único valor ou um tuple de *inicializadores correspondentes*.</span><span class="sxs-lookup"><span data-stu-id="fedaf-116">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of *initializers*.</span></span>

<span data-ttu-id="fedaf-117">Os inicializadores estão disponíveis para um único qubit, indicado como `Qubit()` , ou uma matriz de qubits, onde é uma `Qubit[n]` `n` `Int` expressão.</span><span class="sxs-lookup"><span data-stu-id="fedaf-117">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, `Qubit[n]`, where `n` is an `Int` expression.</span></span>
<span data-ttu-id="fedaf-118">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="fedaf-118">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

<span data-ttu-id="fedaf-119">Quaisquer qubits atribuídos desta forma começam no estado $\ket$ {0}</span><span class="sxs-lookup"><span data-stu-id="fedaf-119">Any qubits allocated in this way start off in the $\ket{0}$ state.</span></span> <span data-ttu-id="fedaf-120">Assim, no exemplo anterior, `auxiliary` é um único qubit no estado $\ket {0} $, e está no estado de `register` cinco qubits $\ket {00000} = \ket {0} \otimes {0} \otimes \otimes \otimes \otimes \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="fedaf-120">Thus in the previous example, `auxiliary` is a single qubit in the state $\ket{0}$, and `register` is in the five-qubit state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="fedaf-121">No final do `using` bloco, quaisquer qubits atribuídos por esse bloco são imediatamente transcilhados e não podem ser usados mais.</span><span class="sxs-lookup"><span data-stu-id="fedaf-121">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="fedaf-122">As máquinas-alvo podem reutilizar qubits deallocados e oferecê-los a outros `using` blocos para alocação.</span><span class="sxs-lookup"><span data-stu-id="fedaf-122">Target machines can reuse deallocated qubits and offer them to other `using` blocks for allocation.</span></span> <span data-ttu-id="fedaf-123">Como tal, a máquina-alvo espera que os qubits estejam no estado de $\ket {0} $ imediatamente antes da negociação.</span><span class="sxs-lookup"><span data-stu-id="fedaf-123">As such, the target machine expects that qubits are in the $\ket{0}$ state immediately before deallocation.</span></span>
> <span data-ttu-id="fedaf-124">Sempre que possível, utilize operações unitárias para devolver quaisquer qubits atribuídos a $\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="fedaf-124">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="fedaf-125">Se necessário, pode utilizar a @"microsoft.quantum.intrinsic.reset" operação, que devolve o qubit a $\ket {0} $ medindo-o e realizando condicionalmente uma operação com base no resultado.</span><span class="sxs-lookup"><span data-stu-id="fedaf-125">If need be, you can use the @"microsoft.quantum.intrinsic.reset" operation, which returns the qubit to $\ket{0}$ by measuring it and conditionally performing an operation based on the result.</span></span> <span data-ttu-id="fedaf-126">Tal medição destrói qualquer emaranhado com os qubits restantes e pode, assim, impactar a computação.</span><span class="sxs-lookup"><span data-stu-id="fedaf-126">Such a measurement destroys any entanglement with the remaining qubits and can thus impact the computation.</span></span>


### <a name="borrowed-qubits"></a><span data-ttu-id="fedaf-127">Qubits emprestados</span><span class="sxs-lookup"><span data-stu-id="fedaf-127">Borrowed Qubits</span></span>

<span data-ttu-id="fedaf-128">Utilize a `borrowing` declaração para alocar qubits para uso temporário, que não precisam de estar num estado específico.</span><span class="sxs-lookup"><span data-stu-id="fedaf-128">Use the `borrowing` statement to allocate qubits for temporary use, which do not need to be in a specific state.</span></span>

<span data-ttu-id="fedaf-129">Você pode usar qubits emprestados como espaço de arranhão durante uma computação.</span><span class="sxs-lookup"><span data-stu-id="fedaf-129">You can use borrowed qubits as scratch space during a computation.</span></span>
<span data-ttu-id="fedaf-130">Estes qubits geralmente não estão em um estado limpo, isto é, eles não são necessariamente inicializados em um estado conhecido como $\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="fedaf-130">These qubits are generally not in a clean state, that is, they are not necessarily initialized in a known state such as $\ket{0}$.</span></span>
<span data-ttu-id="fedaf-131">Estes são muitas vezes referidos como qubits "sujos" porque o seu estado é desconhecido e pode mesmo ser enredado com outras partes da memória do computador quântico.</span><span class="sxs-lookup"><span data-stu-id="fedaf-131">These are often referred to as "dirty" qubits because their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span>

<span data-ttu-id="fedaf-132">A ligação segue o mesmo padrão e regras que a `using` declaração.</span><span class="sxs-lookup"><span data-stu-id="fedaf-132">The binding follows the same pattern and rules as the `using` statement.</span></span>
<span data-ttu-id="fedaf-133">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="fedaf-133">For example,</span></span>
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
<span data-ttu-id="fedaf-134">Os qubits emprestados estão num estado desconhecido e ficam fora de alcance no final do bloco de declaração.</span><span class="sxs-lookup"><span data-stu-id="fedaf-134">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="fedaf-135">O mutuário compromete-se a deixar os qubits no mesmo estado em que estavam quando os pediram emprestado; isto é, o seu estado no início e no fim do bloco de declaração deve ser o mesmo.</span><span class="sxs-lookup"><span data-stu-id="fedaf-135">The borrower commits to leaving the qubits in the same state they were in when they borrowed them; that is, their state at the beginning and the end of the statement block should be the same.</span></span>
<span data-ttu-id="fedaf-136">Como este estado não é necessariamente um estado clássico, na maioria dos casos, os âmbitos de empréstimo não devem conter medições.</span><span class="sxs-lookup"><span data-stu-id="fedaf-136">Because this state is not necessarily a classical state, in most cases borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="fedaf-137">Ao pedir qubits emprestados, o sistema tenta primeiro preencher o pedido de qubits que estão em uso mas não acedidos durante o corpo da `borrowing` declaração.</span><span class="sxs-lookup"><span data-stu-id="fedaf-137">When borrowing qubits, the system first tries to fill the request from qubits that are in use but not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="fedaf-138">Se não houver qubits suficientes, então atribui novos qubits para completar o pedido.</span><span class="sxs-lookup"><span data-stu-id="fedaf-138">If there aren't enough such qubits, then it allocates new qubits to complete the request.</span></span>

<span data-ttu-id="fedaf-139">Entre os casos de uso conhecido de qubits sujos estão implementações de portas CNOT multi-controladas que requerem apenas muito poucos qubits e implementação de incrementadores.</span><span class="sxs-lookup"><span data-stu-id="fedaf-139">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>
<span data-ttu-id="fedaf-140">Para um exemplo da sua utilização em Q# , consulte [Borrowing Qubits Exemplo](#borrowing-qubits-example) neste artigo, ou o papel [*Factoring usando 2n+2 qubits com multiplicação modular baseada em Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler e Svore 2017) para um algoritmo que utiliza qubits emprestados.</span><span class="sxs-lookup"><span data-stu-id="fedaf-140">For an example of their use in Q#, see [Borrowing Qubits Example](#borrowing-qubits-example) in this article, or the paper [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an algorithm which utilizes borrowed qubits.</span></span>

## <a name="intrinsic-operations"></a><span data-ttu-id="fedaf-141">Operações Intrínsecas</span><span class="sxs-lookup"><span data-stu-id="fedaf-141">Intrinsic Operations</span></span>

<span data-ttu-id="fedaf-142">Uma vez atribuído, pode passar um qubit para funções e operações.</span><span class="sxs-lookup"><span data-stu-id="fedaf-142">Once allocated, you can pass a qubit to functions and operations.</span></span>
<span data-ttu-id="fedaf-143">Em certo sentido, isto é tudo o que um Q# programa pode fazer com um qubit, uma vez que as ações que podem ser tomadas são todas definidas como operações.</span><span class="sxs-lookup"><span data-stu-id="fedaf-143">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>

<span data-ttu-id="fedaf-144">Este artigo discute algumas operações úteis Q# que pode usar para interagir com qubits.</span><span class="sxs-lookup"><span data-stu-id="fedaf-144">This article discusses a few useful Q# operations that you can use to interact with qubits.</span></span>
<span data-ttu-id="fedaf-145">Para obter mais detalhes sobre estes e outros, consulte [Operações e Funções Intrínsecas.](xref:microsoft.quantum.libraries.standard.prelude)</span><span class="sxs-lookup"><span data-stu-id="fedaf-145">For more detail about these and others, see [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude).</span></span> 

<span data-ttu-id="fedaf-146">Em primeiro lugar, os operadores de Pauli de um único qubit $X$, $Y$, e $Z$ são representados Q# pelas operações intrínsecas, [`X`](xref:microsoft.quantum.intrinsic.x) e , cada uma delas tem tipo [`Y`](xref:microsoft.quantum.intrinsic.y) [`Z`](xref:microsoft.quantum.intrinsic.z) `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="fedaf-146">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations [`X`](xref:microsoft.quantum.intrinsic.x), [`Y`](xref:microsoft.quantum.intrinsic.y), and [`Z`](xref:microsoft.quantum.intrinsic.z), each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="fedaf-147">Como descrito em [Operações e Funções Intrínsecas,](xref:microsoft.quantum.libraries.standard.prelude)pense em $X$ e, portanto, `X` como uma operação de inversão de marcha ou portão NÃO.</span><span class="sxs-lookup"><span data-stu-id="fedaf-147">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="fedaf-148">Você pode usar a `X` operação para preparar estados do formulário $\ket{s_0 s_1 \dots s_n}$ para algum fio de bit clássico $s$:</span><span class="sxs-lookup"><span data-stu-id="fedaf-148">You can use the `X` operation to prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

```qsharp
operation PrepareBitString(bitstring : Bool[], register : Qubit[]) : Unit
is Adj + Ctl {
    let nQubits = Length(register);
    for (idxQubit in 0..nQubits - 1) {
        if (bitstring[idxQubit]) {
            X(register[idxQubit]);
        }
    }
}

operation RunExample() : Unit {
    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
        // Remember to reset the qubits before deallocation:
        ResetAll(register);
    }
}
```

> [!TIP]
> <span data-ttu-id="fedaf-149">Mais tarde, verá formas mais compactas de escrever esta operação que não requerem fluxo manual de controlo.</span><span class="sxs-lookup"><span data-stu-id="fedaf-149">Later, you will see more compact ways of writing this operation that do not require manual control flow.</span></span>

<span data-ttu-id="fedaf-150">Também pode preparar estados como $\ket{+} = \left(\ket {0} + \ket {1} \ket \right) / \sqrt {2} $ e $\ket {-} = \left(\ket {0} \ket {1} \right) / \sqrt {2} $ usando a transformação Hadamard $H$, que é representada Q# pela operação intrínseca [`H`](xref:microsoft.quantum.intrinsic.h) (também do tipo (Qubit => Unidade é Aj + Ctl)):)):</span><span class="sxs-lookup"><span data-stu-id="fedaf-150">You can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation [`H`](xref:microsoft.quantum.intrinsic.h) (also of type (Qubit => Unit is Adj + Ctl)\`):</span></span>

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString in the earlier example.
    PrepareBitString(bitstring, register);
    // Next, use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the desired state.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a><span data-ttu-id="fedaf-151">Medições</span><span class="sxs-lookup"><span data-stu-id="fedaf-151">Measurements</span></span>

<span data-ttu-id="fedaf-152">As medições de qubits individuais podem ser realizadas em diferentes bases, cada uma representada por um eixo Pauli na [esfera bloch.](xref:microsoft.quantum.glossary#bloch-sphere)</span><span class="sxs-lookup"><span data-stu-id="fedaf-152">Measurements of individual qubits can be performed in different bases, each represented by a Pauli axis on the [Bloch sphere](xref:microsoft.quantum.glossary#bloch-sphere).</span></span>
<span data-ttu-id="fedaf-153">A *base computacional* refere-se à `PauliZ` base, e é a base mais comum utilizada para a medição.</span><span class="sxs-lookup"><span data-stu-id="fedaf-153">The *computational basis* refers to the `PauliZ` basis, and is the most common basis used for measurement.</span></span>

### <a name="measure-a-single-qubit-in-the-pauliz-basis"></a><span data-ttu-id="fedaf-154">Meça um único qubit na `PauliZ` base</span><span class="sxs-lookup"><span data-stu-id="fedaf-154">Measure a single qubit in the `PauliZ` basis</span></span>

<span data-ttu-id="fedaf-155">Utilize a [`M`](xref:microsoft.quantum.intrinsic.m) operação, que é uma operação não unitária incorporada, para medir um único qubit na `PauliZ` base e atribuir um valor clássico ao resultado.</span><span class="sxs-lookup"><span data-stu-id="fedaf-155">Use the [`M`](xref:microsoft.quantum.intrinsic.m) operation, which is a built-in intrinsic non-unitary operation, to measure a single qubit in the `PauliZ` basis and assign a classical value to the result.</span></span>
<span data-ttu-id="fedaf-156">`M` tem um tipo de retorno reservado, `Result` que só pode tomar valores ou corresponder aos `Zero` `One` estados medidos $\ket {0} $ ou $\ket {1} $ - indicando que o resultado já não é um estado quântico.</span><span class="sxs-lookup"><span data-stu-id="fedaf-156">`M` has a reserved return type, `Result`, which can only take values `Zero` or `One` corresponding to the measured states $\ket{0}$ or $\ket{1}$ - indicating that the result is no longer a quantum state.</span></span>

<span data-ttu-id="fedaf-157">Um exemplo simples é a seguinte operação, que atribui um qubit no estado $\ket {0} $, em seguida, aplica uma operação Hadamard `H` a ele e mede o resultado na `PauliZ` base.</span><span class="sxs-lookup"><span data-stu-id="fedaf-157">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // Apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, return the result of the measurement.
        return result;
    }
}
```

### <a name="measure-one-or-more-qubits-in-specific-bases"></a><span data-ttu-id="fedaf-158">Medir um ou mais qubits em bases específicas</span><span class="sxs-lookup"><span data-stu-id="fedaf-158">Measure one or more qubits in specific bases</span></span>

<span data-ttu-id="fedaf-159">Para medir um conjunto de um ou mais qubits em bases específicas, pode utilizar a [`Measure`](xref:microsoft.quantum.intrinsic.measure) operação.</span><span class="sxs-lookup"><span data-stu-id="fedaf-159">To measure an array of one or more qubits in specific bases, you can use the [`Measure`](xref:microsoft.quantum.intrinsic.measure) operation.</span></span>

<span data-ttu-id="fedaf-160">As entradas `Measure` são uma matriz de `Pauli` tipos (por exemplo, `[PauliX, PauliZ, PauliZ]` ) e uma matriz de qubits.</span><span class="sxs-lookup"><span data-stu-id="fedaf-160">The inputs to `Measure` are an array of `Pauli` types (for example, `[PauliX, PauliZ, PauliZ]`) and an array of qubits.</span></span>

<span data-ttu-id="fedaf-161">Um exemplo um pouco mais complicado é dado pela seguinte operação, que devolve o valor Boolean `true` se todos os qubits num registo de tipo `Qubit[]` estiverem no estado zero quando medidos numa base Pauli especificada, e que retorna `false` de outra forma.</span><span class="sxs-lookup"><span data-stu-id="fedaf-161">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

```qsharp
operation MeasureIfAllQubitsAreZero(qubits : Qubit[], pauli : Pauli) : Bool {
    mutable value = true;
    for (qubit in qubits) {
        if (Measure([pauli], [qubit]) == One) {
            set value = false;
        }
    }
    return value;
}
```

<span data-ttu-id="fedaf-162">Note que este exemplo ainda só funciona `Measure` em qubits individuais um de cada vez, mas a operação pode ser estendida a medições articulares em múltiplos qubits.</span><span class="sxs-lookup"><span data-stu-id="fedaf-162">Note that this example still only performs `Measure` on individual qubits one at a time, but the operation can be extended to joint measurements on multiple qubits.</span></span>

## <a name="borrowing-qubits-example"></a><span data-ttu-id="fedaf-163">Exemplo de Qubits emprestado</span><span class="sxs-lookup"><span data-stu-id="fedaf-163">Borrowing Qubits Example</span></span>

<span data-ttu-id="fedaf-164">Existem exemplos no cânone que usam a `borrowing` palavra-chave, como a seguinte função `MultiControlledXBorrow` .</span><span class="sxs-lookup"><span data-stu-id="fedaf-164">There are examples in the canon that use the `borrowing` keyword, such as the following function `MultiControlledXBorrow`.</span></span> <span data-ttu-id="fedaf-165">Se `controls` denotar os qubits de controlo para adicionar a uma `X` operação, então o número de [ancillas sujas adicionadas](xref:microsoft.quantum.glossary#ancilla) por esta implementação é `Length(controls)-2` .</span><span class="sxs-lookup"><span data-stu-id="fedaf-165">If `controls` denotes the control qubits to add to an `X` operation, then the number of dirty [ancillas](xref:microsoft.quantum.glossary#ancilla) added by this implementation is `Length(controls)-2`.</span></span>

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

<span data-ttu-id="fedaf-166">Note-se que este exemplo utilizou extensivamente o `With` combinador, na sua forma aplicável às operações que suportam, por exemplo, `WithA` .</span><span class="sxs-lookup"><span data-stu-id="fedaf-166">Note that this example used extensive use of the `With` combinator, in its form that is applicable for operations that support adjoint, for example, `WithA`.</span></span>
<span data-ttu-id="fedaf-167">Este é um bom estilo de programação, porque adicionar controlo às estruturas que envolvem `With` o controlo de propagações apenas para o funcionamento interno.</span><span class="sxs-lookup"><span data-stu-id="fedaf-167">This is good programming style, because adding control to structures involving `With` propagates control only to the inner operation.</span></span>
<span data-ttu-id="fedaf-168">Note-se ainda que, para além `body` da operação, foi explicitamente fornecida uma implementação `controlled` do corpo da operação, em vez de recorrer a um `controlled auto` comunicado.</span><span class="sxs-lookup"><span data-stu-id="fedaf-168">Also note that, in addition to the `body` of the operation, an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span>
<span data-ttu-id="fedaf-169">A razão para isso é que, devido à estrutura do circuito, é fácil adicionar mais controlos, o que é benéfico em comparação com a adição de controlo a cada portão do `body` .</span><span class="sxs-lookup"><span data-stu-id="fedaf-169">The reason for this is that, because of the structure of the circuit, it is easy to add further controls, which is beneficial compared to adding control to each gate in the `body`.</span></span> 

<span data-ttu-id="fedaf-170">É instrutivo comparar este código com outra função canónica `MultiControlledXClean` que alcança o mesmo objetivo de implementar uma operação controlada por multi-animais, no `X` entanto, que utiliza vários qubits limpos usando o `using` mecanismo.</span><span class="sxs-lookup"><span data-stu-id="fedaf-170">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="fedaf-171">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="fedaf-171">Next steps</span></span>

<span data-ttu-id="fedaf-172">Saiba mais sobre [o Control Flow](xref:microsoft.quantum.guide.controlflow) em Q# .</span><span class="sxs-lookup"><span data-stu-id="fedaf-172">Learn about [Control Flow](xref:microsoft.quantum.guide.controlflow) in Q#.</span></span>