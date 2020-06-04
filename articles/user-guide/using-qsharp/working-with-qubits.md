---
title: Trabalhar com qubits
description: preencher descrição
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: 0deb0729a88c49798f32a22a943b935d383c570b
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327548"
---
# <a name="working-with-qubits"></a><span data-ttu-id="d114d-103">Trabalhar com qubits</span><span class="sxs-lookup"><span data-stu-id="d114d-103">Working with qubits</span></span>

<span data-ttu-id="d114d-104">Tendo visto agora uma variedade de diferentes partes da língua Q#, vamos entrar no espesso dela e ver como usar os próprios qubits.</span><span class="sxs-lookup"><span data-stu-id="d114d-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

<span data-ttu-id="d114d-105">Note que nenhuma destas declarações é permitida dentro do corpo de uma função.</span><span class="sxs-lookup"><span data-stu-id="d114d-105">Note that none of these statements are allowed within the body of a function.</span></span>
<span data-ttu-id="d114d-106">Só são válidos dentro das operações.</span><span class="sxs-lookup"><span data-stu-id="d114d-106">They are only valid within operations.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="d114d-107">Atribuição de Qubits</span><span class="sxs-lookup"><span data-stu-id="d114d-107">Allocating Qubits</span></span>

### <a name="clean-qubits"></a><span data-ttu-id="d114d-108">Qubits limpos</span><span class="sxs-lookup"><span data-stu-id="d114d-108">Clean qubits</span></span>

<span data-ttu-id="d114d-109">A `using` declaração é usada para *alocar* novos qubits para uso durante um bloco de declaração.</span><span class="sxs-lookup"><span data-stu-id="d114d-109">The `using` statement is used to *allocate* new qubits for use during a statement block.</span></span>

<span data-ttu-id="d114d-110">A declaração consiste na palavra-chave `using` , seguida de um parênteses aberto , uma `(` ligação, um parênteses `)` próximos , e o bloco de declaração dentro do qual os qubits estarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d114d-110">The statement consists of the keyword `using`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="d114d-111">A ligação segue o mesmo padrão que `let` as declarações: ou um único símbolo ou um tuple de símbolos, seguido de um sinal de iguais `=` , e um único valor ou um tuple de *inicializadores correspondentes*.</span><span class="sxs-lookup"><span data-stu-id="d114d-111">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of *initializers*.</span></span>

<span data-ttu-id="d114d-112">Os inicializadores estão disponíveis para um único qubit, indicado como `Qubit()` , ou uma matriz de qubits, onde é uma `Qubit[n]` `n` `Int` expressão.</span><span class="sxs-lookup"><span data-stu-id="d114d-112">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, `Qubit[n]`, where `n` is an `Int` expression.</span></span>
<span data-ttu-id="d114d-113">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="d114d-113">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

<span data-ttu-id="d114d-114">Quaisquer qubits atribuídos desta forma começam no estado de $\ket {0} $; no exemplo acima, `register` está assim no estado $\ket = {00000} \ket {0} \otimes {0} \otimes \otimes \otimes \otimes \otimes \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="d114d-114">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="d114d-115">No final do `using` bloco, quaisquer qubits atribuídos por esse bloco são imediatamente transcilhados e não podem ser usados mais.</span><span class="sxs-lookup"><span data-stu-id="d114d-115">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="d114d-116">As máquinas-alvo esperam que os qubits estejam no estado de $\ket {0} $ imediatamente antes da negociação, para que possam ser reutilizados e oferecidos a outros `using` blocos para alocação.</span><span class="sxs-lookup"><span data-stu-id="d114d-116">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="d114d-117">Sempre que possível, utilize operações unitárias para devolver quaisquer qubits atribuídos a $\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="d114d-117">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="d114d-118">Se necessário, a @"microsoft.quantum.intrinsic.reset" operação pode ser usada para medir um qubit em vez disso, e para utilizar esse resultado de medição para garantir que o qubit medido seja devolvido a $\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="d114d-118">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="d114d-119">Tal medição destruirá qualquer emaranhado com os qubits restantes e poderá, assim, impactar a computação.</span><span class="sxs-lookup"><span data-stu-id="d114d-119">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span>


### <a name="borrowed-qubits"></a><span data-ttu-id="d114d-120">Qubits emprestados</span><span class="sxs-lookup"><span data-stu-id="d114d-120">Borrowed Qubits</span></span>

<span data-ttu-id="d114d-121">A `borrowing` declaração é utilizada para disponibilizar qubits para uso temporário, que não precisam de estar num determinado estado.</span><span class="sxs-lookup"><span data-stu-id="d114d-121">The `borrowing` statement is used to make qubits available for temporary use, which do not need be in a specific state.</span></span>

<span data-ttu-id="d114d-122">O mecanismo de empréstimo permite a atribuição de qubits que podem ser usados como espaço de risco durante um cálculo.</span><span class="sxs-lookup"><span data-stu-id="d114d-122">The borrowing mechanism allows the allocation of qubits that can be used as scratch space during a computation.</span></span>
<span data-ttu-id="d114d-123">Estes qubits geralmente não estão em estado limpo, ou seja, não são necessariamente inicializados num estado conhecido como $\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="d114d-123">These qubits are generally not in a clean state, i.e., they are not necessarily initialized in a known state such as $\ket{0}$.</span></span>
<span data-ttu-id="d114d-124">Estes são muitas vezes referidos como qubits "sujos" porque o seu estado é desconhecido e pode mesmo ser enredado com outras partes da memória do computador quântico.</span><span class="sxs-lookup"><span data-stu-id="d114d-124">These are often referred to as "dirty" qubits because their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span>

<span data-ttu-id="d114d-125">A ligação segue o mesmo padrão e regras que a de um `using` comunicado.</span><span class="sxs-lookup"><span data-stu-id="d114d-125">The binding follows the same pattern and rules as the one in a `using` statement.</span></span>
<span data-ttu-id="d114d-126">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="d114d-126">For example,</span></span>
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
<span data-ttu-id="d114d-127">Os qubits emprestados estão num estado desconhecido e ficam fora de alcance no final do bloco de declaração.</span><span class="sxs-lookup"><span data-stu-id="d114d-127">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="d114d-128">O mutuário compromete-se a deixar os qubits no mesmo estado em que estavam quando foram emprestados, ou seja, o seu estado no início e no final do bloco de declaração deverá ser o mesmo.</span><span class="sxs-lookup"><span data-stu-id="d114d-128">The borrower commits to leaving the qubits in the same state they were in when they were borrowed,  i.e. their state at the beginning and at the end of the statement block is expected to be the same.</span></span>
<span data-ttu-id="d114d-129">Este Estado, em particular, não é necessariamente um estado clássico, tal como, na maioria dos casos, os âmbitos de empréstimo não devem conter medições.</span><span class="sxs-lookup"><span data-stu-id="d114d-129">This state in particular is not necessarily a classical state, such that in most cases, borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="d114d-130">Ao pedir qubits emprestados, o sistema tentará primeiro preencher o pedido de qubits que estão em uso mas que não são acedidos durante o corpo da `borrowing` declaração.</span><span class="sxs-lookup"><span data-stu-id="d114d-130">When borrowing qubits, the system will first try to fill the request from qubits that are in use but that are not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="d114d-131">Se não houver qubits suficientes, então irá alocar novos qubits para completar o pedido.</span><span class="sxs-lookup"><span data-stu-id="d114d-131">If there aren't enough such qubits, then it will allocate new qubits to complete the request.</span></span>


<span data-ttu-id="d114d-132">Entre os casos de uso conhecido de qubits sujos estão implementações de portas CNOT multi-controladas que requerem apenas muito poucos qubits e implementação de incrementadores.</span><span class="sxs-lookup"><span data-stu-id="d114d-132">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>
<span data-ttu-id="d114d-133">Veja o [Exemplo de Qubits Emprestado](#borrowing-qubits-example) abaixo para ver um exemplo da sua utilização em Q#, ou o papel [*Factoring usando 2n+2 qubits com multiplicação modular baseada em Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler e Svore 2017) para um algoritmo que utiliza qubits emprestados.</span><span class="sxs-lookup"><span data-stu-id="d114d-133">See the [Borrowing Qubits Example](#borrowing-qubits-example) below to see an example of their use in Q#, or the paper [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an algorithm which utilizes borrowed qubits.</span></span>


## <a name="intrinsic-operations"></a><span data-ttu-id="d114d-134">Operações Intrínsecas</span><span class="sxs-lookup"><span data-stu-id="d114d-134">Intrinsic Operations</span></span>

<span data-ttu-id="d114d-135">Uma vez atribuído, um qubit pode então ser passado para funções e operações.</span><span class="sxs-lookup"><span data-stu-id="d114d-135">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="d114d-136">Em certo sentido, isto é tudo o que um programa Q# pode fazer com um qubit, uma vez que as ações que podem ser tomadas são todas definidas como operações.</span><span class="sxs-lookup"><span data-stu-id="d114d-136">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="d114d-137">Veremos estas operações com mais detalhes em [Operações e Funções Intrínsecas,](xref:microsoft.quantum.libraries.standard.prelude)mas por enquanto, mencionamos algumas operações úteis que podem ser usadas para interagir com qubits.</span><span class="sxs-lookup"><span data-stu-id="d114d-137">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="d114d-138">Em primeiro lugar, os operadores de Pauli de um único qubit $X$, $Y$, e $Z$ são representados em Q# pelas operações intrínsecas, `X` e , cada um dos quais tem tipo `Y` `Z` `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="d114d-138">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="d114d-139">Como descrito em [Operações e Funções Intrínsecas, podemos](xref:microsoft.quantum.libraries.standard.prelude)pensar em $X$ e, portanto, `X` como uma operação de inversão de marcha ou portão NÃO.</span><span class="sxs-lookup"><span data-stu-id="d114d-139">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="d114d-140">A `X` operação permite-nos preparar estados do formulário $\ket{s_0 s_1 \dots s_n}$ para uma corda clássica $s$:</span><span class="sxs-lookup"><span data-stu-id="d114d-140">The `X` operation lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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
        // Resetting the qubits will allow us to deallocate them properly.
        ResetAll(register);
    }
}
```

> [!TIP]
> <span data-ttu-id="d114d-141">Mais tarde, veremos formas mais compactas de escrever esta operação que não requerem controlo manual do fluxo.</span><span class="sxs-lookup"><span data-stu-id="d114d-141">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="d114d-142">Também podemos preparar estados como $\ket{+} = \left(\ket {0} + \ket {1} \ket \right) / \sqrt {2} $ e $\ket {-} = \left (\ket {0} - \ket {1} \right) / \sqrt {2} $ usando a transformação Hadamard $H$, que é representada em Q# pela operação intrínseca `H : (Qubit => Unit is Adj + Ctl)` :</span><span class="sxs-lookup"><span data-stu-id="d114d-142">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString, above.
    PrepareBitString(bitstring, register);
    // Next, we use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the state we want.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a><span data-ttu-id="d114d-143">Medições</span><span class="sxs-lookup"><span data-stu-id="d114d-143">Measurements</span></span>

<span data-ttu-id="d114d-144">Utilizando a `Measure` operação, que é uma operação não-unitária intrínseca incorporada, podemos extrair informação clássica de um objeto de tipo `Qubit` e atribuir um valor clássico como resultado, que tem um tipo `Result` reservado, indicando que o resultado já não é um estado quântico.</span><span class="sxs-lookup"><span data-stu-id="d114d-144">Using the `Measure` operation, which is a built-in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span>
<span data-ttu-id="d114d-145">A entrada `Measure` é um eixo Pauli na esfera Bloch, representado por um valor de tipo `Pauli` (por `PauliX` exemplo) e um valor de tipo `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="d114d-145">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by a value of type `Pauli` (for instance `PauliX`) and an value of type `Qubit`.</span></span>

<span data-ttu-id="d114d-146">Um exemplo simples é a seguinte operação, que atribui um qubit no estado $\ket {0} $, em seguida, aplica uma operação Hadamard `H` a ele e mede o resultado na `PauliZ` base.</span><span class="sxs-lookup"><span data-stu-id="d114d-146">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

<span data-ttu-id="d114d-147">Um exemplo um pouco mais complicado é dado pela seguinte operação, que devolve o valor Boolean `true` se todos os qubits num registo de tipo `Qubit[]` estiverem no estado zero quando medidos numa base Pauli especificada, e que retorna `false` de outra forma.</span><span class="sxs-lookup"><span data-stu-id="d114d-147">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

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

## <a name="borrowing-qubits-example"></a><span data-ttu-id="d114d-148">Exemplo de Qubits emprestado</span><span class="sxs-lookup"><span data-stu-id="d114d-148">Borrowing Qubits Example</span></span>

<span data-ttu-id="d114d-149">No cânone existem exemplos que usam a `borrowing` palavra-chave, por exemplo a função `MultiControlledXBorrow` definida abaixo.</span><span class="sxs-lookup"><span data-stu-id="d114d-149">In the canon there are examples that use the `borrowing` keyword, for instance the function `MultiControlledXBorrow` defined below.</span></span>
<span data-ttu-id="d114d-150">Se `controls` denotar os qubits de controlo que devem ser adicionados a uma `X` operação, então um total de `Length(controls)-2` muitas ancillas sujas serão adicionados por esta implementação.</span><span class="sxs-lookup"><span data-stu-id="d114d-150">If `controls` denotes the control qubits that should be added to an `X` operation, then an overall of `Length(controls)-2` many dirty ancillas will be added by this implementation.</span></span>

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

<span data-ttu-id="d114d-151">Note-se que o uso extensivo do `With` combinador--- na sua forma aplicável para operações que suportam adjacentes, ou seja, `WithA` ---foi feito neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="d114d-151">Note that extensive use of the `With` combinator---in its form that is applicable for operations that support adjoint, i.e., `WithA`---was made in this example.</span></span>
<span data-ttu-id="d114d-152">Este é um bom estilo de programação, porque adicionar controlo às estruturas que envolvem `With` o controlo de propagações apenas para o funcionamento interno.</span><span class="sxs-lookup"><span data-stu-id="d114d-152">This is good programming style, because adding control to structures involving `With` propagates control only to the inner operation.</span></span>
<span data-ttu-id="d114d-153">Além disso, note-se que aqui, para além `body` da operação, foi explicitamente fornecida uma implementação `controlled` do corpo da operação, em vez de recorrer a um `controlled auto` comunicado.</span><span class="sxs-lookup"><span data-stu-id="d114d-153">Further, note that here in addition to the `body` of the operation, an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span>
<span data-ttu-id="d114d-154">A razão para isso é que sabemos pela estrutura do circuito como adicionar facilmente mais controlos que são benéficos em comparação com a adição de controlo a cada portão individual do `body` .</span><span class="sxs-lookup"><span data-stu-id="d114d-154">The reason for this is that we know from the structure of the circuit how to easily add further controls which is beneficial compared to adding control to each and every individual gate in the `body`.</span></span> 

<span data-ttu-id="d114d-155">É instrutivo comparar este código com outra função canónica `MultiControlledXClean` que alcança o mesmo objetivo de implementar uma operação controlada por multi-animais, no `X` entanto, que utiliza vários qubits limpos usando o `using` mecanismo.</span><span class="sxs-lookup"><span data-stu-id="d114d-155">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="d114d-156">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="d114d-156">Next steps</span></span>

<span data-ttu-id="d114d-157">Saiba mais sobre [o Control Flow](xref:microsoft.quantum.guide.controlflow) em Q#.</span><span class="sxs-lookup"><span data-stu-id="d114d-157">Learn about [Control Flow](xref:microsoft.quantum.guide.controlflow) in Q#.</span></span>