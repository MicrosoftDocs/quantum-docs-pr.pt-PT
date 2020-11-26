---
title: Formas de executar um Q# programa
description: Visão geral das diferentes formas de executar Q# programas. A partir do pedido de comando, Q# Jupyter Notebooks, e programas de anfitrião clássicos em Python ou uma língua .NET.
author: gillenhaalb
ms.author: a-gibec
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2c5bdebc826bb85f6d7e0ade6232e15e29e8fb19
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231694"
---
# <a name="ways-to-run-a-no-locq-program"></a><span data-ttu-id="cdf68-104">Formas de executar um Q# programa</span><span class="sxs-lookup"><span data-stu-id="cdf68-104">Ways to run a Q# program</span></span>

<span data-ttu-id="cdf68-105">Um dos maiores pontos fortes do Kit de Desenvolvimento Quântico é a sua flexibilidade em plataformas e ambientes de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="cdf68-105">One of the Quantum Development Kit's greatest strengths is its flexibility across platforms and development environments.</span></span>
<span data-ttu-id="cdf68-106">No entanto, isto também significa que os novos Q# utilizadores podem encontrar-se confusos ou sobrecarregados com as inúmeras opções encontradas no [guia de instalação](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="cdf68-106">However, this also means that new Q# users may find themselves confused or overwhelmed by the numerous options found in the [install guide](xref:microsoft.quantum.install).</span></span>
<span data-ttu-id="cdf68-107">Nesta página, explicamos o que acontece quando um Q# programa é executado, e comparamos as diferentes formas de os utilizadores o poderem fazer.</span><span class="sxs-lookup"><span data-stu-id="cdf68-107">On this page, we explain what happens when a Q# program is run, and compare the different ways in which users can do so.</span></span>

<span data-ttu-id="cdf68-108">Uma distinção primária é que Q# pode ser executada:</span><span class="sxs-lookup"><span data-stu-id="cdf68-108">A primary distinction is that Q# can be run:</span></span>
- <span data-ttu-id="cdf68-109">como uma aplicação autónoma, onde Q# é a única língua envolvida e o programa é invocado diretamente.</span><span class="sxs-lookup"><span data-stu-id="cdf68-109">as a standalone application, where Q# is the only language involved and the program is invoked directly.</span></span> <span data-ttu-id="cdf68-110">Na verdade, dois métodos enquadram-se nesta categoria:</span><span class="sxs-lookup"><span data-stu-id="cdf68-110">Two methods actually fall in this category:</span></span>
  - <span data-ttu-id="cdf68-111">a interface de linha de comando</span><span class="sxs-lookup"><span data-stu-id="cdf68-111">the command-line interface</span></span>
  - <span data-ttu-id="cdf68-112">Q# Cadernos Jupyter</span><span class="sxs-lookup"><span data-stu-id="cdf68-112">Q# Jupyter Notebooks</span></span>
- <span data-ttu-id="cdf68-113">com um programa adicional *de anfitrião*, escrito em Python ou uma língua .NET (por exemplo, C# ou F#), que depois invoca o programa e pode processar mais resultados devolvidos.</span><span class="sxs-lookup"><span data-stu-id="cdf68-113">with an additional *host program*, written in Python or a .NET language (for example, C# or F#), which then invokes the program and can further process returned results.</span></span>

<span data-ttu-id="cdf68-114">Para melhor entender estes processos e as suas diferenças, consideramos um programa simples Q# e comparamos as formas de execução.</span><span class="sxs-lookup"><span data-stu-id="cdf68-114">To best understand these processes and their differences, we consider a simple Q# program and compare the ways it can be run.</span></span>

## <a name="basic-no-locq-program"></a><span data-ttu-id="cdf68-115">Programa Q# básico</span><span class="sxs-lookup"><span data-stu-id="cdf68-115">Basic Q# program</span></span>

<span data-ttu-id="cdf68-116">Um programa quântico básico pode consistir em preparar um qubit em uma superposição igual de Estados {0} $\ket $ e $\ket {1} $, medindo-o, e devolvendo o resultado, que será aleatoriamente qualquer um destes dois estados com igual probabilidade.</span><span class="sxs-lookup"><span data-stu-id="cdf68-116">A basic quantum program might consist of preparing a qubit in an equal superposition of states $\ket{0}$ and $\ket{1}$, measuring it, and returning the result, which will be randomly either one of these two states with equal probability.</span></span>
<span data-ttu-id="cdf68-117">Na verdade, este processo está no centro do rápido arranque do [gerador de números aleatórios quânticos.](xref:microsoft.quantum.quickstarts.qrng)</span><span class="sxs-lookup"><span data-stu-id="cdf68-117">Indeed, this process is at the core of the [quantum random number generator](xref:microsoft.quantum.quickstarts.qrng) quickstart.</span></span>

<span data-ttu-id="cdf68-118">Em Q# , isto seria realizado pelo seguinte código:</span><span class="sxs-lookup"><span data-stu-id="cdf68-118">In Q#, this would be performed by the following code:</span></span>

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

<span data-ttu-id="cdf68-119">No entanto, este código por si só não pode ser gerido Q# por.</span><span class="sxs-lookup"><span data-stu-id="cdf68-119">However, this code alone can't be run by Q#.</span></span>
<span data-ttu-id="cdf68-120">Para isso, tem de constituir o corpo de uma [operação](xref:microsoft.quantum.qsharp.operationsandfunctions), que é depois executada quando chamada--- direto ou por outra operação.</span><span class="sxs-lookup"><span data-stu-id="cdf68-120">For that, it needs to make up the body of an [operation](xref:microsoft.quantum.qsharp.operationsandfunctions), which is then run when called---either directly or by another operation.</span></span> <span data-ttu-id="cdf68-121">Assim, pode escrever uma operação do seguinte formulário:</span><span class="sxs-lookup"><span data-stu-id="cdf68-121">Hence, you can write an operation of the following form:</span></span>
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
<span data-ttu-id="cdf68-122">Definiu uma `MeasureSuperposition` operação, que não leva entradas e devolve um valor do tipo [Resultado](xref:microsoft.quantum.qsharp.typesystem-index#available-types).</span><span class="sxs-lookup"><span data-stu-id="cdf68-122">You have defined an operation, `MeasureSuperposition`, which takes no inputs and returns a value of type [Result](xref:microsoft.quantum.qsharp.typesystem-index#available-types).</span></span>

<span data-ttu-id="cdf68-123">Além das operações, Q# também permite encapsular computações determinísticas em funções.</span><span class="sxs-lookup"><span data-stu-id="cdf68-123">In addition to operations, Q# also allows to encapsulate deterministic computations into functions.</span></span> <span data-ttu-id="cdf68-124">Para além da garantia determinista que implica que os cálculos que atuam sobre os qubits precisam de ser encapsulados em operações e não em funções, há pouca diferença entre operações e função.</span><span class="sxs-lookup"><span data-stu-id="cdf68-124">Aside from the determinism guarantee that implies that computations that act on qubits need to be encapsulated into operations rather than functions, there is little difference between operations and function.</span></span> <span data-ttu-id="cdf68-125">Referimo-nos a eles colectivamente como *callables.*</span><span class="sxs-lookup"><span data-stu-id="cdf68-125">We refer to them collectively as *callables*.</span></span>

### <a name="callable-defined-in-a-no-locq-file"></a><span data-ttu-id="cdf68-126">Calável definido num Q# ficheiro</span><span class="sxs-lookup"><span data-stu-id="cdf68-126">Callable defined in a Q# file</span></span>

<span data-ttu-id="cdf68-127">O callable é precisamente o que é chamado e dirigido Q# por.</span><span class="sxs-lookup"><span data-stu-id="cdf68-127">The callable is precisely what's called and run by Q#.</span></span>
<span data-ttu-id="cdf68-128">No entanto, requer mais algumas adições para incluir um `*.qs` Q# ficheiro completo.</span><span class="sxs-lookup"><span data-stu-id="cdf68-128">However, it requires a few more additions to comprise a full `*.qs` Q# file.</span></span>

<span data-ttu-id="cdf68-129">Todos os Q# tipos e callables (tanto aqueles que define como os intrínsecos à língua) são definidos dentro *de espaços de nome,* que fornecem a cada um um nome completo que pode então ser referenciado.</span><span class="sxs-lookup"><span data-stu-id="cdf68-129">All Q# types and callables (both those you define and those intrinsic to the language) are defined within *namespaces*, which provide each a full name that can then be referenced.</span></span>

<span data-ttu-id="cdf68-130">Por exemplo, as [`H`](xref:Microsoft.Quantum.Intrinsic.H) operações e [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) as operações [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) encontram-se nos espaços e [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) nomes (parte das [ Q# Bibliotecas Padrão).](xref:microsoft.quantum.libraries.standard.intro)</span><span class="sxs-lookup"><span data-stu-id="cdf68-130">For example, the [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) operations are found in the [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) and [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) namespaces (part of the [Q# Standard Libraries](xref:microsoft.quantum.libraries.standard.intro)).</span></span>
<span data-ttu-id="cdf68-131">Como tal, podem sempre ser chamados através dos seus nomes *completos,* `Microsoft.Quantum.Intrinsic.H(<qubit>)` e , mas `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` fazê-lo sempre levaria a um código muito desordenado.</span><span class="sxs-lookup"><span data-stu-id="cdf68-131">As such, they can always be called via their *full* names, `Microsoft.Quantum.Intrinsic.H(<qubit>)` and `Microsoft.Quantum.Measurement.MResetZ(<qubit>)`, but always doing this would lead to very cluttered code.</span></span>

<span data-ttu-id="cdf68-132">Em vez disso, `open` as declarações permitem que os callables sejam referenciados com uma abreviatura mais concisa, como fizemos no corpo de operação acima.</span><span class="sxs-lookup"><span data-stu-id="cdf68-132">Instead, `open` statements allow callables to be referenced with more concise shorthand, as we've done in the operation body above.</span></span>
<span data-ttu-id="cdf68-133">O ficheiro completo Q# que contém a nossa operação consistiria, portanto, em definir o nosso próprio espaço de nome, abrindo os espaços de nome para os callables que a nossa operação utiliza e, em seguida, a nossa operação:</span><span class="sxs-lookup"><span data-stu-id="cdf68-133">The full Q# file containing our operation would therefore consist of defining our own namespace, opening the namespaces for those callables our operation uses, and then our operation:</span></span>

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="cdf68-134">Os espaços de nome também podem ser *aliased quando abertos,* o que pode ser útil se nomes callable/tipo em dois espaços de nome conflito.</span><span class="sxs-lookup"><span data-stu-id="cdf68-134">Namespaces can also be *aliased* when opened, which can be helpful if callable/type names in two namespaces conflict.</span></span>
> <span data-ttu-id="cdf68-135">Por exemplo, poderíamos, em vez disso, usar `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` acima, e depois ligar `H` via `NamespaceWithH.H(<qubit>)` .</span><span class="sxs-lookup"><span data-stu-id="cdf68-135">For example, we could instead use `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` above, and then call `H` via `NamespaceWithH.H(<qubit>)`.</span></span>

> [!NOTE]
> <span data-ttu-id="cdf68-136">Uma exceção a tudo isto é o espaço de [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) nome, que é sempre automaticamente aberto.</span><span class="sxs-lookup"><span data-stu-id="cdf68-136">One exception to all of this is the [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) namespace, which is always automatically opened.</span></span>
> <span data-ttu-id="cdf68-137">Portanto, os calíveis como [`Length`](xref:Microsoft.Quantum.Core.Length) podem sempre ser usados diretamente.</span><span class="sxs-lookup"><span data-stu-id="cdf68-137">Therefore, callables like [`Length`](xref:Microsoft.Quantum.Core.Length) can always be used directly.</span></span>

### <a name="running-on-target-machines"></a><span data-ttu-id="cdf68-138">Correndo em máquinas-alvo</span><span class="sxs-lookup"><span data-stu-id="cdf68-138">Running on target machines</span></span>

<span data-ttu-id="cdf68-139">Agora o modelo de execução geral de um Q# programa torna-se claro.</span><span class="sxs-lookup"><span data-stu-id="cdf68-139">Now the general run model of a Q# program becomes clear.</span></span>

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

<span data-ttu-id="cdf68-140">Em primeiro lugar, a chamada específica a ser executada tem acesso a quaisquer outros calíveis e tipos definidos no mesmo espaço de nome.</span><span class="sxs-lookup"><span data-stu-id="cdf68-140">Firstly, the specific callable to be run has access to any other callables and types defined in the same namespace.</span></span>
<span data-ttu-id="cdf68-141">Também acede às que provêm de qualquer uma das [ Q# bibliotecas](xref:microsoft.quantum.libraries), mas estas devem ser referenciadas quer através do seu nome completo, quer através da utilização de `open` declarações acima descritas.</span><span class="sxs-lookup"><span data-stu-id="cdf68-141">It also access those from any of the [Q# libraries](xref:microsoft.quantum.libraries), but those must be referenced either via their full name, or through the use of `open` statements described above.</span></span>

<span data-ttu-id="cdf68-142">A própria chamada é então executada numa *[máquina-alvo](xref:microsoft.quantum.machines)*.</span><span class="sxs-lookup"><span data-stu-id="cdf68-142">The callable itself is then run on a *[target machine](xref:microsoft.quantum.machines)*.</span></span>
<span data-ttu-id="cdf68-143">Tais máquinas-alvo podem ser hardware quântico real ou os múltiplos simuladores disponíveis como parte do QDK.</span><span class="sxs-lookup"><span data-stu-id="cdf68-143">Such target machines can be actual quantum hardware or the multiple simulators available as part of the QDK.</span></span>
<span data-ttu-id="cdf68-144">Para os nossos propósitos aqui, a máquina alvo mais útil é um exemplo do [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator) `QuantumSimulator` , que calcula o comportamento do programa como se estivesse sendo executado em um computador quântico sem ruído.</span><span class="sxs-lookup"><span data-stu-id="cdf68-144">For our purposes here, the most useful target machine is an instance of the [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator`, which calculates the program's behavior as if it were being run on a noise-free quantum computer.</span></span>

<span data-ttu-id="cdf68-145">Até agora, descrevemos o que acontece quando uma chamada específica Q# está a ser executada.</span><span class="sxs-lookup"><span data-stu-id="cdf68-145">So far, we've described what happens when a specific Q# callable is being run.</span></span>
<span data-ttu-id="cdf68-146">Independentemente de ser Q# usado numa aplicação autónoma ou com um programa de acolhimento, este processo geral é mais ou menos o mesmo---a flexibilidade do QDK.</span><span class="sxs-lookup"><span data-stu-id="cdf68-146">Regardless of whether Q# is used in a standalone application or with a host program, this general process is more or less the same---hence the QDK's flexibility.</span></span>
<span data-ttu-id="cdf68-147">As diferenças entre as formas de chamar para o Kit de Desenvolvimento Quântico revelam-se, portanto, na *forma como* essa chamada é chamada a Q# ser executada, e de que forma quaisquer resultados são devolvidos.</span><span class="sxs-lookup"><span data-stu-id="cdf68-147">The differences between the ways of calling into the Quantum Development Kit therefore reveal themselves in *how* that Q# callable is called to be run, and in what manner any results are returned.</span></span>
<span data-ttu-id="cdf68-148">Mais especificamente, as diferenças giram em torno de:</span><span class="sxs-lookup"><span data-stu-id="cdf68-148">More specifically, the differences revolve around:</span></span>

- <span data-ttu-id="cdf68-149">Indicando qual Q# é o chamado a ser executado</span><span class="sxs-lookup"><span data-stu-id="cdf68-149">Indicating which Q# callable is to be run</span></span>
- <span data-ttu-id="cdf68-150">Como potenciais argumentos caláveis são fornecidos</span><span class="sxs-lookup"><span data-stu-id="cdf68-150">How potential callable arguments are provided</span></span>
- <span data-ttu-id="cdf68-151">Especificando a máquina-alvo em que a executar</span><span class="sxs-lookup"><span data-stu-id="cdf68-151">Specifying the target machine on which to run it</span></span>
- <span data-ttu-id="cdf68-152">Como quaisquer resultados são devolvidos</span><span class="sxs-lookup"><span data-stu-id="cdf68-152">How any results are returned</span></span>

<span data-ttu-id="cdf68-153">Primeiro, discutimos como isto é feito com a Q# aplicação autónoma a partir do pedido de comando, e depois procedemos à utilização de programas de anfitriões Python e C#.</span><span class="sxs-lookup"><span data-stu-id="cdf68-153">First, we discuss how this is done with the Q# standalone application from the command prompt, and then proceed to using Python and C# host programs.</span></span>
<span data-ttu-id="cdf68-154">Reservamos a aplicação autónoma de Q# Cadernos Jupyter para o final, porque ao contrário dos três primeiros, a sua funcionalidade primária não se centra em torno de um Q# arquivo local.</span><span class="sxs-lookup"><span data-stu-id="cdf68-154">We reserve the standalone application of Q# Jupyter Notebooks for last, because unlike the first three, it's primary functionality does not center around a local Q# file.</span></span>

> [!NOTE]
> <span data-ttu-id="cdf68-155">Embora não o ilustremos nestes exemplos, uma comunhão entre os métodos de execução é que quaisquer mensagens impressas a partir de dentro do Q# programa (por [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) exemplo) serão normalmente impressas na respetiva consola.</span><span class="sxs-lookup"><span data-stu-id="cdf68-155">Although we don't illustrate it in these examples, one commonality between the run methods is that any messages printed from inside the Q# program (by way of [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) or [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine), for example) will typically always be printed to the respective console.</span></span>

## <a name="no-locq-from-the-command-prompt"></a><span data-ttu-id="cdf68-156">Q# a partir da pronta de comando</span><span class="sxs-lookup"><span data-stu-id="cdf68-156">Q# from the command prompt</span></span>
<span data-ttu-id="cdf68-157">Uma das formas mais fáceis de começar a escrever Q# programas é evitar preocupar-se com ficheiros separados e uma segunda língua completamente.</span><span class="sxs-lookup"><span data-stu-id="cdf68-157">One of the easiest ways to get started writing Q# programs is to avoid worrying about separate files and a second language altogether.</span></span>
<span data-ttu-id="cdf68-158">A utilização do Visual Studio Code ou do Visual Studio com a extensão QDK permite um fluxo de trabalho sem emenda no qual executamos Q# callables a partir de apenas um Q# ficheiro.</span><span class="sxs-lookup"><span data-stu-id="cdf68-158">Using Visual Studio Code or Visual Studio with the QDK extension allows for a seamless work flow in which we run Q# callables from only a single Q# file.</span></span>

<span data-ttu-id="cdf68-159">Para isso, vamos, em última análise, executar o programa entrando</span><span class="sxs-lookup"><span data-stu-id="cdf68-159">For this, we will ultimately run the program by entering</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="cdf68-160">no pedido de comando.</span><span class="sxs-lookup"><span data-stu-id="cdf68-160">at the command prompt.</span></span>
<span data-ttu-id="cdf68-161">O fluxo de trabalho mais simples é quando a localização do diretório do terminal é a mesma que o Q# ficheiro, que pode ser facilmente manuseado ao lado Q# da edição de ficheiros utilizando o terminal integrado no Código VS, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="cdf68-161">The simplest workflow is when the terminal's directory location is the same as the Q# file, which can be easily handled alongside Q# file editing by using the integrated terminal in VS Code, for example.</span></span>
<span data-ttu-id="cdf68-162">No entanto, o [ `dotnet run` comando](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) aceita inúmeras opções, e o programa também pode ser executado a partir de um local diferente, simplesmente fornecendo `--project <PATH>` a localização do Q# ficheiro.</span><span class="sxs-lookup"><span data-stu-id="cdf68-162">However, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepts numerous options, and the program can also be run from a different location by simply providing `--project <PATH>` with the location of the Q# file.</span></span>


### <a name="add-entry-point-to-no-locq-file"></a><span data-ttu-id="cdf68-163">Adicionar ponto de entrada para Q# arquivar</span><span class="sxs-lookup"><span data-stu-id="cdf68-163">Add entry point to Q# file</span></span>

<span data-ttu-id="cdf68-164">A maioria dos Q# ficheiros conterá mais do que uma chamada, por isso, naturalmente, precisamos de informar o compilador *sobre qual* a chamada a executar quando fornecessarmos o `dotnet run` comando.</span><span class="sxs-lookup"><span data-stu-id="cdf68-164">Most Q# files will contain more than one callable, so naturally we need to let the compiler know *which* callable to run when we provide the `dotnet run` command.</span></span>
<span data-ttu-id="cdf68-165">Isto é feito com uma simples alteração ao Q# próprio ficheiro:</span><span class="sxs-lookup"><span data-stu-id="cdf68-165">This is done with a simple change to the Q# file itself:</span></span> 
    - <span data-ttu-id="cdf68-166">adicionar uma linha com `@EntryPoint()` diretamente precedendo o callable.</span><span class="sxs-lookup"><span data-stu-id="cdf68-166">add a line with `@EntryPoint()` directly preceding the callable.</span></span>

<span data-ttu-id="cdf68-167">Nosso arquivo de cima seria, portanto, tornar-se</span><span class="sxs-lookup"><span data-stu-id="cdf68-167">Our file from above would therefore become</span></span>
```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    @EntryPoint()
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

<span data-ttu-id="cdf68-168">Agora, uma chamada `dotnet run` do pedido de comando leva a ser `MeasureSuperposition` executado, e o valor devolvido é então impresso diretamente para o terminal.</span><span class="sxs-lookup"><span data-stu-id="cdf68-168">Now, a call of `dotnet run` from the command prompt leads to `MeasureSuperposition` being run, and the returned value is then printed directly to the terminal.</span></span>
<span data-ttu-id="cdf68-169">Então, verá um `One` ou `Zero` impresso.</span><span class="sxs-lookup"><span data-stu-id="cdf68-169">So, you will see either `One` or `Zero` printed.</span></span> 

<span data-ttu-id="cdf68-170">Note que não importa se tiver mais chamadas definidas abaixo, apenas `MeasureSuperposition` será executado.</span><span class="sxs-lookup"><span data-stu-id="cdf68-170">Note that it doesn't matter if you have more callables defined below it, only `MeasureSuperposition` will be run.</span></span>
<span data-ttu-id="cdf68-171">Além disso, não é problema se a sua chamada inclui comentários de [documentação](xref:microsoft.quantum.qsharp.comments#documentation-comments) antes da sua declaração, o `@EntryPoint()` atributo pode simplesmente ser colocado acima deles.</span><span class="sxs-lookup"><span data-stu-id="cdf68-171">Additionally, it's no problem if your callable includes [documentation comments](xref:microsoft.quantum.qsharp.comments#documentation-comments) before its declaration, the `@EntryPoint()` attribute can be simply placed above them.</span></span>

### <a name="callable-arguments"></a><span data-ttu-id="cdf68-172">Argumentos insutilizáveis</span><span class="sxs-lookup"><span data-stu-id="cdf68-172">Callable arguments</span></span>

<span data-ttu-id="cdf68-173">Até agora, só consideramos uma operação que não tem entradas.</span><span class="sxs-lookup"><span data-stu-id="cdf68-173">So far, we've only considered an operation that takes no inputs.</span></span>
<span data-ttu-id="cdf68-174">Suponha que quiséssemos realizar uma operação semelhante, mas em múltiplos qubits---o número do qual é fornecido como argumento.</span><span class="sxs-lookup"><span data-stu-id="cdf68-174">Suppose we wanted to perform a similar operation, but on multiple qubits---the number of which is provided as an argument.</span></span>
<span data-ttu-id="cdf68-175">Tal operação poderia ser escrito como</span><span class="sxs-lookup"><span data-stu-id="cdf68-175">Such an operation could be written as</span></span>
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
<span data-ttu-id="cdf68-176">onde o valor devolvido é um conjunto dos resultados da medição.</span><span class="sxs-lookup"><span data-stu-id="cdf68-176">where the returned value is an array of the measurement results.</span></span>
<span data-ttu-id="cdf68-177">Note que [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) e [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) estão nos [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) espaços e [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) nomes, exigindo declarações adicionais `open` para cada um.</span><span class="sxs-lookup"><span data-stu-id="cdf68-177">Note that [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) and [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) are in the [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) and [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) namespaces, requiring additional `open` statements for each.</span></span>

<span data-ttu-id="cdf68-178">Se movermos o `@EntryPoint()` atributo para preceder esta nova operação (note que só pode haver uma dessas linhas num ficheiro), tentar executá-lo simplesmente `dotnet run` resulta numa mensagem de erro que indica quais as opções adicionais da linha de comando e como expressá-las.</span><span class="sxs-lookup"><span data-stu-id="cdf68-178">If we move the `@EntryPoint()` attribute to precede this new operation (note there can only be one such line in a file), attempting to run it with simply `dotnet run` results in an error message which indicates what additional command-line options are required, and how to express them.</span></span>

<span data-ttu-id="cdf68-179">O formato geral da linha de comando é, na `dotnet run [options]` verdade, e os argumentos callable são fornecidos lá.</span><span class="sxs-lookup"><span data-stu-id="cdf68-179">The general format for the command line is actually `dotnet run [options]`, and callable arguments are provided there.</span></span>
<span data-ttu-id="cdf68-180">Neste caso, falta o `n` argumento, e mostra que temos de fornecer a opção. `-n <n>`</span><span class="sxs-lookup"><span data-stu-id="cdf68-180">In this case, the argument `n` is missing, and it shows that we need to provide the option `-n <n>`.</span></span> <span data-ttu-id="cdf68-181">Para correr `MeasureSuperpositionArray` para `n=4` qubits, portanto usamos</span><span class="sxs-lookup"><span data-stu-id="cdf68-181">To run `MeasureSuperpositionArray` for `n=4` qubits, we therefore use</span></span>

```dotnetcli
dotnet run -n 4
```

<span data-ttu-id="cdf68-182">produzindo uma saída semelhante a</span><span class="sxs-lookup"><span data-stu-id="cdf68-182">yielding an output similar to</span></span>

```output
[Zero,One,One,One]
```

<span data-ttu-id="cdf68-183">Isto, naturalmente, estende-se a múltiplos argumentos.</span><span class="sxs-lookup"><span data-stu-id="cdf68-183">This of course extends to multiple arguments.</span></span>

> [!NOTE]
> <span data-ttu-id="cdf68-184">Os nomes de argumentos `camelCase` definidos são ligeiramente alterados pelo compilador para serem aceites como Q# entradas.</span><span class="sxs-lookup"><span data-stu-id="cdf68-184">Argument names defined in `camelCase` are slightly altered by the compiler to be accepted as Q# inputs.</span></span> <span data-ttu-id="cdf68-185">Por exemplo, se em vez `n` de, nós usamos o nome `numQubits` acima, então esta entrada seria fornecida na linha de comando via `--num-qubits 4` em vez de `-n 4` .</span><span class="sxs-lookup"><span data-stu-id="cdf68-185">For example, if instead of `n`, we used the name `numQubits` above, then this input would be provided in the command line via `--num-qubits 4` instead of `-n 4`.</span></span>

<span data-ttu-id="cdf68-186">A mensagem de erro também fornece outras opções que podem ser usadas, incluindo como alterar a máquina-alvo.</span><span class="sxs-lookup"><span data-stu-id="cdf68-186">The error message also provides other options which can be used, including how to change the target machine.</span></span>

### <a name="different-target-machines"></a><span data-ttu-id="cdf68-187">Diferentes máquinas-alvo</span><span class="sxs-lookup"><span data-stu-id="cdf68-187">Different target machines</span></span>

<span data-ttu-id="cdf68-188">Como as saídas das nossas operações até agora têm sido os resultados esperados da sua ação em qubits reais, é claro que a máquina-alvo padrão da linha de comando é o simulador quântico de estado completo, `QuantumSimulator` .</span><span class="sxs-lookup"><span data-stu-id="cdf68-188">As the outputs from our operations thus far have been the expected results of their action on real qubits, it's clear that the default target machine from the command line is the full-state quantum simulator, `QuantumSimulator`.</span></span>
<span data-ttu-id="cdf68-189">No entanto, podemos instruir os callables a serem executados numa máquina-alvo específica com a opção `--simulator` (ou a abreviatura). `-s`</span><span class="sxs-lookup"><span data-stu-id="cdf68-189">However, we can instruct callables to be run on a specific target machine with the option `--simulator` (or the shorthand `-s`).</span></span>

<span data-ttu-id="cdf68-190">Por exemplo, poderíamos executá-lo [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) em:</span><span class="sxs-lookup"><span data-stu-id="cdf68-190">For example, we could run it on [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator):</span></span>

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

<span data-ttu-id="cdf68-191">A saída impressa é então</span><span class="sxs-lookup"><span data-stu-id="cdf68-191">The printed output is then</span></span>

```output
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

<span data-ttu-id="cdf68-192">Para obter mais informações sobre o que estas métricas indicam, consulte [o estimador de recursos: métricas reportadas](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span><span class="sxs-lookup"><span data-stu-id="cdf68-192">For details on what these metrics indicate, see [Resource estimator: metrics reported](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span></span>

### <a name="command-line-run-summary"></a><span data-ttu-id="cdf68-193">Resumo da linha de comando</span><span class="sxs-lookup"><span data-stu-id="cdf68-193">Command line run summary</span></span>
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-no-locq-dotnet-run-options"></a><span data-ttu-id="cdf68-194">Q# `dotnet run` Não-opções</span><span class="sxs-lookup"><span data-stu-id="cdf68-194">Non-Q# `dotnet run` options</span></span>

<span data-ttu-id="cdf68-195">Como mencionamos brevemente acima com a `--project` opção, o [ `dotnet run` comando](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) também aceita opções não relacionadas com os Q# argumentos caláveis.</span><span class="sxs-lookup"><span data-stu-id="cdf68-195">As we briefly mentioned above with the `--project` option, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) also accepts options unrelated to the Q# callable arguments.</span></span>
<span data-ttu-id="cdf68-196">Se fornecer ambos os tipos de opções, as `dotnet` opções específicas devem ser fornecidas primeiro, seguidas por um delimetro `--` , e depois as Q# opções específicas.</span><span class="sxs-lookup"><span data-stu-id="cdf68-196">If providing both kinds of options, the `dotnet`-specific options must be provided first, followed by a delimeter `--`, and then the Q#-specific options.</span></span>
<span data-ttu-id="cdf68-197">Por exemplo, especificar um caminho juntamente com um número de qubits para a operação acima seria executado via `dotnet run --project <PATH> -- -n <n>` .</span><span class="sxs-lookup"><span data-stu-id="cdf68-197">For example, specifying a path along with a number qubits for the operation above would be run via `dotnet run --project <PATH> -- -n <n>`.</span></span>

## <a name="no-locq-with-host-programs"></a><span data-ttu-id="cdf68-198">Q# com programas de anfitrião</span><span class="sxs-lookup"><span data-stu-id="cdf68-198">Q# with host programs</span></span>

<span data-ttu-id="cdf68-199">Com o nosso Q# ficheiro na mão, uma alternativa para chamar uma operação ou funcionar diretamente a partir do pedido de comando é usar um *programa de anfitrião* em outra língua clássica.</span><span class="sxs-lookup"><span data-stu-id="cdf68-199">With our Q# file in hand, an alternative to calling an operation or function directly from the command prompt is to use a *host program* in another classical language.</span></span> <span data-ttu-id="cdf68-200">Especificamente, isto pode ser feito com python ou uma língua .NET como C# ou F# (por uma questão de brevidade só vamos detalhar C# aqui).</span><span class="sxs-lookup"><span data-stu-id="cdf68-200">Specifically, this can be done with either Python or a .NET language such as C# or F# (for the sake of brevity we will only detail C# here).</span></span>
<span data-ttu-id="cdf68-201">É necessário um pouco mais de configuração para permitir a interoperabilidade, mas esses detalhes podem ser encontrados nos [guias de instalação](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="cdf68-201">A little more setup is required to enable the interoperability, but those details can be found in the [install guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="cdf68-202">Em resumo, a situação agora inclui um ficheiro de programa de anfitrião (por exemplo, `*.py` `*.cs` ou) no mesmo local que o nosso Q# ficheiro.</span><span class="sxs-lookup"><span data-stu-id="cdf68-202">In a nutshell, the situation now includes a host program file (for example, `*.py` or `*.cs`) in the same location as our Q# file.</span></span>
<span data-ttu-id="cdf68-203">É agora o programa *de anfitrião* que é executado, e enquanto está em execução, pode chamar Q# operações e funções específicas do Q# ficheiro.</span><span class="sxs-lookup"><span data-stu-id="cdf68-203">It's now the *host* program that gets run, and while it is running, it can call specific Q# operations and functions from the Q# file.</span></span>
<span data-ttu-id="cdf68-204">O núcleo da interoperabilidade baseia-se no Q# compilador que torna o conteúdo do Q# ficheiro acessível ao programa anfitrião para que possam ser chamados.</span><span class="sxs-lookup"><span data-stu-id="cdf68-204">The core of the interoperability is based on the Q# compiler making the contents of the Q# file accessible to the host program so that they can be called.</span></span>

<span data-ttu-id="cdf68-205">Um dos principais benefícios da utilização de um programa de anfitrião é que os dados clássicos devolvidos pelo Q# programa podem então ser processados na língua de acolhimento.</span><span class="sxs-lookup"><span data-stu-id="cdf68-205">One of the main benefits of using a host program is that the classical data returned by the Q# program can then be further processed in the host language.</span></span>
<span data-ttu-id="cdf68-206">Isto poderia consistir em algum processamento avançado de dados (por exemplo, algo que não pode ser realizado internamente), e, em Q# seguida, chamar mais Q# ações com base nesses resultados, ou algo tão simples como traçar os Q# resultados.</span><span class="sxs-lookup"><span data-stu-id="cdf68-206">This could consist of some advanced data processing (for example, something that can't be performed internally in Q#), and then calling further Q# actions based on those results, or something as simple as plotting the Q# results.</span></span>

<span data-ttu-id="cdf68-207">O esquema geral é mostrado aqui, e discutimos as implementações específicas para Python e C# abaixo.</span><span class="sxs-lookup"><span data-stu-id="cdf68-207">The general scheme is shown here, and we discuss the specific implementations for Python and C# below.</span></span> <span data-ttu-id="cdf68-208">Uma amostra utilizando um programa de anfitrião F# pode ser encontrada nas [amostras de interoperabilidade .NET](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="cdf68-208">A sample using an F# host program can be found at the [.NET interoperability samples](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> <span data-ttu-id="cdf68-209">O `@EntryPoint()` atributo utilizado para Q# aplicações não pode ser utilizado com programas de anfitrião.</span><span class="sxs-lookup"><span data-stu-id="cdf68-209">The `@EntryPoint()` attribute used for Q# applications cannot be used with host programs.</span></span>
> <span data-ttu-id="cdf68-210">Um erro será levantado se estiver presente no Q# ficheiro sendo chamado por um anfitrião.</span><span class="sxs-lookup"><span data-stu-id="cdf68-210">An error will be raised if it is present in the Q# file being called by a host.</span></span> 

<span data-ttu-id="cdf68-211">Para trabalhar com diferentes programas de anfitrião, não são necessárias alterações a um `*.qs` Q# ficheiro.</span><span class="sxs-lookup"><span data-stu-id="cdf68-211">To work with different host programs, there are no changes required to a `*.qs` Q# file.</span></span>
<span data-ttu-id="cdf68-212">As seguintes implementações do programa anfitrião funcionam com o mesmo Q# ficheiro:</span><span class="sxs-lookup"><span data-stu-id="cdf68-212">The following host program implementations all work with the same Q# file:</span></span>

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // contains H
    open Microsoft.Quantum.Measurement;   // MResetZ
    open Microsoft.Quantum.Canon;         // ApplyToEach
    open Microsoft.Quantum.Arrays;        // ForEach

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }

    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {  
            ApplyToEach(H, qubits); 
            return ForEach(MResetZ, qubits);    
        }
    }
}
```

<span data-ttu-id="cdf68-213">Selecione o separador correspondente ao seu idioma de interesse anfitrião.</span><span class="sxs-lookup"><span data-stu-id="cdf68-213">Select the tab corresponding to your host language of interest.</span></span>

### <a name="python"></a>[<span data-ttu-id="cdf68-214">Python</span><span class="sxs-lookup"><span data-stu-id="cdf68-214">Python</span></span>](#tab/tabid-python)
<span data-ttu-id="cdf68-215">Um programa de anfitrião Python é construído da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="cdf68-215">A Python host program is constructed as follows:</span></span>
1. <span data-ttu-id="cdf68-216">Importe o `qsharp` módulo, que regista o carregador de módulos para Q# interoperabilidade.</span><span class="sxs-lookup"><span data-stu-id="cdf68-216">Import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="cdf68-217">Isto permite que Q# os espaços de nome apareçam como módulos Python, a partir dos quais podemos "importar" Q# callables.</span><span class="sxs-lookup"><span data-stu-id="cdf68-217">This allows Q# namespaces to appear as Python modules, from which we can "import" Q# callables.</span></span>
    <span data-ttu-id="cdf68-218">Note-se que, tecnicamente, não são os Q# próprios callables que são importados, mas sim os canhotos Python que permitem chamá-los.</span><span class="sxs-lookup"><span data-stu-id="cdf68-218">Note that it is technically not the Q# callables themselves which are imported, but rather Python stubs which allow calling into them.</span></span>
    <span data-ttu-id="cdf68-219">Estes comportam-se como objetos das aulas de Python.</span><span class="sxs-lookup"><span data-stu-id="cdf68-219">These behave as objects of Python classes.</span></span> <span data-ttu-id="cdf68-220">Utilizamos métodos nestes objetos para especificar as máquinas-alvo para as quais enviamos a operação quando executamos o programa.</span><span class="sxs-lookup"><span data-stu-id="cdf68-220">We use methods on these objects to specify the target machines that we send the operation to when running the program.</span></span>

2. <span data-ttu-id="cdf68-221">Importe os Q# calíveis que invocaremos directamente--- neste caso, `MeasureSuperposition` `MeasureSuperpositionArray` e.</span><span class="sxs-lookup"><span data-stu-id="cdf68-221">Import those Q# callables which we will directly invoke---in this case, `MeasureSuperposition` and `MeasureSuperpositionArray`.</span></span>
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    <span data-ttu-id="cdf68-222">Com o `qsharp` módulo importado, também pode importar callables diretamente dos espaços de nome da Q# biblioteca.</span><span class="sxs-lookup"><span data-stu-id="cdf68-222">With the `qsharp` module imported, you can also import callables directly from the Q# library namespaces.</span></span>

3. <span data-ttu-id="cdf68-223">Entre qualquer outro código Python, pode agora ligar para as chamadas em máquinas-alvo específicas e atribuir os seus retornos a variáveis (se devolverem um valor) para posterior utilização.</span><span class="sxs-lookup"><span data-stu-id="cdf68-223">Among any other Python code, you can now call those callables on specific target machines, and assign their returns to variables (if they return a value) for further use.</span></span>

#### <a name="specifying-target-machines"></a><span data-ttu-id="cdf68-224">Especificar máquinas-alvo</span><span class="sxs-lookup"><span data-stu-id="cdf68-224">Specifying target machines</span></span>
<span data-ttu-id="cdf68-225">Chamar uma operação a ser executada numa máquina-alvo específica é feita através de diferentes métodos Python no objeto importado.</span><span class="sxs-lookup"><span data-stu-id="cdf68-225">Calling an operation to be run on a specific target machine is done via different Python methods on the imported object.</span></span>
<span data-ttu-id="cdf68-226">Por `.simulate(<args>)` exemplo, usa o `QuantumSimulator` para executar a operação, enquanto `.estimate_resources(<args>)` o faz no `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="cdf68-226">For example, `.simulate(<args>)`, uses the `QuantumSimulator` to run the operation, whereas `.estimate_resources(<args>)` does so on the `ResourcesEstimator`.</span></span>

#### <a name="passing-inputs-to-q"></a><span data-ttu-id="cdf68-227">Passando entradas para Q\#</span><span class="sxs-lookup"><span data-stu-id="cdf68-227">Passing inputs to Q\#</span></span>
<span data-ttu-id="cdf68-228">Os argumentos para a Q# chamada devem ser apresentados sob a forma de um argumento de palavra-chave, em que a palavra-chave é o nome do argumento na Q# definição de chamada.</span><span class="sxs-lookup"><span data-stu-id="cdf68-228">Arguments for the Q# callable should be provided in the form of a keyword argument, where the keyword is the argument name in the Q# callable definition.</span></span>
<span data-ttu-id="cdf68-229">Ou `MeasureSuperpositionArray.simulate(n=4)` seja, é válido, ao passo `MeasureSuperpositionArray.simulate(4)` que um erro.</span><span class="sxs-lookup"><span data-stu-id="cdf68-229">That is, `MeasureSuperpositionArray.simulate(n=4)` is valid, whereas `MeasureSuperpositionArray.simulate(4)` would throw an error.</span></span>

<span data-ttu-id="cdf68-230">Portanto, o programa de anfitrião Python</span><span class="sxs-lookup"><span data-stu-id="cdf68-230">Therefore, the Python host program</span></span> 

```python
import qsharp
from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray

single_qubit_result = MeasureSuperposition.simulate()
single_qubit_resources = MeasureSuperposition.estimate_resources()

multi_qubit_result = MeasureSuperpositionArray.simulate(n=4)
multi_qubit_resources = MeasureSuperpositionArray.estimate_resources(n=4)

print('Single qubit:\n' + str(single_qubit_result))
print(single_qubit_resources)

print('\nMultiple qubits:\n' + str(multi_qubit_result))
print(multi_qubit_resources)
```

<span data-ttu-id="cdf68-231">resulta numa saída como a seguinte:</span><span class="sxs-lookup"><span data-stu-id="cdf68-231">results in an output like the following:</span></span>

```output
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

#### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="cdf68-232">Utilização Q# de código de outros projetos ou pacotes</span><span class="sxs-lookup"><span data-stu-id="cdf68-232">Using Q# code from other projects or packages</span></span>

<span data-ttu-id="cdf68-233">Por predefinição, o `import qsharp` comando carrega todos os `.qs` ficheiros na pasta atual e disponibiliza as suas Q# operações e funções para utilização a partir do interior do script Python.</span><span class="sxs-lookup"><span data-stu-id="cdf68-233">By default, the `import qsharp` command loads all of the `.qs` files in the current folder and makes their Q# operations and functions available for use from inside the Python script.</span></span>

<span data-ttu-id="cdf68-234">Para carregar Q# código de outra pasta, a [ `qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) pode ser usada para adicionar uma referência a um `.csproj` ficheiro para um projeto Q# (isto é, um projeto que faz `Microsoft.Quantum.Sdk` referência).</span><span class="sxs-lookup"><span data-stu-id="cdf68-234">To load Q# code from another folder, the [`qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) can be used to add a reference to a `.csproj` file for a Q# project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span>
<span data-ttu-id="cdf68-235">Este comando compilará quaisquer `.qs` ficheiros na pasta que contenha as `.csproj` sub-dobradeiras e as suas sub-dobradeiras.</span><span class="sxs-lookup"><span data-stu-id="cdf68-235">This command will compile any `.qs` files in the folder containing the `.csproj` and its subfolders.</span></span> <span data-ttu-id="cdf68-236">Também carregará novamente quaisquer pacotes referenciados através `PackageReference` ou Q# projetos referenciados através `ProjectReference` desse `.csproj` ficheiro.</span><span class="sxs-lookup"><span data-stu-id="cdf68-236">It will also recursively load any packages referenced via `PackageReference` or Q# projects referenced via `ProjectReference` in that `.csproj` file.</span></span>

<span data-ttu-id="cdf68-237">Como exemplo, o seguinte código Python importa um projeto externo, referindo o seu percurso em relação à pasta atual, e invoca uma das suas Q# operações:</span><span class="sxs-lookup"><span data-stu-id="cdf68-237">As an example, the following Python code imports an external project, referencing its path relative to the current folder, and invokes one of its Q# operations:</span></span>

```python
import qsharp
qsharp.projects.add("../qrng/Qrng.csproj")
from Qrng import SampleQuantumRandomNumberGenerator
print(f"Qrng result: {SampleQuantumRandomNumberGenerator.simulate()}")
```

<span data-ttu-id="cdf68-238">Isto resulta em saídas como as seguintes:</span><span class="sxs-lookup"><span data-stu-id="cdf68-238">This results in output like the following:</span></span>

```output
Adding reference to project: ../qrng/Qrng.csproj
Qrng result: 0
```

<span data-ttu-id="cdf68-239">Para carregar pacotes externos que contenham Q# código, utilize a [ `qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages).</span><span class="sxs-lookup"><span data-stu-id="cdf68-239">To load external packages containing Q# code, use the [`qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages).</span></span>

<span data-ttu-id="cdf68-240">Se o Q# código da pasta atual depender de projetos ou pacotes externos, poderá ver erros ao executar , uma vez que as `import qsharp` dependências ainda não foram carregadas.</span><span class="sxs-lookup"><span data-stu-id="cdf68-240">If the Q# code in the current folder depends on external projects or packages, you may see errors when running `import qsharp`, since the dependencies have not yet been loaded.</span></span>
<span data-ttu-id="cdf68-241">Para carregar os pacotes ou projetos externos necessários Q# durante o `import qsharp` comando, certifique-se de que a pasta com o script Python contém um `.csproj` ficheiro que faz referências `Microsoft.Quantum.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="cdf68-241">To load required external packages or Q# projects during the `import qsharp` command, ensure that the folder with the Python script contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="cdf68-242">Nisso, `.csproj` adicione a propriedade ao `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` `<PropertyGroup>` .</span><span class="sxs-lookup"><span data-stu-id="cdf68-242">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="cdf68-243">Isto instrui-me Q# a carregar novamente quaisquer `ProjectReference` ou `PackageReference` itens encontrados nele `.csproj` durante o `import qsharp` comando.</span><span class="sxs-lookup"><span data-stu-id="cdf68-243">This will instruct IQ# to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` during the `import qsharp` command.</span></span>

<span data-ttu-id="cdf68-244">Por exemplo, aqui está um ficheiro simples `.csproj` que faz com que eu Q# carregue automaticamente a `Microsoft.Quantum.Chemistry` embalagem:</span><span class="sxs-lookup"><span data-stu-id="cdf68-244">For example, here is a simple `.csproj` file that causes IQ# to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="cdf68-245">Atualmente esta propriedade personalizada `<IQSharpLoadAutomatically>` é exigida pelos anfitriões Python, mas no futuro, este pode tornar-se o comportamento padrão para um `.csproj` ficheiro localizado na mesma pasta que o script Python.</span><span class="sxs-lookup"><span data-stu-id="cdf68-245">Currently this custom `<IQSharpLoadAutomatically>` property is required by Python hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the Python script.</span></span>

> [!NOTE]
> <span data-ttu-id="cdf68-246">Atualmente, a `<QsharpCompile>` definição no `.csproj` é ignorada pelos anfitriões Python, e todos os `.qs` ficheiros na pasta das `.csproj` sub-dobras (incluindo sub-24) são carregados e compilados.</span><span class="sxs-lookup"><span data-stu-id="cdf68-246">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by Python hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="cdf68-247">O suporte para `.csproj` definições será melhorado no futuro (ver [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) para mais detalhes).</span><span class="sxs-lookup"><span data-stu-id="cdf68-247">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>


### <a name="c"></a>[<span data-ttu-id="cdf68-248">C#</span><span class="sxs-lookup"><span data-stu-id="cdf68-248">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="cdf68-249">Um programa de anfitrião C# tem vários componentes, e funciona muito de perto com alguns componentes do QDK, como os simuladores, que são eles próprios construídos em C#.</span><span class="sxs-lookup"><span data-stu-id="cdf68-249">A C# host program has multiple components, and works very closely with some components of the QDK, such as the simulators, which are themselves built on C#.</span></span>

<span data-ttu-id="cdf68-250">O Q# compilador funciona aqui gerando um espaço de nome C# do espaço de Q# nomes no nosso Q# ficheiro.</span><span class="sxs-lookup"><span data-stu-id="cdf68-250">The Q# compiler works here by generating an equivalently named C# namespace from the Q# namespace in our Q# file.</span></span>
<span data-ttu-id="cdf68-251">Gera ainda uma classe C# de nome equivalente para cada uma das Q# ligas ou tipos neles definidos.</span><span class="sxs-lookup"><span data-stu-id="cdf68-251">It further generates an equivalently named C# class for each of the Q# callables or types defined therein.</span></span>

<span data-ttu-id="cdf68-252">Em primeiro lugar, disponibilizamos todas as aulas usadas no nosso programa de anfitriões com `using` declarações, que são aproximadamente analagous às `open` declarações no nosso Q# ficheiro:</span><span class="sxs-lookup"><span data-stu-id="cdf68-252">First, we make any classes used in our host program available with `using` statements, which are roughly analagous to the `open` statements in our Q# file:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (for example, QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

<span data-ttu-id="cdf68-253">Em seguida, declaramos o nosso espaço de nome C#, algumas outras peças (ver o bloco de código completo abaixo), e depois qualquer programação clássica que gossemos (por exemplo, argumentos de computação para os Q# callables).</span><span class="sxs-lookup"><span data-stu-id="cdf68-253">Next, we declare our C# namespace, a few other bits and pieces (see the full code block below), and then any classical programming we would like (for example, computing arguments for the Q# callables).</span></span>
<span data-ttu-id="cdf68-254">Este último não é necessário no nosso caso, mas um exemplo de tal utilização pode ser encontrado na  [amostra de interoperabilidade .NET](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="cdf68-254">The latter isn't necessary in our case, but an example of such usage can be found at the  [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

#### <a name="target-machines"></a><span data-ttu-id="cdf68-255">Computadores de destino</span><span class="sxs-lookup"><span data-stu-id="cdf68-255">Target machines</span></span>

<span data-ttu-id="cdf68-256">Voltando Q# a, temos de criar uma instância de qualquer máquina alvo em que vamos executar as nossas operações.</span><span class="sxs-lookup"><span data-stu-id="cdf68-256">Getting back to Q#, we must create an instance of whatever target machine we will run our operations on.</span></span>

```csharp
            using var sim = new QuantumSimulator();
```

<span data-ttu-id="cdf68-257">A utilização de outras máquinas-alvo é tão simples como instantanear uma diferente, embora a forma de o fazer e processar as devoluções possa ser ligeiramente diferente.</span><span class="sxs-lookup"><span data-stu-id="cdf68-257">Using other target machines is as simple as instantiating a different one, although the manner of doing so and processing the returns can be slightly different.</span></span>
<span data-ttu-id="cdf68-258">Para a brevidade, ficamos com o [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) por enquanto, e incluímos o [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [abaixo.](#including-the-resources-estimator)</span><span class="sxs-lookup"><span data-stu-id="cdf68-258">For brevity, we stick to the [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) for now, and include the [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).</span></span>

<span data-ttu-id="cdf68-259">Cada classe C# gerada a partir das Q# operações tem um `Run` método, o primeiro argumento que deve ser a instância-alvo da máquina.</span><span class="sxs-lookup"><span data-stu-id="cdf68-259">Each C# class generated from the Q# operations have a `Run` method, the first argument of which must be the target machine instance.</span></span>
<span data-ttu-id="cdf68-260">Então, para correr `MeasureSuperposition` `QuantumSimulator` no, nós usamos `MeasureSuperposition.Run(sim)` .</span><span class="sxs-lookup"><span data-stu-id="cdf68-260">So, to run `MeasureSuperposition` on the `QuantumSimulator`, we use `MeasureSuperposition.Run(sim)`.</span></span>
<span data-ttu-id="cdf68-261">Os resultados devolvidos podem então ser atribuídos a variáveis em C#:</span><span class="sxs-lookup"><span data-stu-id="cdf68-261">The returned results can then be assigned to variables in C#:</span></span>

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> <span data-ttu-id="cdf68-262">O `Run` método é executado assíncronosamente porque este será o caso de hardware quântico real, e, portanto, a `await` palavra-chave bloqueia o processamento até que a tarefa esteja concluída.</span><span class="sxs-lookup"><span data-stu-id="cdf68-262">The `Run` method is run asynchronously because this will be the case for real quantum hardware, and therefore the `await` keyword blocks further processing until the task completes.</span></span>

<span data-ttu-id="cdf68-263">Se a Q# chamada não tiver quaisquer devoluções (por exemplo, tem tipo de `Unit` retorno), então a execução ainda pode ser feita da mesma forma sem atribuí-la a uma variável.</span><span class="sxs-lookup"><span data-stu-id="cdf68-263">If the Q# callable does not have any returns (for example, it has return type `Unit`), then the run can still be done in the same manner without assigning it to a variable.</span></span>
<span data-ttu-id="cdf68-264">Nesse caso, toda a linha seria simplesmente consistir em</span><span class="sxs-lookup"><span data-stu-id="cdf68-264">In that case, the entire line would simply consist of</span></span> 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a><span data-ttu-id="cdf68-265">Argumentos</span><span class="sxs-lookup"><span data-stu-id="cdf68-265">Arguments</span></span>

<span data-ttu-id="cdf68-266">Quaisquer argumentos para a Q# chamada são simplesmente passados como argumentos adicionais após a máquina-alvo.</span><span class="sxs-lookup"><span data-stu-id="cdf68-266">Any arguments to the Q# callable are simply passed as additional arguments after the target machine.</span></span>
<span data-ttu-id="cdf68-267">Daí os resultados de `MeasureSuperpositionArray` `n=4` em qubits seria recolhido através</span><span class="sxs-lookup"><span data-stu-id="cdf68-267">Hence the results of `MeasureSuperpositionArray` on `n=4` qubits would fetched via</span></span> 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

<span data-ttu-id="cdf68-268">Um programa de anfitrião C# completo poderia assim parecer</span><span class="sxs-lookup"><span data-stu-id="cdf68-268">A full C# host program could thus look like</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine($"Multiple qubit result: {multiQubitResult}");
        }
    }
}
```

<span data-ttu-id="cdf68-269">Na localização do ficheiro C#, o programa de anfitrião pode ser executado a partir do pedido de comando, introduzindo</span><span class="sxs-lookup"><span data-stu-id="cdf68-269">At the location of the C# file, the host program can be run from the command prompt by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="cdf68-270">e neste caso verá a saída escrita para a consola semelhante a</span><span class="sxs-lookup"><span data-stu-id="cdf68-270">and in this case you will see output written to the console similar to</span></span> 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> <span data-ttu-id="cdf68-271">Devido à interoperabilidade do compilador com espaços de nome, poderíamos, em alternativa, Q# disponibilizar os nossos callables sem a `using NamespaceName;` declaração e simplesmente combinar o título de espaço de nome C# com ele.</span><span class="sxs-lookup"><span data-stu-id="cdf68-271">Due to the compiler's interoperability with namespaces, we could alternatively make our Q# callables available without the `using NamespaceName;` statement, and simply matching the C# namespace title to it.</span></span>
> <span data-ttu-id="cdf68-272">Isto é, substituindo `namespace host` `namespace NamespaceName` por.</span><span class="sxs-lookup"><span data-stu-id="cdf68-272">That is, by replacing `namespace host` with `namespace NamespaceName`.</span></span>

#### <a name="including-the-resources-estimator"></a><span data-ttu-id="cdf68-273">Incluindo o estimador de recursos</span><span class="sxs-lookup"><span data-stu-id="cdf68-273">Including the resources estimator</span></span>

<span data-ttu-id="cdf68-274">[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)Requer uma implementação ligeiramente diferente para recuperar a saída.</span><span class="sxs-lookup"><span data-stu-id="cdf68-274">The [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requires a slightly different implementation to retrieve the output.</span></span>

<span data-ttu-id="cdf68-275">Em primeiro lugar, em vez de os instantanear como uma variável com uma `using` afirmação (como fazemos com `QuantumSimulator` o), mais diretamente instantâneos objetos da classe via</span><span class="sxs-lookup"><span data-stu-id="cdf68-275">Firstly, instead of instantiating them as a variable with a `using` statement (as we do with the `QuantumSimulator`), we more directly instantiate objects of the class via</span></span>

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

<span data-ttu-id="cdf68-276">Note que em vez de um único simulador de alvo para ser usado por múltiplas Q# operações, instantaneamente um para cada um.</span><span class="sxs-lookup"><span data-stu-id="cdf68-276">Notice that instead of a single target simulator to be used by multiple Q# operations, we have instantiated one for each.</span></span> <span data-ttu-id="cdf68-277">Isto porque os próprios objetos são modificados quando utilizados como máquinas-alvo, podendo os seus resultados ser recuperados posteriormente com o método de classe `.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="cdf68-277">This is because the objects themselves are modified when used as target machines, and their results can then be retrieved afterwards with the class method `.ToTSV()`.</span></span>

<span data-ttu-id="cdf68-278">Para executar as operações nos estimadores de recursos, usamos</span><span class="sxs-lookup"><span data-stu-id="cdf68-278">To run the operations on the resource estimators, we use</span></span>

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
<span data-ttu-id="cdf68-279">e, em seguida, obter os resultados como valores separados por separados (TSV) com `estimatorSingleQ.ToTSV()` e `estimatorMultiQ.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="cdf68-279">and then fetch the results as tab-separated-values (TSV) with `estimatorSingleQ.ToTSV()` and `estimatorMultiQ.ToTSV()`.</span></span>

<span data-ttu-id="cdf68-280">Assim, um programa de anfitrião C# completo que faz uso de ambos `QuantumSimulator` e pode assumir o `ResourcesEstimator` formulário:</span><span class="sxs-lookup"><span data-stu-id="cdf68-280">So, a full C# host program making use of both the `QuantumSimulator` and `ResourcesEstimator` could take the form:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine("Single qubit resources:");
            Console.WriteLine(estimatorSingleQ.ToTSV());

            Console.WriteLine($"\nMultiple qubit result: {multiQubitResult}");
            Console.WriteLine("Multiple qubit resources:");
            Console.WriteLine(estimatorMultiQ.ToTSV());
        }
    }
}
```


<span data-ttu-id="cdf68-281">que produziria produção semelhante a</span><span class="sxs-lookup"><span data-stu-id="cdf68-281">which would yield output similar to</span></span>

```output
Single qubit result: One
Single qubit resources:
Metric          Sum
CNOT            0
QubitClifford   1
R               0
Measure         1
T               0
Depth           0
Width           1
BorrowedWidth   0

Multiple qubit result: [One,One,One,Zero]
Multiple qubit resources:
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

***

## <a name="no-locq-jupyter-notebooks"></a><span data-ttu-id="cdf68-282">Q# Cadernos Jupyter</span><span class="sxs-lookup"><span data-stu-id="cdf68-282">Q# Jupyter Notebooks</span></span>
<span data-ttu-id="cdf68-283">Q# Os Cadernos Jupyter utilizam o Q# núcleo I, que permite definir, compilar e executar Q# callables num único caderno--- tudo ao lado de instruções, notas e outros conteúdos.</span><span class="sxs-lookup"><span data-stu-id="cdf68-283">Q# Jupyter Notebooks make use of the IQ# kernel, which allows you to define, compile, and run Q# callables in a single notebook---all alongside instructions, notes, and other content.</span></span>
<span data-ttu-id="cdf68-284">Isto significa que, embora seja possível importar e utilizar o conteúdo dos `*.qs` Q# ficheiros, estes não são necessários no modelo de execução.</span><span class="sxs-lookup"><span data-stu-id="cdf68-284">This means that while it is possible to import and use the contents of `*.qs` Q# files, they are not necessary in the run model.</span></span>

<span data-ttu-id="cdf68-285">Aqui, vamos detalhar como executar as Q# operações acima definidas, mas uma introdução mais ampla à utilização Q# de Cadernos Jupyter é fornecida na [Introdução e Q# Jupyter Notebooks.](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)</span><span class="sxs-lookup"><span data-stu-id="cdf68-285">Here, we will detail how to run the Q# operations defined above, but a more broad introduction to using Q# Jupyter Notebooks is provided at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span></span>

### <a name="defining-operations"></a><span data-ttu-id="cdf68-286">Definição de operações</span><span class="sxs-lookup"><span data-stu-id="cdf68-286">Defining operations</span></span>

<span data-ttu-id="cdf68-287">Num Q# Caderno Jupyter, introduzes Q# código como nós de dentro do espaço de nome de um Q# ficheiro.</span><span class="sxs-lookup"><span data-stu-id="cdf68-287">In a Q# Jupyter Notebook, you enter Q# code just as we would from inside the namespace of a Q# file.</span></span>

<span data-ttu-id="cdf68-288">Assim, podemos permitir o acesso a callables a partir das [ Q# bibliotecas padrão](xref:microsoft.quantum.libraries.standard.intro) com `open` declarações para os respetivos espaços de nome.</span><span class="sxs-lookup"><span data-stu-id="cdf68-288">So, we can enable access to callables from the [Q# standard libraries](xref:microsoft.quantum.libraries.standard.intro) with `open` statements for their respective namespaces.</span></span>
<span data-ttu-id="cdf68-289">Ao executar uma célula com tal afirmação, as definições desses espaços de nome estão disponíveis em todo o espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="cdf68-289">Upon running a cell with such a statement, the definitions from those namespaces are available throughout the workspace.</span></span>

> [!NOTE]
> <span data-ttu-id="cdf68-290">Os callables da [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic) e [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon) (por exemplo, [`H`](xref:Microsoft.Quantum.Intrinsic.H) e ) [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) estão automaticamente disponíveis para operações definidas dentro de células em Q# Cadernos Jupyter.</span><span class="sxs-lookup"><span data-stu-id="cdf68-290">Callables from [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic) and [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon) (for example, [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach)) are automatically available to operations defined within cells in Q# Jupyter Notebooks.</span></span>
> <span data-ttu-id="cdf68-291">No entanto, isso não é verdade para o código trazido a partir de ficheiros de origem externa Q# (um processo mostrado na Introdução e na [ Q# Jupyter Notebooks).](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)</span><span class="sxs-lookup"><span data-stu-id="cdf68-291">However, this is not true for code brought in from external Q# source files (a process shown at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span></span> 
> 

<span data-ttu-id="cdf68-292">Da mesma forma, a definição de operações requer apenas escrever o Q# código e executar a célula.</span><span class="sxs-lookup"><span data-stu-id="cdf68-292">Similarly, defining operations requires only writing the Q# code and running the cell.</span></span>

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="773">

<span data-ttu-id="cdf68-293">A saída enumera então essas operações, que podem ser chamadas de futuras células.</span><span class="sxs-lookup"><span data-stu-id="cdf68-293">The output then lists those operations, which can then be called from future cells.</span></span>

### <a name="target-machines"></a><span data-ttu-id="cdf68-294">Computadores de destino</span><span class="sxs-lookup"><span data-stu-id="cdf68-294">Target machines</span></span>

<span data-ttu-id="cdf68-295">A funcionalidade para executar operações em máquinas-alvo específicas é fornecida através de [I Q# Comandos Mágicos](xref:microsoft.quantum.guide.quickref.iqsharp).</span><span class="sxs-lookup"><span data-stu-id="cdf68-295">The functionality to run operations on specific target machines is provided via [IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp).</span></span>
<span data-ttu-id="cdf68-296">Por exemplo, `%simulate` faz uso do , e usa o `QuantumSimulator` `%estimate` `ResourcesEstimator` :</span><span class="sxs-lookup"><span data-stu-id="cdf68-296">For example, `%simulate` makes use of the `QuantumSimulator`, and `%estimate` uses the `ResourcesEstimator`:</span></span>

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Jupyter cell simulating a Q# operation and running resource estimation" width="773">

### <a name="passing-inputs-to-functions-and-operations"></a><span data-ttu-id="cdf68-297">Passando entradas para funções e operações</span><span class="sxs-lookup"><span data-stu-id="cdf68-297">Passing inputs to functions and operations</span></span>

<span data-ttu-id="cdf68-298">Para passar entradas para as Q# operações, os argumentos podem ser passados como `key=value` pares para o comando mágico de corrida.</span><span class="sxs-lookup"><span data-stu-id="cdf68-298">To pass inputs to the Q# operations, the arguments can be passed as `key=value` pairs to the run magic command.</span></span>
<span data-ttu-id="cdf68-299">Então, para correr `MeasureSuperpositionArray` com quatro qubits, podemos `%simulate MeasureSuperpositionArray n=4` correr:</span><span class="sxs-lookup"><span data-stu-id="cdf68-299">So, to run `MeasureSuperpositionArray` with four qubits, we can run `%simulate MeasureSuperpositionArray n=4`:</span></span>

<img src="../media/hostprograms_jupyter_args_sim_crop.png" alt="Jupyter cell simulating a Q# operation with arguments" width="773">

<span data-ttu-id="cdf68-300">Este padrão pode ser usado da mesma forma com `%estimate` e outros comandos de execução.</span><span class="sxs-lookup"><span data-stu-id="cdf68-300">This pattern can be used similarly with `%estimate` and other run commands.</span></span>

### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="cdf68-301">Utilização Q# de código de outros projetos ou pacotes</span><span class="sxs-lookup"><span data-stu-id="cdf68-301">Using Q# code from other projects or packages</span></span>

<span data-ttu-id="cdf68-302">Por predefinição, um Q# Bloco de Notas Jupyter carrega todos os `.qs` ficheiros da pasta atual e disponibiliza as suas Q# operações e funções para utilização a partir de dentro do caderno.</span><span class="sxs-lookup"><span data-stu-id="cdf68-302">By default, a Q# Jupyter Notebook loads all of the `.qs` files in the current folder and makes their Q# operations and functions available for use from inside the notebook.</span></span> <span data-ttu-id="cdf68-303">O [ `%who` comando mágico](xref:microsoft.quantum.iqsharp.magic-ref.who) lista todas as operações e funções atualmente Q# disponíveis.</span><span class="sxs-lookup"><span data-stu-id="cdf68-303">The [`%who` magic command](xref:microsoft.quantum.iqsharp.magic-ref.who) lists all currently-available Q# operations and functions.</span></span>

<span data-ttu-id="cdf68-304">Para carregar Q# código de outra pasta, o comando [ `%project` mágico](xref:microsoft.quantum.iqsharp.magic-ref.project) pode ser usado para adicionar uma referência a um `.csproj` ficheiro para um projeto Q# (isto é, um projeto que faz `Microsoft.Quantum.Sdk` referência).</span><span class="sxs-lookup"><span data-stu-id="cdf68-304">To load Q# code from another folder, the [`%project` magic command](xref:microsoft.quantum.iqsharp.magic-ref.project) can be used to add a reference to a `.csproj` file for a Q# project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span> <span data-ttu-id="cdf68-305">Este comando compilará quaisquer `.qs` ficheiros na pasta que contenha as `.csproj` (e sub-dobras).</span><span class="sxs-lookup"><span data-stu-id="cdf68-305">This command will compile any `.qs` files in the folder containing the `.csproj` (and subfolders).</span></span> <span data-ttu-id="cdf68-306">Também carregará novamente quaisquer pacotes referenciados através `PackageReference` ou Q# projetos referenciados através `ProjectReference` desse `.csproj` ficheiro.</span><span class="sxs-lookup"><span data-stu-id="cdf68-306">It will also recursively load any packages referenced via `PackageReference` or Q# projects referenced via `ProjectReference` in that `.csproj` file.</span></span> 

<span data-ttu-id="cdf68-307">Como exemplo, as seguintes células simulam uma Q# operação a partir de um projeto externo, onde o percurso do projeto é referenciado em relação à pasta atual:</span><span class="sxs-lookup"><span data-stu-id="cdf68-307">As an example, the following cells simulate a Q# operation from an external project, where the project path is referenced relative to the current folder:</span></span>

<img src="../media/hostprograms_jupyter_project_crop.png" alt="Jupyter cell simulating a Q# operation from an external project" width="773">

<span data-ttu-id="cdf68-308">Para carregar pacotes externos que contenham Q# código, utilize o [ `%package` comando mágico](xref:microsoft.quantum.iqsharp.magic-ref.package).</span><span class="sxs-lookup"><span data-stu-id="cdf68-308">To load external packages containing Q# code, use the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="cdf68-309">O carregamento de um pacote também disponibilizará quaisquer comandos mágicos personalizados ou codificadores de exibição que estejam contidos em quaisquer conjuntos que façam parte do pacote.</span><span class="sxs-lookup"><span data-stu-id="cdf68-309">Loading a package will also make available any custom magic commands or display encoders that are contained in any assemblies that are part of the package.</span></span>

<span data-ttu-id="cdf68-310">Para carregar pacotes ou projetos externos Q# no tempo de invisibilidade do portátil, certifique-se de que a pasta do portátil contém um `.csproj` ficheiro que faz referências `Microsoft.Quantum.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="cdf68-310">To load external packages or Q# projects at notebook intialization time, ensure that the notebook folder contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="cdf68-311">Nisso, `.csproj` adicione a propriedade ao `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` `<PropertyGroup>` .</span><span class="sxs-lookup"><span data-stu-id="cdf68-311">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="cdf68-312">Isto instrui-me Q# para carregar novamente qualquer `ProjectReference` ou `PackageReference` itens encontrados no `.csproj` tempo de carregamento do caderno.</span><span class="sxs-lookup"><span data-stu-id="cdf68-312">This will instruct IQ# to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` at notebook load time.</span></span>

<span data-ttu-id="cdf68-313">Por exemplo, aqui está um ficheiro simples `.csproj` que faz com que eu Q# carregue automaticamente a `Microsoft.Quantum.Chemistry` embalagem:</span><span class="sxs-lookup"><span data-stu-id="cdf68-313">For example, here is a simple `.csproj` file that causes IQ# to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="cdf68-314">Atualmente esta propriedade personalizada `<IQSharpLoadAutomatically>` é exigida pelos Q# anfitriões do Jupyter Notebook, mas no futuro, este pode tornar-se o comportamento padrão para um `.csproj` ficheiro localizado na mesma pasta que o ficheiro do portátil.</span><span class="sxs-lookup"><span data-stu-id="cdf68-314">Currently this custom `<IQSharpLoadAutomatically>` property is required by Q# Jupyter Notebook hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the notebook file.</span></span>

> [!NOTE]
> <span data-ttu-id="cdf68-315">Atualmente, a `<QsharpCompile>` definição no `.csproj` é ignorada pelos Q# anfitriões do Jupyter Notebook, e todos os `.qs` ficheiros na pasta das `.csproj` sub-dobras (incluindo sub-24) são carregados e compilados.</span><span class="sxs-lookup"><span data-stu-id="cdf68-315">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by Q# Jupyter Notebook hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="cdf68-316">O suporte para `.csproj` definições será melhorado no futuro (ver [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) para mais detalhes).</span><span class="sxs-lookup"><span data-stu-id="cdf68-316">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>
