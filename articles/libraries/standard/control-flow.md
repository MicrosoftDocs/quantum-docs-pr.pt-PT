---
title: Q# bibliotecas padrão - controlo e fluxo / Microsoft Docs
description: Q# bibliotecas padrão - controlo e fluxo
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: ff73cef12a3b8c2a6559308dc244c7c2e865ba9f
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820458"
---
# <a name="higher-order-control-flow"></a><span data-ttu-id="74236-103">Fluxo de controlo de ordem superior</span><span class="sxs-lookup"><span data-stu-id="74236-103">Higher-Order Control Flow</span></span> #

<span data-ttu-id="74236-104">Um dos principais papéis da biblioteca padrão é facilitar a expressão de ideias algorítmicas de alto nível como [programas quânticos.](https://en.wikipedia.org/wiki/Quantum_programming)</span><span class="sxs-lookup"><span data-stu-id="74236-104">One of the primary roles of the standard library is to make it easier to express high-level algorithmic ideas as [quantum programs](https://en.wikipedia.org/wiki/Quantum_programming).</span></span>
<span data-ttu-id="74236-105">Assim, o cânone Q# fornece uma variedade de diferentes construções de controlo de fluxo, cada uma implementada usando aplicação parcial de funções e operações.</span><span class="sxs-lookup"><span data-stu-id="74236-105">Thus, the Q# canon provides a variety of different flow control constructs, each implemented using partial application of functions and operations.</span></span>
<span data-ttu-id="74236-106">Saltando imediatamente para um exemplo, considere o caso em que se quer construir uma "escada CNOT" num registo:</span><span class="sxs-lookup"><span data-stu-id="74236-106">Jumping immediately into an example, consider the case in which one wants to construct a "CNOT ladder" on a register:</span></span>

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

<span data-ttu-id="74236-107">Podemos expressar este padrão usando iteração e `for` loops:</span><span class="sxs-lookup"><span data-stu-id="74236-107">We can express this pattern by using iteration and `for` loops:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

<span data-ttu-id="74236-108">Expresso em termos de <xref:microsoft.quantum.canon.applytoeachca> e de manipulação de matriz, tais como <xref:microsoft.quantum.arrays.zip>, no entanto, isto é muito mais curto e fácil de ler:</span><span class="sxs-lookup"><span data-stu-id="74236-108">Expressed in terms of <xref:microsoft.quantum.canon.applytoeachca> and array manipulation functions such as <xref:microsoft.quantum.arrays.zip>, however, this is much shorter and easier to read:</span></span>

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

<span data-ttu-id="74236-109">No resto desta secção, forneceremos uma série de exemplos de como usar as várias operações e funções de controlo de fluxo fornecidas pelo cânon para expressar compactamente programas quânticos.</span><span class="sxs-lookup"><span data-stu-id="74236-109">In the rest of this section, we will provide a number of examples of how to use the various flow control operations and functions provided by the canon to compactly express quantum programs.</span></span>

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a><span data-ttu-id="74236-110">Aplicação de operações e funções sobre matrizes e gamas</span><span class="sxs-lookup"><span data-stu-id="74236-110">Applying Operations and Functions over Arrays and Ranges</span></span> ##

<span data-ttu-id="74236-111">Uma das abstrações primárias fornecidas pelo cânone é a da iteração.</span><span class="sxs-lookup"><span data-stu-id="74236-111">One of the primary abstractions provided by the canon is that of iteration.</span></span>
<span data-ttu-id="74236-112">Por exemplo, considere um unitário do formulário $U \otimes U \otimes \cdots \otimes U$ para um único qubit unitary $U$.</span><span class="sxs-lookup"><span data-stu-id="74236-112">For instance, consider a unitary of the form $U \otimes U \otimes \cdots \otimes U$ for a single-qubit unitary $U$.</span></span>
<span data-ttu-id="74236-113">Em Q#, podemos usar <xref:microsoft.quantum.arrays.indexrange> para representar isto como um ciclo `for` sobre um registo:</span><span class="sxs-lookup"><span data-stu-id="74236-113">In Q#, we might use <xref:microsoft.quantum.arrays.indexrange> to represent this as as a `for` loop over a register:</span></span>

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation ApplyHadamardToAll(
    register : Qubit[])
: Unit is Adj + Ctl {
    for (qubit in register) {
        H(qubit);
    }
}
```

<span data-ttu-id="74236-114">Podemos então usar esta nova operação como `HAll(register)` para aplicar $H \otimes H \otimes \cdots \otimes H$.</span><span class="sxs-lookup"><span data-stu-id="74236-114">We can then use this new operation as `HAll(register)` to apply $H \otimes H \otimes \cdots \otimes H$.</span></span>

<span data-ttu-id="74236-115">Isto é complicado de fazer, no entanto, especialmente num algoritmo maior.</span><span class="sxs-lookup"><span data-stu-id="74236-115">This is cumbersome to do, however, especially in a larger algorithm.</span></span>
<span data-ttu-id="74236-116">Além disso, esta abordagem é especializada na operação específica que pretendemos aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="74236-116">Moreover, this approach is specialized to the particular operation that we wish to apply to each qubit.</span></span>
<span data-ttu-id="74236-117">Podemos usar o facto de que as operações são de primeira classe para expressar este conceito algorítmico de forma mais explícita:</span><span class="sxs-lookup"><span data-stu-id="74236-117">We can use the fact that operations are first-class to express this algorithmic concept more explicitly:</span></span>

```qsharp
ApplyToEachCA(H, register);
```

<span data-ttu-id="74236-118">Aqui, o sufixo `CA` indica que a chamada para `ApplyToEach` é em si mesma adjointable e controlável.</span><span class="sxs-lookup"><span data-stu-id="74236-118">Here, the suffix `CA` indicates that the call to `ApplyToEach` is itself adjointable and controllable.</span></span>
<span data-ttu-id="74236-119">Assim, se `U` apoia `Adjoint` e `Controlled`, as seguintes linhas são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="74236-119">Thus, if `U` supports `Adjoint` and `Controlled`, the following lines are equivalent:</span></span>

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

<span data-ttu-id="74236-120">Isto significa, em particular, que as chamadas para `ApplyToEachCA` podem aparecer em operações para as quais uma especialização adjoint é gerada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="74236-120">In particular, this means that calls to `ApplyToEachCA` can appear in operations for which an adjoint specialization is auto-generated.</span></span>
<span data-ttu-id="74236-121">Da mesma forma, <xref:microsoft.quantum.canon.applytoeachindex> é útil para representar padrões do formulário `U(0, targets[0]); U(1, targets[1]); ...`, e oferece versões para cada combinação de functores suportados pela sua entrada.</span><span class="sxs-lookup"><span data-stu-id="74236-121">Similarly, <xref:microsoft.quantum.canon.applytoeachindex> is useful for representing patterns of the form `U(0, targets[0]); U(1, targets[1]); ...`, and offers versions for each combination of functors supported by its input.</span></span>

> [!TIP]
> <span data-ttu-id="74236-122">`ApplyToEach` é parâmetro de tipo de modo a que possa ser utilizado com operações que tomem inputs que não sejam `Qubit`.</span><span class="sxs-lookup"><span data-stu-id="74236-122">`ApplyToEach` is type-parameterized such that it can be used with operations that take inputs other than `Qubit`.</span></span>
> <span data-ttu-id="74236-123">Por exemplo, suponha que `codeBlocks` é uma série de valores <xref:microsoft.quantum.errorcorrection.logicalregister> que precisam de ser recuperados.</span><span class="sxs-lookup"><span data-stu-id="74236-123">For example, suppose that `codeBlocks` is an array of <xref:microsoft.quantum.errorcorrection.logicalregister> values that need to be recovered.</span></span>
> <span data-ttu-id="74236-124">Em seguida, `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` aplicará o código de correção de erros `code` e função de recuperação `recoveryFn` a cada bloco de forma independente.</span><span class="sxs-lookup"><span data-stu-id="74236-124">Then `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` will apply the error-correcting code `code` and recovery function `recoveryFn` to each block independently.</span></span>
> <span data-ttu-id="74236-125">Isto mantém-se mesmo para entradas clássicas: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` aplicará uma rotação de $\pi / 2$ cerca de $X$ seguido de uma rotação de $pi / 3$ cerca de $Y$.</span><span class="sxs-lookup"><span data-stu-id="74236-125">This holds even for classical inputs: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` will apply a rotation of $\pi / 2$ about $X$ followed by a rotation of $pi / 3$ about $Y$.</span></span>

<span data-ttu-id="74236-126">O cânon Q# também fornece suporte para padrões de enumeração clássica familiares à programação funcional.</span><span class="sxs-lookup"><span data-stu-id="74236-126">The Q# canon also provides support for classical enumeration patterns familiar to functional programming.</span></span>
<span data-ttu-id="74236-127">Por exemplo, <xref:microsoft.quantum.arrays.fold> implementa o padrão $f (f(f(s\_{\text{initial}}, x\_0), x\_1), \pontos)$ para reduzir uma função sobre uma lista.</span><span class="sxs-lookup"><span data-stu-id="74236-127">For instance, <xref:microsoft.quantum.arrays.fold> implements the pattern $f(f(f(s\_{\text{initial}}, x\_0), x\_1), \dots)$ for reducing a function over a list.</span></span>
<span data-ttu-id="74236-128">Este padrão pode ser utilizado para implementar somas, produtos, minima, maxima e outras funções:</span><span class="sxs-lookup"><span data-stu-id="74236-128">This pattern can be used to implement sums, products, minima, maxima and other such functions:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

<span data-ttu-id="74236-129">Da mesma forma, funções como <xref:microsoft.quantum.arrays.mapped> e <xref:microsoft.quantum.arrays.mappedbyindex> podem ser usadas para expressar conceitos de programação funcional em Q#.</span><span class="sxs-lookup"><span data-stu-id="74236-129">Similarly, functions like <xref:microsoft.quantum.arrays.mapped> and <xref:microsoft.quantum.arrays.mappedbyindex> can be used to express functional programming concepts in Q#.</span></span>

## <a name="composing-operations-and-functions"></a><span data-ttu-id="74236-130">Compor operações e funções</span><span class="sxs-lookup"><span data-stu-id="74236-130">Composing Operations and Functions</span></span> ##

<span data-ttu-id="74236-131">As construções de fluxo de controlo oferecidas pelo cânon tomam as operações e funções como suas inputs, de modo a que seja útil ser capaz de compor várias operações ou funções numa única chamada.</span><span class="sxs-lookup"><span data-stu-id="74236-131">The control flow constructs offered by the canon take operations and functions as their inputs, such that it is helpful to be able to compose several operations or functions into a single callable.</span></span>
<span data-ttu-id="74236-132">Por exemplo, o padrão $UVU^{\dagger}$ é extremamente comum na programação quântica, de tal forma que o cânã fornece a operação <xref:microsoft.quantum.canon.applywith> como uma abstração para este padrão.</span><span class="sxs-lookup"><span data-stu-id="74236-132">For instance, the pattern $UVU^{\dagger}$ is extremely common in quantum programming, such that the canon provides the operation <xref:microsoft.quantum.canon.applywith> as an abstraction for this pattern.</span></span>
<span data-ttu-id="74236-133">Esta abstração também permite uma complição mais eficiente em circuitos, uma vez que `Controlled` atuando na sequência `U(qubit); V(qubit); Adjoint U(qubit);` não precisa de agir em cada `U`.</span><span class="sxs-lookup"><span data-stu-id="74236-133">This abstraction also allows for more efficient compliation into circuits, as `Controlled` acting on the sequence `U(qubit); V(qubit); Adjoint U(qubit);` does not need to act on each `U`.</span></span>
<span data-ttu-id="74236-134">Para ver isto, que $c(U)$ seja o unitário que representa `Controlled U([control], target)` e deixe que $c(V)$ seja definido da mesma forma.</span><span class="sxs-lookup"><span data-stu-id="74236-134">To see this, let $c(U)$ be the unitary representing `Controlled U([control], target)` and let $c(V)$ be defined in the same way.</span></span>
<span data-ttu-id="74236-135">Em seguida, para um estado arbitrário $\ket {\psi}$, \start{align} c(U) c(V) c(U)^\dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU^{\dagger} \ket{\psi}) \\\\ & =(\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{1} \otimes \otimes \otimes</span><span class="sxs-lookup"><span data-stu-id="74236-135">Then for an arbitrary state $\ket{\psi}$, \begin{align} c(U) c(V) c(U)^\dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU^{\dagger} \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{1} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="74236-136">\fim{alinhar} pela definição de `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="74236-136">\end{align} by the definition of `Controlled`.</span></span>
<span data-ttu-id="74236-137">Por outro lado, \begin{align} c(U) c(V) c(U)^dagger \ket{0} \otimes \ket {\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU^\dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{0} \otimes \ket {\psi}.</span><span class="sxs-lookup"><span data-stu-id="74236-137">On the other hand, \begin{align} c(U) c(V) c(U)^\dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU^\dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{0} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="74236-138">\end{align} Por linearidade, podemos concluir que podemos considerar $U$ desta forma para todos os estados de entrada.</span><span class="sxs-lookup"><span data-stu-id="74236-138">\end{align} By linearity, we can conclude that we can factor $U$ out in this way for all input states.</span></span>
<span data-ttu-id="74236-139">Ou seja, $c (UVU^\dagger) = U c(V) U^\dagger$.</span><span class="sxs-lookup"><span data-stu-id="74236-139">That is, $c(UVU^\dagger) = U c(V) U^\dagger$.</span></span>
<span data-ttu-id="74236-140">Uma vez que o controlo das operações pode ser dispendioso em geral, a utilização de variantes controladas como `WithC` e `WithCA` pode ajudar a reduzir o número de functores de controlo que precisam de ser aplicados.</span><span class="sxs-lookup"><span data-stu-id="74236-140">Since controlling operations can be expensive in general, using controlled variants such as `WithC` and `WithCA` can help reduce the number of control functors that need to be applied.</span></span>

> [!NOTE]
> <span data-ttu-id="74236-141">Uma outra consequência de ter $U$ é que nem sequer precisamos de saber como aplicar o functor `Controlled` para `U`.</span><span class="sxs-lookup"><span data-stu-id="74236-141">One other consequence of factoring out $U$ is that we need not even know how to apply the `Controlled` functor to `U`.</span></span>
> <span data-ttu-id="74236-142">`ApplyWithCA`, portanto, tem uma assinatura mais fraca do que seria de esperar:</span><span class="sxs-lookup"><span data-stu-id="74236-142">`ApplyWithCA` therefore has a weaker signature than might be expected:</span></span>
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

<span data-ttu-id="74236-143">Da mesma forma, <xref:microsoft.quantum.canon.bound> produz operações que aplicam uma sequência de outras operações por sua vez.</span><span class="sxs-lookup"><span data-stu-id="74236-143">Similarly, <xref:microsoft.quantum.canon.bound> produces operations which apply a sequence of other operations in turn.</span></span>
<span data-ttu-id="74236-144">Por exemplo, os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="74236-144">For instance, the following are equivalent:</span></span>

```qsharp
H(qubit); X(qubit);
Bound([H, X], qubit);
```

<span data-ttu-id="74236-145">Combinar com padrões de iteração pode tornar isto especialmente útil:</span><span class="sxs-lookup"><span data-stu-id="74236-145">Combining with iteration patterns can make this especially useful:</span></span>

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bound([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a><span data-ttu-id="74236-146">Composição ordenada pelo tempo</span><span class="sxs-lookup"><span data-stu-id="74236-146">Time-Ordered Composition</span></span> ###

<span data-ttu-id="74236-147">Podemos ir ainda mais longe pensando no controlo de fluxos em termos de aplicação parcial e funções clássicas, e podemos modelar conceitos quânticos até bastante sofisticados em termos de controlo de fluxoclássico.</span><span class="sxs-lookup"><span data-stu-id="74236-147">We can go still further by thinking of flow control in terms of partial application and classical functions, and can model even fairly sophisticated quantum concepts in terms of classical flow control.</span></span>
<span data-ttu-id="74236-148">Esta analogia é feita precisamente pelo reconhecimento de que os operadores unitários correspondem exatamente aos efeitos secundários das operações de chamada, de modo a que qualquer decomposição dos operadores unitários em termos de outros operadores unitários corresponda à construção de um determinado a sequência de chamadas para subrotinas clássicas que emitem instruções para agir como operadores unitários específicos.</span><span class="sxs-lookup"><span data-stu-id="74236-148">This analogy is made precise by the recognition that unitary operators correspond exactly to the side effects of calling operations, such that any decomposition of unitary operators in terms of other unitary operators corresponds to constructing a particular calling sequence for classical subroutines which emit instructions to act as particular unitary operators.</span></span>
<span data-ttu-id="74236-149">Nesta perspetiva, `Bound` é precisamente a representação do produto matricial, uma vez que `Bound([A, B])(target)` equivale a `A(target); B(target);`, que por sua vez é a sequência de chamadas correspondente a $BA$.</span><span class="sxs-lookup"><span data-stu-id="74236-149">Under this view, `Bound` is precisely the representation of the matrix product, since `Bound([A, B])(target)` is equivalent to `A(target); B(target);`, which in turn is the calling sequence corresponding to $BA$.</span></span>

<span data-ttu-id="74236-150">Um exemplo mais sofisticado é a [expansão Trotter-Suzuki.](https://arxiv.org/abs/math-ph/0506007v1)</span><span class="sxs-lookup"><span data-stu-id="74236-150">A more sophisticated example is the [Trotter–Suzuki expansion](https://arxiv.org/abs/math-ph/0506007v1).</span></span>
<span data-ttu-id="74236-151">Conforme discutido na secção dinâmica de representação do gerador das estruturas de [dados,](xref:microsoft.quantum.libraries.data-structures)a expansão Trotter-Suzuki fornece uma forma particularmente útil de expressar exponenciais matriciais.</span><span class="sxs-lookup"><span data-stu-id="74236-151">As discussed in the Dynamical Generator Representation section of [data structures](xref:microsoft.quantum.libraries.data-structures), the Trotter–Suzuki expansion provides a particularly useful way of expressing matrix exponentials.</span></span>
<span data-ttu-id="74236-152">Por exemplo, aplicar a expansão à sua ordem mais baixa rende que para quaisquer operadores $A$ e $B$ de tal forma que $A = A^\dagger$ e $B = B^\dagger$, \begin{align} \tag{★} \label{eq:trotter-suzuki-0} \exp (i [A + B] t) = \lim_{n\to\infty} \left(\exp(i A/ n) \exp(i B t / n)\right^n.</span><span class="sxs-lookup"><span data-stu-id="74236-152">For instance, applying the expansion at its lowest order yields that for any operators $A$ and $B$ such that $A = A^\dagger$ and $B = B^\dagger$, \begin{align} \tag{★} \label{eq:trotter-suzuki-0} \exp(i [A + B] t) = \lim_{n\to\infty} \left(\exp(i A t / n) \exp(i B t / n)\right)^n.</span></span>
<span data-ttu-id="74236-153">\end{align} Colloquially, isto diz que podemos evoluir aproximadamente um estado sob $A + B$ evoluindo alternadamente sob $A$ e $B$ apenas.</span><span class="sxs-lookup"><span data-stu-id="74236-153">\end{align} Colloquially, this says that we can approximately evolve a state under $A + B$ by alternately evolving under $A$ and $B$ alone.</span></span>
<span data-ttu-id="74236-154">Se representarmos a evolução sob $A$ por uma operação `A : (Double, Qubit[]) => Unit` que se aplica $e^{i a}$, então a representação da expansão Trotter-Suzuki em termos de reorganização de sequências de chamadas torna-se clara.</span><span class="sxs-lookup"><span data-stu-id="74236-154">If we represent evolution under $A$ by an operation `A : (Double, Qubit[]) => Unit` that applies $e^{i t A}$, then the representation of the Trotter–Suzuki expansion in terms of rearranging calling sequences becomes clear.</span></span>
<span data-ttu-id="74236-155">Concretamente, dada uma operação `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` tal que `A = U(0, _, _)` e `B = U(1, _, _)`, podemos definir uma nova operação que represente a integral da `U` no momento $t$ gerando sequências da forma</span><span class="sxs-lookup"><span data-stu-id="74236-155">Concretely, given an operation `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` such that `A = U(0, _, _)` and `B = U(1, _, _)`, we can define a new operation representing the integral of `U` at time $t$ by generating sequences of the form</span></span>

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

<span data-ttu-id="74236-156">Neste momento, podemos agora raciocinar sobre a expansão Trotter-Suzuki *sem qualquer referência à mecânica quântica.*</span><span class="sxs-lookup"><span data-stu-id="74236-156">At this point, we can now reason about the Trotter–Suzuki expansion *without reference to quantum mechanics at all*.</span></span>
<span data-ttu-id="74236-157">A expansão é efetivamente um padrão de iteração muito particular motivado por $\eqref{eq:trotter-suzuki-0}$.</span><span class="sxs-lookup"><span data-stu-id="74236-157">The expansion is effectively a very particular iteration pattern motivated by $\eqref{eq:trotter-suzuki-0}$.</span></span>
<span data-ttu-id="74236-158">Este padrão de iteração é implementado por <xref:microsoft.quantum.canon.decomposeintotimestepsca>:</span><span class="sxs-lookup"><span data-stu-id="74236-158">This iteration pattern is implemented by <xref:microsoft.quantum.canon.decomposeintotimestepsca>:</span></span>

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

<span data-ttu-id="74236-159">A assinatura de `DecomposeIntoTimeStepsCA` segue um padrão comum em Q#, onde coleções que podem ser apoiadas quer por matrizes, quer por algo que computa elementos na mosca são representados por tuples cujos primeiros elementos são `Int` valores indicando os seus comprimentos.</span><span class="sxs-lookup"><span data-stu-id="74236-159">The signature of `DecomposeIntoTimeStepsCA` follows a common pattern in Q#, where collections that may be backed either by arrays or by something which compute elements on the fly are represented by tuples whose first elements are `Int` values indicating their lengths.</span></span>

## <a name="putting-it-together-controlling-operations"></a><span data-ttu-id="74236-160">Reunindo-o: Operações de Controlo</span><span class="sxs-lookup"><span data-stu-id="74236-160">Putting it Together: Controlling Operations</span></span> ##

<span data-ttu-id="74236-161">Finalmente, o cânon baseia-se no functor `Controlled`, fornecendo formas adicionais de condicionar as operações quânticas.</span><span class="sxs-lookup"><span data-stu-id="74236-161">Finally, the canon builds on the `Controlled` functor by providing additional ways to condition quantum operations.</span></span>
<span data-ttu-id="74236-162">É comum, especialmente na aritmética quântica, condicionar operações em estados computacionais que não $\ket{0\cdots 0}$.</span><span class="sxs-lookup"><span data-stu-id="74236-162">It is common, especially in quantum arithmetic, to condition operations on computational basis states other than $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="74236-163">Utilizando as operações de controlo e as funções acima introduzidas, podemos condições quânticas mais gerais numa única declaração.</span><span class="sxs-lookup"><span data-stu-id="74236-163">Using the control operations and functions introduced above, we can more general quantum conditions in a single statement.</span></span>
<span data-ttu-id="74236-164">Vamos saltar para a forma como <xref:microsoft.quantum.canon.controlledonbitstring> faz (parâmetros do tipo sans), então vamos quebrar as peças um a um.</span><span class="sxs-lookup"><span data-stu-id="74236-164">Let's jump in to how <xref:microsoft.quantum.canon.controlledonbitstring> does it (sans type parameters), then we'll break down the pieces one by one.</span></span>
<span data-ttu-id="74236-165">A primeira coisa que temos de fazer é definir uma operação que realmente faz o pesado levantamento da implementação do controlo em estados computacionais arbitrários.</span><span class="sxs-lookup"><span data-stu-id="74236-165">The first thing we'll need to do is to define an operation which actually does the heavy lifting of implementing the control on arbitrary computational basis states.</span></span>
<span data-ttu-id="74236-166">No entanto, não chamaremos esta operação diretamente, e por isso adicionamos `_` ao início do nome para indicar que é uma implementação de outra construção noutro lugar.</span><span class="sxs-lookup"><span data-stu-id="74236-166">We won't call this operation directly, however, and so we add `_` to the beginning of the name to indicate that it's an implementation of another construct elsewhere.</span></span>

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

<span data-ttu-id="74236-167">Note que tomamos uma série de bits, representados como uma matriz de `Bool`, que usamos para especificar o condicionamento que queremos aplicar à operação `oracle` que nos é dado.</span><span class="sxs-lookup"><span data-stu-id="74236-167">Note that we take a string of bits, represented as a `Bool` array, that we use to specify the conditioning that we want to apply to the operation `oracle` that we are given.</span></span>
<span data-ttu-id="74236-168">Uma vez que esta operação efetivamente faz a aplicação diretamente, precisamos também de assumir os registos de controlo e de alvo, ambos aqui representados como `Qubit[]`.</span><span class="sxs-lookup"><span data-stu-id="74236-168">Since this operation actually does the application directly, we also need to take the control and target registers, both represented here as `Qubit[]`.</span></span>

<span data-ttu-id="74236-169">Em seguida, notamos que o controlo na base computacional estado $\ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n - 1}}} para um pouco de cadeia $\vec{s}$ pode ser realizado transformando $\ket{{{s}}$} em $\ket{0\cdots 0}$.</span><span class="sxs-lookup"><span data-stu-id="74236-169">Next, we note that controlling on the computational basis state $\ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n - 1}}$ for a bit string $\vec{s}$ can be realized by transforming $\ket{\vec{s}}$ into $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="74236-170">Em particular, $\ket{\vec{s}} = X^{s\_0} \otimes X^{s\_1} \otimes \otimes \otimes X^{s\_{n - 1}} \ket{0\cdots 0}$.</span><span class="sxs-lookup"><span data-stu-id="74236-170">In particular, $\ket{\vec{s}} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{0\cdots 0}$.</span></span>
<span data-ttu-id="74236-171">Desde $X^{\dagger} = X$, isto implica que $\ket{0\dots 0} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{\vec{s}}}.$.</span><span class="sxs-lookup"><span data-stu-id="74236-171">Since $X^{\dagger} = X$, this implies that $\ket{0\dots 0} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{\vec{s}}$.</span></span>
<span data-ttu-id="74236-172">Assim, podemos aplicar $P = X^{s\_0} \otimes X^{s\_1} \otimes \otimes X^{s\_{n - 1}}},apply `Controlled oracle`, e transformar-se novamente em $\vec{s}$.</span><span class="sxs-lookup"><span data-stu-id="74236-172">Thus, we can apply $P = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}}$, apply `Controlled oracle`, and transform back to $\vec{s}$.</span></span>
<span data-ttu-id="74236-173">Esta construção é precisamente `ApplyWith`, por isso escrevemos o corpo da nossa nova operação em conformidade:</span><span class="sxs-lookup"><span data-stu-id="74236-173">This construction is precisely `ApplyWith`, so we write the body of our new operation accordingly:</span></span>

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

<span data-ttu-id="74236-174">Aqui, utilizámos <xref:microsoft.quantum.canon.applypaulifrombitstring> para aplicar $P$, aplicando-se parcialmente sobre o seu alvo para utilização com `ApplyWith`.</span><span class="sxs-lookup"><span data-stu-id="74236-174">Here, we have used <xref:microsoft.quantum.canon.applypaulifrombitstring> to apply $P$, partially applying over its target for use with `ApplyWith`.</span></span>
<span data-ttu-id="74236-175">Note-se, no entanto, que precisamos de transformar o registo de *controlo* na nossa forma desejada, pelo que aplicamos parcialmente a operação interna `(Controlled oracle)` no *alvo.*</span><span class="sxs-lookup"><span data-stu-id="74236-175">Note, however, that we need to transform the *control* register to our desired form, so we partially apply the inner operation `(Controlled oracle)` on the *target*.</span></span>
<span data-ttu-id="74236-176">Isto deixa `ApplyWith` a agir para estoirar o registo de controlo com $P$, exatamente como desejávamos.</span><span class="sxs-lookup"><span data-stu-id="74236-176">This leaves `ApplyWith` acting to bracket the control register with $P$, exactly as we desired.</span></span>

<span data-ttu-id="74236-177">Neste momento, poderíamos ser feitos, mas é de alguma forma insatisfatório que a nossa nova operação não "sinta" como aplicar o `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="74236-177">At this point, we could be done, but it is somehow unsatisfying that our new operation does not "feel" like applying the `Controlled` functor.</span></span>
<span data-ttu-id="74236-178">Assim, terminamos a definição do nosso novo conceito de fluxo de controlo escrevendo uma função que leva o oráculo a ser controlado e que devolve uma nova operação.</span><span class="sxs-lookup"><span data-stu-id="74236-178">Thus, we finish defining our new control flow concept by writing a function that takes the oracle to be controlled and that returns a new operation.</span></span>
<span data-ttu-id="74236-179">Desta forma, a nossa nova função parece-se muito com `Controlled`, ilustrando que podemos facilmente definir novas e poderosas construções de fluxo de controlo usando Q# e o cânone juntos:</span><span class="sxs-lookup"><span data-stu-id="74236-179">In this way, our new function looks and feels very much like `Controlled`, illustrating that we can easily define powerful new control flow constructs using Q# and the canon together:</span></span>

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
