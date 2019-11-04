---
title: 'P # bibliotecas padrão – controle e fluxo | Microsoft Docs'
description: 'P # bibliotecas padrão – controle e fluxo'
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 5e865dbb48029724b6f507ecb63b85d10d80c9a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185652"
---
# <a name="higher-order-control-flow"></a><span data-ttu-id="533c0-103">Fluxo de controle de ordem superior</span><span class="sxs-lookup"><span data-stu-id="533c0-103">Higher-Order Control Flow</span></span> #

<span data-ttu-id="533c0-104">Uma das principais funções da biblioteca padrão é tornar mais fácil expressar ideias de algoritmos de alto nível como [programas Quantum](https://en.wikipedia.org/wiki/Quantum_programming).</span><span class="sxs-lookup"><span data-stu-id="533c0-104">One of the primary roles of the standard library is to make it easier to express high-level algorithmic ideas as [quantum programs](https://en.wikipedia.org/wiki/Quantum_programming).</span></span>
<span data-ttu-id="533c0-105">Assim, o Q # Canon fornece uma variedade de diferentes construções de controle de fluxo, cada uma implementada usando aplicativos parciais de funções e operações.</span><span class="sxs-lookup"><span data-stu-id="533c0-105">Thus, the Q# canon provides a variety of different flow control constructs, each implemented using partial application of functions and operations.</span></span>
<span data-ttu-id="533c0-106">Passando imediatamente para um exemplo, considere o caso em que um deseja construir uma "escada CNOT" em um registro:</span><span class="sxs-lookup"><span data-stu-id="533c0-106">Jumping immediately into an example, consider the case in which one wants to construct a "CNOT ladder" on a register:</span></span>

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

<span data-ttu-id="533c0-107">Podemos expressar esse padrão usando loops de iteração e de `for`:</span><span class="sxs-lookup"><span data-stu-id="533c0-107">We can express this pattern by using iteration and `for` loops:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

<span data-ttu-id="533c0-108">Expresso em termos de <xref:microsoft.quantum.canon.applytoeachca> e funções de manipulação de matriz, como <xref:microsoft.quantum.arrays.zip>, no entanto, isso é muito mais curto e mais fácil de ler:</span><span class="sxs-lookup"><span data-stu-id="533c0-108">Expressed in terms of <xref:microsoft.quantum.canon.applytoeachca> and array manipulation functions such as <xref:microsoft.quantum.arrays.zip>, however, this is much shorter and easier to read:</span></span>

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

<span data-ttu-id="533c0-109">No restante desta seção, forneceremos vários exemplos de como usar as várias operações de controle de fluxo e funções fornecidas pela Canon para os programas Quantum Compact expressamente.</span><span class="sxs-lookup"><span data-stu-id="533c0-109">In the rest of this section, we will provide a number of examples of how to use the various flow control operations and functions provided by the canon to compactly express quantum programs.</span></span>

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a><span data-ttu-id="533c0-110">Aplicando operações e funções em matrizes e intervalos</span><span class="sxs-lookup"><span data-stu-id="533c0-110">Applying Operations and Functions over Arrays and Ranges</span></span> ##

<span data-ttu-id="533c0-111">Uma das abstrações primárias fornecidas pela Canon é a de iteração.</span><span class="sxs-lookup"><span data-stu-id="533c0-111">One of the primary abstractions provided by the canon is that of iteration.</span></span>
<span data-ttu-id="533c0-112">Por exemplo, considere um meio do formato $U \otimes U \otimes \cdots \otimes U $ para um único-qubit unitário $U $.</span><span class="sxs-lookup"><span data-stu-id="533c0-112">For instance, consider a unitary of the form $U \otimes U \otimes \cdots \otimes U$ for a single-qubit unitary $U$.</span></span>
<span data-ttu-id="533c0-113">Em Q #, podemos usar <xref:microsoft.quantum.arrays.indexrange> para representar isso como um loop de `for` sobre um registro:</span><span class="sxs-lookup"><span data-stu-id="533c0-113">In Q#, we might use <xref:microsoft.quantum.arrays.indexrange> to represent this as as a `for` loop over a register:</span></span>

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation HAll(register : Qubit[]) : Unit 
is Adj + Ctl {

    for (qubit in register) {
        H(qubit);
    }
}
```

<span data-ttu-id="533c0-114">Em seguida, podemos usar essa nova operação como `HAll(register)` para aplicar $H \otimes H \otimes \cdots \otimes H $.</span><span class="sxs-lookup"><span data-stu-id="533c0-114">We can then use this new operation as `HAll(register)` to apply $H \otimes H \otimes \cdots \otimes H$.</span></span>

<span data-ttu-id="533c0-115">No entanto, isso é complicado, especialmente em um algoritmo maior.</span><span class="sxs-lookup"><span data-stu-id="533c0-115">This is cumbersome to do, however, especially in a larger algorithm.</span></span>
<span data-ttu-id="533c0-116">Além disso, essa abordagem é especializada para a operação específica que desejamos aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="533c0-116">Moreover, this approach is specialized to the particular operation that we wish to apply to each qubit.</span></span>
<span data-ttu-id="533c0-117">Podemos usar o fato de que as operações são de primeira classe para expressar esse conceito de algoritmo mais explicitamente:</span><span class="sxs-lookup"><span data-stu-id="533c0-117">We can use the fact that operations are first-class to express this algorithmic concept more explicitly:</span></span>

```qsharp
ApplyToEachCA(H, register);
```

<span data-ttu-id="533c0-118">Aqui, o sufixo `CA` indica que a chamada para `ApplyToEach` é, por sua vez, adjacente e controlável.</span><span class="sxs-lookup"><span data-stu-id="533c0-118">Here, the suffix `CA` indicates that the call to `ApplyToEach` is itself adjointable and controllable.</span></span>
<span data-ttu-id="533c0-119">Portanto, se `U` oferecer suporte a `Adjoint` e `Controlled`, as seguintes linhas serão equivalentes:</span><span class="sxs-lookup"><span data-stu-id="533c0-119">Thus, if `U` supports `Adjoint` and `Controlled`, the following lines are equivalent:</span></span>

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

<span data-ttu-id="533c0-120">Em particular, isso significa que as chamadas para `ApplyToEachCA` podem aparecer em operações para as quais uma especialização adjacente é gerada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="533c0-120">In particular, this means that calls to `ApplyToEachCA` can appear in operations for which an adjoint specialization is auto-generated.</span></span>
<span data-ttu-id="533c0-121">Da mesma forma, <xref:microsoft.quantum.canon.applytoeachindex> é útil para representar padrões do formulário `U(0, targets[0]); U(1, targets[1]); ...`e oferece versões para cada combinação de transmissão functors com suporte em sua entrada.</span><span class="sxs-lookup"><span data-stu-id="533c0-121">Similarly, <xref:microsoft.quantum.canon.applytoeachindex> is useful for representing patterns of the form `U(0, targets[0]); U(1, targets[1]); ...`, and offers versions for each combination of functors supported by its input.</span></span>

> [!TIP]
> <span data-ttu-id="533c0-122">o `ApplyToEach` é de tipo parametrizado, de modo que possa ser usado com operações que usam entradas diferentes de `Qubit`.</span><span class="sxs-lookup"><span data-stu-id="533c0-122">`ApplyToEach` is type-parameterized such that it can be used with operations that take inputs other than `Qubit`.</span></span>
> <span data-ttu-id="533c0-123">Por exemplo, suponha que `codeBlocks` seja uma matriz de valores de <xref:microsoft.quantum.errorcorrection.logicalregister> que precisam ser recuperados.</span><span class="sxs-lookup"><span data-stu-id="533c0-123">For example, suppose that `codeBlocks` is an array of <xref:microsoft.quantum.errorcorrection.logicalregister> values that need to be recovered.</span></span>
> <span data-ttu-id="533c0-124">Em seguida, `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` aplicará o código de correção de erros `code` e a função de recuperação `recoveryFn` para cada bloco de forma independente.</span><span class="sxs-lookup"><span data-stu-id="533c0-124">Then `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` will apply the error-correcting code `code` and recovery function `recoveryFn` to each block independently.</span></span>
> <span data-ttu-id="533c0-125">Isso contém até mesmo para entradas clássicas: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` aplicará uma rotação de $ \pi/$2 sobre $X $ seguido de uma rotação de $pi/$3 sobre $Y $.</span><span class="sxs-lookup"><span data-stu-id="533c0-125">This holds even for classical inputs: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` will apply a rotation of $\pi / 2$ about $X$ followed by a rotation of $pi / 3$ about $Y$.</span></span>

<span data-ttu-id="533c0-126">O Q # Canon também fornece suporte para padrões de enumeração clássicas familiares à programação funcional.</span><span class="sxs-lookup"><span data-stu-id="533c0-126">The Q# canon also provides support for classical enumeration patterns familiar to functional programming.</span></span>
<span data-ttu-id="533c0-127">Por exemplo, <xref:microsoft.quantum.arrays.fold> implementa o $f padrão (f (f (s\_{\Text{Initial}}, x\_0), x\_1), \dots) $ para reduzir uma função em uma lista.</span><span class="sxs-lookup"><span data-stu-id="533c0-127">For instance, <xref:microsoft.quantum.arrays.fold> implements the pattern $f(f(f(s\_{\text{initial}}, x\_0), x\_1), \dots)$ for reducing a function over a list.</span></span>
<span data-ttu-id="533c0-128">Esse padrão pode ser usado para implementar somas, produtos, mínimo, máximo e outras funções desse tipo:</span><span class="sxs-lookup"><span data-stu-id="533c0-128">This pattern can be used to implement sums, products, minima, maxima and other such functions:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

<span data-ttu-id="533c0-129">Da mesma forma, funções como <xref:microsoft.quantum.arrays.mapped> e <xref:microsoft.quantum.arrays.mappedbyindex> podem ser usadas para expressar conceitos de programação funcional em Q #.</span><span class="sxs-lookup"><span data-stu-id="533c0-129">Similarly, functions like <xref:microsoft.quantum.arrays.mapped> and <xref:microsoft.quantum.arrays.mappedbyindex> can be used to express functional programming concepts in Q#.</span></span>

## <a name="composing-operations-and-functions"></a><span data-ttu-id="533c0-130">Compondo operações e funções</span><span class="sxs-lookup"><span data-stu-id="533c0-130">Composing Operations and Functions</span></span> ##

<span data-ttu-id="533c0-131">As construções de fluxo de controle oferecidas pela Canon tomam operações e funções como suas entradas, de modo que é útil poder compor várias operações ou funções em um único callable.</span><span class="sxs-lookup"><span data-stu-id="533c0-131">The control flow constructs offered by the canon take operations and functions as their inputs, such that it is helpful to be able to compose several operations or functions into a single callable.</span></span>
<span data-ttu-id="533c0-132">Por exemplo, o padrão $UVU ^ {\dagger} $ é extremamente comum na programação Quantum, de modo que a Canon fornece a operação <xref:microsoft.quantum.canon.applywith> como uma abstração para esse padrão.</span><span class="sxs-lookup"><span data-stu-id="533c0-132">For instance, the pattern $UVU^{\dagger}$ is extremely common in quantum programming, such that the canon provides the operation <xref:microsoft.quantum.canon.applywith> as an abstraction for this pattern.</span></span>
<span data-ttu-id="533c0-133">Essa abstração também permite um compliation mais eficiente em circuitos, pois `Controlled` atuando na sequência `U(qubit); V(qubit); Adjoint U(qubit);` não precisa agir em cada `U`.</span><span class="sxs-lookup"><span data-stu-id="533c0-133">This abstraction also allows for more efficient compliation into circuits, as `Controlled` acting on the sequence `U(qubit); V(qubit); Adjoint U(qubit);` does not need to act on each `U`.</span></span>
<span data-ttu-id="533c0-134">Para ver isso, permita que $c (U) $ seja o unitário que representa `Controlled U([control], target)` e permita que $c (V) $ seja definido da mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="533c0-134">To see this, let $c(U)$ be the unitary representing `Controlled U([control], target)` and let $c(V)$ be defined in the same way.</span></span>
<span data-ttu-id="533c0-135">Em seguida, para um estado arbitrário $ \ket{\psi} $, \begin{align} c (U) c (V) c (U) ^ \dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU ^ {\dagger} \ket{\psi}) \\\\ & = (\boldone \otimes U) (c (V)) (\boldone \otimes U ^ \dagger) \ ket{1} \otimes \ket{\psi}.</span><span class="sxs-lookup"><span data-stu-id="533c0-135">Then for an arbitrary state $\ket{\psi}$, \begin{align} c(U) c(V) c(U)^\dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU^{\dagger} \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{1} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="533c0-136">\end{align} pela definição de `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="533c0-136">\end{align} by the definition of `Controlled`.</span></span>
<span data-ttu-id="533c0-137">Por outro lado, \begin{align} c (U) c (V) c (U) ^ \dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU ^ \dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c ( V)) (\boldone \otimes U ^ \dagger) \ket{0} \otimes \ket{\psi}.</span><span class="sxs-lookup"><span data-stu-id="533c0-137">On the other hand, \begin{align} c(U) c(V) c(U)^\dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU^\dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{0} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="533c0-138">\end{align} por linearidade, podemos concluir que podemos fatorar $U $ out dessa maneira para todos os Estados de entrada.</span><span class="sxs-lookup"><span data-stu-id="533c0-138">\end{align} By linearity, we can conclude that we can factor $U$ out in this way for all input states.</span></span>
<span data-ttu-id="533c0-139">Ou seja, $c (UVU ^ \dagger) = U c (V) U ^ \dagger $.</span><span class="sxs-lookup"><span data-stu-id="533c0-139">That is, $c(UVU^\dagger) = U c(V) U^\dagger$.</span></span>
<span data-ttu-id="533c0-140">Como o controle de operações pode ser caro em geral, o uso de variantes controladas como `WithC` e `WithCA` pode ajudar a reduzir o número de transmissão functors de controle que precisam ser aplicados.</span><span class="sxs-lookup"><span data-stu-id="533c0-140">Since controlling operations can be expensive in general, using controlled variants such as `WithC` and `WithCA` can help reduce the number of control functors that need to be applied.</span></span>

> [!NOTE]
> <span data-ttu-id="533c0-141">Uma outra consequência de fatorar $U $ é que não precisamos nem saber como aplicar o `Controlled` functor ao `U`.</span><span class="sxs-lookup"><span data-stu-id="533c0-141">One other consequence of factoring out $U$ is that we need not even know how to apply the `Controlled` functor to `U`.</span></span>
> <span data-ttu-id="533c0-142">`ApplyWithCA`, portanto, tem uma assinatura mais fraca do que pode ser esperado:</span><span class="sxs-lookup"><span data-stu-id="533c0-142">`ApplyWithCA` therefore has a weaker signature than might be expected:</span></span>
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

<span data-ttu-id="533c0-143">Da mesma forma, <xref:microsoft.quantum.canon.bind> produz operações que aplicam uma sequência de outras operações por vez.</span><span class="sxs-lookup"><span data-stu-id="533c0-143">Similarly, <xref:microsoft.quantum.canon.bind> produces operations which apply a sequence of other operations in turn.</span></span>
<span data-ttu-id="533c0-144">Por exemplo, os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="533c0-144">For instance, the following are equivalent:</span></span>

```qsharp
H(qubit); X(qubit);
Bind([H, X], qubit);
```

<span data-ttu-id="533c0-145">Combinar com padrões de iteração pode tornar isso especialmente útil:</span><span class="sxs-lookup"><span data-stu-id="533c0-145">Combining with iteration patterns can make this especially useful:</span></span>

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bind([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a><span data-ttu-id="533c0-146">Composição de tempo ordenado</span><span class="sxs-lookup"><span data-stu-id="533c0-146">Time-Ordered Composition</span></span> ###

<span data-ttu-id="533c0-147">Podemos continuar ainda mais pensando no controle de fluxo em termos de aplicativos parciais e funções clássicas e pode modelar conceitos de Quantum ainda mais sofisticados em termos de controle de fluxo clássico.</span><span class="sxs-lookup"><span data-stu-id="533c0-147">We can go still further by thinking of flow control in terms of partial application and classical functions, and can model even fairly sophisticated quantum concepts in terms of classical flow control.</span></span>
<span data-ttu-id="533c0-148">Essa analogia se torna precisa pelo reconhecimento de que os operadores unitários correspondem exatamente aos efeitos colaterais das operações de chamada, de modo que qualquer decomposição de operadores unitários em termos de outros operadores unitários corresponde à construção de um determinado sequência de chamada para sub-rotinas clássicas que emite instruções para atuar como operadores unitários específicos.</span><span class="sxs-lookup"><span data-stu-id="533c0-148">This analogy is made precise by the recognition that unitary operators correspond exactly to the side effects of calling operations, such that any decomposition of unitary operators in terms of other unitary operators corresponds to constructing a particular calling sequence for classical subroutines which emit instructions to act as particular unitary operators.</span></span>
<span data-ttu-id="533c0-149">Nessa exibição, `Bind` é precisamente a representação do produto de matriz, uma vez que `Bind([A, B])(target)` é equivalente a `A(target); B(target);`, que, por sua vez, é a sequência de chamada correspondente ao $BA $.</span><span class="sxs-lookup"><span data-stu-id="533c0-149">Under this view, `Bind` is precisely the representation of the matrix product, since `Bind([A, B])(target)` is equivalent to `A(target); B(target);`, which in turn is the calling sequence corresponding to $BA$.</span></span>

<span data-ttu-id="533c0-150">Um exemplo mais sofisticado é a [expansão Trotter – Suzuki](https://arxiv.org/abs/math-ph/0506007v1).</span><span class="sxs-lookup"><span data-stu-id="533c0-150">A more sophisticated example is the [Trotter–Suzuki expansion](https://arxiv.org/abs/math-ph/0506007v1).</span></span>
<span data-ttu-id="533c0-151">Conforme discutido na seção representação do gerador dinâmico de [estruturas de dados](xref:microsoft.quantum.libraries.data-structures), a expansão Trotter – Suzuki fornece uma maneira particularmente útil de expressar exponencials de matriz.</span><span class="sxs-lookup"><span data-stu-id="533c0-151">As discussed in the Dynamical Generator Representation section of [data structures](xref:microsoft.quantum.libraries.data-structures), the Trotter–Suzuki expansion provides a particularly useful way of expressing matrix exponentials.</span></span>
<span data-ttu-id="533c0-152">Por exemplo, aplicar a expansão em sua ordem mais baixa produz isso para qualquer operador $A $ e $B $ de modo que $A = A ^ \dagger $ e $B = B ^ \dagger $, \begin{align} \tag{★} \label{EQ: Trotter-Suzuki-0} \exp (i [A + B] t) = \lim_{n\to\infty} \left (\exp (i t/n) \exp (i B/n ) \right) ^ n.</span><span class="sxs-lookup"><span data-stu-id="533c0-152">For instance, applying the expansion at its lowest order yields that for any operators $A$ and $B$ such that $A = A^\dagger$ and $B = B^\dagger$, \begin{align} \tag{★} \label{eq:trotter-suzuki-0} \exp(i [A + B] t) = \lim_{n\to\infty} \left(\exp(i A t / n) \exp(i B t / n)\right)^n.</span></span>
<span data-ttu-id="533c0-153">\end{align} coloquialmente, isso diz que podemos expandir um estado em $A + B $ em constante evolução em $A $ e $B $ sozinho.</span><span class="sxs-lookup"><span data-stu-id="533c0-153">\end{align} Colloquially, this says that we can approximately evolve a state under $A + B$ by alternately evolving under $A$ and $B$ alone.</span></span>
<span data-ttu-id="533c0-154">Se representarmos a evolução em $A $ por uma operação `A : (Double, Qubit[]) => Unit` que se aplica $e ^ {i t A} $, a representação da expansão Trotter – Suzuki em termos de reorganizar as sequências de chamada torna-se clara.</span><span class="sxs-lookup"><span data-stu-id="533c0-154">If we represent evolution under $A$ by an operation `A : (Double, Qubit[]) => Unit` that applies $e^{i t A}$, then the representation of the Trotter–Suzuki expansion in terms of rearranging calling sequences becomes clear.</span></span>
<span data-ttu-id="533c0-155">Concretamente, dada uma operação `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` de modo que `A = U(0, _, _)` e `B = U(1, _, _)`, podemos definir uma nova operação representando o integral de `U` no tempo $t $ gerando sequências do formulário</span><span class="sxs-lookup"><span data-stu-id="533c0-155">Concretely, given an operation `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` such that `A = U(0, _, _)` and `B = U(1, _, _)`, we can define a new operation representing the integral of `U` at time $t$ by generating sequences of the form</span></span>

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

<span data-ttu-id="533c0-156">Neste ponto, agora podemos ter uma razão da expansão Trotter – Suzuki *sem referência à mecânica quantum*.</span><span class="sxs-lookup"><span data-stu-id="533c0-156">At this point, we can now reason about the Trotter–Suzuki expansion *without reference to quantum mechanics at all*.</span></span>
<span data-ttu-id="533c0-157">A expansão é efetivamente um padrão de iteração muito específico motivado por $ \eqref{EQ: Trotter-Suzuki-0} $.</span><span class="sxs-lookup"><span data-stu-id="533c0-157">The expansion is effectively a very particular iteration pattern motivated by $\eqref{eq:trotter-suzuki-0}$.</span></span>
<span data-ttu-id="533c0-158">Esse padrão de iteração é implementado por <xref:microsoft.quantum.canon.decomposeintotimestepsca>:</span><span class="sxs-lookup"><span data-stu-id="533c0-158">This iteration pattern is implemented by <xref:microsoft.quantum.canon.decomposeintotimestepsca>:</span></span>

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

<span data-ttu-id="533c0-159">A assinatura de `DecomposeIntoTimeStepsCA` segue um padrão comum em Q #, em que coleções podem ser apoiadas por matrizes ou por algo que os elementos de computação em tempo real são representados por tuplas cujos primeiros elementos são `Int` valores que indicam seus comprimentos.</span><span class="sxs-lookup"><span data-stu-id="533c0-159">The signature of `DecomposeIntoTimeStepsCA` follows a common pattern in Q#, where collections that may be backed either by arrays or by something which compute elements on the fly are represented by tuples whose first elements are `Int` values indicating their lengths.</span></span>

## <a name="putting-it-together-controlling-operations"></a><span data-ttu-id="533c0-160">Juntando-as: controlando as operações</span><span class="sxs-lookup"><span data-stu-id="533c0-160">Putting it Together: Controlling Operations</span></span> ##

<span data-ttu-id="533c0-161">Por fim, a Canon baseia-se no `Controlled` functor fornecendo maneiras adicionais de operações de Quantum de condição.</span><span class="sxs-lookup"><span data-stu-id="533c0-161">Finally, the canon builds on the `Controlled` functor by providing additional ways to condition quantum operations.</span></span>
<span data-ttu-id="533c0-162">É comum, especialmente em aritmética de Quantum, para operações de condição em Estados de base computacional diferentes de $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="533c0-162">It is common, especially in quantum arithmetic, to condition operations on computational basis states other than $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="533c0-163">Usando as operações de controle e as funções apresentadas acima, podemos obter mais condições de Quantum geral em uma única instrução.</span><span class="sxs-lookup"><span data-stu-id="533c0-163">Using the control operations and functions introduced above, we can more general quantum conditions in a single statement.</span></span>
<span data-ttu-id="533c0-164">Vamos pular para o modo como <xref:microsoft.quantum.canon.controlledonbitstring> (os parâmetros de tipo Sans), em seguida, dividiremos as partes uma a uma.</span><span class="sxs-lookup"><span data-stu-id="533c0-164">Let's jump in to how <xref:microsoft.quantum.canon.controlledonbitstring> does it (sans type parameters), then we'll break down the pieces one by one.</span></span>
<span data-ttu-id="533c0-165">A primeira coisa que precisaremos fazer é definir uma operação que realmente faça o trabalho pesado de implementar o controle em Estados de base computacional arbitrários.</span><span class="sxs-lookup"><span data-stu-id="533c0-165">The first thing we'll need to do is to define an operation which actually does the heavy lifting of implementing the control on arbitrary computational basis states.</span></span>
<span data-ttu-id="533c0-166">No entanto, não chamaremos essa operação diretamente e, portanto, adicionamos `_` ao início do nome para indicar que é uma implementação de outra construção em outro lugar.</span><span class="sxs-lookup"><span data-stu-id="533c0-166">We won't call this operation directly, however, and so we add `_` to the beginning of the name to indicate that it's an implementation of another construct elsewhere.</span></span>

```qsharp
operation _ControlledOnBitString(
        bits : Bool[],
        oracle: (Qubit[] => Unit is Adj + Ctl),
        controlRegister : Qubit[],
        targetRegister: Qubit[]) 
: Unit 
is Adj + Ctl {
```

<span data-ttu-id="533c0-167">Observe que pegamos uma cadeia de caracteres de bits, representada como uma matriz `Bool`, que usamos para especificar o condicionamento que queremos aplicar à operação `oracle` que recebemos.</span><span class="sxs-lookup"><span data-stu-id="533c0-167">Note that we take a string of bits, represented as a `Bool` array, that we use to specify the conditioning that we want to apply to the operation `oracle` that we are given.</span></span>
<span data-ttu-id="533c0-168">Como essa operação realmente faz o aplicativo diretamente, também precisamos pegar o controle e os registros de destino, ambos representados aqui como `Qubit[]`.</span><span class="sxs-lookup"><span data-stu-id="533c0-168">Since this operation actually does the application directly, we also need to take the control and target registers, both represented here as `Qubit[]`.</span></span>

<span data-ttu-id="533c0-169">Em seguida, observamos que o controle do estado de base computacional $ \ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n-1}} $ para uma cadeia de caracteres de bits $ \vec{s} $ pode ser realizado com a transformação de $ \ket{\vec{s}} $ em $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="533c0-169">Next, we note that controlling on the computational basis state $\ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n - 1}}$ for a bit string $\vec{s}$ can be realized by transforming $\ket{\vec{s}}$ into $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="533c0-170">Em particular, $ \ket{\vec{s}} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="533c0-170">In particular, $\ket{\vec{s}} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{0\cdots 0}$.</span></span>
<span data-ttu-id="533c0-171">Como $X ^ {\dagger} = X $, isso implica que $ \ket{0\dots 0} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{\vec{s}} $.</span><span class="sxs-lookup"><span data-stu-id="533c0-171">Since $X^{\dagger} = X$, this implies that $\ket{0\dots 0} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{\vec{s}}$.</span></span>
<span data-ttu-id="533c0-172">Portanto, podemos aplicar $P = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} $, aplicar `Controlled oracle`e transformar de volta em $ \vec{s} $.</span><span class="sxs-lookup"><span data-stu-id="533c0-172">Thus, we can apply $P = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}}$, apply `Controlled oracle`, and transform back to $\vec{s}$.</span></span>
<span data-ttu-id="533c0-173">Essa construção é precisamente `ApplyWith`, portanto, escrevemos o corpo da nossa nova operação de acordo:</span><span class="sxs-lookup"><span data-stu-id="533c0-173">This construction is precisely `ApplyWith`, so we write the body of our new operation accordingly:</span></span>

```qsharp
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

<span data-ttu-id="533c0-174">Aqui, usamos <xref:microsoft.quantum.canon.applypaulifrombitstring> para aplicar $P $, parcialmente aplicando seu destino para uso com `ApplyWith`.</span><span class="sxs-lookup"><span data-stu-id="533c0-174">Here, we have used <xref:microsoft.quantum.canon.applypaulifrombitstring> to apply $P$, partially applying over its target for use with `ApplyWith`.</span></span>
<span data-ttu-id="533c0-175">No entanto, observe que precisamos transformar o registro de *controle* em nosso formato desejado, portanto, aplicamos parcialmente a operação interna `(Controlled oracle)` no *destino*.</span><span class="sxs-lookup"><span data-stu-id="533c0-175">Note, however, that we need to transform the *control* register to our desired form, so we partially apply the inner operation `(Controlled oracle)` on the *target*.</span></span>
<span data-ttu-id="533c0-176">Isso deixa `ApplyWith` atuando para colocar o registro de controle com $P $, exatamente como desejamos.</span><span class="sxs-lookup"><span data-stu-id="533c0-176">This leaves `ApplyWith` acting to bracket the control register with $P$, exactly as we desired.</span></span>

<span data-ttu-id="533c0-177">Neste ponto, poderíamos ser feito, mas está, de alguma forma, desconhecendo que nossa nova operação não "sente", como aplicar o `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="533c0-177">At this point, we could be done, but it is somehow unsatisfying that our new operation does not "feel" like applying the `Controlled` functor.</span></span>
<span data-ttu-id="533c0-178">Portanto, terminamos de definir nosso novo conceito de fluxo de controle escrevendo uma função que usa o Oracle para ser controlado e que retorna uma nova operação.</span><span class="sxs-lookup"><span data-stu-id="533c0-178">Thus, we finish defining our new control flow concept by writing a function that takes the oracle to be controlled and that returns a new operation.</span></span>
<span data-ttu-id="533c0-179">Dessa forma, nossa nova função parece ser muito parecida com a `Controlled`, ilustrando que podemos facilmente definir novas construções poderosas de fluxo de controle usando Q # e a Canon juntas:</span><span class="sxs-lookup"><span data-stu-id="533c0-179">In this way, our new function looks and feels very much like `Controlled`, illustrating that we can easily define powerful new control flow constructs using Q# and the canon together:</span></span>

```qsharp
function ControlledOnBitString(
        bits : Bool[],
        oracle: (Qubit[] => Unit is Adj + Ctl)) 
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
