---
title: Trabalhando com qubits | Microsoft Docs
description: Trabalhando com qubits
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: d1a8ccc9423a9a04e12bc98e3783790232b2f5d8
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183476"
---
# <a name="working-with-qubits"></a><span data-ttu-id="5ff0c-103">Trabalhando com qubits</span><span class="sxs-lookup"><span data-stu-id="5ff0c-103">Working with Qubits</span></span> #

<span data-ttu-id="5ff0c-104">Agora que já vi uma variedade de diferentes partes da linguagem Q #, vamos nos aprofundar em tudo e ver como usar o qubits em si.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="5ff0c-105">Alocando qubits</span><span class="sxs-lookup"><span data-stu-id="5ff0c-105">Allocating Qubits</span></span> ##

<span data-ttu-id="5ff0c-106">Primeiro, para obter um qubit que possamos usar em Q #, *alocamos* qubits em um bloco de `using`:</span><span class="sxs-lookup"><span data-stu-id="5ff0c-106">First, to obtain a qubit that we can use in Q#, we *allocate* qubits within a `using` block:</span></span>

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

<span data-ttu-id="5ff0c-107">Qualquer qubits alocado dessa maneira começa no $ \ket{0}$ State; no exemplo acima, `register` é, portanto, no estado $ \ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-107">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="5ff0c-108">No final do bloco de `using`, qualquer qubits alocada por esse bloco será imediatamente desalocada e não poderá mais ser usada.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-108">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="5ff0c-109">Os computadores de destino esperam que qubits estejam no $ \ket{0}$ State imediatamente antes da desalocação, para que possam ser reutilizados e oferecidos a outros blocos de `using` para alocação.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-109">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="5ff0c-110">Sempre que possível, use operações de unitário para retornar qualquer qubits alocado para $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-110">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="5ff0c-111">Se necessário, a operação de @"microsoft.quantum.intrinsic.reset" pode ser usada para medir um qubit em vez disso e usar esse resultado de medida para garantir que o qubit medido seja retornado para $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-111">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="5ff0c-112">Essa medida destruirá qualquer Entanglement com a qubits restante e, portanto, poderá afetar a computação.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-112">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span> 

## <a name="intrinsic-operations"></a><span data-ttu-id="5ff0c-113">Operações intrínsecas</span><span class="sxs-lookup"><span data-stu-id="5ff0c-113">Intrinsic Operations</span></span> ##

<span data-ttu-id="5ff0c-114">Uma vez alocada, um qubit pode ser passado para funções e operações.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-114">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="5ff0c-115">De certa forma, isso é tudo o que um programa Q # pode fazer com um qubit, pois as ações que podem ser executadas são todas definidas como operações.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-115">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="5ff0c-116">Veremos essas operações com mais detalhes em [operações intrínsecas e funções](xref:microsoft.quantum.libraries.standard.prelude), mas, por enquanto, mencionamos algumas operações úteis que podem ser usadas para interagir com o qubits.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-116">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="5ff0c-117">Primeiro, os operadores de Pauli qubit $X $, $Y $ e $Z $ são representados em Q # pelas operações intrínsecas `X`, `Y`e `Z`, cada uma delas com o tipo `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-117">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="5ff0c-118">Conforme descrito em [operações e funções intrínsecas](xref:microsoft.quantum.libraries.standard.prelude), podemos considerar $X $ e, portanto, `X` como uma operação de inversão de bits ou não de porta.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-118">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="5ff0c-119">Isso nos permite preparar Estados do formulário $ \ket{s_0 s_1 \dots s_n} $ para algumas cadeias de caracteres de bits clássicas $s $:</span><span class="sxs-lookup"><span data-stu-id="5ff0c-119">This lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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

operation Example() : Unit {

    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
    }
}
```

> [!TIP]
> <span data-ttu-id="5ff0c-120">Mais tarde, veremos mais formas compactadas de gravar essa operação que não exigem controle de fluxo manual.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-120">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="5ff0c-121">Também podemos preparar Estados como $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ e $ \ket{-} = \left (\ket{0}-\ket{1}\right)/\sqrt{2}$ usando a transformação Hadamard $H $ , que é representado em Q # pela operação intrínseca `H : (Qubit => Unit is Adj + Ctl)`:</span><span class="sxs-lookup"><span data-stu-id="5ff0c-121">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

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

## <a name="measurements"></a><span data-ttu-id="5ff0c-122">Medições</span><span class="sxs-lookup"><span data-stu-id="5ff0c-122">Measurements</span></span> ##

<span data-ttu-id="5ff0c-123">Usando a operação `Measure`, que é uma operação não-unitário intrínseca interna, podemos extrair informações clássicas de um objeto do tipo `Qubit` e atribuir um valor clássico como resultado, que tem um tipo reservado `Result`, indicando que o resultado é não mais um estado Quantum.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-123">Using the `Measure` operation, which is a built in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span> <span data-ttu-id="5ff0c-124">A entrada para `Measure` é um eixo Pauli na esfera Bloch, representado por um objeto do tipo `Pauli` (ou seja, por instância `PauliX`) e um objeto do tipo `Qubit`.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-124">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by an object of type `Pauli` (i.e., for instance `PauliX`) and an object of type `Qubit`.</span></span> 

<span data-ttu-id="5ff0c-125">Um exemplo simples é a operação a seguir, que cria um qubit no estado $ \ket{0}$ e, em seguida, aplica um portão Hadamard ``H`` a ele e, em seguida, mede o resultado na base `PauliZ`.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-125">A simple example is the following operation which creates one qubit in the $\ket{0}$ state, then applies a Hadamard gate ``H`` to it and then measures the result in the `PauliZ` basis.</span></span> 

```qsharp
operation MeasurementOneQubit () : Result {

    // The following using block creates a fresh qubit and initializes it 
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby creating the 
        // state 1/sqrt(2)(|0〉+|1〉). 
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

<span data-ttu-id="5ff0c-126">Um exemplo um pouco mais complicado é dado pela seguinte operação que retorna o valor booliano `true` se todos os qubits em um registro do tipo `Qubit[]` estiverem no estado zero, quando medido em uma base de Pauli especificada e `false` caso contrário.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-126">A slightly more complicated example is given by the following operation which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero, when measured in a specified Pauli basis and `false` otherwise.</span></span> 

```qsharp
operation AllMeasurementsZero (qs : Qubit[], pauli : Pauli) : Bool {

    mutable value = true;
    for (q in qs) {
        if ( Measure([pauli], [q]) == One ) {
            set value = false;
        }
    }
    return value;
}
```

<span data-ttu-id="5ff0c-127">A linguagem Q # permite dependências do fluxo de controle clássico nos resultados da medição de qubits.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-127">The Q# language allows dependencies of classical control flow on measurement results of qubits.</span></span> <span data-ttu-id="5ff0c-128">Isso, por sua vez, permite implementar gadgets probabilística poderosos que podem reduzir o custo computacional para a implementação de unidades.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-128">This in turn enables to implement powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span> <span data-ttu-id="5ff0c-129">Por exemplo, é fácil implementar de forma que seja chamado de *repetir-até-êxito* em Q #, que são probabilística circuitos que têm um baixo custo *esperado* em termos de Gates elementares, mas para os quais o custo real depende de uma execução e de um real intercalação de várias ramificações possíveis.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-129">As an example, it is easy to implement so-called *Repeat-Until-Success* in Q# which are probabilistic circuits that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span> 

<span data-ttu-id="5ff0c-130">Para facilitar os padrões do RUS (repetição até o êxito), o Q # dá suporte à construção</span><span class="sxs-lookup"><span data-stu-id="5ff0c-130">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the construct</span></span>
```qsharp
repeat {
    statementBlock1 
}
until (expression)
fixup {
    statementBlock2
}
```
<span data-ttu-id="5ff0c-131">onde `statementBlock1` e `statementBlock2` são zero ou mais instruções Q # e `expression` qualquer expressão válida que seja avaliada como um valor do tipo `Bool`.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-131">where `statementBlock1` and `statementBlock2` are zero or more Q# statements, and `expression` any valid expression that evaluates to a value of type `Bool`.</span></span> <span data-ttu-id="5ff0c-132">Em um caso de uso típico, o circuito a seguir implementa uma rotação em um eixo irracional de $ (I + 2i Z)/\sqrt{5}$ na esfera de Bloch.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-132">In a typical use case, the following circuit implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="5ff0c-133">Isso é feito usando um padrão de RUS conhecido:</span><span class="sxs-lookup"><span data-stu-id="5ff0c-133">This is accomplished by using a known RUS pattern:</span></span> 

```qsharp
operation RUScircuit (qubit : Qubit) : Unit {

    using(ancillas = Qubit[2]) {
        ApplyToEachA(H, ancillas);
        mutable finished = false;
        repeat {
            Controlled X(ancillas, qubit);
            S(qubit);
            Controlled X(ancillas, qubit);
            Z(qubit);
        }
        until(finished)
        fixup {
            if AllMeasurementsZero(ancillas, Xpauli) {
                set finished = true;
            }
        }
    }
}
```

<span data-ttu-id="5ff0c-134">Este exemplo mostra o uso de uma variável mutável `finished` que está no escopo de todo o loop Repeat-Until-recorretion e que é inicializado antes do loop e atualizado na etapa de correção.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-134">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

<span data-ttu-id="5ff0c-135">Por fim, mostramos um exemplo de um padrão RUS para preparar um estado Quantum $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\ket{0}+ \ket{1}\right) $, começando com o estado $ \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-135">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span> <span data-ttu-id="5ff0c-136">Consulte também o [exemplo de teste de unidade fornecido com a biblioteca padrão](https://github.com/Microsoft/Quantum/blob/master/Samples/src/UnitTesting/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="5ff0c-136">See also the [unit testing sample provided with the standard library](https://github.com/Microsoft/Quantum/blob/master/Samples/src/UnitTesting/RepeatUntilSuccessCircuits.qs):</span></span> 

```qsharp
operation RepeatUntilSuccessStatePreparation( target : Qubit ) : Unit {

    using( ancilla = Qubit() ) {
        H(ancilla);
        repeat {
            // We expect target and ancilla qubit to be in |+⟩ state.
            AssertProb( 
                [PauliX], [target], Zero, 1.0, 
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb( 
                [PauliX], [ancilla], Zero, 1.0,
                "ancilla qubit should be in the |+⟩ state", 1e-10 );
                
            Adjoint T(ancilla);
            CNOT(target, ancilla);
            T(ancilla);

            // The probability of measuring |+⟩ state on ancilla is 3/4.
            AssertProb( 
                [PauliX], [ancilla], Zero, 3. / 4., 
                "Error: the probability to measure |+⟩ in the first 
                ancilla must be 3/4",
                1e-10);

            // If we get measurement outcome Zero, we prepare the required state 
            let outcome = Measure([PauliX], [ancilla]);
        }
        until( outcome == Zero )
        fixup {
            // Bring ancilla and target back to |+⟩ state
            if( outcome == One ) {
                Z(ancilla);
                X(target);
                H(target);
            }
        }
        // Return ancilla back to Zero state
        H(ancilla);
    }
}
```
 
<span data-ttu-id="5ff0c-137">Os recursos programáticos notáveis mostrados nesta operação são uma parte `fixup` mais complexa do loop, que envolve operações de Quantum e o uso de instruções `AssertProb` para determinar a probabilidade de medir o estado Quantum em determinados pontos especificados no Program.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-137">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span> <span data-ttu-id="5ff0c-138">Consulte também [testando e Depurando](xref:microsoft.quantum.techniques.testing-and-debugging) para obter mais informações sobre instruções `Assert` e `AssertProb`.</span><span class="sxs-lookup"><span data-stu-id="5ff0c-138">See also [Testing and debugging](xref:microsoft.quantum.techniques.testing-and-debugging) for more information about `Assert` and `AssertProb` statements.</span></span> 
