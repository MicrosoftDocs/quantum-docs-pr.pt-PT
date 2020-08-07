---
title: Escrever e simular programas de nível qubit emQ#
description: Tutorial passo a passo sobre a escrita e simulação de um programa quântico que opera ao nível do qubit individual
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
no-loc:
- Q#
- $$v
ms.openlocfilehash: 22c79e4e01db1a0d0c291d0dcff81dbfa8df5cd3
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869720"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a><span data-ttu-id="154b0-103">Tutorial: Escreva e simula programas de nível qubit em Q\#</span><span class="sxs-lookup"><span data-stu-id="154b0-103">Tutorial: Write and simulate qubit-level programs in Q\#</span></span>

<span data-ttu-id="154b0-104">Bem-vindo ao tutorial do Kit de Desenvolvimento Quântico sobre a escrita e simulação de um programa quântico básico que opera em qubits individuais.</span><span class="sxs-lookup"><span data-stu-id="154b0-104">Welcome to the Quantum Development Kit tutorial on writing and simulating a basic quantum program that operates on individual qubits.</span></span> 

<span data-ttu-id="154b0-105">Embora tenha Q# sido criada principalmente como uma linguagem de programação de alto nível para programas quânticos em larga escala, pode ser facilmente usada para explorar o nível mais baixo de programas quânticos: abordando diretamente qubits específicos.</span><span class="sxs-lookup"><span data-stu-id="154b0-105">Although Q# was primarily created as a high-level programming language for large-scale quantum programs, it can just as easily be used to explore the lower level of quantum programs: directly addressing specific qubits.</span></span>
<span data-ttu-id="154b0-106">A flexibilidade Q# permite que os utilizadores se aproximem dos sistemas quânticos a partir de qualquer tal nível de abstração, e neste tutorial mergulhamos nos próprios qubits.</span><span class="sxs-lookup"><span data-stu-id="154b0-106">The flexibility of Q# allows users to approach quantum systems from any such level of abstraction, and in this tutorial we dive into the qubits themselves.</span></span>
<span data-ttu-id="154b0-107">Especificamente, damos uma olhada sob o capuz da [transformação quântica de Fourier,](https://en.wikipedia.org/wiki/Quantum_Fourier_transform)uma sub-rotina que é parte integrante de muitos algoritmos quânticos maiores.</span><span class="sxs-lookup"><span data-stu-id="154b0-107">Specifically, we take a look under the hood of the [quantum Fourier transform](https://en.wikipedia.org/wiki/Quantum_Fourier_transform), a subroutine that is integral to many larger quantum algorithms.</span></span>

<span data-ttu-id="154b0-108">Note-se que esta visão de baixo nível do processamento de informação quântica é frequentemente descrita em termos de "[circuitos quânticos](xref:microsoft.quantum.concepts.circuits)", que representam a aplicação sequencial dos portões a qubits específicos de um sistema.</span><span class="sxs-lookup"><span data-stu-id="154b0-108">Note that this low-level view of quantum information processing is often described in terms of "[quantum circuits](xref:microsoft.quantum.concepts.circuits)," which represent the sequential application of gates to specific qubits of a system.</span></span>

<span data-ttu-id="154b0-109">Assim, as operações de mono e múltiplos qubits que aplicamos sequencialmente podem ser facilmente representadas num "diagrama de circuito".</span><span class="sxs-lookup"><span data-stu-id="154b0-109">Thus, the single- and multi-qubit operations we sequentially apply can be readily represented in a "circuit diagram."</span></span>
<span data-ttu-id="154b0-110">No nosso caso, vamos definir uma Q# operação para executar a transformação completa de Fourier quântico de três qubits, que tem a seguinte representação como um circuito:</span><span class="sxs-lookup"><span data-stu-id="154b0-110">In our case, we will define a Q# operation to perform the full three-qubit quantum Fourier transform, which has the following representation as a circuit:</span></span>

<br/>
<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a><span data-ttu-id="154b0-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="154b0-111">Prerequisites</span></span>

* <span data-ttu-id="154b0-112">[Instale](xref:microsoft.quantum.install) o Kit de Desenvolvimento Quântico utilizando o seu ambiente de linguagem e desenvolvimento preferido.</span><span class="sxs-lookup"><span data-stu-id="154b0-112">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your preferred language and development environment.</span></span>
* <span data-ttu-id="154b0-113">Se já tiver o QDK instalado, confirme que o [atualizou](xref:microsoft.quantum.update) para a versão mais recente</span><span class="sxs-lookup"><span data-stu-id="154b0-113">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>


## <a name="in-this-tutorial-youll-learn-how-to"></a><span data-ttu-id="154b0-114">Neste tutorial, irá aprender a:</span><span class="sxs-lookup"><span data-stu-id="154b0-114">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="154b0-115">Definir operações quânticas emQ#</span><span class="sxs-lookup"><span data-stu-id="154b0-115">Define quantum operations in Q#</span></span>
> * <span data-ttu-id="154b0-116">Ligue Q# para operações diretamente da linha de comando ou usando um programa de anfitrião clássico</span><span class="sxs-lookup"><span data-stu-id="154b0-116">Call Q# operations directly from the command line or using a classical host program</span></span>
> * <span data-ttu-id="154b0-117">Simular uma operação quântica da alocação de qubits à saída de medição</span><span class="sxs-lookup"><span data-stu-id="154b0-117">Simulate a quantum operation from qubit allocation to measurement output</span></span>
> * <span data-ttu-id="154b0-118">Observe como a simulação de função de onda do sistema quântico evolui ao longo da operação</span><span class="sxs-lookup"><span data-stu-id="154b0-118">Observe how the quantum system's simulated wavefunction evolves throughout the operation</span></span>

<span data-ttu-id="154b0-119">Executar um programa quântico com o Kit de Desenvolvimento Quântico da Microsoft é normalmente composto por duas partes:</span><span class="sxs-lookup"><span data-stu-id="154b0-119">Running a quantum program with Microsoft's Quantum Development Kit typically consists of two parts:</span></span>
1. <span data-ttu-id="154b0-120">O programa em si, que é implementado usando a Q# linguagem de programação quântica, e depois invocado para funcionar em um computador quântico ou simulador quântico.</span><span class="sxs-lookup"><span data-stu-id="154b0-120">The program itself, which is implemented using the Q# quantum programming language, and then invoked to run on a quantum computer or quantum simulator.</span></span> <span data-ttu-id="154b0-121">Estes consistem de</span><span class="sxs-lookup"><span data-stu-id="154b0-121">These consist of</span></span> 
    - <span data-ttu-id="154b0-122">Q#operações: sub-rotinas que atuam nos registos quânticos, e</span><span class="sxs-lookup"><span data-stu-id="154b0-122">Q# operations: subroutines acting on quantum registers, and</span></span> 
    - <span data-ttu-id="154b0-123">Q#funções: sub-rotinas clássicas utilizadas dentro do algoritmo quântico.</span><span class="sxs-lookup"><span data-stu-id="154b0-123">Q# functions: classical subroutines used within the quantum algorithm.</span></span>
2. <span data-ttu-id="154b0-124">O ponto de entrada utilizado para chamar o programa quântico e especificar a máquina-alvo na qual deve ser executado.</span><span class="sxs-lookup"><span data-stu-id="154b0-124">The entry point used to call the quantum program and specify the target machine on which it should be run.</span></span>
    <span data-ttu-id="154b0-125">Isto pode ser feito diretamente a partir da linha de comando, ou através de um programa de anfitrião escrito em uma linguagem de programação clássica como Python ou C#.</span><span class="sxs-lookup"><span data-stu-id="154b0-125">This can be done directly from the command line, or through a host program written in a classical programming language like Python or C#.</span></span>
    <span data-ttu-id="154b0-126">Este tutorial inclui instruções para o método que preferir.</span><span class="sxs-lookup"><span data-stu-id="154b0-126">This tutorial includes instructions for whichever method you prefer.</span></span>

## <a name="allocate-qubits-and-define-quantum-operations"></a><span data-ttu-id="154b0-127">Alocar qubits e definir operações quânticas</span><span class="sxs-lookup"><span data-stu-id="154b0-127">Allocate qubits and define quantum operations</span></span>

<span data-ttu-id="154b0-128">A primeira parte deste tutorial consiste em definir a Q# `Perform3qubitQFT` operação, que realiza a transformação quântica de Fourier em três qubits.</span><span class="sxs-lookup"><span data-stu-id="154b0-128">The first part of this tutorial consists of defining the Q# operation `Perform3qubitQFT`, which performs the quantum Fourier transform on three qubits.</span></span> 

<span data-ttu-id="154b0-129">Além disso, usaremos a [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) função para observar como a simulação de função de onda do nosso sistema de três qubits evolui em toda a operação.</span><span class="sxs-lookup"><span data-stu-id="154b0-129">In addition, we will use the [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) function to observe how the simulated wavefunction of our three qubit system evolves across the operation.</span></span>

<span data-ttu-id="154b0-130">O primeiro passo é criar o seu Q# projeto e arquivo.</span><span class="sxs-lookup"><span data-stu-id="154b0-130">The first step is creating your Q# project and file.</span></span>
<span data-ttu-id="154b0-131">Os passos para tal dependem do ambiente que utilizará para ligar para o programa, podendo encontrar os detalhes nos [respetivos guias de instalação.](xref:microsoft.quantum.install)</span><span class="sxs-lookup"><span data-stu-id="154b0-131">The steps for this depend on the environment you will use to call the program, and you can find the details in the respective [installation guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="154b0-132">Vamos acompanhá-lo através dos componentes do ficheiro passo a passo, mas o código também está disponível como um bloco completo abaixo.</span><span class="sxs-lookup"><span data-stu-id="154b0-132">We will walk you through the components of the file step-by-step, but the code is also available as a full block below.</span></span>

### <a name="namespaces-to-access-other-no-locq-operations"></a><span data-ttu-id="154b0-133">Espaços de nome para aceder a outras Q# operações</span><span class="sxs-lookup"><span data-stu-id="154b0-133">Namespaces to access other Q# operations</span></span>
<span data-ttu-id="154b0-134">Dentro do ficheiro, primeiro definimos o espaço de nome `NamespaceQFT` que será acedido pelo compilador.</span><span class="sxs-lookup"><span data-stu-id="154b0-134">Inside the file, we first define the namespace `NamespaceQFT` which will be accessed by the compiler.</span></span>
<span data-ttu-id="154b0-135">Para a nossa operação de utilização das Q# operações existentes, abrimos os `Microsoft.Quantum.<>` espaços de nome relevantes.</span><span class="sxs-lookup"><span data-stu-id="154b0-135">For our operation to make use of existing Q# operations, we open the relevant `Microsoft.Quantum.<>` namespaces.</span></span>

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a><span data-ttu-id="154b0-136">Definir operações com argumentos e devoluções</span><span class="sxs-lookup"><span data-stu-id="154b0-136">Define operations with arguments and returns</span></span>
<span data-ttu-id="154b0-137">Em seguida, definimos a `Perform3qubitQFT` operação:</span><span class="sxs-lookup"><span data-stu-id="154b0-137">Next, we define the `Perform3qubitQFT` operation:</span></span>

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

<span data-ttu-id="154b0-138">Para já, a operação não aceita argumentos e não devolve nada--- neste caso escrevemos que devolve um `Unit` objeto, que é semelhante a `void` C# ou um tuple vazio, `Tuple[()]` em Python.</span><span class="sxs-lookup"><span data-stu-id="154b0-138">For now, the operation takes no arguments and does not return anything---in this case we write that it returns a `Unit` object, which is akin to `void` in C# or an empty tuple, `Tuple[()]`, in Python.</span></span>
<span data-ttu-id="154b0-139">Mais tarde, vamos modificá-lo para devolver uma série de resultados de medição, altura em que `Unit` será substituído por `Result[]` .</span><span class="sxs-lookup"><span data-stu-id="154b0-139">Later, we will modify it to return an array of measurement results, at which point `Unit` will be replaced by `Result[]`.</span></span> 

### <a name="allocate-qubits-with-using"></a><span data-ttu-id="154b0-140">Alocar qubits com`using`</span><span class="sxs-lookup"><span data-stu-id="154b0-140">Allocate qubits with `using`</span></span>
<span data-ttu-id="154b0-141">No âmbito da nossa Q# operação, atribuímos primeiro um registo de três qubits com a `using` declaração:</span><span class="sxs-lookup"><span data-stu-id="154b0-141">Within our Q# operation, we first allocate a register of three qubits with the `using` statement:</span></span>

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

<span data-ttu-id="154b0-142">Com `using` , os qubits são automaticamente atribuídos no estado $\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="154b0-142">With `using`, the qubits are automatically allocated in the $\ket{0}$ state.</span></span> <span data-ttu-id="154b0-143">Podemos verificar isto utilizando [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) e [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) , que imprimimos uma cadeia e o estado atual do sistema para a consola.</span><span class="sxs-lookup"><span data-stu-id="154b0-143">We can verify this by using [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) and [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine), which print a string and the system's current state to the console.</span></span>

> [!NOTE]
> <span data-ttu-id="154b0-144">As `Message(<string>)` `DumpMachine()` funções (de [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics) e, respectivamente) são ambas impressas diretamente para a consola.</span><span class="sxs-lookup"><span data-stu-id="154b0-144">The `Message(<string>)` and `DumpMachine()` functions (from [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) and [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics), respectively) both print directly to the console.</span></span> <span data-ttu-id="154b0-145">Tal como uma computação quântica real, Q# não nos permite aceder diretamente aos estados qubit.</span><span class="sxs-lookup"><span data-stu-id="154b0-145">Just like a real quantum computation, Q# does not allow us to directly access qubit states.</span></span>
> <span data-ttu-id="154b0-146">No entanto, à medida `DumpMachine` que imprime o estado atual da máquina-alvo, pode fornecer informações valiosas para depurar e aprender quando usado em conjunto com o simulador de estado completo.</span><span class="sxs-lookup"><span data-stu-id="154b0-146">However, as `DumpMachine` prints the target machine's current state, it can provide valuable insight for debugging and learning when used in conjunction with the full state simulator.</span></span>


### <a name="applying-single-qubit-and-controlled-gates"></a><span data-ttu-id="154b0-147">Aplicação de portões mono-qubit e controlados</span><span class="sxs-lookup"><span data-stu-id="154b0-147">Applying single-qubit and controlled gates</span></span>

<span data-ttu-id="154b0-148">Em seguida, aplicamos os portões que compõem a própria operação.</span><span class="sxs-lookup"><span data-stu-id="154b0-148">Next, we apply the gates which comprise the operation itself.</span></span>
<span data-ttu-id="154b0-149">Q#já contém muitos portões quânticos básicos como operações no [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) espaço de nome, e estes não são exceção.</span><span class="sxs-lookup"><span data-stu-id="154b0-149">Q# already contains many basic quantum gates as operations in the [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) namespace, and these are no exception.</span></span> 

<span data-ttu-id="154b0-150">Dentro de uma Q# operação, as declarações invocando callables serão, naturalmente, executadas por ordem sequencial.</span><span class="sxs-lookup"><span data-stu-id="154b0-150">Within a Q# operation, the statements invoking callables will of course be executed in sequential order.</span></span>
<span data-ttu-id="154b0-151">Assim, o primeiro portão a aplicar é o [`H`](xref:microsoft.quantum.intrinsic.h) (Hadamard) ao primeiro qubit:</span><span class="sxs-lookup"><span data-stu-id="154b0-151">Hence, the first gate to apply is the [`H`](xref:microsoft.quantum.intrinsic.h) (Hadamard) to the first qubit:</span></span>

<br/>
<img src="../media/qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

<span data-ttu-id="154b0-152">Para aplicar uma operação a um qubit específico a partir de um registo (isto é, um único `Qubit` de uma matriz ), `Qubit[]` usamos a notação de índice padrão.</span><span class="sxs-lookup"><span data-stu-id="154b0-152">To apply an operation to a specific qubit from a register (i.e. a single `Qubit` from an array `Qubit[]`) we use standard index notation.</span></span>
<span data-ttu-id="154b0-153">Assim, a aplicação [`H`](xref:microsoft.quantum.intrinsic.h) do primeiro qubit do nosso registo `qs` assume o formulário:</span><span class="sxs-lookup"><span data-stu-id="154b0-153">So, applying the [`H`](xref:microsoft.quantum.intrinsic.h) to the first qubit of our register `qs` takes the form:</span></span>

```qsharp
            H(qs[0]);
```

<span data-ttu-id="154b0-154">Além de aplicar o `H` portão (Hadamard) a qubits individuais, o circuito QFT consiste principalmente em [`R1`](xref:microsoft.quantum.intrinsic.r1) rotações controladas.</span><span class="sxs-lookup"><span data-stu-id="154b0-154">Besides applying the `H` (Hadamard) gate to individual qubits, the QFT circuit consists primarily of controlled [`R1`](xref:microsoft.quantum.intrinsic.r1) rotations.</span></span>
<span data-ttu-id="154b0-155">Uma `R1(θ, <qubit>)` operação em geral deixa inalterado o componente $\ket {0} $ do qubit, ao mesmo tempo que aplica uma rotação de $e^{i\theta}$ para o componente $\ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="154b0-155">An `R1(θ, <qubit>)` operation in general leaves the $\ket{0}$ component of the qubit unchanged, while applying a rotation of $e^{i\theta}$ to the $\ket{1}$ component.</span></span>

#### <a name="controlled-operations"></a><span data-ttu-id="154b0-156">Operações controladas</span><span class="sxs-lookup"><span data-stu-id="154b0-156">Controlled operations</span></span>

<span data-ttu-id="154b0-157">Q#torna extremamente fácil condicionar a execução de uma operação em um ou múltiplos qubits de controlo.</span><span class="sxs-lookup"><span data-stu-id="154b0-157">Q# makes it extremely easy to condition the execution of an operation upon one or multiple control qubits.</span></span>
<span data-ttu-id="154b0-158">Em geral, limitamo-nos a prefaciar a chamada `Controlled` com, e os argumentos da operação mudam como:</span><span class="sxs-lookup"><span data-stu-id="154b0-158">In general, we merely preface the call with `Controlled`, and the operation arguments change as:</span></span>

 <span data-ttu-id="154b0-159">`Op(<normal args>)`$\a$ `Controlled Op([<control qubits>], (<normal args>))` a$ .</span><span class="sxs-lookup"><span data-stu-id="154b0-159">`Op(<normal args>)` $\to$ `Controlled Op([<control qubits>], (<normal args>))`.</span></span>

<span data-ttu-id="154b0-160">Note que os qubits de controlo devem ser fornecidos como uma matriz, mesmo que seja um único qubit.</span><span class="sxs-lookup"><span data-stu-id="154b0-160">Note that the control qubits must be provided as an array, even if it is a single qubit.</span></span>

<span data-ttu-id="154b0-161">Depois do `H` , vemos que os portões seguintes são os `R1` portões agindo no primeiro qubit (e controlados pelo segundo/terceiro):</span><span class="sxs-lookup"><span data-stu-id="154b0-161">After the `H`, we see that the next gates are the `R1` gates acting on the first qubit (and controlled by the second/third):</span></span>

<br/>
<img src="../media/qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

<span data-ttu-id="154b0-162">Chamamos isto com</span><span class="sxs-lookup"><span data-stu-id="154b0-162">We call these with</span></span>

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

<span data-ttu-id="154b0-163">Note que usamos a [`PI()`](xref:microsoft.quantum.math.pi) função do [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) espaço de nome para definir as rotações em termos de raios pi.</span><span class="sxs-lookup"><span data-stu-id="154b0-163">Note that we use the [`PI()`](xref:microsoft.quantum.math.pi) function from the [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) namespace to define the rotations in terms of pi radians.</span></span>
<span data-ttu-id="154b0-164">Além disso, dividimo-nos por um `Double` (por `2.0` exemplo) porque dividir por um inteiro `2` lançaria um erro tipo.</span><span class="sxs-lookup"><span data-stu-id="154b0-164">Additionally, we divide by a `Double` (e.g. `2.0`) because dividing by an integer `2` would throw a type error.</span></span> 

> [!TIP]
> <span data-ttu-id="154b0-165">`R1(π/2)`e `R1(π/4)` são equivalentes às `S` `T` operações (também em `Microsoft.Quantum.Intrinsic` ).</span><span class="sxs-lookup"><span data-stu-id="154b0-165">`R1(π/2)` and `R1(π/4)` are equivalent to the `S` and `T` operations (also in `Microsoft.Quantum.Intrinsic`).</span></span>


<span data-ttu-id="154b0-166">Após a aplicação das `H` operações pertinentes e das rotações controladas ao segundo e terceiro qubits:</span><span class="sxs-lookup"><span data-stu-id="154b0-166">After applying the relevant `H` operations and controlled rotations to the second and third qubits:</span></span>

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

<span data-ttu-id="154b0-167">só precisamos de aplicar um [`SWAP`](xref:microsoft.quantum.intrinsic.swap) portão para completar o circuito:</span><span class="sxs-lookup"><span data-stu-id="154b0-167">we need only apply a [`SWAP`](xref:microsoft.quantum.intrinsic.swap) gate to complete the circuit:</span></span>

```qsharp
            SWAP(qs[2], qs[0]);
```

<span data-ttu-id="154b0-168">Isto é necessário porque a natureza do Quantum Fourier transforma as saídas dos qubits em ordem inversa, de modo que os swaps permitem uma integração perfeita da subbroutina em algoritmos maiores.</span><span class="sxs-lookup"><span data-stu-id="154b0-168">This is necessary because the nature of the quantum Fourier transform outputs the qubits in reverse order, so the swaps allow for seamless integration of the subroutine into larger algorithms.</span></span>

<span data-ttu-id="154b0-169">Assim, terminamos de escrever as operações de nível qubit do Quantum Fourier transformar em nossa Q# operação:</span><span class="sxs-lookup"><span data-stu-id="154b0-169">Hence we have finished writing the qubit-level operations of the quantum Fourier transform into our Q# operation:</span></span>

<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

<span data-ttu-id="154b0-170">No entanto, não podemos encerrar o dia ainda.</span><span class="sxs-lookup"><span data-stu-id="154b0-170">However, we can't call it a day just yet.</span></span>
<span data-ttu-id="154b0-171">Os nossos qubits estavam no estado $\ket {0} $ quando os atribuímos, e tal como na vida, Q# devemos deixar as coisas da mesma forma que as encontramos (ou melhor!).</span><span class="sxs-lookup"><span data-stu-id="154b0-171">Our qubits were in state $\ket{0}$ when we allocated them, and much like in life, in Q# we should leave things the same way we found them (or better!).</span></span>

### <a name="deallocate-qubits"></a><span data-ttu-id="154b0-172">Qubits de deallocate</span><span class="sxs-lookup"><span data-stu-id="154b0-172">Deallocate qubits</span></span>

<span data-ttu-id="154b0-173">Ligamos [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) novamente para ver o estado pós-operação, e finalmente aplicamo-nos ao registo qubit para redefinir os [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) nossos qubits para $\ket {0} $ antes de concluir a operação:</span><span class="sxs-lookup"><span data-stu-id="154b0-173">We call [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) again to see the post-operation state, and finally apply [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) to the qubit register to reset our qubits to $\ket{0}$ before completing the operation:</span></span>

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

<span data-ttu-id="154b0-174">Exigir que todos os qubits translocados sejam explicitamente definidos para $\ket {0} $ é uma característica básica de , pois permite que Q# outras operações conheçam o seu estado precisamente quando começam a usar esses mesmos qubits (um recurso escasso).</span><span class="sxs-lookup"><span data-stu-id="154b0-174">Requiring that all deallocated qubits be explicitly set to $\ket{0}$ is a basic feature of Q#, as it allows other operations to know their state precisely when they begin using those same qubits (a scarce resource).</span></span>
<span data-ttu-id="154b0-175">Além disso, isto garante que não se enredam com quaisquer outros qubits no sistema.</span><span class="sxs-lookup"><span data-stu-id="154b0-175">Additionally, this assures that they not be entangled with any other qubits in the system.</span></span>
<span data-ttu-id="154b0-176">Se o reset não for efetuado no final de um bloco de `using` atribuição, será lançado um erro de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="154b0-176">If the reset is not performed at the end of a `using` allocation block, a runtime error will be thrown.</span></span>

<span data-ttu-id="154b0-177">O seu ficheiro completo Q# deve agora ser assim:</span><span class="sxs-lookup"><span data-stu-id="154b0-177">Your full Q# file should now look like this:</span></span>

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    operation Perform3qubitQFT() : Unit {

        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("After:");
            DumpMachine();

            ResetAll(qs);
        }
    }
}
```


<span data-ttu-id="154b0-178">Com o Q# ficheiro e a operação completos, o nosso programa quântico está pronto para ser chamado e simulado.</span><span class="sxs-lookup"><span data-stu-id="154b0-178">With the Q# file and operation complete, our quantum program is ready to be called and simulated.</span></span>

## <a name="execute-the-program"></a><span data-ttu-id="154b0-179">Executar o programa</span><span class="sxs-lookup"><span data-stu-id="154b0-179">Execute the program</span></span>

<span data-ttu-id="154b0-180">Tendo definido a nossa Q# operação num `.qs` ficheiro, precisamos agora ligar para essa operação e observar quaisquer dados clássicos devolvidos.</span><span class="sxs-lookup"><span data-stu-id="154b0-180">Having defined our Q# operation in a `.qs` file, we now need to call that operation and observe any returned classical data.</span></span>
<span data-ttu-id="154b0-181">Para já, não há nada devolvido (lembre-se que a nossa operação definida acima de `Unit` voltas), mas quando mais tarde modificarmos a Q# operação para devolver uma série de resultados de medição `Result[]` (), iremos abordar esta questão.</span><span class="sxs-lookup"><span data-stu-id="154b0-181">For now, there isn't anything returned (recall that our operation defined above returns `Unit`), but when we later modify the Q# operation to return an array of measurement results (`Result[]`), we will address this.</span></span>

<span data-ttu-id="154b0-182">Embora o Q# programa seja omnipresente em todos os ambientes usados para chamá-lo, a maneira de fazê-lo vai naturalmente variar.</span><span class="sxs-lookup"><span data-stu-id="154b0-182">While the Q# program is ubiquitous across the environments used to call it, the manner of doing so will of course vary.</span></span> <span data-ttu-id="154b0-183">Como tal, basta seguir as instruções no separador correspondente à sua configuração: trabalhar a partir da aplicação da linha de Q# comando ou utilizar um programa de anfitrião em Python ou C#.</span><span class="sxs-lookup"><span data-stu-id="154b0-183">As such, simply follow the instructions in the tab corresponding to your setup: working from the Q# command line application or using a host program in Python or C#.</span></span>

#### <a name="command-line"></a>[<span data-ttu-id="154b0-184">Linha de comandos</span><span class="sxs-lookup"><span data-stu-id="154b0-184">Command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="154b0-185">Executar o Q# programa a partir da linha de comando requer apenas uma pequena alteração no Q# ficheiro.</span><span class="sxs-lookup"><span data-stu-id="154b0-185">Running the Q# program from the command line requires only a small change to the Q# file.</span></span>

<span data-ttu-id="154b0-186">Basta adicionar `@EntryPoint()` a uma linha anterior à definição de operação:</span><span class="sxs-lookup"><span data-stu-id="154b0-186">Simply add `@EntryPoint()` to a line preceding the operation definition:</span></span>

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

<span data-ttu-id="154b0-187">Para executar o programa, abra o terminal na pasta do seu projeto e insira</span><span class="sxs-lookup"><span data-stu-id="154b0-187">To run the program, open the terminal in the folder of your project and enter</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="154b0-188">Após a execução, deverá ver as `Message` saídas e `DumpMachine` saídas abaixo impressas na sua consola.</span><span class="sxs-lookup"><span data-stu-id="154b0-188">Upon execution, you should see the `Message` and `DumpMachine` outputs below printed in your console.</span></span>


#### <a name="python"></a>[<span data-ttu-id="154b0-189">Python</span><span class="sxs-lookup"><span data-stu-id="154b0-189">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="154b0-190">Criar um ficheiro de hospedeiro Python: `host.py` .</span><span class="sxs-lookup"><span data-stu-id="154b0-190">Create a Python host file: `host.py`.</span></span>

<span data-ttu-id="154b0-191">O ficheiro do anfitrião é construído da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="154b0-191">The host file is constructed as follows:</span></span> 
1. <span data-ttu-id="154b0-192">Primeiro, importamos o `qsharp` módulo, que regista o carregador de módulos para Q# interoperabilidade.</span><span class="sxs-lookup"><span data-stu-id="154b0-192">First, we import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="154b0-193">Isto permite que Q# espaços de nome (por exemplo, o `NamespaceQFT` que definimos no nosso Q# arquivo) apareçam como módulos Python, a partir dos quais podemos importar Q# operações.</span><span class="sxs-lookup"><span data-stu-id="154b0-193">This allows Q# namespaces (e.g. the `NamespaceQFT` we defined in our Q# file) to appear as Python modules, from which we can import Q# operations.</span></span>
2. <span data-ttu-id="154b0-194">Em seguida, importe as Q# operações que iremos invocar directamente--- neste caso, `Perform3qubitQFT` .</span><span class="sxs-lookup"><span data-stu-id="154b0-194">Then, import the Q# operations which we will directly invoke---in this case, `Perform3qubitQFT`.</span></span>
    <span data-ttu-id="154b0-195">Só precisamos de importar o ponto de entrada num Q# programa _(isto_ é, não operações como `H` e , que são chamadas por `R1` outras Q# operações, mas nunca pelo anfitrião clássico).</span><span class="sxs-lookup"><span data-stu-id="154b0-195">We need only import the entry point into a Q# program (i.e. _not_ operations like `H` and `R1`, which are called by other Q# operations but never by the classical host).</span></span>
3. <span data-ttu-id="154b0-196">Na simulação de Q# operações ou funções, utilize o formulário `<Q#callable>.simulate(<args>)` para executá-los na `QuantumSimulator()` máquina-alvo.</span><span class="sxs-lookup"><span data-stu-id="154b0-196">In simulating Q# operations or functions, use the form `<Q#callable>.simulate(<args>)` to run them on the `QuantumSimulator()` target machine.</span></span> 

> [!NOTE]
> <span data-ttu-id="154b0-197">Se quiséssemos chamar a operação para uma máquina diferente, por `ResourceEstimator()` exemplo, usaríamos `<Q#callable>.estimate_resources(<args>)` simplesmente.</span><span class="sxs-lookup"><span data-stu-id="154b0-197">If we wanted to call the operation on a different machine, for example the `ResourceEstimator()`, we would simply use `<Q#callable>.estimate_resources(<args>)`.</span></span>
> <span data-ttu-id="154b0-198">Em geral, Q# as operações são agnósticas para as máquinas em que são executadas, mas algumas características como `DumpMachine` podem comportar-se de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="154b0-198">In general, Q# operations are agnostic to the machines on which they're run, but some features such as `DumpMachine` may behave differently.</span></span>

4. <span data-ttu-id="154b0-199">Após a realização da simulação, a chamada de operação devolverá valores conforme definido no Q# ficheiro.</span><span class="sxs-lookup"><span data-stu-id="154b0-199">Upon performing the simulation, the operation call will return values as defined in the Q# file.</span></span>
    <span data-ttu-id="154b0-200">Por enquanto não há nada devolvido, mas mais tarde veremos um exemplo de atribuição e processamento destes valores.</span><span class="sxs-lookup"><span data-stu-id="154b0-200">For now there is nothing returned, but later on we will see an example of assigning and processing these values.</span></span>
    <span data-ttu-id="154b0-201">Com os dados resultantes nas nossas mãos e totalmente clássicos, podemos fazer o que quisermos com ele.</span><span class="sxs-lookup"><span data-stu-id="154b0-201">With the resultant data in our hands and totally classical, we can do whatever we'd like with it.</span></span>

<span data-ttu-id="154b0-202">O seu ficheiro completo `host.py` deve ser o seguinte:</span><span class="sxs-lookup"><span data-stu-id="154b0-202">Your full `host.py` file should be this:</span></span>

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

<span data-ttu-id="154b0-203">Execute o ficheiro Python e impresso na sua consola deve ver as `Message` saídas e `DumpMachine` saídas abaixo.</span><span class="sxs-lookup"><span data-stu-id="154b0-203">Run the Python file, and printed in your console you should see the `Message` and `DumpMachine` outputs below.</span></span> 


#### <a name="c"></a>[<span data-ttu-id="154b0-204">C#</span><span class="sxs-lookup"><span data-stu-id="154b0-204">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="154b0-205">Seguindo as mesmas instruções que no [guia de instalação,](xref:microsoft.quantum.install.cs)crie um ficheiro de anfitrião C# e rebatize-o para `host.cs` .</span><span class="sxs-lookup"><span data-stu-id="154b0-205">Following the same instructions as in the [install guide](xref:microsoft.quantum.install.cs), create a C# host file, and rename it to `host.cs`.</span></span>

<span data-ttu-id="154b0-206">O anfitrião C# tem quatro partes:</span><span class="sxs-lookup"><span data-stu-id="154b0-206">The C# host has four parts:</span></span>
1. <span data-ttu-id="154b0-207">Construa um simulador quântico.</span><span class="sxs-lookup"><span data-stu-id="154b0-207">Construct a quantum simulator.</span></span>
    <span data-ttu-id="154b0-208">No código abaixo, esta é a `qsim` variável.</span><span class="sxs-lookup"><span data-stu-id="154b0-208">In the code below, this is the variable `qsim`.</span></span>
2. <span data-ttu-id="154b0-209">Calcule todos os argumentos necessários do algoritmo quântico.</span><span class="sxs-lookup"><span data-stu-id="154b0-209">Compute any arguments required for the quantum algorithm.</span></span>
    <span data-ttu-id="154b0-210">Não há nenhum neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="154b0-210">There are none in this example.</span></span>
3. <span data-ttu-id="154b0-211">Execute o algoritmo quântico.</span><span class="sxs-lookup"><span data-stu-id="154b0-211">Run the quantum algorithm.</span></span> 
    <span data-ttu-id="154b0-212">Cada Q# operação gera uma classe C# com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="154b0-212">Each Q# operation generates a C# class with the same name.</span></span> 
    <span data-ttu-id="154b0-213">Esta classe possui um método `Run` que de forma **assíncrona** executa a operação.</span><span class="sxs-lookup"><span data-stu-id="154b0-213">This class has a `Run` method that **asynchronously** executes the operation.</span></span>
    <span data-ttu-id="154b0-214">A execução é assíncrona porque a execução no hardware real será assíncrona.</span><span class="sxs-lookup"><span data-stu-id="154b0-214">The execution is asynchronous because execution on actual hardware will be asynchronous.</span></span> 
    <span data-ttu-id="154b0-215">Como o `Run` método é assíncrona, chamamos o `Wait()` método; isto bloqueia a execução até que a tarefa complete e retorne o resultado de forma sincronizada.</span><span class="sxs-lookup"><span data-stu-id="154b0-215">Because the `Run` method is asynchronous, we call the `Wait()` method; this blocks execution until the task completes and returns the result synchronously.</span></span> 
4. <span data-ttu-id="154b0-216">Processe o resultado devolvido da operação.</span><span class="sxs-lookup"><span data-stu-id="154b0-216">Process the returned result of the operation.</span></span>
    <span data-ttu-id="154b0-217">Por enquanto, a operação não devolve nada.</span><span class="sxs-lookup"><span data-stu-id="154b0-217">For now, the operation returns nothing.</span></span>


```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                Perform3QubitQFT.Run(qsim).Wait();
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}

```
<span data-ttu-id="154b0-218">Executar a aplicação, e a sua saída deve corresponder a baixo.</span><span class="sxs-lookup"><span data-stu-id="154b0-218">Run the application, and your output should match that below.</span></span>
<span data-ttu-id="154b0-219">O programa será encerrado após premir uma tecla.</span><span class="sxs-lookup"><span data-stu-id="154b0-219">The program will exit after you press a key.</span></span>
***

```Output
Initial state |000>:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
After:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
```

<span data-ttu-id="154b0-220">Quando chamado ao simulador de estado inteiro, `DumpMachine()` fornece estas representações mutliple da função de onda do estado quântico.</span><span class="sxs-lookup"><span data-stu-id="154b0-220">When called on the full-state simulator, `DumpMachine()` provides these mutliple representations of the quantum state's wavefunction.</span></span> <span data-ttu-id="154b0-221">Os possíveis estados de um sistema de $n$-qubit podem ser representados por $2^n$ estados de base computacional, cada um com um coeficiente complexo correspondente (simplesmente uma amplitude e uma fase).</span><span class="sxs-lookup"><span data-stu-id="154b0-221">The possible states of an $n$-qubit system can be represented by $2^n$ computational basis states, each with a corresponding complex coefficient (simply an amplitude and a phase).</span></span>
<span data-ttu-id="154b0-222">Os estados de base computacional correspondem a todas as possíveis cadeias binárias de comprimento $n$--- ou seja, todas as combinações possíveis de qubits estados $\ket {0} $ e $\ket {1} $, onde cada dígito binário corresponde a um qubit individual.</span><span class="sxs-lookup"><span data-stu-id="154b0-222">The computational basis states correspond to all the possible binary strings of length $n$---that is, all the possible combinations of qubit states $\ket{0}$ and $\ket{1}$, where each binary digit corresponds to an individual qubit.</span></span>

<span data-ttu-id="154b0-223">A primeira linha fornece um comentário com os IDs dos qubits correspondentes na sua ordem significativa.</span><span class="sxs-lookup"><span data-stu-id="154b0-223">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="154b0-224">Qubit `2` ser o "mais significativo" significa simplesmente que na representação binária do vetor de estado de base $\ket{i}$, o estado do qubit `2` corresponde ao dígito mais à esquerda.</span><span class="sxs-lookup"><span data-stu-id="154b0-224">Qubit `2` being the "most significant" simply means that in the binary representation of basis state vector $\ket{i}$, the state of qubit `2` corresponds to the left-most digit.</span></span> <span data-ttu-id="154b0-225">Por exemplo, $\ket {6} = \ket {110} $ inclui qubits `2` e ambos em `1` $\ket {1} $ e qubit em `0` $\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="154b0-225">For example, $\ket{6} = \ket{110}$ comprises qubits `2` and `1` both in $\ket{1}$ and qubit `0` in $\ket{0}$.</span></span>


<span data-ttu-id="154b0-226">As restantes linhas descrevem a amplitude de probabilidade de medir o vetor de estado base $\ket{i}$ em formatos cartesianos e polares.</span><span class="sxs-lookup"><span data-stu-id="154b0-226">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{i}$ in both Cartesian and polar formats.</span></span>
<span data-ttu-id="154b0-227">Em detalhe para a primeira linha do nosso estado de entrada $\ket {000} $:</span><span class="sxs-lookup"><span data-stu-id="154b0-227">In detail for the first row of our input state $\ket{000}$:</span></span>
* <span data-ttu-id="154b0-228">**`|0>:`** esta linha corresponde ao `0` estado de base computacional (dado que a nossa pós-atribuição inicial do Estado era $\ket {000} $, esperamos que este seja o único estado com amplitude de probabilidade neste momento).</span><span class="sxs-lookup"><span data-stu-id="154b0-228">**`|0>:`** this row corresponds to the `0` computational basis state (given that our initial state post-allocation was $\ket{000}$, we would expect this to be the only state with probability amplitude at this point).</span></span>
* <span data-ttu-id="154b0-229">**`1.000000 +  0.000000 i`**: a amplitude de probabilidade no formato cartesiano.</span><span class="sxs-lookup"><span data-stu-id="154b0-229">**`1.000000 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="154b0-230">**` == `**: o `equal` sinal separa ambas as representações equivalentes.</span><span class="sxs-lookup"><span data-stu-id="154b0-230">**` == `**: the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="154b0-231">**`********************`**: Uma representação gráfica da magnitude, o número `*` de é proporcional à probabilidade de medir este vetor de estado.</span><span class="sxs-lookup"><span data-stu-id="154b0-231">**`********************`**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span> 
* <span data-ttu-id="154b0-232">**`[ 1.000000 ]`**: o valor numérico da magnitude</span><span class="sxs-lookup"><span data-stu-id="154b0-232">**`[ 1.000000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="154b0-233">**`    ---`**: Uma representação gráfica da fase da amplitude.</span><span class="sxs-lookup"><span data-stu-id="154b0-233">**`    ---`**: A graphical representation of the amplitude's phase.</span></span>
* <span data-ttu-id="154b0-234">**`[ 0.0000 rad ]`**: o valor numérico da fase (em radianos).</span><span class="sxs-lookup"><span data-stu-id="154b0-234">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="154b0-235">Tanto a magnitude como a fase são exibidas com uma representação gráfica.</span><span class="sxs-lookup"><span data-stu-id="154b0-235">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="154b0-236">A representação de magnitude é simples: mostra uma barra de `*` , e quanto maior a probabilidade, maior será a barra.</span><span class="sxs-lookup"><span data-stu-id="154b0-236">The magnitude representation is straightforward: it shows a bar of `*`, and the higher the probability, the larger the bar will be.</span></span> <span data-ttu-id="154b0-237">Para a fase, consulte [Teste e depuração: funções de despejo](xref:microsoft.quantum.guide.testingdebugging#dump-functions) para as possíveis representações de símbolos baseadas em intervalos de ângulo.</span><span class="sxs-lookup"><span data-stu-id="154b0-237">For the phase, see [Testing and debugging: dump functions](xref:microsoft.quantum.guide.testingdebugging#dump-functions) for the possible symbol representations based on angle ranges.</span></span>


<span data-ttu-id="154b0-238">Assim, a saída impressa está ilustrando que os nossos portões programados transformaram o nosso estado de</span><span class="sxs-lookup"><span data-stu-id="154b0-238">So, the printed output is illustrating that our programmed gates transformed our state from</span></span>

<span data-ttu-id="154b0-239">$$ \ket{\psi} \_ {initial} = \ket {000} $$</span><span class="sxs-lookup"><span data-stu-id="154b0-239">$$ \ket{\psi}\_{initial} = \ket{000} $$</span></span>

<span data-ttu-id="154b0-240">para</span><span class="sxs-lookup"><span data-stu-id="154b0-240">to</span></span> 

<span data-ttu-id="154b0-241">$$ \start{align} \ket{\psi} \_ {final} &= \frac {1} {\sqrt {8} } \ket {000} + \ket {001} + \ket {010} + \ket {011} + \ket {100} + \ket + \ket + \ket + \ket + \ket + \ket {101} + \ket {110} + \ket {111} \ket \right) \\ \\ &= \frac {1} {\sqrt{2^n}}\sum \_ {j=0}^{2^n-1} \ket{j}, \end{align} $$</span><span class="sxs-lookup"><span data-stu-id="154b0-241">$$ \begin{align} \ket{\psi}\_{final} &= \frac{1}{\sqrt{8}} \left( \ket{000} + \ket{001} + \ket{010} + \ket{011} + \ket{100} + \ket{101} + \ket{110} + \ket{111}  \right) \\\\ &= \frac{1}{\sqrt{2^n}}\sum\_{j=0}^{2^n-1} \ket{j}, \end{align} $$</span></span>

<span data-ttu-id="154b0-242">que é precisamente o comportamento da transformação de Fourier 3-qubit.</span><span class="sxs-lookup"><span data-stu-id="154b0-242">which is precisely the behavior of the 3-qubit Fourier transform.</span></span> 

<span data-ttu-id="154b0-243">Se está curioso sobre como outros estados de entrada são afetados, encorajamo-lo a brincar com a aplicação de operações de qubit antes da transformação.</span><span class="sxs-lookup"><span data-stu-id="154b0-243">If you are curious about how other input states are affected, we encourage you to play around with applying qubit operations before the transform.</span></span>

## <a name="adding-measurements"></a><span data-ttu-id="154b0-244">Adição de medições</span><span class="sxs-lookup"><span data-stu-id="154b0-244">Adding measurements</span></span>

<span data-ttu-id="154b0-245">Infelizmente, uma pedra angular da mecânica quântica diz-nos que um verdadeiro sistema quântico não pode ter tal `DumpMachine` função.</span><span class="sxs-lookup"><span data-stu-id="154b0-245">Unfortunately, a cornerstone of quantum mechanics tells us that a real quantum system cannot have such a `DumpMachine` function.</span></span> <span data-ttu-id="154b0-246">Em vez disso, somos forçados a extrair informação através de medições, que em geral não só não nos fornecem todo o estado quântico, como também podem alterar drasticamente o próprio sistema.</span><span class="sxs-lookup"><span data-stu-id="154b0-246">Instead, we're forced to extract information through measurements, which in general not only fail to provide us the full quantum state, but can also drastically alter the system itself.</span></span>
<span data-ttu-id="154b0-247">Existem muitos tipos de medições quânticas, mas vamos focar-nos nas mais básicas: medições projetivas em qubits únicos.</span><span class="sxs-lookup"><span data-stu-id="154b0-247">There are many sorts of quantum measurements, but we will focus on the most basic: projective measurements on single qubits.</span></span>
<span data-ttu-id="154b0-248">Após a medição numa determinada base (por exemplo, a base computacional $ \{ \ket {0} , \ket {1} \} $), o estado qubit é projetado para qualquer estado base medido---hence destruindo qualquer superposição entre os dois.</span><span class="sxs-lookup"><span data-stu-id="154b0-248">Upon measurement in a given basis (e.g. the computational basis $ \{ \ket{0}, \ket{1} \} $), the qubit state is projected onto whichever basis state was measured---hence destroying any superposition between the two.</span></span>

<span data-ttu-id="154b0-249">Para implementar medições dentro de um Q# programa, utilizamos a `M` operação (a partir `Microsoft.Quantum.Intrinsic` de), que devolve um `Result` tipo.</span><span class="sxs-lookup"><span data-stu-id="154b0-249">To implement measurements within a Q# program, we use the `M` operation (from `Microsoft.Quantum.Intrinsic`), which returns a `Result` type.</span></span>

<span data-ttu-id="154b0-250">Primeiro, modificamos a nossa `Perform3QubitQFT` operação para devolver uma série de resultados de medição, `Result[]` em vez de `Unit` .</span><span class="sxs-lookup"><span data-stu-id="154b0-250">First, we modify our `Perform3QubitQFT` operation to return an array of measurement results, `Result[]`, instead of `Unit`.</span></span>

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a><span data-ttu-id="154b0-251">Definir e inicializar `Result[]` matriz</span><span class="sxs-lookup"><span data-stu-id="154b0-251">Define and initialize `Result[]` array</span></span>

<span data-ttu-id="154b0-252">Antes mesmo de atribuir qubits (isto é, antes da `using` declaração), declaramos e ligamos este comprimento-3 matriz (um `Result` para cada qubit):</span><span class="sxs-lookup"><span data-stu-id="154b0-252">Before even allocating qubits (i.e. before the `using` statement), we declare and bind this length-3 array (one `Result` for each qubit):</span></span> 

```qsharp
        mutable resultArray = new Result[3];
```

<span data-ttu-id="154b0-253">A `mutable` pré-criação de `resultArray` palavras-chave permite que a variável seja recuperada mais tarde no código--- por exemplo, ao adicionar os resultados da nossa medição.</span><span class="sxs-lookup"><span data-stu-id="154b0-253">The `mutable` keyword prefacing `resultArray` allows the variable to be rebound later in the code---for example, when adding our measurement results.</span></span>

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a><span data-ttu-id="154b0-254">Executar medições em `for` loop e adicionar resultados à matriz</span><span class="sxs-lookup"><span data-stu-id="154b0-254">Perform measurements in a `for` loop and add results to array</span></span>

<span data-ttu-id="154b0-255">Depois da transformação fourier no interior do `using` bloco, insira o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="154b0-255">After the Fourier transform operations inside the `using` block, insert the following code:</span></span>

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
<span data-ttu-id="154b0-256">A [`IndexRange`](xref:microsoft.quantum.arrays.indexrange) função chamada numa matriz (por exemplo, a nossa matriz de qubits, `qs` ) devolve um intervalo sobre os índices da matriz.</span><span class="sxs-lookup"><span data-stu-id="154b0-256">The [`IndexRange`](xref:microsoft.quantum.arrays.indexrange) function called on an array (e.g. our array of qubits, `qs`) returns a range over the indices of the array.</span></span> <span data-ttu-id="154b0-257">Aqui, nós o usamos no nosso `for` loop para medir sequencialmente cada qubit usando a `M(qs[i])` declaração.</span><span class="sxs-lookup"><span data-stu-id="154b0-257">Here, we use it in our `for` loop to sequentially measure each qubit using the `M(qs[i])` statement.</span></span>
<span data-ttu-id="154b0-258">Cada tipo medido `Result` `Zero` (ou `One` ou ) é adicionado à posição de índice correspondente `resultArray` com uma declaração de atualização e reatribuição.</span><span class="sxs-lookup"><span data-stu-id="154b0-258">Each measured `Result` type (either `Zero` or `One`) is then added to the corresponding index position in `resultArray` with an update-and-reassign statement.</span></span>

> [!NOTE]
> <span data-ttu-id="154b0-259">A sintaxe desta afirmação é única Q# para, mas corresponde à reatribuição variável semelhante `resultArray[i] <- M(qs[i])` vista em outras línguas como F# e R.</span><span class="sxs-lookup"><span data-stu-id="154b0-259">The syntax of this statement is unique to Q#, but corresponds to the similar variable reassignment `resultArray[i] <- M(qs[i])` seen in other languages such as F# and R.</span></span>

<span data-ttu-id="154b0-260">A palavra-chave `set` é sempre usada para reatribuir variáveis ligadas através da utilização `mutable` .</span><span class="sxs-lookup"><span data-stu-id="154b0-260">The keyword `set` is always used to reassign variables bound using `mutable`.</span></span>

#### <a name="return-resultarray"></a><span data-ttu-id="154b0-261">Retorno`resultArray`</span><span class="sxs-lookup"><span data-stu-id="154b0-261">Return `resultArray`</span></span>

<span data-ttu-id="154b0-262">Com os três qubits medidos e os resultados `resultArray` adicionados, estamos seguros para repor e negociar os qubits como antes.</span><span class="sxs-lookup"><span data-stu-id="154b0-262">With all three qubits measured and the results added to `resultArray`, we are safe to reset and deallocate the qubits as before.</span></span>
<span data-ttu-id="154b0-263">Depois do `using` fecho do quarteirão, insira</span><span class="sxs-lookup"><span data-stu-id="154b0-263">After the `using` block's close, insert</span></span>

```qsharp
        return resultArray;
```
<span data-ttu-id="154b0-264">para, em última análise, devolver a saída da nossa operação.</span><span class="sxs-lookup"><span data-stu-id="154b0-264">to ultimately return the output of our operation.</span></span> 

### <a name="understanding-the-effects-of-measurement"></a><span data-ttu-id="154b0-265">Compreender os efeitos da medição</span><span class="sxs-lookup"><span data-stu-id="154b0-265">Understanding the effects of measurement</span></span>

<span data-ttu-id="154b0-266">Vamos alterar a colocação das `DumpMachine` nossas funções para a saída do estado antes e depois das medições.</span><span class="sxs-lookup"><span data-stu-id="154b0-266">Let's change the placement of our `DumpMachine` functions to output the state before and after the measurements.</span></span>
<span data-ttu-id="154b0-267">O código de operação final deve parecer:</span><span class="sxs-lookup"><span data-stu-id="154b0-267">The final operation code should look like:</span></span> 

```qsharp
    operation Perform3QubitQFT() : Result[] {

        mutable resultArray = new Result[3];

        using (qs = Qubit[3]) {

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("Before measurement: ");
            DumpMachine();

            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }

            Message("After measurement: ");
            DumpMachine();

            ResetAll(qs);
        }
        return resultArray;
    }
}
```

<span data-ttu-id="154b0-268">Se estiver a trabalhar a partir da linha de comando, a matriz devolvida será simplesmente impressa diretamente para a consola no final da execução.</span><span class="sxs-lookup"><span data-stu-id="154b0-268">If you are working from the command line, the returned array will simply be printed directly to the console at the end of the execution.</span></span>
<span data-ttu-id="154b0-269">Caso contrário, atualize o seu programa de anfitrião para processar a matriz devolvida.</span><span class="sxs-lookup"><span data-stu-id="154b0-269">Otherwise, update your host program to process the returned array.</span></span>

#### <a name="command-line"></a>[<span data-ttu-id="154b0-270">Linha de comandos</span><span class="sxs-lookup"><span data-stu-id="154b0-270">Command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="154b0-271">Para termos mais compreensão da matriz devolvida que será impressa na consola, podemos adicionar outra `Message` no ficheiro pouco antes da Q# `return` declaração:</span><span class="sxs-lookup"><span data-stu-id="154b0-271">To have more understanding of the returned array which will be printed in the console, we can add another `Message` in the Q# file just before the `return` statement:</span></span>

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

<span data-ttu-id="154b0-272">Executar o projeto, e a sua saída deve ser semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="154b0-272">Run the project, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]
```

#### <a name="python"></a>[<span data-ttu-id="154b0-273">Python</span><span class="sxs-lookup"><span data-stu-id="154b0-273">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="154b0-274">Atualize o seu programa Python para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="154b0-274">Update your Python program to the following:</span></span>

```python
import qsharp
from NamespaceQFT import Perform3QubitQFT

measurementResult = Perform3QubitQFT.simulate()
print("\n")
print("Measured post-QFT state: [qubit0, qubit1, qubit2]")
print(measurementResult)

# reversing order to show corresponding basis state in binary form
binaryCompBasisState = ""
for i in measurementResult:
    binaryCompBasisState = str(i) + binaryCompBasisState
print("Corresponding basis state in binary:")
print("|" + binaryCompBasisState + ">")
```

<span data-ttu-id="154b0-275">Execute o ficheiro e a sua saída deve ser semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="154b0-275">Run the file, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[1, 1, 0]

Corresponding basis state in binary:
|011>
```

#### <a name="c"></a>[<span data-ttu-id="154b0-276">C#</span><span class="sxs-lookup"><span data-stu-id="154b0-276">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="154b0-277">Agora que a nossa operação está a devolver um resultado, substitua a chamada de método `Wait()` por ir buscar a `Result` propriedade.</span><span class="sxs-lookup"><span data-stu-id="154b0-277">Now that our operation is returning a result, replace the method call `Wait()` with fetching the `Result` property.</span></span> <span data-ttu-id="154b0-278">Isto ainda realiza a mesma sincronização discutida anteriormente, e podemos ligar diretamente este valor à `measurementResult` variável.</span><span class="sxs-lookup"><span data-stu-id="154b0-278">This still accomplishes the same synchronicity discussed earlier, and we can directly bind this value to the variable `measurementResult`.</span></span>

```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                var measurementResult = Perform3QubitQFT.Run(qsim).Result;
                System.Console.WriteLine(
                    $"Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
                System.Console.WriteLine(
                    measurementResult);

                // reversing order to show corresponding basis state in binary form
                string binaryCompBasisState = String.Empty;

                foreach (Result i in measurementResult)
                {
                    string iString = i.ToString();
                    binaryCompBasisState = iString + binaryCompBasisState;
                }
                binaryCompBasisState = "|" + binaryCompBasisState + ">";
                System.Console.WriteLine(
                    $"Corresponding basis state in binary:");
                System.Console.WriteLine(
                    binaryCompBasisState);
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="154b0-279">Executar o projeto, e a sua saída deve ser semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="154b0-279">Run the project, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]

Corresponding basis state in binary:
|ZeroOneOne>

Press any key to continue...
```
***

<span data-ttu-id="154b0-280">Esta saída ilustra algumas coisas diferentes:</span><span class="sxs-lookup"><span data-stu-id="154b0-280">This output illustrates a few different things:</span></span>
1. <span data-ttu-id="154b0-281">Comparando o resultado devolvido com a pré-medição, `DumpMachine` claramente _não_ ilustra a sobreposição pós-QFT sobre estados de base.</span><span class="sxs-lookup"><span data-stu-id="154b0-281">Comparing the returned result to the pre-measurement `DumpMachine`, it clearly does _not_ illustrate the post-QFT superposition over basis states.</span></span>
    <span data-ttu-id="154b0-282">Uma medição apenas devolve um único estado base, com uma probabilidade determinada pela amplitude desse estado na função de onda do sistema.</span><span class="sxs-lookup"><span data-stu-id="154b0-282">A measurement only returns a single basis state, with a probability determined by the amplitude of that state in the system's wavefunction.</span></span>
2. <span data-ttu-id="154b0-283">A partir da pós-medição, `DumpMachine` vemos que a medição _muda_ o próprio estado, projetando-o desde a sobreposição inicial sobre estados base para o estado base único que corresponde ao valor medido.</span><span class="sxs-lookup"><span data-stu-id="154b0-283">From the post-measurement `DumpMachine`, we see that measurement _changes_ the state itself, projecting it from the initial superposition over basis states to the single basis state that corresponds to the measured value.</span></span>

<span data-ttu-id="154b0-284">Se repetissemos esta operação muitas vezes, veríamos as estatísticas dos resultados começarem a ilustrar a superposição igualmente ponderada do estado pós-QFT que dá origem a um resultado aleatório em cada disparo.</span><span class="sxs-lookup"><span data-stu-id="154b0-284">If we were to repeat this operation many times, we would see the result statistics begin to illustrate the equally weighted superposition of the post-QFT state that gives rise to a random result on each shot.</span></span>
<span data-ttu-id="154b0-285">_No entanto,_ além de ser ineficiente e ainda imperfeito, isso só reproduziria as amplitudes relativas dos estados de base, e não as fases relativas entre eles.</span><span class="sxs-lookup"><span data-stu-id="154b0-285">_However_, besides being inefficient and still imperfect, this would nevertheless only reproduce the relative amplitudes of the basis states, not the relative phases between them.</span></span>
<span data-ttu-id="154b0-286">Este último não é um problema neste exemplo, mas veríamos fases relativas aparecerem se lhes fosse dada uma entrada mais complexa para o QFT do que $\ket {000} $.</span><span class="sxs-lookup"><span data-stu-id="154b0-286">The latter is not an issue in this example, but we would see relative phases appear if given a more complex input to the QFT than $\ket{000}$.</span></span>

#### <a name="partial-measurements"></a><span data-ttu-id="154b0-287">Medições parciais</span><span class="sxs-lookup"><span data-stu-id="154b0-287">Partial measurements</span></span> 
<span data-ttu-id="154b0-288">Para explorar como a medição de apenas alguns qubits do registo pode afetar o estado do sistema, tente adicionar o seguinte dentro do `for` loop, após a linha de medição:</span><span class="sxs-lookup"><span data-stu-id="154b0-288">To explore how measuring only some qubits of the register can affect the system's state, try adding the following inside the `for` loop, after the measurement line:</span></span>
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

<span data-ttu-id="154b0-289">Note que para aceder à `IntAsString` função terá de adicionar</span><span class="sxs-lookup"><span data-stu-id="154b0-289">Note that to access the `IntAsString` function you will have to add</span></span> 
```qsharp
    open Microsoft.Quantum.Convert;
```
<span data-ttu-id="154b0-290">com o resto das declarações do espaço de `open` nome.</span><span class="sxs-lookup"><span data-stu-id="154b0-290">with the rest of the namespace `open` statements.</span></span>

<span data-ttu-id="154b0-291">Na saída resultante, você verá a projeção gradual em subespaços à medida que cada qubit é medido.</span><span class="sxs-lookup"><span data-stu-id="154b0-291">In the resulting output, you will see the gradual projection into subspaces as each qubit is measured.</span></span>


## <a name="use-the-no-locq-libraries"></a><span data-ttu-id="154b0-292">Use as Q# bibliotecas</span><span class="sxs-lookup"><span data-stu-id="154b0-292">Use the Q# libraries</span></span>
<span data-ttu-id="154b0-293">Como mencionamos na introdução, grande parte do poder assenta no facto de Q# permitir-lhe abstrair as preocupações de lidar com qubits individuais.</span><span class="sxs-lookup"><span data-stu-id="154b0-293">As we mentioned in the introduction, much of Q#'s power rests in the fact that it allows you to abstract-away the worries of dealing with individual qubits.</span></span>
<span data-ttu-id="154b0-294">Na verdade, se quiser desenvolver programas quânticos em larga escala, aplicáveis, preocupar-se se uma `H` operação vai antes ou depois de uma determinada rotação só o atrasaria.</span><span class="sxs-lookup"><span data-stu-id="154b0-294">Indeed, if you want to develop full-scale, applicable quantum programs, worrying about whether an `H` operation goes before or after a particular rotation would only slow you down.</span></span> 

<span data-ttu-id="154b0-295">As Q# bibliotecas contêm a operação [QFT,](xref:microsoft.quantum.canon.qft) que pode simplesmente tomar e solicitar qualquer número de qubits.</span><span class="sxs-lookup"><span data-stu-id="154b0-295">The Q# libraries contain the [QFT](xref:microsoft.quantum.canon.qft) operation, which you can simply take and apply for any number of qubits.</span></span>
<span data-ttu-id="154b0-296">Para tentar, defina uma nova operação no seu Q# ficheiro que tenha o mesmo conteúdo `Perform3QubitQFT` de, mas com tudo, desde o primeiro `H` até ao substituído por `SWAP` duas linhas fáceis:</span><span class="sxs-lookup"><span data-stu-id="154b0-296">To give it a try, define a new operation in your Q# file which has the same contents of `Perform3QubitQFT`, but with everything from the first `H` to the `SWAP` replaced by two easy lines:</span></span>
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
<span data-ttu-id="154b0-297">A primeira linha simplesmente cria uma [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) expressão da matriz de qubits atribuído, que é o que a `qs` operação [QFT](xref:microsoft.quantum.canon.qft) toma como argumento.</span><span class="sxs-lookup"><span data-stu-id="154b0-297">The first line simply creates a [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) expression of the allocated array of qubits, `qs`, which is what the [QFT](xref:microsoft.quantum.canon.qft) operation takes as an argument.</span></span>
<span data-ttu-id="154b0-298">Isto corresponde à ordem de índice dos qubits no registo.</span><span class="sxs-lookup"><span data-stu-id="154b0-298">This corresponds to index ordering of the qubits in the register.</span></span>

<span data-ttu-id="154b0-299">Para ter acesso a estas operações, adicione `open` declarações para os respetivos espaços de nome no início do Q# ficheiro:</span><span class="sxs-lookup"><span data-stu-id="154b0-299">To have access to these operations, add `open` statements for their respective namespaces at the beginning of the Q# file:</span></span>
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

<span data-ttu-id="154b0-300">Agora, ajuste o seu programa de anfitrião para chamar o nome da sua nova operação (por `PerformIntrinsicQFT` exemplo), e dê-lhe um giro.</span><span class="sxs-lookup"><span data-stu-id="154b0-300">Now, adjust your host program to call the name of your new operation (e.g. `PerformIntrinsicQFT`), and give it a whirl.</span></span>

<span data-ttu-id="154b0-301">Para ver o verdadeiro benefício da utilização das operações da Q# biblioteca, altere o número de qubits para outra coisa que `3` não:</span><span class="sxs-lookup"><span data-stu-id="154b0-301">To see the real benefit of using the Q# library operations, change the number of qubits to something other than `3`:</span></span>
```qsharp
        mutable resultArray = new Result[4]; 

        using (qs = Qubit[4]) {
            //...
        }
```
<span data-ttu-id="154b0-302">Pode assim aplicar o QFT adequado para qualquer número de qubits, sem ter que se preocupar com a confusão de novas `H` operações e rotações em cada qubit.</span><span class="sxs-lookup"><span data-stu-id="154b0-302">You can thus apply the proper QFT for any given number of qubits, without having to worry about the mess of new `H` operations and rotations on each qubit.</span></span>

<span data-ttu-id="154b0-303">Note que o simulador quântico leva exponencialmente mais tempo para correr à medida que aumenta o número de qubits---precisamente por que esperamos por hardware quântico real!</span><span class="sxs-lookup"><span data-stu-id="154b0-303">Note that the quantum simulator takes exponentially more time to run as you increase the number of qubits---precisely why we look forward to real quantum hardware!</span></span>













