---
title: Q# Introdução
description: 'Introdução rápida em programas quânticos em Q #'
author: beheim
ms.author: beheim
ms.date: 11/08/2020
ms.topic: article
uid: microsoft.quantum.guide.programs
ms.openlocfilehash: 975bcda5e0042406b465a83f17f1d2d3f5a1ec4f
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234319"
---
# <a name="q-quantum-programming-language"></a><span data-ttu-id="e1f9c-103">Q# Linguagem de Programação Quântica</span><span class="sxs-lookup"><span data-stu-id="e1f9c-103">Q# Quantum Programming Language</span></span>

<span data-ttu-id="e1f9c-104">Tudo o que precisa de saber sobre a linguagem de programação Q# é detalhado no [guia de idiomas Q#](xref:microsoft.quantum.qsharp.index).</span><span class="sxs-lookup"><span data-stu-id="e1f9c-104">Everything you need to know about the Q# programming language is detailed in the [Q# language guide](xref:microsoft.quantum.qsharp.index).</span></span> <span data-ttu-id="e1f9c-105">Como qualquer outra coisa, o nosso [processo de design de línguas](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) é de fonte aberta e congratulamo-nos com as contribuições.</span><span class="sxs-lookup"><span data-stu-id="e1f9c-105">Like anything else, our [language design process](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) is open source and we welcome contributions.</span></span>
<span data-ttu-id="e1f9c-106">Para mais informações sobre as fundações e motivação por trás de Q#, veja [por que precisamos de Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)</span><span class="sxs-lookup"><span data-stu-id="e1f9c-106">For more background about the foundations and motivation behind Q#, see [Why do we need Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>  
<span data-ttu-id="e1f9c-107">Q# é enviado como parte do Kit de Desenvolvimento Quântico (QDK) Para uma visão geral rápida, confira [O que é o QDK?](xref:microsoft.quantum.overview.q-sharp). .</span><span class="sxs-lookup"><span data-stu-id="e1f9c-107">Q# is shipped as part of the Quantum Development Kit (QDK) For a quick overview, check out [What is the QDK?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="e1f9c-108">O que é um programa quântico?</span><span class="sxs-lookup"><span data-stu-id="e1f9c-108">What is a quantum program?</span></span>

<span data-ttu-id="e1f9c-109">Um programa quântico pode ser visto como um conjunto particular de subrotinas clássicas que, quando chamados, realizam uma computação interagindo com um sistema quântico; um programa escrito em Q# não modela diretamente o estado quântico, mas descreve como um computador de controlo clássico interage com qubits.</span><span class="sxs-lookup"><span data-stu-id="e1f9c-109">A quantum program can be seen as a particular set of classical subroutines which, when called, perform a computation by interacting with a quantum system; a program written in Q# does not directly model the quantum state, but rather describes how a classical control computer interacts with qubits.</span></span>
<span data-ttu-id="e1f9c-110">Isto permite-nos ser totalmente agnósticos sobre o que *é* um estado quântico em cada máquina-alvo, que pode ter interpretações diferentes dependendo da máquina.</span><span class="sxs-lookup"><span data-stu-id="e1f9c-110">This allows us to be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="e1f9c-111">Uma consequência importante disso é que Q# não tem capacidade de introspeção no estado de um qubit ou outras propriedades da mecânica quântica diretamente, o que garante que um programa Q# pode ser executado fisicamente num computador quântico.</span><span class="sxs-lookup"><span data-stu-id="e1f9c-111">An important consequence of that is that Q# has no ability to introspect into the state of a qubit or other properties of quantum mechanics directly, which guarantees that a Q# program can be physically executed on a quantum computer.</span></span>
<span data-ttu-id="e1f9c-112">Em vez disso, um programa pode chamar operações como [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) extrair informações clássicas de um qubit.</span><span class="sxs-lookup"><span data-stu-id="e1f9c-112">Instead, a program can call operations such as [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) to extract classical information from a qubit.</span></span>

<span data-ttu-id="e1f9c-113">Uma vez atribuído, um qubit pode ser passado para operações e funções, também referidas como *callables*.</span><span class="sxs-lookup"><span data-stu-id="e1f9c-113">Once allocated, a qubit can be passed to operations and functions, also referred to as *callables*.</span></span> <span data-ttu-id="e1f9c-114">Em certo sentido, isto é tudo o que um programa Q# pode fazer com um qubit; Quaisquer ações diretas sobre o estado de um qubit são todas definidas por calcárias *intrínsecas,* tais como e - isto [`X`](xref:Microsoft.Quantum.Intrinsic.X) [`H`](xref:Microsoft.Quantum.Intrinsic.H) é, calíveis cujas implementações não são definidas dentro de Q# mas são definidas pela máquina-alvo.</span><span class="sxs-lookup"><span data-stu-id="e1f9c-114">In some sense, this is all that a Q# program can do with a qubit; Any direct actions on state of a qubit are all defined by *intrinsic* callables such as [`X`](xref:Microsoft.Quantum.Intrinsic.X) and [`H`](xref:Microsoft.Quantum.Intrinsic.H) - i.e. callables whose implementations are not defined within Q# but are instead defined by the target machine.</span></span> <span data-ttu-id="e1f9c-115">O que estas operações realmente *fazem* é apenas feito concreto pela máquina-alvo que usamos para executar o programa Q# específico.</span><span class="sxs-lookup"><span data-stu-id="e1f9c-115">What these operations actually *do* is only made concrete by the target machine we use to run the particular Q# program.</span></span>

<span data-ttu-id="e1f9c-116">Por exemplo, se executar o programa no nosso [simulador de estado completo,](xref:microsoft.quantum.machines.full-state-simulator)o simulador executa as operações matemáticas correspondentes ao sistema quântico simulado.</span><span class="sxs-lookup"><span data-stu-id="e1f9c-116">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator performs the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="e1f9c-117">Mas olhando para o futuro, quando a máquina-alvo é um verdadeiro computador quântico, chamar tais operações em Q# irá direcionar o computador quântico para realizar as operações *reais* correspondentes no sistema quântico *real* (por exemplo, pulsos laser precisamente cronometrado).</span><span class="sxs-lookup"><span data-stu-id="e1f9c-117">But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# will direct the quantum computer to perform the corresponding *real* operations on the *real* quantum system (e.g. precisely timed laser pulses).</span></span>

<span data-ttu-id="e1f9c-118">Um programa Q# recombina estas operações tal como definido por uma máquina-alvo para criar novas operações de alto nível para expressar a computação quântica.</span><span class="sxs-lookup"><span data-stu-id="e1f9c-118">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="e1f9c-119">Desta forma, q# torna fácil expressar a lógica subjacente a algoritmos quânticos e híbridos quânticos-clássicos, ao mesmo tempo que é geral no que diz respeito à estrutura de uma máquina-alvo ou simulador.</span><span class="sxs-lookup"><span data-stu-id="e1f9c-119">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

<span data-ttu-id="e1f9c-120">Um exemplo simples é o seguinte programa, que atribui um qubit no estado $\ket {0} $, em seguida, aplica uma operação Hadamard `H` ao mesmo e mede o resultado na `PauliZ` base.</span><span class="sxs-lookup"><span data-stu-id="e1f9c-120">A simple example is the following program, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

```qsharp
@EntryPoint()
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

<span data-ttu-id="e1f9c-121">Os [nossos Quantum Katas](https://github.com/microsoft/QuantumKatas#introduction) dão uma boa introdução em [Conceitos de Computação Quântica,](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) tais como operações quânticas comuns e como manipular qubits.</span><span class="sxs-lookup"><span data-stu-id="e1f9c-121">Our [Quantum Katas](https://github.com/microsoft/QuantumKatas#introduction) give a good introduction on [Quantum Computing Concepts](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) such as common quantum operations and how to manipulate qubits.</span></span> <span data-ttu-id="e1f9c-122">Mais exemplos também podem ser encontrados [em Operações e Funções Intrínsecas.](xref:microsoft.quantum.libraries.standard.prelude)</span><span class="sxs-lookup"><span data-stu-id="e1f9c-122">More examples can also be found in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude).</span></span>



