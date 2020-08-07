---
title: Formas de executar um Q# programa
description: Visão geral das diferentes formas de executar Q# programas. Da linha de comando, Q# Jupyter Notebooks, e programas de anfitriões clássicos em Python ou uma língua .NET.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8e3fa83700417a4ffaf9e3be91796c9e9513b253
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869737"
---
# <a name="ways-to-run-a-no-locq-program"></a><span data-ttu-id="8c492-104">Formas de executar um Q# programa</span><span class="sxs-lookup"><span data-stu-id="8c492-104">Ways to run a Q# program</span></span>

<span data-ttu-id="8c492-105">Um dos maiores pontos fortes do Kit de Desenvolvimento Quântico é a sua flexibilidade em plataformas e ambientes de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="8c492-105">One of the Quantum Development Kit's greatest strengths is its flexibility across platforms and development environments.</span></span>
<span data-ttu-id="8c492-106">No entanto, isto também significa que os novos Q# utilizadores podem encontrar-se confusos ou sobrecarregados com as inúmeras opções encontradas no [guia de instalação](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="8c492-106">However, this also means that new Q# users may find themselves confused or overwhelmed by the numerous options found in the [install guide](xref:microsoft.quantum.install).</span></span>
<span data-ttu-id="8c492-107">Nesta página, explicamos o que acontece quando um Q# programa é executado, e comparamos as diferentes formas de os utilizadores o poderem fazer.</span><span class="sxs-lookup"><span data-stu-id="8c492-107">On this page, we explain what happens when a Q# program is run, and compare the different ways in which users can do so.</span></span>

<span data-ttu-id="8c492-108">Uma distinção primária é que Q# pode ser executada:</span><span class="sxs-lookup"><span data-stu-id="8c492-108">A primary distinction is that Q# can be run:</span></span>
- <span data-ttu-id="8c492-109">como uma aplicação autónoma, onde Q# é a única língua envolvida e o programa é invocado diretamente.</span><span class="sxs-lookup"><span data-stu-id="8c492-109">as a standalone application, where Q# is the only language involved and the program is invoked directly.</span></span> <span data-ttu-id="8c492-110">Na verdade, dois métodos enquadram-se nesta categoria:</span><span class="sxs-lookup"><span data-stu-id="8c492-110">Two methods actually fall in this category:</span></span>
  - <span data-ttu-id="8c492-111">a interface da linha de comando</span><span class="sxs-lookup"><span data-stu-id="8c492-111">the command line interface</span></span>
  - <span data-ttu-id="8c492-112">Q#Cadernos Jupyter</span><span class="sxs-lookup"><span data-stu-id="8c492-112">Q# Jupyter Notebooks</span></span>
- <span data-ttu-id="8c492-113">com um programa adicional *de anfitrião*, escrito em Python ou uma língua .NET (por exemplo, C# ou F#), que depois invoca o programa e pode processar mais resultados devolvidos.</span><span class="sxs-lookup"><span data-stu-id="8c492-113">with an additional *host program*, written in Python or a .NET language (e.g. C# or F#), which then invokes the program and can further process returned results.</span></span>

<span data-ttu-id="8c492-114">Para melhor entender estes processos e as suas diferenças, consideramos um programa simples Q# e comparamos as formas como ele pode ser executado.</span><span class="sxs-lookup"><span data-stu-id="8c492-114">To best understand these processes and their differences, we consider a simple Q# program and compare the ways it can be executed.</span></span>

## <a name="basic-no-locq-program"></a><span data-ttu-id="8c492-115">Programa Q# básico</span><span class="sxs-lookup"><span data-stu-id="8c492-115">Basic Q# program</span></span>

<span data-ttu-id="8c492-116">Um programa quântico básico pode consistir em preparar um qubit em uma superposição igual de Estados {0} $\ket $ e $\ket {1} $, medindo-o, e devolvendo o resultado, que será aleatoriamente qualquer um destes dois estados com igual probabilidade.</span><span class="sxs-lookup"><span data-stu-id="8c492-116">A basic quantum program might consist of preparing a qubit in an equal superposition of states $\ket{0}$ and $\ket{1}$, measuring it, and returning the result, which will be randomly either one of these two states with equal probability.</span></span>
<span data-ttu-id="8c492-117">Na verdade, este processo está no centro do rápido arranque do [gerador de números aleatórios quânticos.](xref:microsoft.quantum.quickstarts.qrng)</span><span class="sxs-lookup"><span data-stu-id="8c492-117">Indeed, this process is at the core of the [quantum random number generator](xref:microsoft.quantum.quickstarts.qrng) quickstart.</span></span>

<span data-ttu-id="8c492-118">Em Q# , isto seria realizado pelo seguinte código:</span><span class="sxs-lookup"><span data-stu-id="8c492-118">In Q#, this would be performed by the following code:</span></span>

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

<span data-ttu-id="8c492-119">No entanto, este código por si só não pode ser executado Q# por.</span><span class="sxs-lookup"><span data-stu-id="8c492-119">However, this code alone can't be executed by Q#.</span></span>
<span data-ttu-id="8c492-120">Para isso, tem de constituir o corpo de uma [operação](xref:microsoft.quantum.guide.basics#q-operations-and-functions), que é depois executada quando chamada--- diretamente ou por outra operação.</span><span class="sxs-lookup"><span data-stu-id="8c492-120">For that, it needs to make up the body of an [operation](xref:microsoft.quantum.guide.basics#q-operations-and-functions), which is then executed when called---either directly or by another operation.</span></span> <span data-ttu-id="8c492-121">Assim, pode escrever uma operação do seguinte formulário:</span><span class="sxs-lookup"><span data-stu-id="8c492-121">Hence, you can write an operation of the following form:</span></span>
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
<span data-ttu-id="8c492-122">Definiu uma `MeasureSuperposition` operação, que não leva entradas e devolve um valor do tipo [Resultado](xref:microsoft.quantum.guide.types).</span><span class="sxs-lookup"><span data-stu-id="8c492-122">You have defined an operation, `MeasureSuperposition`, which takes no inputs and returns a value of type [Result](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="8c492-123">Embora os exemplos nesta página consistam apenas em Q# *operações,* todos os conceitos que discutiremos dizem igualmente respeito às Q# *funções*, e, portanto, referimo-los colectivamente como *callables.*</span><span class="sxs-lookup"><span data-stu-id="8c492-123">While the examples on this page only consist of Q# *operations*, all of the concepts we will discuss pertain equally to Q# *functions*, and therefore we refer to them collectively as *callables*.</span></span> <span data-ttu-id="8c492-124">As suas diferenças são discutidas no [ Q# básico: operações e funções,](xref:microsoft.quantum.guide.basics#q-operations-and-functions)e mais detalhes sobre a definição das mesmas podem ser encontrados nas [Operações e funções.](xref:microsoft.quantum.guide.operationsfunctions)</span><span class="sxs-lookup"><span data-stu-id="8c492-124">Their differences are discussed at [Q# basics: operations and functions](xref:microsoft.quantum.guide.basics#q-operations-and-functions), and more details on defining them can be found at [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

### <a name="callable-defined-in-a-no-locq-file"></a><span data-ttu-id="8c492-125">Calável definido num Q# ficheiro</span><span class="sxs-lookup"><span data-stu-id="8c492-125">Callable defined in a Q# file</span></span>

<span data-ttu-id="8c492-126">O callable é precisamente o que é chamado e dirigido Q# por.</span><span class="sxs-lookup"><span data-stu-id="8c492-126">The callable is precisely what's called and run by Q#.</span></span>
<span data-ttu-id="8c492-127">No entanto, requer mais algumas adições para incluir um `*.qs` Q# ficheiro completo.</span><span class="sxs-lookup"><span data-stu-id="8c492-127">However, it requires a few more additions to comprise a full `*.qs` Q# file.</span></span>

<span data-ttu-id="8c492-128">Todos os Q# tipos e callables (tanto aqueles que define como os intrínsecos à língua) são definidos dentro *de espaços de nome,* que fornecem a cada um um nome completo que pode então ser referenciado.</span><span class="sxs-lookup"><span data-stu-id="8c492-128">All Q# types and callables (both those you define and those intrinsic to the language) are defined within *namespaces*, which provide each a full name that can then be referenced.</span></span>

<span data-ttu-id="8c492-129">Por exemplo, as [`H`](xref:microsoft.quantum.intrinsic.h) operações e [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) as operações [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) encontram-se nos espaços e [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) nomes (parte das [ Q# Bibliotecas Padrão).](xref:microsoft.quantum.qsharplibintro)</span><span class="sxs-lookup"><span data-stu-id="8c492-129">For example, the [`H`](xref:microsoft.quantum.intrinsic.h) and [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) operations are found in the [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) and [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) namespaces (part of the [Q# Standard Libraries](xref:microsoft.quantum.qsharplibintro)).</span></span>
<span data-ttu-id="8c492-130">Como tal, podem sempre ser chamados através dos seus nomes *completos,* `Microsoft.Quantum.Intrinsic.H(<qubit>)` e , mas `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` fazê-lo sempre levaria a um código muito desordenado.</span><span class="sxs-lookup"><span data-stu-id="8c492-130">As such, they can always be called via their *full* names, `Microsoft.Quantum.Intrinsic.H(<qubit>)` and `Microsoft.Quantum.Measurement.MResetZ(<qubit>)`, but always doing this would lead to very cluttered code.</span></span>

<span data-ttu-id="8c492-131">Em vez disso, `open` as declarações permitem que os callables sejam referenciados com uma abreviatura mais concisa, como fizemos no corpo de operação acima.</span><span class="sxs-lookup"><span data-stu-id="8c492-131">Instead, `open` statements allow callables to be referenced with more concise shorthand, as we've done in the operation body above.</span></span>
<span data-ttu-id="8c492-132">O ficheiro completo Q# que contém a nossa operação consistiria, portanto, em definir o nosso próprio espaço de nome, abrindo os espaços de nome para os callables que a nossa operação utiliza e, em seguida, a nossa operação:</span><span class="sxs-lookup"><span data-stu-id="8c492-132">The full Q# file containing our operation would therefore consist of defining our own namespace, opening the namespaces for those callables our operation uses, and then our operation:</span></span>

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
> <span data-ttu-id="8c492-133">Os espaços de nome também podem ser *aliased quando abertos,* o que pode ser útil se nomes callable/tipo em dois espaços de nome conflito.</span><span class="sxs-lookup"><span data-stu-id="8c492-133">Namespaces can also be *aliased* when opened, which can be helpful if callable/type names in two namespaces conflict.</span></span>
> <span data-ttu-id="8c492-134">Por exemplo, poderíamos, em vez disso, usar `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` acima, e depois ligar `H` via `NamespaceWithH.H(<qubit>)` .</span><span class="sxs-lookup"><span data-stu-id="8c492-134">For example, we could instead use `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` above, and then call `H` via `NamespaceWithH.H(<qubit>)`.</span></span>

> [!NOTE]
> <span data-ttu-id="8c492-135">Uma exceção a tudo isto é o espaço de [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) nome, que é sempre automaticamente aberto.</span><span class="sxs-lookup"><span data-stu-id="8c492-135">One exception to all of this is the [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) namespace, which is always automatically opened.</span></span>
> <span data-ttu-id="8c492-136">Portanto, os calíveis como [`Length`](xref:microsoft.quantum.core.length) podem sempre ser usados diretamente.</span><span class="sxs-lookup"><span data-stu-id="8c492-136">Therefore, callables like [`Length`](xref:microsoft.quantum.core.length) can always be used directly.</span></span>

### <a name="execution-on-target-machines"></a><span data-ttu-id="8c492-137">Execução em máquinas-alvo</span><span class="sxs-lookup"><span data-stu-id="8c492-137">Execution on target machines</span></span>

<span data-ttu-id="8c492-138">Agora o modelo geral de execução de um Q# programa torna-se claro.</span><span class="sxs-lookup"><span data-stu-id="8c492-138">Now the general execution model of a Q# program becomes clear.</span></span>

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

<span data-ttu-id="8c492-139">Em primeiro lugar, a chamada específica a ser executada tem acesso a quaisquer outros calíveis e tipos definidos no mesmo espaço de nome.</span><span class="sxs-lookup"><span data-stu-id="8c492-139">Firstly, the specific callable to be executed has access to any other callables and types defined in the same namespace.</span></span>
<span data-ttu-id="8c492-140">Também acede às que provêm de qualquer uma das [ Q# bibliotecas](xref:microsoft.quantum.libraries), mas estas devem ser referenciadas quer através do seu nome completo, quer através da utilização de `open` declarações acima descritas.</span><span class="sxs-lookup"><span data-stu-id="8c492-140">It also access those from any of the [Q# libraries](xref:microsoft.quantum.libraries), but those must be referenced either via their full name, or through the use of `open` statements described above.</span></span>

<span data-ttu-id="8c492-141">A própria chamada é executada numa *[máquina-alvo.](xref:microsoft.quantum.machines)*</span><span class="sxs-lookup"><span data-stu-id="8c492-141">The callable itself is then executed on a *[target machine](xref:microsoft.quantum.machines)*.</span></span>
<span data-ttu-id="8c492-142">Tais máquinas-alvo podem ser hardware quântico real ou os múltiplos simuladores disponíveis como parte do QDK.</span><span class="sxs-lookup"><span data-stu-id="8c492-142">Such target machines can be actual quantum hardware or the multiple simulators available as part of the QDK.</span></span>
<span data-ttu-id="8c492-143">Para os nossos propósitos aqui, a máquina alvo mais útil é um exemplo do [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator) `QuantumSimulator` , que calcula o comportamento do programa como se estivesse sendo executado em um computador quântico sem ruído.</span><span class="sxs-lookup"><span data-stu-id="8c492-143">For our purposes here, the most useful target machine is an instance of the [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator`, which calculates the program's behavior as if it were being executed on a noise-free quantum computer.</span></span>

<span data-ttu-id="8c492-144">Até agora, descrevemos o que acontece quando uma chamada específica Q# está a ser executada.</span><span class="sxs-lookup"><span data-stu-id="8c492-144">So far, we've described what happens when a specific Q# callable is being executed.</span></span>
<span data-ttu-id="8c492-145">Independentemente de ser Q# usado numa aplicação autónoma ou com um programa de acolhimento, este processo geral é mais ou menos o mesmo---a flexibilidade do QDK.</span><span class="sxs-lookup"><span data-stu-id="8c492-145">Regardless of whether Q# is used in a standalone application or with a host program, this general process is more or less the same---hence the QDK's flexibility.</span></span>
<span data-ttu-id="8c492-146">As diferenças entre as diferentes formas de chamar para o Kit de Desenvolvimento Quântico revelam-se, portanto, na *forma como* essa chamada é chamada a Q# ser executada, e de que forma quaisquer resultados são devolvidos.</span><span class="sxs-lookup"><span data-stu-id="8c492-146">The differences between the different ways of calling into the Quantum Development Kit therefore reveal themselves in *how* that Q# callable is called to be executed, and in what manner any results are returned.</span></span>
<span data-ttu-id="8c492-147">Mais especificamente, as diferenças giram em torno</span><span class="sxs-lookup"><span data-stu-id="8c492-147">More specifically, the differences revolve around</span></span> 
1. <span data-ttu-id="8c492-148">indicando qual Q# é a chamada a executar,</span><span class="sxs-lookup"><span data-stu-id="8c492-148">indicating which Q# callable is to be executed,</span></span>
2. <span data-ttu-id="8c492-149">como potenciais argumentos caláveis são fornecidos,</span><span class="sxs-lookup"><span data-stu-id="8c492-149">how potential callable arguments are provided,</span></span>
3. <span data-ttu-id="8c492-150">especificando a máquina-alvo em que executá-la, e</span><span class="sxs-lookup"><span data-stu-id="8c492-150">specifying the target machine on which to execute it, and</span></span>
4. <span data-ttu-id="8c492-151">como quaisquer resultados são devolvidos.</span><span class="sxs-lookup"><span data-stu-id="8c492-151">how any results are returned.</span></span>

<span data-ttu-id="8c492-152">Primeiro, discutimos como isto é feito com a Q# aplicação autónoma da linha de comando, e depois procedemos à utilização de programas de anfitriões Python e C#.</span><span class="sxs-lookup"><span data-stu-id="8c492-152">First, we discuss how this is done with the Q# standalone application from the command line, and then proceed to using Python and C# host programs.</span></span>
<span data-ttu-id="8c492-153">Reservamos a aplicação autónoma de Q# Cadernos Jupyter para o final, porque ao contrário dos três primeiros, a sua funcionalidade primária não se centra em torno de um Q# arquivo local.</span><span class="sxs-lookup"><span data-stu-id="8c492-153">We reserve the standalone application of Q# Jupyter Notebooks for last, because unlike the first three, it's primary functionality does not center around a local Q# file.</span></span>

> [!NOTE]
> <span data-ttu-id="8c492-154">Embora não o ilustremos nestes exemplos, uma comunhão entre os métodos de execução é que quaisquer mensagens impressas a partir de dentro do Q# programa (por [`Message`](xref:microsoft.quantum.intrinsic.message) [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) exemplo) serão normalmente impressas na respetiva consola.</span><span class="sxs-lookup"><span data-stu-id="8c492-154">Although we don't illustrate it in these examples, one commonality between the execution methods is that any messages printed from inside the Q# program (by way of [`Message`](xref:microsoft.quantum.intrinsic.message) or [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine), for example) will typically always be printed to the respective console.</span></span>

## <a name="no-locq-from-the-command-line"></a><span data-ttu-id="8c492-155">Q#da linha de comando</span><span class="sxs-lookup"><span data-stu-id="8c492-155">Q# from the command line</span></span>
<span data-ttu-id="8c492-156">Uma das formas mais fáceis de começar a escrever Q# programas é evitar preocupar-se com ficheiros separados e uma segunda língua completamente.</span><span class="sxs-lookup"><span data-stu-id="8c492-156">One of the easiest ways to get started writing Q# programs is to avoid worrying about separate files and a second language altogether.</span></span>
<span data-ttu-id="8c492-157">A utilização do Visual Studio Code ou do Visual Studio com a extensão QDK permite um fluxo de trabalho sem emenda no qual executamos Q# callables a partir de apenas um Q# ficheiro.</span><span class="sxs-lookup"><span data-stu-id="8c492-157">Using Visual Studio Code or Visual Studio with the QDK extension allows for a seamless work flow in which we run Q# callables from only a single Q# file.</span></span>

<span data-ttu-id="8c492-158">Para isso, vamos, em última análise, invocar a execução do programa entrando</span><span class="sxs-lookup"><span data-stu-id="8c492-158">For this, we will ultimately invoke the program's execution by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="8c492-159">na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="8c492-159">in the command line.</span></span>
<span data-ttu-id="8c492-160">O fluxo de trabalho mais simples é quando a localização do diretório do terminal é a mesma que o Q# ficheiro, que pode ser facilmente manuseado ao lado Q# da edição de ficheiros utilizando o terminal integrado no Código VS, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="8c492-160">The simplest workflow is when the terminal's directory location is the same as the Q# file, which can be easily handled alongside Q# file editing by using the integrated terminal in VS Code, for example.</span></span>
<span data-ttu-id="8c492-161">No entanto, o [ `dotnet run` comando](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) aceita inúmeras opções, e o programa também pode ser executado a partir de um local diferente, simplesmente fornecendo `--project <PATH>` a localização do Q# ficheiro.</span><span class="sxs-lookup"><span data-stu-id="8c492-161">However, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepts numerous options, and the program can also be run from a different location by simply providing `--project <PATH>` with the location of the Q# file.</span></span>


### <a name="add-entry-point-to-no-locq-file"></a><span data-ttu-id="8c492-162">Adicionar ponto de entrada para Q# arquivar</span><span class="sxs-lookup"><span data-stu-id="8c492-162">Add entry point to Q# file</span></span>

<span data-ttu-id="8c492-163">A maioria dos Q# ficheiros conterá mais do que uma chamada, por isso, naturalmente, precisamos de informar o compilador *sobre qual* a chamada a executar quando fornecessarmos o `dotnet run` comando.</span><span class="sxs-lookup"><span data-stu-id="8c492-163">Most Q# files will contain more than one callable, so naturally we need to let the compiler know *which* callable to execute when we provide the `dotnet run` command.</span></span>
<span data-ttu-id="8c492-164">Isto é feito com uma simples alteração ao Q# próprio ficheiro:</span><span class="sxs-lookup"><span data-stu-id="8c492-164">This is done with a simple change to the Q# file itself:</span></span> 
    - <span data-ttu-id="8c492-165">adicionar uma linha com `@EntryPoint()` diretamente precedendo o callable.</span><span class="sxs-lookup"><span data-stu-id="8c492-165">add a line with `@EntryPoint()` directly preceding the callable.</span></span>

<span data-ttu-id="8c492-166">Nosso arquivo de cima seria, portanto, tornar-se</span><span class="sxs-lookup"><span data-stu-id="8c492-166">Our file from above would therefore become</span></span>
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

<span data-ttu-id="8c492-167">Agora, uma chamada da linha de `dotnet run` comando leva a ser `MeasureSuperposition` executada, e o valor devolvido é então impresso diretamente para o terminal.</span><span class="sxs-lookup"><span data-stu-id="8c492-167">Now, a call of `dotnet run` from the command line leads to `MeasureSuperposition` being run, and the returned value is then printed directly to the terminal.</span></span>
<span data-ttu-id="8c492-168">Então, verá um `One` ou `Zero` impresso.</span><span class="sxs-lookup"><span data-stu-id="8c492-168">So, you will see either `One` or `Zero` printed.</span></span> 

<span data-ttu-id="8c492-169">Note que não importa se tiver mais chamadas definidas abaixo, apenas `MeasureSuperposition` será executado.</span><span class="sxs-lookup"><span data-stu-id="8c492-169">Note that it doesn't matter if you have more callables defined below it, only `MeasureSuperposition` will be run.</span></span>
<span data-ttu-id="8c492-170">Além disso, não é problema se a sua chamada inclui comentários de [documentação](xref:microsoft.quantum.guide.filestructure#documentation-comments) antes da sua declaração, o `@EntryPoint()` atributo pode simplesmente ser colocado acima deles.</span><span class="sxs-lookup"><span data-stu-id="8c492-170">Additionally, it's no problem if your callable includes [documentation comments](xref:microsoft.quantum.guide.filestructure#documentation-comments) before its declaration, the `@EntryPoint()` attribute can be simply placed above them.</span></span>

### <a name="callable-arguments"></a><span data-ttu-id="8c492-171">Argumentos insutilizáveis</span><span class="sxs-lookup"><span data-stu-id="8c492-171">Callable arguments</span></span>

<span data-ttu-id="8c492-172">Até agora, só consideramos uma operação que não tem entradas.</span><span class="sxs-lookup"><span data-stu-id="8c492-172">So far, we've only considered an operation that takes no inputs.</span></span>
<span data-ttu-id="8c492-173">Suponha que quiséssemos realizar uma operação semelhante, mas em múltiplos qubits---o número do qual é fornecido como argumento.</span><span class="sxs-lookup"><span data-stu-id="8c492-173">Suppose we wanted to perform a similar operation, but on multiple qubits---the number of which is provided as an argument.</span></span>
<span data-ttu-id="8c492-174">Tal operação poderia ser escrito como</span><span class="sxs-lookup"><span data-stu-id="8c492-174">Such an operation could be written as</span></span>
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
<span data-ttu-id="8c492-175">onde o valor devolvido é um conjunto dos resultados da medição.</span><span class="sxs-lookup"><span data-stu-id="8c492-175">where the returned value is an array of the measurement results.</span></span>
<span data-ttu-id="8c492-176">Note que [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) e [`ForEach`](xref:microsoft.quantum.arrays.foreach) estão nos [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) espaços e [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) nomes, exigindo declarações adicionais `open` para cada um.</span><span class="sxs-lookup"><span data-stu-id="8c492-176">Note that [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) and [`ForEach`](xref:microsoft.quantum.arrays.foreach) are in the [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) and [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) namespaces, requiring additional `open` statements for each.</span></span>

<span data-ttu-id="8c492-177">Se movermos o `@EntryPoint()` atributo para preceder esta nova operação (note que só pode haver uma dessas linhas num ficheiro), tentar executá-lo simplesmente resulta `dotnet run` numa mensagem de erro que indica quais as opções adicionais da linha de comando e como expressá-las.</span><span class="sxs-lookup"><span data-stu-id="8c492-177">If we move the `@EntryPoint()` attribute to precede this new operation (note there can only be one such line in a file), attempting to run it with simply `dotnet run` results in an error message which indicates what additional command line options are required, and how to express them.</span></span>

<span data-ttu-id="8c492-178">O formato geral da linha de comando é, na `dotnet run [options]` verdade, e os argumentos callable são fornecidos lá.</span><span class="sxs-lookup"><span data-stu-id="8c492-178">The general format for the command line is actually `dotnet run [options]`, and callable arguments are provided there.</span></span>
<span data-ttu-id="8c492-179">Neste caso, falta o `n` argumento, e mostra que temos de fornecer a opção. `-n <n>`</span><span class="sxs-lookup"><span data-stu-id="8c492-179">In this case, the argument `n` is missing, and it shows that we need to provide the option `-n <n>`.</span></span> <span data-ttu-id="8c492-180">Para correr `MeasureSuperpositionArray` para `n=4` qubits, portanto usamos</span><span class="sxs-lookup"><span data-stu-id="8c492-180">To run `MeasureSuperpositionArray` for `n=4` qubits, we therefore use</span></span>

```dotnetcli
dotnet run -n 4
```

<span data-ttu-id="8c492-181">produzindo uma saída semelhante a</span><span class="sxs-lookup"><span data-stu-id="8c492-181">yielding an output similar to</span></span>

```output
[Zero,One,One,One]
```

<span data-ttu-id="8c492-182">Isto, naturalmente, estende-se a múltiplos argumentos.</span><span class="sxs-lookup"><span data-stu-id="8c492-182">This of course extends to multiple arguments.</span></span>

> [!NOTE]
> <span data-ttu-id="8c492-183">Os nomes de argumentos `camelCase` definidos são ligeiramente alterados pelo compilador para serem aceites como Q# entradas.</span><span class="sxs-lookup"><span data-stu-id="8c492-183">Argument names defined in `camelCase` are slightly altered by the compiler to be accepted as Q# inputs.</span></span> <span data-ttu-id="8c492-184">Por exemplo, se em vez `n` de, nós usamos o nome `numQubits` acima, então esta entrada seria fornecida na linha de comando via `--num-qubits 4` em vez de `-n 4` .</span><span class="sxs-lookup"><span data-stu-id="8c492-184">For example, if instead of `n`, we used the name `numQubits` above, then this input would be provided in the command line via `--num-qubits 4` instead of `-n 4`.</span></span>

<span data-ttu-id="8c492-185">A mensagem de erro também fornece outras opções que podem ser usadas, incluindo como alterar a máquina-alvo.</span><span class="sxs-lookup"><span data-stu-id="8c492-185">The error message also provides other options which can be used, including how to change the target machine.</span></span>

### <a name="different-target-machines"></a><span data-ttu-id="8c492-186">Diferentes máquinas-alvo</span><span class="sxs-lookup"><span data-stu-id="8c492-186">Different target machines</span></span>

<span data-ttu-id="8c492-187">Como as saídas das nossas operações até agora têm sido os resultados esperados da sua ação em qubits reais, é claro que a máquina-alvo padrão da linha de comando é o simulador de quauntum de estado completo, `QuantumSimulator` .</span><span class="sxs-lookup"><span data-stu-id="8c492-187">As the outputs from our operations thus far have been the expected results of their action on real qubits, it's clear that the default target machine from the command line is the full-state quauntum simulator, `QuantumSimulator`.</span></span>
<span data-ttu-id="8c492-188">No entanto, podemos instruir os callables a serem executados numa máquina-alvo específica com a opção `--simulator` (ou a abreviatura). `-s`</span><span class="sxs-lookup"><span data-stu-id="8c492-188">However, we can instruct callables to be run on a specific target machine with the option `--simulator` (or the shorthand `-s`).</span></span>

<span data-ttu-id="8c492-189">Por exemplo, poderíamos executá-lo [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) em:</span><span class="sxs-lookup"><span data-stu-id="8c492-189">For example, we could run it on [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator):</span></span>

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

<span data-ttu-id="8c492-190">A saída impressa é então</span><span class="sxs-lookup"><span data-stu-id="8c492-190">The printed output is then</span></span>

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

<span data-ttu-id="8c492-191">Para obter mais informações sobre o que estas métricas indicam, consulte [o estimador de recursos: métricas reportadas](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span><span class="sxs-lookup"><span data-stu-id="8c492-191">For details on what these metrics indicate, see [Resource estimator: metrics reported](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span></span>

### <a name="command-line-execution-summary"></a><span data-ttu-id="8c492-192">Resumo da execução da linha de comando</span><span class="sxs-lookup"><span data-stu-id="8c492-192">Command line execution summary</span></span>
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-no-locq-dotnet-run-options"></a><span data-ttu-id="8c492-193">Q# `dotnet run` Não-opções</span><span class="sxs-lookup"><span data-stu-id="8c492-193">Non-Q# `dotnet run` options</span></span>

<span data-ttu-id="8c492-194">Como mencionamos brevemente acima com a `--project` opção, o [ `dotnet run` comando](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) também aceita opções não relacionadas com os Q# argumentos caláveis.</span><span class="sxs-lookup"><span data-stu-id="8c492-194">As we briefly mentioned above with the `--project` option, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) also accepts options unrelated to the Q# callable arguments.</span></span>
<span data-ttu-id="8c492-195">Se fornecer ambos os tipos de opções, as `dotnet` opções específicas devem ser fornecidas primeiro, seguidas por um delimetro `--` , e depois as Q# opções específicas.</span><span class="sxs-lookup"><span data-stu-id="8c492-195">If providing both kinds of options, the `dotnet`-specific options must be provided first, followed by a delimeter `--`, and then the Q#-specific options.</span></span>
<span data-ttu-id="8c492-196">Por exemplo, especificar um caminho juntamente com um número de qubits para a operação acima seria executado via `dotnet run --project <PATH> -- -n <n>` .</span><span class="sxs-lookup"><span data-stu-id="8c492-196">For example, specifiying a path along with a number qubits for the operation above would be executed via `dotnet run --project <PATH> -- -n <n>`.</span></span>

## <a name="no-locq-with-host-programs"></a><span data-ttu-id="8c492-197">Q#com programas de anfitrião</span><span class="sxs-lookup"><span data-stu-id="8c492-197">Q# with host programs</span></span>

<span data-ttu-id="8c492-198">Com o nosso Q# ficheiro na mão, uma alternativa para chamar uma operação ou funcionar diretamente da linha de comando é usar um *programa de anfitrião* em outra língua clássica.</span><span class="sxs-lookup"><span data-stu-id="8c492-198">With our Q# file in hand, an alternative to calling an operation or function directly from the command line is to use a *host program* in another classical language.</span></span> <span data-ttu-id="8c492-199">Especificamente, isto pode ser feito com python ou uma língua .NET como C# ou F# (por uma questão de brevidade só vamos detalhar C# aqui).</span><span class="sxs-lookup"><span data-stu-id="8c492-199">Specifically, this can be done with either Python or a .NET language such as C# or F# (for the sake of brevity we will only detail C# here).</span></span>
<span data-ttu-id="8c492-200">É necessário um pouco mais de configuração para permitir a interoperabilidade, mas esses detalhes podem ser encontrados nos [guias de instalação](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="8c492-200">A little more setup is required to enable the interoperability, but those details can be found in the [install guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="8c492-201">Em resumo, a situação agora inclui um ficheiro de programa de anfitrião (por `*.py` exemplo, `*.cs` ou) no mesmo local que o nosso Q# ficheiro.</span><span class="sxs-lookup"><span data-stu-id="8c492-201">In a nutshell, the situation now includes a host program file (e.g. `*.py` or `*.cs`) in the same location as our Q# file.</span></span>
<span data-ttu-id="8c492-202">É agora o programa *de anfitrião* que é executado, e no decorrer da sua execução pode chamar Q# operações e funções específicas do Q# arquivo.</span><span class="sxs-lookup"><span data-stu-id="8c492-202">It's now the *host* program that gets run, and in the course of its execution it can call specific Q# operations and functions from the Q# file.</span></span>
<span data-ttu-id="8c492-203">O núcleo da interoperabilidade baseia-se no Q# compilador que torna o conteúdo do Q# ficheiro acessível ao programa anfitrião para que possam ser chamados.</span><span class="sxs-lookup"><span data-stu-id="8c492-203">The core of the interoperability is based on the Q# compiler making the contents of the Q# file accessible to the host program so that they can be called.</span></span>

<span data-ttu-id="8c492-204">Um dos principais benefícios da utilização de um programa de anfitrião é que os dados clássicos devolvidos pelo Q# programa podem então ser processados na língua de acolhimento.</span><span class="sxs-lookup"><span data-stu-id="8c492-204">One of the main benefits of using a host program is that the classical data returned by the Q# program can then be further processed in the host language.</span></span>
<span data-ttu-id="8c492-205">Isto poderia consistir em algum processamento avançado de dados (por exemplo, algo que não pode ser realizado internamente), e, em Q# seguida, chamar mais Q# ações com base nesses resultados, ou algo tão simples como traçar os Q# resultados.</span><span class="sxs-lookup"><span data-stu-id="8c492-205">This could consist of some advanced data processing (e.g. something that can't be performed internally in Q#), and then calling further Q# actions based on those results, or something as simple as plotting the Q# results.</span></span>

<span data-ttu-id="8c492-206">O esquema geral é mostrado aqui, e discutimos as implementações específicas para Python e C# abaixo.</span><span class="sxs-lookup"><span data-stu-id="8c492-206">The general scheme is shown here, and we discuss the specific implementations for Python and C# below.</span></span> <span data-ttu-id="8c492-207">Uma amostra utilizando um programa de anfitrião F# pode ser encontrada nas [amostras de interoperabilidade .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="8c492-207">A sample using an F# host program can be found at the [.NET interoperability samples](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span></span>

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> <span data-ttu-id="8c492-208">O `@EntryPoint()` atributo utilizado para Q# aplicações de linha de comando não pode ser utilizado com programas de anfitrião.</span><span class="sxs-lookup"><span data-stu-id="8c492-208">The `@EntryPoint()` attribute used for Q# command line applications cannot be used with host programs.</span></span>
> <span data-ttu-id="8c492-209">Um erro será levantado se estiver presente no Q# ficheiro sendo chamado por um anfitrião.</span><span class="sxs-lookup"><span data-stu-id="8c492-209">An error will be raised if it is present in the Q# file being called by a host.</span></span> 

<span data-ttu-id="8c492-210">Para trabalhar com diferentes programas de anfitrião, não são necessárias alterações a um `*.qs` Q# ficheiro.</span><span class="sxs-lookup"><span data-stu-id="8c492-210">To work with different host programs, there are no changes required to a `*.qs` Q# file.</span></span>
<span data-ttu-id="8c492-211">As seguintes implementações do programa anfitrião funcionam com o mesmo Q# ficheiro:</span><span class="sxs-lookup"><span data-stu-id="8c492-211">The following host program implementations all work with the same Q# file:</span></span>

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

<span data-ttu-id="8c492-212">Selecione o separador correspondente ao seu idioma de interesse anfitrião.</span><span class="sxs-lookup"><span data-stu-id="8c492-212">Select the tab corresponding to your host language of interest.</span></span>

### <a name="python"></a>[<span data-ttu-id="8c492-213">Python</span><span class="sxs-lookup"><span data-stu-id="8c492-213">Python</span></span>](#tab/tabid-python)
<span data-ttu-id="8c492-214">Um programa de anfitrião Python é construído da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="8c492-214">A Python host program is constructed as follows:</span></span>
1. <span data-ttu-id="8c492-215">Importe o `qsharp` módulo, que regista o carregador de módulos para Q# interoperabilidade.</span><span class="sxs-lookup"><span data-stu-id="8c492-215">Import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="8c492-216">Isto permite que Q# os espaços de nome apareçam como módulos Python, a partir dos quais podemos "importar" Q# callables.</span><span class="sxs-lookup"><span data-stu-id="8c492-216">This allows Q# namespaces to appear as Python modules, from which we can "import" Q# callables.</span></span>
    <span data-ttu-id="8c492-217">Note-se que, tecnicamente, não são os Q# próprios callables que são importados, mas sim os canhotos Python que permitem chamá-los.</span><span class="sxs-lookup"><span data-stu-id="8c492-217">Note that it is technically not the Q# callables themselves which are imported, but rather Python stubs which allow calling into them.</span></span>
    <span data-ttu-id="8c492-218">Estes comportam-se então como objetos de classes Python, nos quais usamos métodos para especificar as máquinas-alvo para enviar a operação para a execução.</span><span class="sxs-lookup"><span data-stu-id="8c492-218">These then behave as objects of Python classes, on which we use methods to specify the target machines to send the operation to for execution.</span></span>

2. <span data-ttu-id="8c492-219">Importe os Q# calíveis que invocaremos directamente--- neste caso, `MeasureSuperposition` `MeasureSuperpositionArray` e.</span><span class="sxs-lookup"><span data-stu-id="8c492-219">Import those Q# callables which we will directly invoke---in this case, `MeasureSuperposition` and `MeasureSuperpositionArray`.</span></span>
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    <span data-ttu-id="8c492-220">Com o `qsharp` módulo importado, também pode importar callables diretamente dos espaços de nome da Q# biblioteca.</span><span class="sxs-lookup"><span data-stu-id="8c492-220">With the `qsharp` module imported, you can also import callables directly from the Q# library namespaces.</span></span>

3. <span data-ttu-id="8c492-221">Entre qualquer outro código Python, pode agora ligar para as chamadas em máquinas-alvo específicas e atribuir os seus retornos a variáveis (se devolverem um valor) para posterior utilização.</span><span class="sxs-lookup"><span data-stu-id="8c492-221">Among any other Python code, you can now call those callables on specific target machines, and assign their returns to variables (if they return a value) for further use.</span></span>

#### <a name="specifying-target-machines"></a><span data-ttu-id="8c492-222">Especificar máquinas-alvo</span><span class="sxs-lookup"><span data-stu-id="8c492-222">Specifying target machines</span></span>
<span data-ttu-id="8c492-223">Chamar uma operação a ser executada numa máquina-alvo específica é feita através de diferentes métodos Python no objeto importado.</span><span class="sxs-lookup"><span data-stu-id="8c492-223">Calling an operation to be run on a specific target machine is done via different Python methods on the imported object.</span></span>
<span data-ttu-id="8c492-224">Por `.simulate(<args>)` exemplo, usa o `QuantumSimulator` para executar a operação, enquanto `.estimate_resources(<args>)` o faz no `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="8c492-224">For example, `.simulate(<args>)`, uses the `QuantumSimulator` to run the operation, whereas `.estimate_resources(<args>)` does so on the `ResourcesEstimator`.</span></span>

#### <a name="passing-inputs-to-q"></a><span data-ttu-id="8c492-225">Passando entradas para Q\#</span><span class="sxs-lookup"><span data-stu-id="8c492-225">Passing inputs to Q\#</span></span>
<span data-ttu-id="8c492-226">Os argumentos para a Q# chamada devem ser apresentados sob a forma de um argumento de palavra-chave, em que a palavra-chave é o nome do argumento na Q# definição de chamada.</span><span class="sxs-lookup"><span data-stu-id="8c492-226">Arguments for the Q# callable should be provided in the form of a keyword argument, where the keyword is the argument name in the Q# callable definition.</span></span>
<span data-ttu-id="8c492-227">Ou `MeasureSuperpositionArray.simulate(n=4)` seja, é válido, ao passo `MeasureSuperpositionArray.simulate(4)` que um erro.</span><span class="sxs-lookup"><span data-stu-id="8c492-227">That is, `MeasureSuperpositionArray.simulate(n=4)` is valid, whereas `MeasureSuperpositionArray.simulate(4)` would throw an error.</span></span>

<span data-ttu-id="8c492-228">Portanto, o programa de anfitrião Python</span><span class="sxs-lookup"><span data-stu-id="8c492-228">Therefore, the Python host program</span></span> 

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

<span data-ttu-id="8c492-229">resulta numa saída como a seguinte:</span><span class="sxs-lookup"><span data-stu-id="8c492-229">results in an output like the following:</span></span>

```python
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

### <a name="c"></a>[<span data-ttu-id="8c492-230">C#</span><span class="sxs-lookup"><span data-stu-id="8c492-230">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="8c492-231">Um programa de anfitrião C# tem vários componentes, e funciona muito de perto com alguns componentes do QDK, como os simuladores, que são eles próprios construídos em C#.</span><span class="sxs-lookup"><span data-stu-id="8c492-231">A C# host program has multiple components, and works very closely with some components of the QDK, such as the simulators, which are themselves built on C#.</span></span>

<span data-ttu-id="8c492-232">O Q# compilador funciona aqui gerando um espaço de nome C# do espaço de Q# nomes no nosso Q# ficheiro.</span><span class="sxs-lookup"><span data-stu-id="8c492-232">The Q# compiler works here by generating an equivalently named C# namespace from the Q# namespace in our Q# file.</span></span>
<span data-ttu-id="8c492-233">Gera ainda uma classe C# de nome equivalente para cada uma das Q# ligas ou tipos neles definidos.</span><span class="sxs-lookup"><span data-stu-id="8c492-233">It further generates an equivalently named C# class for each of the Q# callables or types defined therein.</span></span>

<span data-ttu-id="8c492-234">Em primeiro lugar, disponibilizamos todas as aulas usadas no nosso programa de anfitriões com `using` declarações, que são aproximadamente analagous às `open` declarações no nosso Q# ficheiro:</span><span class="sxs-lookup"><span data-stu-id="8c492-234">First, we make any classes used in our host program available with `using` statements, which are roughly analagous to the `open` statements in our Q# file:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

<span data-ttu-id="8c492-235">Em seguida, declaramos o nosso espaço de nome C#, algumas outras peças (ver o bloco de código completo abaixo), e, em seguida, qualquer programação clássica que gostaríamos (por exemplo, argumentos de computação para os Q# callables).</span><span class="sxs-lookup"><span data-stu-id="8c492-235">Next, we declare our C# namespace, a few other bits and pieces (see the full code block below), and then any classical programming we would like (e.g. computing arguments for the Q# callables).</span></span>
<span data-ttu-id="8c492-236">Este último não é necessário no nosso caso, mas um exemplo de tal utilização pode ser encontrado na [amostra de interoperabilidade .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="8c492-236">The latter isn't necessary in our case, but an example of such usage can be found at the  [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span></span>

#### <a name="target-machines"></a><span data-ttu-id="8c492-237">Computadores de destino</span><span class="sxs-lookup"><span data-stu-id="8c492-237">Target machines</span></span>

<span data-ttu-id="8c492-238">Voltando Q# a, temos de criar uma instância de qualquer máquina alvo em que executaremos as nossas operações.</span><span class="sxs-lookup"><span data-stu-id="8c492-238">Getting back to Q#, we must create an instance of whatever target machine we will execute our operations on.</span></span>

```csharp
            using var sim = new QuantumSimulator();
```

<span data-ttu-id="8c492-239">A utilização de outras máquinas-alvo é tão simples como instantanear uma diferente, embora a forma de o fazer e processar as devoluções possa ser ligeiramente diferente.</span><span class="sxs-lookup"><span data-stu-id="8c492-239">Using other target machines is as simple as instantiating a different one, although the manner of doing so and processing the returns can be slightly different.</span></span>
<span data-ttu-id="8c492-240">Para a brevidade, ficamos com o [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) por enquanto, e incluímos o [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [abaixo.](#including-the-resources-estimator)</span><span class="sxs-lookup"><span data-stu-id="8c492-240">For brevity, we stick to the [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) for now, and include the [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).</span></span>

<span data-ttu-id="8c492-241">Cada classe C# gerada a partir das Q# operações tem um `Run` método, o primeiro argumento que deve ser a instância-alvo da máquina.</span><span class="sxs-lookup"><span data-stu-id="8c492-241">Each C# class generated from the Q# operations have a `Run` method, the first argument of which must be the target machine instance.</span></span>
<span data-ttu-id="8c492-242">Então, para correr `MeasureSuperposition` `QuantumSimulator` no, nós usamos `MeasureSuperposition.Run(sim)` .</span><span class="sxs-lookup"><span data-stu-id="8c492-242">So, to run `MeasureSuperposition` on the `QuantumSimulator`, we use `MeasureSuperposition.Run(sim)`.</span></span>
<span data-ttu-id="8c492-243">Os resultados devolvidos podem então ser atribuídos a variáveis em C#:</span><span class="sxs-lookup"><span data-stu-id="8c492-243">The returned results can then be assigned to variables in C#:</span></span>

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> <span data-ttu-id="8c492-244">O `Run` método é executado assíncroticamente porque este será o caso de hardware quântico real, e, portanto, a `await` palavra-chave bloqueia a execução até que a tarefa esteja concluída.</span><span class="sxs-lookup"><span data-stu-id="8c492-244">The `Run` method is executed asynchronously because this will be the case for real quantum hardware, and therefore the `await` keyword blocks further execution until the task completes.</span></span>

<span data-ttu-id="8c492-245">Se a Q# chamada não tiver quaisquer devoluções (ou seja, tem tipo de `Unit` retorno), então a execução ainda pode ser feita da mesma forma sem atribuí-la a uma variável.</span><span class="sxs-lookup"><span data-stu-id="8c492-245">If the Q# callable does not have any returns (i.e. has return type `Unit`), then the execution can still be done in the same manner without assigning it to a variable.</span></span>
<span data-ttu-id="8c492-246">Nesse caso, toda a linha seria simplesmente consistir em</span><span class="sxs-lookup"><span data-stu-id="8c492-246">In that case, the entire line would simply consist of</span></span> 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a><span data-ttu-id="8c492-247">Argumentos</span><span class="sxs-lookup"><span data-stu-id="8c492-247">Arguments</span></span>

<span data-ttu-id="8c492-248">Quaisquer argumentos para a Q# chamada são simplesmente passados como argumentos adicionais aferir a máquina-alvo.</span><span class="sxs-lookup"><span data-stu-id="8c492-248">Any arguments to the Q# callable are simply passed as additional arguments afer the target machine.</span></span>
<span data-ttu-id="8c492-249">Daí os resultados de `MeasureSuperpositionArray` `n=4` em qubits seria recolhido através</span><span class="sxs-lookup"><span data-stu-id="8c492-249">Hence the results of `MeasureSuperpositionArray` on `n=4` qubits would fetched via</span></span> 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

<span data-ttu-id="8c492-250">Um programa de anfitrião C# completo poderia assim parecer</span><span class="sxs-lookup"><span data-stu-id="8c492-250">A full C# host program could thus look like</span></span>

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

<span data-ttu-id="8c492-251">Na localização do ficheiro C#, o programa de anfitrião pode ser executado a partir da linha de comando, introduzindo</span><span class="sxs-lookup"><span data-stu-id="8c492-251">At the location of the C# file, the host program can be run from the command line by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="8c492-252">e neste caso verá a saída escrita para a consola semelhante a</span><span class="sxs-lookup"><span data-stu-id="8c492-252">and in this case you will see output written to the console similar to</span></span> 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> <span data-ttu-id="8c492-253">Devido à interoperabilidade do compilador com espaços de nome, poderíamos, em alternativa, Q# disponibilizar os nossos callables sem a `using NamespaceName;` declaração e simplesmente combinar o título de espaço de nome C# com ele.</span><span class="sxs-lookup"><span data-stu-id="8c492-253">Due to the compiler's interoperability with namespaces, we could alternatively make our Q# callables available without the `using NamespaceName;` statement, and simply matching the C# namespace title to it.</span></span>
> <span data-ttu-id="8c492-254">Isto é, substituindo `namespace host` `namespace NamespaceName` por.</span><span class="sxs-lookup"><span data-stu-id="8c492-254">That is, by replacing `namespace host` with `namespace NamespaceName`.</span></span>

#### <a name="including-the-resources-estimator"></a><span data-ttu-id="8c492-255">Incluindo o estimador de recursos</span><span class="sxs-lookup"><span data-stu-id="8c492-255">Including the resources estimator</span></span>

<span data-ttu-id="8c492-256">[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)Requer uma implementação ligeiramente diferente para recuperar a saída.</span><span class="sxs-lookup"><span data-stu-id="8c492-256">The [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requires a slightly different implementation to retrieve the output.</span></span>

<span data-ttu-id="8c492-257">Em primeiro lugar, em vez de os instantanear como uma variável com uma `using` afirmação (como fazemos com `QuantumSimulator` o), mais diretamente instantâneos objetos da classe via</span><span class="sxs-lookup"><span data-stu-id="8c492-257">Firstly, instead of instantiating them as a variable with a `using` statement (as we do with the `QuantumSimulator`), we more directly instantiate objects of the class via</span></span>

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

<span data-ttu-id="8c492-258">Note que em vez de um único simulador de alvo para ser usado por múltiplas Q# operações, instantaneamente um para cada um.</span><span class="sxs-lookup"><span data-stu-id="8c492-258">Notice that instead of a single target simulator to be used by multiple Q# operations, we have instantiated one for each.</span></span> <span data-ttu-id="8c492-259">Isto porque os próprios objetos são modificados quando utilizados como máquinas-alvo, podendo os seus resultados ser recuperados posteriormente com o método de classe `.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="8c492-259">This is because the objects themselves are modified when used as target machines, and their results can then be retrieved afterwards with the class method `.ToTSV()`.</span></span>

<span data-ttu-id="8c492-260">Para executar as operações nos estimadores de recursos, usamos</span><span class="sxs-lookup"><span data-stu-id="8c492-260">To run the operations on the resource estimators, we use</span></span>

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
<span data-ttu-id="8c492-261">e, em seguida, obter os resultados como valores separados por separados (TSV) com `estimatorSingleQ.ToTSV()` e `estimatorMultiQ.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="8c492-261">and then fetch the results as tab-separated-values (TSV) with `estimatorSingleQ.ToTSV()` and `estimatorMultiQ.ToTSV()`.</span></span>

<span data-ttu-id="8c492-262">Assim, um programa de anfitrião C# completo que faz uso de ambos `QuantumSimulator` e pode assumir o `ResourcesEstimator` formulário:</span><span class="sxs-lookup"><span data-stu-id="8c492-262">So, a full C# host program making use of both the `QuantumSimulator` and `ResourcesEstimator` could take the form:</span></span>

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


<span data-ttu-id="8c492-263">que produziria produção semelhante a</span><span class="sxs-lookup"><span data-stu-id="8c492-263">which would yield output similar to</span></span>

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

## <a name="no-locq-jupyter-notebooks"></a><span data-ttu-id="8c492-264">Q#Cadernos Jupyter</span><span class="sxs-lookup"><span data-stu-id="8c492-264">Q# Jupyter Notebooks</span></span>
<span data-ttu-id="8c492-265">Q#Os Cadernos Jupyter utilizam o Q# núcleo I, que permite definir, compilar e executar Q# callables num único caderno--- tudo ao lado de instruções, notas e outros conteúdos.</span><span class="sxs-lookup"><span data-stu-id="8c492-265">Q# Jupyter Notebooks make use of the IQ# kernel, which allows you to define, compile, and run Q# callables in a single notebook---all alongside instructions, notes, and other content.</span></span>
<span data-ttu-id="8c492-266">Isto significa que, embora seja possível importar e utilizar o conteúdo dos `*.qs` Q# ficheiros, estes não são necessários no modelo de execução.</span><span class="sxs-lookup"><span data-stu-id="8c492-266">This means that while it is possible to import and use the contents of `*.qs` Q# files, they are not necessary in the execution model.</span></span>

<span data-ttu-id="8c492-267">Aqui, vamos detalhar como executar as Q# operações acima definidas, mas uma introdução mais ampla à utilização Q# de Cadernos Jupyter é fornecida na [Introdução e Q# Jupyter Notebooks.](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)</span><span class="sxs-lookup"><span data-stu-id="8c492-267">Here, we will detail how to run the Q# operations defined above, but a more broad introduction to using Q# Jupyter Notebooks is provided at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span></span>

### <a name="defining-operations"></a><span data-ttu-id="8c492-268">Definição de operações</span><span class="sxs-lookup"><span data-stu-id="8c492-268">Defining operations</span></span>

<span data-ttu-id="8c492-269">Num Q# Caderno Jupyter, introduzes Q# código como nós de dentro do espaço de nome de um Q# ficheiro.</span><span class="sxs-lookup"><span data-stu-id="8c492-269">In a Q# Jupyter Notebook, you enter Q# code just as we would from inside the namespace of a Q# file.</span></span>

<span data-ttu-id="8c492-270">Assim, podemos permitir o acesso a callables a partir das [ Q# bibliotecas padrão](xref:microsoft.quantum.qsharplibintro) com `open` declarações para os respetivos espaços de nome.</span><span class="sxs-lookup"><span data-stu-id="8c492-270">So, we can enable access to callables from the [Q# standard libraries](xref:microsoft.quantum.qsharplibintro) with `open` statements for their respective namespaces.</span></span>
<span data-ttu-id="8c492-271">Ao executar uma célula com tal afirmação, as definições desses espaços de nome estão disponíveis em todo o espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="8c492-271">Upon running a cell with such a statement, the definitions from those namespaces are available throughout the workspace.</span></span>

> [!NOTE]
> <span data-ttu-id="8c492-272">As chamadas da [Microsoft.Quantum.Intrínseca](xref:microsoft.quantum.intrinsic) e [da Microsoft.Quantum.Canon](xref:microsoft.quantum.canon) (por [`H`](xref:microsoft.quantum.intrinsic.h) exemplo, [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) e) estão automaticamente disponíveis para operações definidas dentro de células em Q# Cadernos Jupyter.</span><span class="sxs-lookup"><span data-stu-id="8c492-272">Callables from [Microsoft.Quantum.Intrinsic](xref:microsoft.quantum.intrinsic) and [Microsoft.Quantum.Canon](xref:microsoft.quantum.canon) (e.g. [`H`](xref:microsoft.quantum.intrinsic.h) and [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach)) are automatically available to operations defined within cells in Q# Jupyter Notebooks.</span></span>
> <span data-ttu-id="8c492-273">No entanto, isso não é verdade para o código trazido a partir de ficheiros de origem externa Q# (um processo mostrado na Introdução e na [ Q# Jupyter Notebooks).](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)</span><span class="sxs-lookup"><span data-stu-id="8c492-273">However, this is not true for code brought in from external Q# source files (a process shown at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span></span> 
> 

<span data-ttu-id="8c492-274">Da mesma forma, a definição de operações requer apenas escrever o Q# código e executar a célula.</span><span class="sxs-lookup"><span data-stu-id="8c492-274">Similarly, defining operations requires only writing the Q# code and running the cell.</span></span>

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="600">

<span data-ttu-id="8c492-275">A saída enumera então essas operações, que podem ser chamadas de futuras células.</span><span class="sxs-lookup"><span data-stu-id="8c492-275">The output then lists those operations, which can then be called from future cells.</span></span>

### <a name="target-machines"></a><span data-ttu-id="8c492-276">Computadores de destino</span><span class="sxs-lookup"><span data-stu-id="8c492-276">Target machines</span></span>

<span data-ttu-id="8c492-277">A funcionalidade para executar operações em máquinas-alvo específicas é fornecida através de [I Q# Comandos Mágicos](xref:microsoft.quantum.guide.quickref.iqsharp).</span><span class="sxs-lookup"><span data-stu-id="8c492-277">The functionality to run operations on specific target machines is provided via [IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp).</span></span>
<span data-ttu-id="8c492-278">Por exemplo, `%simulate` faz uso do , e usa o `QuantumSimulator` `%estimate` `ResourcesEstimator` :</span><span class="sxs-lookup"><span data-stu-id="8c492-278">For example, `%simulate` makes use of the `QuantumSimulator`, and `%estimate` uses the `ResourcesEstimator`:</span></span>

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Simulate and estimate resources Jupyter cell" width="500">

### <a name="passing-inputs-to-functions-and-operations"></a><span data-ttu-id="8c492-279">Passando entradas para funções e operações</span><span class="sxs-lookup"><span data-stu-id="8c492-279">Passing inputs to functions and operations</span></span>

<span data-ttu-id="8c492-280">Atualmente, os comandos mágicos de execução só podem ser usados com operações que não têm argumentos.</span><span class="sxs-lookup"><span data-stu-id="8c492-280">Currently the execution magic commands can only be used with operations that take no arguments.</span></span> <span data-ttu-id="8c492-281">Assim, para `MeasureSuperpositionArray` correr, precisamos definir uma operação de "invólucro" que depois chama a operação com os argumentos:</span><span class="sxs-lookup"><span data-stu-id="8c492-281">So, to run `MeasureSuperpositionArray`, we need to define a "wrapper" operation which then calls the operation with the arguments:</span></span>

<img src="../media/hostprograms_jupyter_wrapper_def_sim_crop.png" alt="Wrapper function and simulate Jupyter cell" width="550">

<span data-ttu-id="8c492-282">Esta operação pode, naturalmente, ser utilizada da mesma forma com `%estimate` outros comandos de execução.</span><span class="sxs-lookup"><span data-stu-id="8c492-282">This operation can of course be used similarly with `%estimate` and other execution commands.</span></span>
