---
title: 'Formas de executar um :::no-loc(Q#)::: programa'
description: 'Visão geral das diferentes formas de executar :::no-loc(Q#)::: programas. A partir do pedido de comando, :::no-loc(Q#)::: Jupyter Notebooks, e programas de anfitrião clássicos em Python ou uma língua .NET.'
author: gillenhaalb
ms.author: a-gibec
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: f1a4ef0616a8a3f1548b7a7207cf8cbb9dcc7260
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691709"
---
# <a name="ways-to-run-a-no-locq-program"></a><span data-ttu-id="e294f-104">Formas de executar um :::no-loc(Q#)::: programa</span><span class="sxs-lookup"><span data-stu-id="e294f-104">Ways to run a :::no-loc(Q#)::: program</span></span>

<span data-ttu-id="e294f-105">Um dos maiores pontos fortes do Kit de Desenvolvimento Quântico é a sua flexibilidade em plataformas e ambientes de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="e294f-105">One of the Quantum Development Kit's greatest strengths is its flexibility across platforms and development environments.</span></span>
<span data-ttu-id="e294f-106">No entanto, isto também significa que os novos :::no-loc(Q#)::: utilizadores podem encontrar-se confusos ou sobrecarregados com as inúmeras opções encontradas no [guia de instalação](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="e294f-106">However, this also means that new :::no-loc(Q#)::: users may find themselves confused or overwhelmed by the numerous options found in the [install guide](xref:microsoft.quantum.install).</span></span>
<span data-ttu-id="e294f-107">Nesta página, explicamos o que acontece quando um :::no-loc(Q#)::: programa é executado, e comparamos as diferentes formas de os utilizadores o poderem fazer.</span><span class="sxs-lookup"><span data-stu-id="e294f-107">On this page, we explain what happens when a :::no-loc(Q#)::: program is run, and compare the different ways in which users can do so.</span></span>

<span data-ttu-id="e294f-108">Uma distinção primária é que :::no-loc(Q#)::: pode ser executada:</span><span class="sxs-lookup"><span data-stu-id="e294f-108">A primary distinction is that :::no-loc(Q#)::: can be run:</span></span>
- <span data-ttu-id="e294f-109">como uma aplicação autónoma, onde :::no-loc(Q#)::: é a única língua envolvida e o programa é invocado diretamente.</span><span class="sxs-lookup"><span data-stu-id="e294f-109">as a standalone application, where :::no-loc(Q#)::: is the only language involved and the program is invoked directly.</span></span> <span data-ttu-id="e294f-110">Na verdade, dois métodos enquadram-se nesta categoria:</span><span class="sxs-lookup"><span data-stu-id="e294f-110">Two methods actually fall in this category:</span></span>
  - <span data-ttu-id="e294f-111">a interface de linha de comando</span><span class="sxs-lookup"><span data-stu-id="e294f-111">the command-line interface</span></span>
  - <span data-ttu-id="e294f-112">:::no-loc(Q#)::: Cadernos Jupyter</span><span class="sxs-lookup"><span data-stu-id="e294f-112">:::no-loc(Q#)::: Jupyter Notebooks</span></span>
- <span data-ttu-id="e294f-113">com um programa adicional *de anfitrião* , escrito em Python ou uma língua .NET (por exemplo, C# ou F#), que depois invoca o programa e pode processar mais resultados devolvidos.</span><span class="sxs-lookup"><span data-stu-id="e294f-113">with an additional *host program* , written in Python or a .NET language (for example, C# or F#), which then invokes the program and can further process returned results.</span></span>

<span data-ttu-id="e294f-114">Para melhor entender estes processos e as suas diferenças, consideramos um programa simples :::no-loc(Q#)::: e comparamos as formas de execução.</span><span class="sxs-lookup"><span data-stu-id="e294f-114">To best understand these processes and their differences, we consider a simple :::no-loc(Q#)::: program and compare the ways it can be run.</span></span>

## <a name="basic-no-locq-program"></a><span data-ttu-id="e294f-115">Programa :::no-loc(Q#)::: básico</span><span class="sxs-lookup"><span data-stu-id="e294f-115">Basic :::no-loc(Q#)::: program</span></span>

<span data-ttu-id="e294f-116">Um programa quântico básico pode consistir em preparar um qubit em uma superposição igual de Estados {0} $\ket $ e $\ket {1} $, medindo-o, e devolvendo o resultado, que será aleatoriamente qualquer um destes dois estados com igual probabilidade.</span><span class="sxs-lookup"><span data-stu-id="e294f-116">A basic quantum program might consist of preparing a qubit in an equal superposition of states $\ket{0}$ and $\ket{1}$, measuring it, and returning the result, which will be randomly either one of these two states with equal probability.</span></span>
<span data-ttu-id="e294f-117">Na verdade, este processo está no centro do rápido arranque do [gerador de números aleatórios quânticos.](xref:microsoft.quantum.quickstarts.qrng)</span><span class="sxs-lookup"><span data-stu-id="e294f-117">Indeed, this process is at the core of the [quantum random number generator](xref:microsoft.quantum.quickstarts.qrng) quickstart.</span></span>

<span data-ttu-id="e294f-118">Em :::no-loc(Q#)::: , isto seria realizado pelo seguinte código:</span><span class="sxs-lookup"><span data-stu-id="e294f-118">In :::no-loc(Q#):::, this would be performed by the following code:</span></span>

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

<span data-ttu-id="e294f-119">No entanto, este código por si só não pode ser gerido :::no-loc(Q#)::: por.</span><span class="sxs-lookup"><span data-stu-id="e294f-119">However, this code alone can't be run by :::no-loc(Q#):::.</span></span>
<span data-ttu-id="e294f-120">Para isso, tem de constituir o corpo de uma [operação](xref:microsoft.quantum.guide.basics#q-operations-and-functions), que é depois executada quando chamada--- direto ou por outra operação.</span><span class="sxs-lookup"><span data-stu-id="e294f-120">For that, it needs to make up the body of an [operation](xref:microsoft.quantum.guide.basics#q-operations-and-functions), which is then run when called---either directly or by another operation.</span></span> <span data-ttu-id="e294f-121">Assim, pode escrever uma operação do seguinte formulário:</span><span class="sxs-lookup"><span data-stu-id="e294f-121">Hence, you can write an operation of the following form:</span></span>
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
<span data-ttu-id="e294f-122">Definiu uma `MeasureSuperposition` operação, que não leva entradas e devolve um valor do tipo [Resultado](xref:microsoft.quantum.guide.types).</span><span class="sxs-lookup"><span data-stu-id="e294f-122">You have defined an operation, `MeasureSuperposition`, which takes no inputs and returns a value of type [Result](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="e294f-123">Embora os exemplos nesta página consistam apenas em :::no-loc(Q#)::: *operações,* todos os conceitos que discutiremos dizem igualmente respeito às :::no-loc(Q#)::: *funções* , e, portanto, referimo-los colectivamente como *callables.*</span><span class="sxs-lookup"><span data-stu-id="e294f-123">While the examples on this page only consist of :::no-loc(Q#)::: *operations* , all of the concepts we will discuss pertain equally to :::no-loc(Q#)::: *functions* , and therefore we refer to them collectively as *callables* .</span></span> <span data-ttu-id="e294f-124">As suas diferenças são discutidas no [ :::no-loc(Q#)::: básico: operações e funções,](xref:microsoft.quantum.guide.basics#q-operations-and-functions)e mais detalhes sobre a definição das mesmas podem ser encontrados nas [Operações e funções.](xref:microsoft.quantum.guide.operationsfunctions)</span><span class="sxs-lookup"><span data-stu-id="e294f-124">Their differences are discussed at [:::no-loc(Q#)::: basics: operations and functions](xref:microsoft.quantum.guide.basics#q-operations-and-functions), and more details on defining them can be found at [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

### <a name="callable-defined-in-a-no-locq-file"></a><span data-ttu-id="e294f-125">Calável definido num :::no-loc(Q#)::: ficheiro</span><span class="sxs-lookup"><span data-stu-id="e294f-125">Callable defined in a :::no-loc(Q#)::: file</span></span>

<span data-ttu-id="e294f-126">O callable é precisamente o que é chamado e dirigido :::no-loc(Q#)::: por.</span><span class="sxs-lookup"><span data-stu-id="e294f-126">The callable is precisely what's called and run by :::no-loc(Q#):::.</span></span>
<span data-ttu-id="e294f-127">No entanto, requer mais algumas adições para incluir um `*.qs` :::no-loc(Q#)::: ficheiro completo.</span><span class="sxs-lookup"><span data-stu-id="e294f-127">However, it requires a few more additions to comprise a full `*.qs` :::no-loc(Q#)::: file.</span></span>

<span data-ttu-id="e294f-128">Todos os :::no-loc(Q#)::: tipos e callables (tanto aqueles que define como os intrínsecos à língua) são definidos dentro *de espaços de nome,* que fornecem a cada um um nome completo que pode então ser referenciado.</span><span class="sxs-lookup"><span data-stu-id="e294f-128">All :::no-loc(Q#)::: types and callables (both those you define and those intrinsic to the language) are defined within *namespaces* , which provide each a full name that can then be referenced.</span></span>

<span data-ttu-id="e294f-129">Por exemplo, as [`H`](xref:Microsoft.Quantum.Intrinsic.H) operações e [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) as operações [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) encontram-se nos espaços e [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) nomes (parte das [ :::no-loc(Q#)::: Bibliotecas Padrão).](xref:microsoft.quantum.qsharplibintro)</span><span class="sxs-lookup"><span data-stu-id="e294f-129">For example, the [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) operations are found in the [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) and [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) namespaces (part of the [:::no-loc(Q#)::: Standard Libraries](xref:microsoft.quantum.qsharplibintro)).</span></span>
<span data-ttu-id="e294f-130">Como tal, podem sempre ser chamados através dos seus nomes *completos,* `Microsoft.Quantum.Intrinsic.H(<qubit>)` e , mas `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` fazê-lo sempre levaria a um código muito desordenado.</span><span class="sxs-lookup"><span data-stu-id="e294f-130">As such, they can always be called via their *full* names, `Microsoft.Quantum.Intrinsic.H(<qubit>)` and `Microsoft.Quantum.Measurement.MResetZ(<qubit>)`, but always doing this would lead to very cluttered code.</span></span>

<span data-ttu-id="e294f-131">Em vez disso, `open` as declarações permitem que os callables sejam referenciados com uma abreviatura mais concisa, como fizemos no corpo de operação acima.</span><span class="sxs-lookup"><span data-stu-id="e294f-131">Instead, `open` statements allow callables to be referenced with more concise shorthand, as we've done in the operation body above.</span></span>
<span data-ttu-id="e294f-132">O ficheiro completo :::no-loc(Q#)::: que contém a nossa operação consistiria, portanto, em definir o nosso próprio espaço de nome, abrindo os espaços de nome para os callables que a nossa operação utiliza e, em seguida, a nossa operação:</span><span class="sxs-lookup"><span data-stu-id="e294f-132">The full :::no-loc(Q#)::: file containing our operation would therefore consist of defining our own namespace, opening the namespaces for those callables our operation uses, and then our operation:</span></span>

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
> <span data-ttu-id="e294f-133">Os espaços de nome também podem ser *aliased quando abertos,* o que pode ser útil se nomes callable/tipo em dois espaços de nome conflito.</span><span class="sxs-lookup"><span data-stu-id="e294f-133">Namespaces can also be *aliased* when opened, which can be helpful if callable/type names in two namespaces conflict.</span></span>
> <span data-ttu-id="e294f-134">Por exemplo, poderíamos, em vez disso, usar `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` acima, e depois ligar `H` via `NamespaceWithH.H(<qubit>)` .</span><span class="sxs-lookup"><span data-stu-id="e294f-134">For example, we could instead use `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` above, and then call `H` via `NamespaceWithH.H(<qubit>)`.</span></span>

> [!NOTE]
> <span data-ttu-id="e294f-135">Uma exceção a tudo isto é o espaço de [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) nome, que é sempre automaticamente aberto.</span><span class="sxs-lookup"><span data-stu-id="e294f-135">One exception to all of this is the [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) namespace, which is always automatically opened.</span></span>
> <span data-ttu-id="e294f-136">Portanto, os calíveis como [`Length`](xref:Microsoft.Quantum.Core.Length) podem sempre ser usados diretamente.</span><span class="sxs-lookup"><span data-stu-id="e294f-136">Therefore, callables like [`Length`](xref:Microsoft.Quantum.Core.Length) can always be used directly.</span></span>

### <a name="running-on-target-machines"></a><span data-ttu-id="e294f-137">Correndo em máquinas-alvo</span><span class="sxs-lookup"><span data-stu-id="e294f-137">Running on target machines</span></span>

<span data-ttu-id="e294f-138">Agora o modelo de execução geral de um :::no-loc(Q#)::: programa torna-se claro.</span><span class="sxs-lookup"><span data-stu-id="e294f-138">Now the general run model of a :::no-loc(Q#)::: program becomes clear.</span></span>

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt=":::no-loc(Q#)::: program execution diagram" width="400">

<span data-ttu-id="e294f-139">Em primeiro lugar, a chamada específica a ser executada tem acesso a quaisquer outros calíveis e tipos definidos no mesmo espaço de nome.</span><span class="sxs-lookup"><span data-stu-id="e294f-139">Firstly, the specific callable to be run has access to any other callables and types defined in the same namespace.</span></span>
<span data-ttu-id="e294f-140">Também acede às que provêm de qualquer uma das [ :::no-loc(Q#)::: bibliotecas](xref:microsoft.quantum.libraries), mas estas devem ser referenciadas quer através do seu nome completo, quer através da utilização de `open` declarações acima descritas.</span><span class="sxs-lookup"><span data-stu-id="e294f-140">It also access those from any of the [:::no-loc(Q#)::: libraries](xref:microsoft.quantum.libraries), but those must be referenced either via their full name, or through the use of `open` statements described above.</span></span>

<span data-ttu-id="e294f-141">A própria chamada é então executada numa *[máquina-alvo](xref:microsoft.quantum.machines)* .</span><span class="sxs-lookup"><span data-stu-id="e294f-141">The callable itself is then run on a *[target machine](xref:microsoft.quantum.machines)* .</span></span>
<span data-ttu-id="e294f-142">Tais máquinas-alvo podem ser hardware quântico real ou os múltiplos simuladores disponíveis como parte do QDK.</span><span class="sxs-lookup"><span data-stu-id="e294f-142">Such target machines can be actual quantum hardware or the multiple simulators available as part of the QDK.</span></span>
<span data-ttu-id="e294f-143">Para os nossos propósitos aqui, a máquina alvo mais útil é um exemplo do [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator) `QuantumSimulator` , que calcula o comportamento do programa como se estivesse sendo executado em um computador quântico sem ruído.</span><span class="sxs-lookup"><span data-stu-id="e294f-143">For our purposes here, the most useful target machine is an instance of the [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator`, which calculates the program's behavior as if it were being run on a noise-free quantum computer.</span></span>

<span data-ttu-id="e294f-144">Até agora, descrevemos o que acontece quando uma chamada específica :::no-loc(Q#)::: está a ser executada.</span><span class="sxs-lookup"><span data-stu-id="e294f-144">So far, we've described what happens when a specific :::no-loc(Q#)::: callable is being run.</span></span>
<span data-ttu-id="e294f-145">Independentemente de ser :::no-loc(Q#)::: usado numa aplicação autónoma ou com um programa de acolhimento, este processo geral é mais ou menos o mesmo---a flexibilidade do QDK.</span><span class="sxs-lookup"><span data-stu-id="e294f-145">Regardless of whether :::no-loc(Q#)::: is used in a standalone application or with a host program, this general process is more or less the same---hence the QDK's flexibility.</span></span>
<span data-ttu-id="e294f-146">As diferenças entre as formas de chamar para o Kit de Desenvolvimento Quântico revelam-se, portanto, na *forma como* essa chamada é chamada a :::no-loc(Q#)::: ser executada, e de que forma quaisquer resultados são devolvidos.</span><span class="sxs-lookup"><span data-stu-id="e294f-146">The differences between the ways of calling into the Quantum Development Kit therefore reveal themselves in *how* that :::no-loc(Q#)::: callable is called to be run, and in what manner any results are returned.</span></span>
<span data-ttu-id="e294f-147">Mais especificamente, as diferenças giram em torno de:</span><span class="sxs-lookup"><span data-stu-id="e294f-147">More specifically, the differences revolve around:</span></span>

- <span data-ttu-id="e294f-148">Indicando qual :::no-loc(Q#)::: é o chamado a ser executado</span><span class="sxs-lookup"><span data-stu-id="e294f-148">Indicating which :::no-loc(Q#)::: callable is to be run</span></span>
- <span data-ttu-id="e294f-149">Como potenciais argumentos caláveis são fornecidos</span><span class="sxs-lookup"><span data-stu-id="e294f-149">How potential callable arguments are provided</span></span>
- <span data-ttu-id="e294f-150">Especificando a máquina-alvo em que a executar</span><span class="sxs-lookup"><span data-stu-id="e294f-150">Specifying the target machine on which to run it</span></span>
- <span data-ttu-id="e294f-151">Como quaisquer resultados são devolvidos</span><span class="sxs-lookup"><span data-stu-id="e294f-151">How any results are returned</span></span>

<span data-ttu-id="e294f-152">Primeiro, discutimos como isto é feito com a :::no-loc(Q#)::: aplicação autónoma a partir do pedido de comando, e depois procedemos à utilização de programas de anfitriões Python e C#.</span><span class="sxs-lookup"><span data-stu-id="e294f-152">First, we discuss how this is done with the :::no-loc(Q#)::: standalone application from the command prompt, and then proceed to using Python and C# host programs.</span></span>
<span data-ttu-id="e294f-153">Reservamos a aplicação autónoma de :::no-loc(Q#)::: Cadernos Jupyter para o final, porque ao contrário dos três primeiros, a sua funcionalidade primária não se centra em torno de um :::no-loc(Q#)::: arquivo local.</span><span class="sxs-lookup"><span data-stu-id="e294f-153">We reserve the standalone application of :::no-loc(Q#)::: Jupyter Notebooks for last, because unlike the first three, it's primary functionality does not center around a local :::no-loc(Q#)::: file.</span></span>

> [!NOTE]
> <span data-ttu-id="e294f-154">Embora não o ilustremos nestes exemplos, uma comunhão entre os métodos de execução é que quaisquer mensagens impressas a partir de dentro do :::no-loc(Q#)::: programa (por [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) exemplo) serão normalmente impressas na respetiva consola.</span><span class="sxs-lookup"><span data-stu-id="e294f-154">Although we don't illustrate it in these examples, one commonality between the run methods is that any messages printed from inside the :::no-loc(Q#)::: program (by way of [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) or [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine), for example) will typically always be printed to the respective console.</span></span>

## <a name="no-locq-from-the-command-prompt"></a><span data-ttu-id="e294f-155">:::no-loc(Q#)::: a partir da pronta de comando</span><span class="sxs-lookup"><span data-stu-id="e294f-155">:::no-loc(Q#)::: from the command prompt</span></span>
<span data-ttu-id="e294f-156">Uma das formas mais fáceis de começar a escrever :::no-loc(Q#)::: programas é evitar preocupar-se com ficheiros separados e uma segunda língua completamente.</span><span class="sxs-lookup"><span data-stu-id="e294f-156">One of the easiest ways to get started writing :::no-loc(Q#)::: programs is to avoid worrying about separate files and a second language altogether.</span></span>
<span data-ttu-id="e294f-157">A utilização do Visual Studio Code ou do Visual Studio com a extensão QDK permite um fluxo de trabalho sem emenda no qual executamos :::no-loc(Q#)::: callables a partir de apenas um :::no-loc(Q#)::: ficheiro.</span><span class="sxs-lookup"><span data-stu-id="e294f-157">Using Visual Studio Code or Visual Studio with the QDK extension allows for a seamless work flow in which we run :::no-loc(Q#)::: callables from only a single :::no-loc(Q#)::: file.</span></span>

<span data-ttu-id="e294f-158">Para isso, vamos, em última análise, executar o programa entrando</span><span class="sxs-lookup"><span data-stu-id="e294f-158">For this, we will ultimately run the program by entering</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="e294f-159">no pedido de comando.</span><span class="sxs-lookup"><span data-stu-id="e294f-159">at the command prompt.</span></span>
<span data-ttu-id="e294f-160">O fluxo de trabalho mais simples é quando a localização do diretório do terminal é a mesma que o :::no-loc(Q#)::: ficheiro, que pode ser facilmente manuseado ao lado :::no-loc(Q#)::: da edição de ficheiros utilizando o terminal integrado no Código VS, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="e294f-160">The simplest workflow is when the terminal's directory location is the same as the :::no-loc(Q#)::: file, which can be easily handled alongside :::no-loc(Q#)::: file editing by using the integrated terminal in VS Code, for example.</span></span>
<span data-ttu-id="e294f-161">No entanto, o [ `dotnet run` comando](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) aceita inúmeras opções, e o programa também pode ser executado a partir de um local diferente, simplesmente fornecendo `--project <PATH>` a localização do :::no-loc(Q#)::: ficheiro.</span><span class="sxs-lookup"><span data-stu-id="e294f-161">However, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepts numerous options, and the program can also be run from a different location by simply providing `--project <PATH>` with the location of the :::no-loc(Q#)::: file.</span></span>


### <a name="add-entry-point-to-no-locq-file"></a><span data-ttu-id="e294f-162">Adicionar ponto de entrada para :::no-loc(Q#)::: arquivar</span><span class="sxs-lookup"><span data-stu-id="e294f-162">Add entry point to :::no-loc(Q#)::: file</span></span>

<span data-ttu-id="e294f-163">A maioria dos :::no-loc(Q#)::: ficheiros conterá mais do que uma chamada, por isso, naturalmente, precisamos de informar o compilador *sobre qual* a chamada a executar quando fornecessarmos o `dotnet run` comando.</span><span class="sxs-lookup"><span data-stu-id="e294f-163">Most :::no-loc(Q#)::: files will contain more than one callable, so naturally we need to let the compiler know *which* callable to run when we provide the `dotnet run` command.</span></span>
<span data-ttu-id="e294f-164">Isto é feito com uma simples alteração ao :::no-loc(Q#)::: próprio ficheiro:</span><span class="sxs-lookup"><span data-stu-id="e294f-164">This is done with a simple change to the :::no-loc(Q#)::: file itself:</span></span> 
    - <span data-ttu-id="e294f-165">adicionar uma linha com `@EntryPoint()` diretamente precedendo o callable.</span><span class="sxs-lookup"><span data-stu-id="e294f-165">add a line with `@EntryPoint()` directly preceding the callable.</span></span>

<span data-ttu-id="e294f-166">Nosso arquivo de cima seria, portanto, tornar-se</span><span class="sxs-lookup"><span data-stu-id="e294f-166">Our file from above would therefore become</span></span>
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

<span data-ttu-id="e294f-167">Agora, uma chamada `dotnet run` do pedido de comando leva a ser `MeasureSuperposition` executado, e o valor devolvido é então impresso diretamente para o terminal.</span><span class="sxs-lookup"><span data-stu-id="e294f-167">Now, a call of `dotnet run` from the command prompt leads to `MeasureSuperposition` being run, and the returned value is then printed directly to the terminal.</span></span>
<span data-ttu-id="e294f-168">Então, verá um `One` ou `Zero` impresso.</span><span class="sxs-lookup"><span data-stu-id="e294f-168">So, you will see either `One` or `Zero` printed.</span></span> 

<span data-ttu-id="e294f-169">Note que não importa se tiver mais chamadas definidas abaixo, apenas `MeasureSuperposition` será executado.</span><span class="sxs-lookup"><span data-stu-id="e294f-169">Note that it doesn't matter if you have more callables defined below it, only `MeasureSuperposition` will be run.</span></span>
<span data-ttu-id="e294f-170">Além disso, não é problema se a sua chamada inclui comentários de [documentação](xref:microsoft.quantum.guide.filestructure#documentation-comments) antes da sua declaração, o `@EntryPoint()` atributo pode simplesmente ser colocado acima deles.</span><span class="sxs-lookup"><span data-stu-id="e294f-170">Additionally, it's no problem if your callable includes [documentation comments](xref:microsoft.quantum.guide.filestructure#documentation-comments) before its declaration, the `@EntryPoint()` attribute can be simply placed above them.</span></span>

### <a name="callable-arguments"></a><span data-ttu-id="e294f-171">Argumentos insutilizáveis</span><span class="sxs-lookup"><span data-stu-id="e294f-171">Callable arguments</span></span>

<span data-ttu-id="e294f-172">Até agora, só consideramos uma operação que não tem entradas.</span><span class="sxs-lookup"><span data-stu-id="e294f-172">So far, we've only considered an operation that takes no inputs.</span></span>
<span data-ttu-id="e294f-173">Suponha que quiséssemos realizar uma operação semelhante, mas em múltiplos qubits---o número do qual é fornecido como argumento.</span><span class="sxs-lookup"><span data-stu-id="e294f-173">Suppose we wanted to perform a similar operation, but on multiple qubits---the number of which is provided as an argument.</span></span>
<span data-ttu-id="e294f-174">Tal operação poderia ser escrito como</span><span class="sxs-lookup"><span data-stu-id="e294f-174">Such an operation could be written as</span></span>
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
<span data-ttu-id="e294f-175">onde o valor devolvido é um conjunto dos resultados da medição.</span><span class="sxs-lookup"><span data-stu-id="e294f-175">where the returned value is an array of the measurement results.</span></span>
<span data-ttu-id="e294f-176">Note que [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) e [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) estão nos [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) espaços e [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) nomes, exigindo declarações adicionais `open` para cada um.</span><span class="sxs-lookup"><span data-stu-id="e294f-176">Note that [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) and [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) are in the [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) and [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) namespaces, requiring additional `open` statements for each.</span></span>

<span data-ttu-id="e294f-177">Se movermos o `@EntryPoint()` atributo para preceder esta nova operação (note que só pode haver uma dessas linhas num ficheiro), tentar executá-lo simplesmente `dotnet run` resulta numa mensagem de erro que indica quais as opções adicionais da linha de comando e como expressá-las.</span><span class="sxs-lookup"><span data-stu-id="e294f-177">If we move the `@EntryPoint()` attribute to precede this new operation (note there can only be one such line in a file), attempting to run it with simply `dotnet run` results in an error message which indicates what additional command-line options are required, and how to express them.</span></span>

<span data-ttu-id="e294f-178">O formato geral da linha de comando é, na `dotnet run [options]` verdade, e os argumentos callable são fornecidos lá.</span><span class="sxs-lookup"><span data-stu-id="e294f-178">The general format for the command line is actually `dotnet run [options]`, and callable arguments are provided there.</span></span>
<span data-ttu-id="e294f-179">Neste caso, falta o `n` argumento, e mostra que temos de fornecer a opção. `-n <n>`</span><span class="sxs-lookup"><span data-stu-id="e294f-179">In this case, the argument `n` is missing, and it shows that we need to provide the option `-n <n>`.</span></span> <span data-ttu-id="e294f-180">Para correr `MeasureSuperpositionArray` para `n=4` qubits, portanto usamos</span><span class="sxs-lookup"><span data-stu-id="e294f-180">To run `MeasureSuperpositionArray` for `n=4` qubits, we therefore use</span></span>

```dotnetcli
dotnet run -n 4
```

<span data-ttu-id="e294f-181">produzindo uma saída semelhante a</span><span class="sxs-lookup"><span data-stu-id="e294f-181">yielding an output similar to</span></span>

```output
[Zero,One,One,One]
```

<span data-ttu-id="e294f-182">Isto, naturalmente, estende-se a múltiplos argumentos.</span><span class="sxs-lookup"><span data-stu-id="e294f-182">This of course extends to multiple arguments.</span></span>

> [!NOTE]
> <span data-ttu-id="e294f-183">Os nomes de argumentos `camelCase` definidos são ligeiramente alterados pelo compilador para serem aceites como :::no-loc(Q#)::: entradas.</span><span class="sxs-lookup"><span data-stu-id="e294f-183">Argument names defined in `camelCase` are slightly altered by the compiler to be accepted as :::no-loc(Q#)::: inputs.</span></span> <span data-ttu-id="e294f-184">Por exemplo, se em vez `n` de, nós usamos o nome `numQubits` acima, então esta entrada seria fornecida na linha de comando via `--num-qubits 4` em vez de `-n 4` .</span><span class="sxs-lookup"><span data-stu-id="e294f-184">For example, if instead of `n`, we used the name `numQubits` above, then this input would be provided in the command line via `--num-qubits 4` instead of `-n 4`.</span></span>

<span data-ttu-id="e294f-185">A mensagem de erro também fornece outras opções que podem ser usadas, incluindo como alterar a máquina-alvo.</span><span class="sxs-lookup"><span data-stu-id="e294f-185">The error message also provides other options which can be used, including how to change the target machine.</span></span>

### <a name="different-target-machines"></a><span data-ttu-id="e294f-186">Diferentes máquinas-alvo</span><span class="sxs-lookup"><span data-stu-id="e294f-186">Different target machines</span></span>

<span data-ttu-id="e294f-187">Como as saídas das nossas operações até agora têm sido os resultados esperados da sua ação em qubits reais, é claro que a máquina-alvo padrão da linha de comando é o simulador quântico de estado completo, `QuantumSimulator` .</span><span class="sxs-lookup"><span data-stu-id="e294f-187">As the outputs from our operations thus far have been the expected results of their action on real qubits, it's clear that the default target machine from the command line is the full-state quantum simulator, `QuantumSimulator`.</span></span>
<span data-ttu-id="e294f-188">No entanto, podemos instruir os callables a serem executados numa máquina-alvo específica com a opção `--simulator` (ou a abreviatura). `-s`</span><span class="sxs-lookup"><span data-stu-id="e294f-188">However, we can instruct callables to be run on a specific target machine with the option `--simulator` (or the shorthand `-s`).</span></span>

<span data-ttu-id="e294f-189">Por exemplo, poderíamos executá-lo [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) em:</span><span class="sxs-lookup"><span data-stu-id="e294f-189">For example, we could run it on [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator):</span></span>

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

<span data-ttu-id="e294f-190">A saída impressa é então</span><span class="sxs-lookup"><span data-stu-id="e294f-190">The printed output is then</span></span>

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

<span data-ttu-id="e294f-191">Para obter mais informações sobre o que estas métricas indicam, consulte [o estimador de recursos: métricas reportadas](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span><span class="sxs-lookup"><span data-stu-id="e294f-191">For details on what these metrics indicate, see [Resource estimator: metrics reported](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span></span>

### <a name="command-line-run-summary"></a><span data-ttu-id="e294f-192">Resumo da linha de comando</span><span class="sxs-lookup"><span data-stu-id="e294f-192">Command line run summary</span></span>
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt=":::no-loc(Q#)::: program from command line" width="700">

### <a name="non-no-locq-dotnet-run-options"></a><span data-ttu-id="e294f-193">:::no-loc(Q#)::: `dotnet run` Não-opções</span><span class="sxs-lookup"><span data-stu-id="e294f-193">Non-:::no-loc(Q#)::: `dotnet run` options</span></span>

<span data-ttu-id="e294f-194">Como mencionamos brevemente acima com a `--project` opção, o [ `dotnet run` comando](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) também aceita opções não relacionadas com os :::no-loc(Q#)::: argumentos caláveis.</span><span class="sxs-lookup"><span data-stu-id="e294f-194">As we briefly mentioned above with the `--project` option, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) also accepts options unrelated to the :::no-loc(Q#)::: callable arguments.</span></span>
<span data-ttu-id="e294f-195">Se fornecer ambos os tipos de opções, as `dotnet` opções específicas devem ser fornecidas primeiro, seguidas por um delimetro `--` , e depois as :::no-loc(Q#)::: opções específicas.</span><span class="sxs-lookup"><span data-stu-id="e294f-195">If providing both kinds of options, the `dotnet`-specific options must be provided first, followed by a delimeter `--`, and then the :::no-loc(Q#):::-specific options.</span></span>
<span data-ttu-id="e294f-196">Por exemplo, especificar um caminho juntamente com um número de qubits para a operação acima seria executado via `dotnet run --project <PATH> -- -n <n>` .</span><span class="sxs-lookup"><span data-stu-id="e294f-196">For example, specifying a path along with a number qubits for the operation above would be run via `dotnet run --project <PATH> -- -n <n>`.</span></span>

## <a name="no-locq-with-host-programs"></a><span data-ttu-id="e294f-197">:::no-loc(Q#)::: com programas de anfitrião</span><span class="sxs-lookup"><span data-stu-id="e294f-197">:::no-loc(Q#)::: with host programs</span></span>

<span data-ttu-id="e294f-198">Com o nosso :::no-loc(Q#)::: ficheiro na mão, uma alternativa para chamar uma operação ou funcionar diretamente a partir do pedido de comando é usar um *programa de anfitrião* em outra língua clássica.</span><span class="sxs-lookup"><span data-stu-id="e294f-198">With our :::no-loc(Q#)::: file in hand, an alternative to calling an operation or function directly from the command prompt is to use a *host program* in another classical language.</span></span> <span data-ttu-id="e294f-199">Especificamente, isto pode ser feito com python ou uma língua .NET como C# ou F# (por uma questão de brevidade só vamos detalhar C# aqui).</span><span class="sxs-lookup"><span data-stu-id="e294f-199">Specifically, this can be done with either Python or a .NET language such as C# or F# (for the sake of brevity we will only detail C# here).</span></span>
<span data-ttu-id="e294f-200">É necessário um pouco mais de configuração para permitir a interoperabilidade, mas esses detalhes podem ser encontrados nos [guias de instalação](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="e294f-200">A little more setup is required to enable the interoperability, but those details can be found in the [install guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="e294f-201">Em resumo, a situação agora inclui um ficheiro de programa de anfitrião (por exemplo, `*.py` `*.cs` ou) no mesmo local que o nosso :::no-loc(Q#)::: ficheiro.</span><span class="sxs-lookup"><span data-stu-id="e294f-201">In a nutshell, the situation now includes a host program file (for example, `*.py` or `*.cs`) in the same location as our :::no-loc(Q#)::: file.</span></span>
<span data-ttu-id="e294f-202">É agora o programa *de anfitrião* que é executado, e enquanto está em execução, pode chamar :::no-loc(Q#)::: operações e funções específicas do :::no-loc(Q#)::: ficheiro.</span><span class="sxs-lookup"><span data-stu-id="e294f-202">It's now the *host* program that gets run, and while it is running, it can call specific :::no-loc(Q#)::: operations and functions from the :::no-loc(Q#)::: file.</span></span>
<span data-ttu-id="e294f-203">O núcleo da interoperabilidade baseia-se no :::no-loc(Q#)::: compilador que torna o conteúdo do :::no-loc(Q#)::: ficheiro acessível ao programa anfitrião para que possam ser chamados.</span><span class="sxs-lookup"><span data-stu-id="e294f-203">The core of the interoperability is based on the :::no-loc(Q#)::: compiler making the contents of the :::no-loc(Q#)::: file accessible to the host program so that they can be called.</span></span>

<span data-ttu-id="e294f-204">Um dos principais benefícios da utilização de um programa de anfitrião é que os dados clássicos devolvidos pelo :::no-loc(Q#)::: programa podem então ser processados na língua de acolhimento.</span><span class="sxs-lookup"><span data-stu-id="e294f-204">One of the main benefits of using a host program is that the classical data returned by the :::no-loc(Q#)::: program can then be further processed in the host language.</span></span>
<span data-ttu-id="e294f-205">Isto poderia consistir em algum processamento avançado de dados (por exemplo, algo que não pode ser realizado internamente), e, em :::no-loc(Q#)::: seguida, chamar mais :::no-loc(Q#)::: ações com base nesses resultados, ou algo tão simples como traçar os :::no-loc(Q#)::: resultados.</span><span class="sxs-lookup"><span data-stu-id="e294f-205">This could consist of some advanced data processing (for example, something that can't be performed internally in :::no-loc(Q#):::), and then calling further :::no-loc(Q#)::: actions based on those results, or something as simple as plotting the :::no-loc(Q#)::: results.</span></span>

<span data-ttu-id="e294f-206">O esquema geral é mostrado aqui, e discutimos as implementações específicas para Python e C# abaixo.</span><span class="sxs-lookup"><span data-stu-id="e294f-206">The general scheme is shown here, and we discuss the specific implementations for Python and C# below.</span></span> <span data-ttu-id="e294f-207">Uma amostra utilizando um programa de anfitrião F# pode ser encontrada nas [amostras de interoperabilidade .NET](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="e294f-207">A sample using an F# host program can be found at the [.NET interoperability samples](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt=":::no-loc(Q#)::: program from a host program" width="700">

> [!NOTE]
> <span data-ttu-id="e294f-208">O `@EntryPoint()` atributo utilizado para :::no-loc(Q#)::: aplicações não pode ser utilizado com programas de anfitrião.</span><span class="sxs-lookup"><span data-stu-id="e294f-208">The `@EntryPoint()` attribute used for :::no-loc(Q#)::: applications cannot be used with host programs.</span></span>
> <span data-ttu-id="e294f-209">Um erro será levantado se estiver presente no :::no-loc(Q#)::: ficheiro sendo chamado por um anfitrião.</span><span class="sxs-lookup"><span data-stu-id="e294f-209">An error will be raised if it is present in the :::no-loc(Q#)::: file being called by a host.</span></span> 

<span data-ttu-id="e294f-210">Para trabalhar com diferentes programas de anfitrião, não são necessárias alterações a um `*.qs` :::no-loc(Q#)::: ficheiro.</span><span class="sxs-lookup"><span data-stu-id="e294f-210">To work with different host programs, there are no changes required to a `*.qs` :::no-loc(Q#)::: file.</span></span>
<span data-ttu-id="e294f-211">As seguintes implementações do programa anfitrião funcionam com o mesmo :::no-loc(Q#)::: ficheiro:</span><span class="sxs-lookup"><span data-stu-id="e294f-211">The following host program implementations all work with the same :::no-loc(Q#)::: file:</span></span>

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

<span data-ttu-id="e294f-212">Selecione o separador correspondente ao seu idioma de interesse anfitrião.</span><span class="sxs-lookup"><span data-stu-id="e294f-212">Select the tab corresponding to your host language of interest.</span></span>

### <a name="python"></a>[<span data-ttu-id="e294f-213">Python</span><span class="sxs-lookup"><span data-stu-id="e294f-213">Python</span></span>](#tab/tabid-python)
<span data-ttu-id="e294f-214">Um programa de anfitrião Python é construído da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="e294f-214">A Python host program is constructed as follows:</span></span>
1. <span data-ttu-id="e294f-215">Importe o `qsharp` módulo, que regista o carregador de módulos para :::no-loc(Q#)::: interoperabilidade.</span><span class="sxs-lookup"><span data-stu-id="e294f-215">Import the `qsharp` module, which registers the module loader for :::no-loc(Q#)::: interoperability.</span></span> 
    <span data-ttu-id="e294f-216">Isto permite que :::no-loc(Q#)::: os espaços de nome apareçam como módulos Python, a partir dos quais podemos "importar" :::no-loc(Q#)::: callables.</span><span class="sxs-lookup"><span data-stu-id="e294f-216">This allows :::no-loc(Q#)::: namespaces to appear as Python modules, from which we can "import" :::no-loc(Q#)::: callables.</span></span>
    <span data-ttu-id="e294f-217">Note-se que, tecnicamente, não são os :::no-loc(Q#)::: próprios callables que são importados, mas sim os canhotos Python que permitem chamá-los.</span><span class="sxs-lookup"><span data-stu-id="e294f-217">Note that it is technically not the :::no-loc(Q#)::: callables themselves which are imported, but rather Python stubs which allow calling into them.</span></span>
    <span data-ttu-id="e294f-218">Estes comportam-se como objetos das aulas de Python.</span><span class="sxs-lookup"><span data-stu-id="e294f-218">These behave as objects of Python classes.</span></span> <span data-ttu-id="e294f-219">Utilizamos métodos nestes objetos para especificar as máquinas-alvo para as quais enviamos a operação quando executamos o programa.</span><span class="sxs-lookup"><span data-stu-id="e294f-219">We use methods on these objects to specify the target machines that we send the operation to when running the program.</span></span>

2. <span data-ttu-id="e294f-220">Importe os :::no-loc(Q#)::: calíveis que invocaremos directamente--- neste caso, `MeasureSuperposition` `MeasureSuperpositionArray` e.</span><span class="sxs-lookup"><span data-stu-id="e294f-220">Import those :::no-loc(Q#)::: callables which we will directly invoke---in this case, `MeasureSuperposition` and `MeasureSuperpositionArray`.</span></span>
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    <span data-ttu-id="e294f-221">Com o `qsharp` módulo importado, também pode importar callables diretamente dos espaços de nome da :::no-loc(Q#)::: biblioteca.</span><span class="sxs-lookup"><span data-stu-id="e294f-221">With the `qsharp` module imported, you can also import callables directly from the :::no-loc(Q#)::: library namespaces.</span></span>

3. <span data-ttu-id="e294f-222">Entre qualquer outro código Python, pode agora ligar para as chamadas em máquinas-alvo específicas e atribuir os seus retornos a variáveis (se devolverem um valor) para posterior utilização.</span><span class="sxs-lookup"><span data-stu-id="e294f-222">Among any other Python code, you can now call those callables on specific target machines, and assign their returns to variables (if they return a value) for further use.</span></span>

#### <a name="specifying-target-machines"></a><span data-ttu-id="e294f-223">Especificar máquinas-alvo</span><span class="sxs-lookup"><span data-stu-id="e294f-223">Specifying target machines</span></span>
<span data-ttu-id="e294f-224">Chamar uma operação a ser executada numa máquina-alvo específica é feita através de diferentes métodos Python no objeto importado.</span><span class="sxs-lookup"><span data-stu-id="e294f-224">Calling an operation to be run on a specific target machine is done via different Python methods on the imported object.</span></span>
<span data-ttu-id="e294f-225">Por `.simulate(<args>)` exemplo, usa o `QuantumSimulator` para executar a operação, enquanto `.estimate_resources(<args>)` o faz no `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="e294f-225">For example, `.simulate(<args>)`, uses the `QuantumSimulator` to run the operation, whereas `.estimate_resources(<args>)` does so on the `ResourcesEstimator`.</span></span>

#### <a name="passing-inputs-to-q"></a><span data-ttu-id="e294f-226">Passando entradas para Q\#</span><span class="sxs-lookup"><span data-stu-id="e294f-226">Passing inputs to Q\#</span></span>
<span data-ttu-id="e294f-227">Os argumentos para a :::no-loc(Q#)::: chamada devem ser apresentados sob a forma de um argumento de palavra-chave, em que a palavra-chave é o nome do argumento na :::no-loc(Q#)::: definição de chamada.</span><span class="sxs-lookup"><span data-stu-id="e294f-227">Arguments for the :::no-loc(Q#)::: callable should be provided in the form of a keyword argument, where the keyword is the argument name in the :::no-loc(Q#)::: callable definition.</span></span>
<span data-ttu-id="e294f-228">Ou `MeasureSuperpositionArray.simulate(n=4)` seja, é válido, ao passo `MeasureSuperpositionArray.simulate(4)` que um erro.</span><span class="sxs-lookup"><span data-stu-id="e294f-228">That is, `MeasureSuperpositionArray.simulate(n=4)` is valid, whereas `MeasureSuperpositionArray.simulate(4)` would throw an error.</span></span>

<span data-ttu-id="e294f-229">Portanto, o programa de anfitrião Python</span><span class="sxs-lookup"><span data-stu-id="e294f-229">Therefore, the Python host program</span></span> 

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

<span data-ttu-id="e294f-230">resulta numa saída como a seguinte:</span><span class="sxs-lookup"><span data-stu-id="e294f-230">results in an output like the following:</span></span>

```output
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

#### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="e294f-231">Utilização :::no-loc(Q#)::: de código de outros projetos ou pacotes</span><span class="sxs-lookup"><span data-stu-id="e294f-231">Using :::no-loc(Q#)::: code from other projects or packages</span></span>

<span data-ttu-id="e294f-232">Por predefinição, o `import qsharp` comando carrega todos os `.qs` ficheiros na pasta atual e disponibiliza as suas :::no-loc(Q#)::: operações e funções para utilização a partir do interior do script Python.</span><span class="sxs-lookup"><span data-stu-id="e294f-232">By default, the `import qsharp` command loads all of the `.qs` files in the current folder and makes their :::no-loc(Q#)::: operations and functions available for use from inside the Python script.</span></span>

<span data-ttu-id="e294f-233">Para carregar :::no-loc(Q#)::: código de outra pasta, a [ `qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) pode ser usada para adicionar uma referência a um `.csproj` ficheiro para um projeto :::no-loc(Q#)::: (isto é, um projeto que faz `Microsoft.Quantum.Sdk` referência).</span><span class="sxs-lookup"><span data-stu-id="e294f-233">To load :::no-loc(Q#)::: code from another folder, the [`qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) can be used to add a reference to a `.csproj` file for a :::no-loc(Q#)::: project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span>
<span data-ttu-id="e294f-234">Este comando compilará quaisquer `.qs` ficheiros na pasta que contenha as `.csproj` sub-dobradeiras e as suas sub-dobradeiras.</span><span class="sxs-lookup"><span data-stu-id="e294f-234">This command will compile any `.qs` files in the folder containing the `.csproj` and its subfolders.</span></span> <span data-ttu-id="e294f-235">Também carregará novamente quaisquer pacotes referenciados através `PackageReference` ou :::no-loc(Q#)::: projetos referenciados através `ProjectReference` desse `.csproj` ficheiro.</span><span class="sxs-lookup"><span data-stu-id="e294f-235">It will also recursively load any packages referenced via `PackageReference` or :::no-loc(Q#)::: projects referenced via `ProjectReference` in that `.csproj` file.</span></span>

<span data-ttu-id="e294f-236">Como exemplo, o seguinte código Python importa um projeto externo, referindo o seu percurso em relação à pasta atual, e invoca uma das suas :::no-loc(Q#)::: operações:</span><span class="sxs-lookup"><span data-stu-id="e294f-236">As an example, the following Python code imports an external project, referencing its path relative to the current folder, and invokes one of its :::no-loc(Q#)::: operations:</span></span>

```python
import qsharp
qsharp.projects.add("../qrng/Qrng.csproj")
from Qrng import SampleQuantumRandomNumberGenerator
print(f"Qrng result: {SampleQuantumRandomNumberGenerator.simulate()}")
```

<span data-ttu-id="e294f-237">Isto resulta em saídas como as seguintes:</span><span class="sxs-lookup"><span data-stu-id="e294f-237">This results in output like the following:</span></span>

```output
Adding reference to project: ../qrng/Qrng.csproj
Qrng result: 0
```

<span data-ttu-id="e294f-238">Para carregar pacotes externos que contenham :::no-loc(Q#)::: código, utilize a [ `qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages).</span><span class="sxs-lookup"><span data-stu-id="e294f-238">To load external packages containing :::no-loc(Q#)::: code, use the [`qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages).</span></span>

<span data-ttu-id="e294f-239">Se o :::no-loc(Q#)::: código da pasta atual depender de projetos ou pacotes externos, poderá ver erros ao executar , uma vez que as `import qsharp` dependências ainda não foram carregadas.</span><span class="sxs-lookup"><span data-stu-id="e294f-239">If the :::no-loc(Q#)::: code in the current folder depends on external projects or packages, you may see errors when running `import qsharp`, since the dependencies have not yet been loaded.</span></span>
<span data-ttu-id="e294f-240">Para carregar os pacotes ou projetos externos necessários :::no-loc(Q#)::: durante o `import qsharp` comando, certifique-se de que a pasta com o script Python contém um `.csproj` ficheiro que faz referências `Microsoft.Quantum.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="e294f-240">To load required external packages or :::no-loc(Q#)::: projects during the `import qsharp` command, ensure that the folder with the Python script contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="e294f-241">Nisso, `.csproj` adicione a propriedade ao `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` `<PropertyGroup>` .</span><span class="sxs-lookup"><span data-stu-id="e294f-241">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="e294f-242">Isto instrui-me :::no-loc(Q#)::: a carregar novamente quaisquer `ProjectReference` ou `PackageReference` itens encontrados nele `.csproj` durante o `import qsharp` comando.</span><span class="sxs-lookup"><span data-stu-id="e294f-242">This will instruct I:::no-loc(Q#)::: to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` during the `import qsharp` command.</span></span>

<span data-ttu-id="e294f-243">Por exemplo, aqui está um ficheiro simples `.csproj` que faz com que eu :::no-loc(Q#)::: carregue automaticamente a `Microsoft.Quantum.Chemistry` embalagem:</span><span class="sxs-lookup"><span data-stu-id="e294f-243">For example, here is a simple `.csproj` file that causes I:::no-loc(Q#)::: to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

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
> <span data-ttu-id="e294f-244">Atualmente esta propriedade personalizada `<IQSharpLoadAutomatically>` é exigida pelos anfitriões Python, mas no futuro, este pode tornar-se o comportamento padrão para um `.csproj` ficheiro localizado na mesma pasta que o script Python.</span><span class="sxs-lookup"><span data-stu-id="e294f-244">Currently this custom `<IQSharpLoadAutomatically>` property is required by Python hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the Python script.</span></span>

> [!NOTE]
> <span data-ttu-id="e294f-245">Atualmente, a `<QsharpCompile>` definição no `.csproj` é ignorada pelos anfitriões Python, e todos os `.qs` ficheiros na pasta das `.csproj` sub-dobras (incluindo sub-24) são carregados e compilados.</span><span class="sxs-lookup"><span data-stu-id="e294f-245">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by Python hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="e294f-246">O suporte para `.csproj` definições será melhorado no futuro (ver [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) para mais detalhes).</span><span class="sxs-lookup"><span data-stu-id="e294f-246">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>


### <a name="c"></a>[<span data-ttu-id="e294f-247">C#</span><span class="sxs-lookup"><span data-stu-id="e294f-247">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="e294f-248">Um programa de anfitrião C# tem vários componentes, e funciona muito de perto com alguns componentes do QDK, como os simuladores, que são eles próprios construídos em C#.</span><span class="sxs-lookup"><span data-stu-id="e294f-248">A C# host program has multiple components, and works very closely with some components of the QDK, such as the simulators, which are themselves built on C#.</span></span>

<span data-ttu-id="e294f-249">O :::no-loc(Q#)::: compilador funciona aqui gerando um espaço de nome C# do espaço de :::no-loc(Q#)::: nomes no nosso :::no-loc(Q#)::: ficheiro.</span><span class="sxs-lookup"><span data-stu-id="e294f-249">The :::no-loc(Q#)::: compiler works here by generating an equivalently named C# namespace from the :::no-loc(Q#)::: namespace in our :::no-loc(Q#)::: file.</span></span>
<span data-ttu-id="e294f-250">Gera ainda uma classe C# de nome equivalente para cada uma das :::no-loc(Q#)::: ligas ou tipos neles definidos.</span><span class="sxs-lookup"><span data-stu-id="e294f-250">It further generates an equivalently named C# class for each of the :::no-loc(Q#)::: callables or types defined therein.</span></span>

<span data-ttu-id="e294f-251">Em primeiro lugar, disponibilizamos todas as aulas usadas no nosso programa de anfitriões com `using` declarações, que são aproximadamente analagous às `open` declarações no nosso :::no-loc(Q#)::: ficheiro:</span><span class="sxs-lookup"><span data-stu-id="e294f-251">First, we make any classes used in our host program available with `using` statements, which are roughly analagous to the `open` statements in our :::no-loc(Q#)::: file:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (for example, QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the :::no-loc(Q#)::: namespace available
```

<span data-ttu-id="e294f-252">Em seguida, declaramos o nosso espaço de nome C#, algumas outras peças (ver o bloco de código completo abaixo), e depois qualquer programação clássica que gossemos (por exemplo, argumentos de computação para os :::no-loc(Q#)::: callables).</span><span class="sxs-lookup"><span data-stu-id="e294f-252">Next, we declare our C# namespace, a few other bits and pieces (see the full code block below), and then any classical programming we would like (for example, computing arguments for the :::no-loc(Q#)::: callables).</span></span>
<span data-ttu-id="e294f-253">Este último não é necessário no nosso caso, mas um exemplo de tal utilização pode ser encontrado na  [amostra de interoperabilidade .NET](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="e294f-253">The latter isn't necessary in our case, but an example of such usage can be found at the  [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

#### <a name="target-machines"></a><span data-ttu-id="e294f-254">Computadores de destino</span><span class="sxs-lookup"><span data-stu-id="e294f-254">Target machines</span></span>

<span data-ttu-id="e294f-255">Voltando :::no-loc(Q#)::: a, temos de criar uma instância de qualquer máquina alvo em que vamos executar as nossas operações.</span><span class="sxs-lookup"><span data-stu-id="e294f-255">Getting back to :::no-loc(Q#):::, we must create an instance of whatever target machine we will run our operations on.</span></span>

```csharp
            using var sim = new QuantumSimulator();
```

<span data-ttu-id="e294f-256">A utilização de outras máquinas-alvo é tão simples como instantanear uma diferente, embora a forma de o fazer e processar as devoluções possa ser ligeiramente diferente.</span><span class="sxs-lookup"><span data-stu-id="e294f-256">Using other target machines is as simple as instantiating a different one, although the manner of doing so and processing the returns can be slightly different.</span></span>
<span data-ttu-id="e294f-257">Para a brevidade, ficamos com o [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) por enquanto, e incluímos o [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [abaixo.](#including-the-resources-estimator)</span><span class="sxs-lookup"><span data-stu-id="e294f-257">For brevity, we stick to the [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) for now, and include the [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).</span></span>

<span data-ttu-id="e294f-258">Cada classe C# gerada a partir das :::no-loc(Q#)::: operações tem um `Run` método, o primeiro argumento que deve ser a instância-alvo da máquina.</span><span class="sxs-lookup"><span data-stu-id="e294f-258">Each C# class generated from the :::no-loc(Q#)::: operations have a `Run` method, the first argument of which must be the target machine instance.</span></span>
<span data-ttu-id="e294f-259">Então, para correr `MeasureSuperposition` `QuantumSimulator` no, nós usamos `MeasureSuperposition.Run(sim)` .</span><span class="sxs-lookup"><span data-stu-id="e294f-259">So, to run `MeasureSuperposition` on the `QuantumSimulator`, we use `MeasureSuperposition.Run(sim)`.</span></span>
<span data-ttu-id="e294f-260">Os resultados devolvidos podem então ser atribuídos a variáveis em C#:</span><span class="sxs-lookup"><span data-stu-id="e294f-260">The returned results can then be assigned to variables in C#:</span></span>

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> <span data-ttu-id="e294f-261">O `Run` método é executado assíncronosamente porque este será o caso de hardware quântico real, e, portanto, a `await` palavra-chave bloqueia o processamento até que a tarefa esteja concluída.</span><span class="sxs-lookup"><span data-stu-id="e294f-261">The `Run` method is run asynchronously because this will be the case for real quantum hardware, and therefore the `await` keyword blocks further processing until the task completes.</span></span>

<span data-ttu-id="e294f-262">Se a :::no-loc(Q#)::: chamada não tiver quaisquer devoluções (por exemplo, tem tipo de `Unit` retorno), então a execução ainda pode ser feita da mesma forma sem atribuí-la a uma variável.</span><span class="sxs-lookup"><span data-stu-id="e294f-262">If the :::no-loc(Q#)::: callable does not have any returns (for example, it has return type `Unit`), then the run can still be done in the same manner without assigning it to a variable.</span></span>
<span data-ttu-id="e294f-263">Nesse caso, toda a linha seria simplesmente consistir em</span><span class="sxs-lookup"><span data-stu-id="e294f-263">In that case, the entire line would simply consist of</span></span> 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a><span data-ttu-id="e294f-264">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e294f-264">Arguments</span></span>

<span data-ttu-id="e294f-265">Quaisquer argumentos para a :::no-loc(Q#)::: chamada são simplesmente passados como argumentos adicionais após a máquina-alvo.</span><span class="sxs-lookup"><span data-stu-id="e294f-265">Any arguments to the :::no-loc(Q#)::: callable are simply passed as additional arguments after the target machine.</span></span>
<span data-ttu-id="e294f-266">Daí os resultados de `MeasureSuperpositionArray` `n=4` em qubits seria recolhido através</span><span class="sxs-lookup"><span data-stu-id="e294f-266">Hence the results of `MeasureSuperpositionArray` on `n=4` qubits would fetched via</span></span> 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

<span data-ttu-id="e294f-267">Um programa de anfitrião C# completo poderia assim parecer</span><span class="sxs-lookup"><span data-stu-id="e294f-267">A full C# host program could thus look like</span></span>

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

<span data-ttu-id="e294f-268">Na localização do ficheiro C#, o programa de anfitrião pode ser executado a partir do pedido de comando, introduzindo</span><span class="sxs-lookup"><span data-stu-id="e294f-268">At the location of the C# file, the host program can be run from the command prompt by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="e294f-269">e neste caso verá a saída escrita para a consola semelhante a</span><span class="sxs-lookup"><span data-stu-id="e294f-269">and in this case you will see output written to the console similar to</span></span> 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> <span data-ttu-id="e294f-270">Devido à interoperabilidade do compilador com espaços de nome, poderíamos, em alternativa, :::no-loc(Q#)::: disponibilizar os nossos callables sem a `using NamespaceName;` declaração e simplesmente combinar o título de espaço de nome C# com ele.</span><span class="sxs-lookup"><span data-stu-id="e294f-270">Due to the compiler's interoperability with namespaces, we could alternatively make our :::no-loc(Q#)::: callables available without the `using NamespaceName;` statement, and simply matching the C# namespace title to it.</span></span>
> <span data-ttu-id="e294f-271">Isto é, substituindo `namespace host` `namespace NamespaceName` por.</span><span class="sxs-lookup"><span data-stu-id="e294f-271">That is, by replacing `namespace host` with `namespace NamespaceName`.</span></span>

#### <a name="including-the-resources-estimator"></a><span data-ttu-id="e294f-272">Incluindo o estimador de recursos</span><span class="sxs-lookup"><span data-stu-id="e294f-272">Including the resources estimator</span></span>

<span data-ttu-id="e294f-273">[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)Requer uma implementação ligeiramente diferente para recuperar a saída.</span><span class="sxs-lookup"><span data-stu-id="e294f-273">The [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requires a slightly different implementation to retrieve the output.</span></span>

<span data-ttu-id="e294f-274">Em primeiro lugar, em vez de os instantanear como uma variável com uma `using` afirmação (como fazemos com `QuantumSimulator` o), mais diretamente instantâneos objetos da classe via</span><span class="sxs-lookup"><span data-stu-id="e294f-274">Firstly, instead of instantiating them as a variable with a `using` statement (as we do with the `QuantumSimulator`), we more directly instantiate objects of the class via</span></span>

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

<span data-ttu-id="e294f-275">Note que em vez de um único simulador de alvo para ser usado por múltiplas :::no-loc(Q#)::: operações, instantaneamente um para cada um.</span><span class="sxs-lookup"><span data-stu-id="e294f-275">Notice that instead of a single target simulator to be used by multiple :::no-loc(Q#)::: operations, we have instantiated one for each.</span></span> <span data-ttu-id="e294f-276">Isto porque os próprios objetos são modificados quando utilizados como máquinas-alvo, podendo os seus resultados ser recuperados posteriormente com o método de classe `.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="e294f-276">This is because the objects themselves are modified when used as target machines, and their results can then be retrieved afterwards with the class method `.ToTSV()`.</span></span>

<span data-ttu-id="e294f-277">Para executar as operações nos estimadores de recursos, usamos</span><span class="sxs-lookup"><span data-stu-id="e294f-277">To run the operations on the resource estimators, we use</span></span>

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
<span data-ttu-id="e294f-278">e, em seguida, obter os resultados como valores separados por separados (TSV) com `estimatorSingleQ.ToTSV()` e `estimatorMultiQ.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="e294f-278">and then fetch the results as tab-separated-values (TSV) with `estimatorSingleQ.ToTSV()` and `estimatorMultiQ.ToTSV()`.</span></span>

<span data-ttu-id="e294f-279">Assim, um programa de anfitrião C# completo que faz uso de ambos `QuantumSimulator` e pode assumir o `ResourcesEstimator` formulário:</span><span class="sxs-lookup"><span data-stu-id="e294f-279">So, a full C# host program making use of both the `QuantumSimulator` and `ResourcesEstimator` could take the form:</span></span>

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


<span data-ttu-id="e294f-280">que produziria produção semelhante a</span><span class="sxs-lookup"><span data-stu-id="e294f-280">which would yield output similar to</span></span>

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

## <a name="no-locq-jupyter-notebooks"></a><span data-ttu-id="e294f-281">:::no-loc(Q#)::: Cadernos Jupyter</span><span class="sxs-lookup"><span data-stu-id="e294f-281">:::no-loc(Q#)::: Jupyter Notebooks</span></span>
<span data-ttu-id="e294f-282">:::no-loc(Q#)::: Os Cadernos Jupyter utilizam o :::no-loc(Q#)::: núcleo I, que permite definir, compilar e executar :::no-loc(Q#)::: callables num único caderno--- tudo ao lado de instruções, notas e outros conteúdos.</span><span class="sxs-lookup"><span data-stu-id="e294f-282">:::no-loc(Q#)::: Jupyter Notebooks make use of the I:::no-loc(Q#)::: kernel, which allows you to define, compile, and run :::no-loc(Q#)::: callables in a single notebook---all alongside instructions, notes, and other content.</span></span>
<span data-ttu-id="e294f-283">Isto significa que, embora seja possível importar e utilizar o conteúdo dos `*.qs` :::no-loc(Q#)::: ficheiros, estes não são necessários no modelo de execução.</span><span class="sxs-lookup"><span data-stu-id="e294f-283">This means that while it is possible to import and use the contents of `*.qs` :::no-loc(Q#)::: files, they are not necessary in the run model.</span></span>

<span data-ttu-id="e294f-284">Aqui, vamos detalhar como executar as :::no-loc(Q#)::: operações acima definidas, mas uma introdução mais ampla à utilização :::no-loc(Q#)::: de Cadernos Jupyter é fornecida na [Introdução e :::no-loc(Q#)::: Jupyter Notebooks.](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)</span><span class="sxs-lookup"><span data-stu-id="e294f-284">Here, we will detail how to run the :::no-loc(Q#)::: operations defined above, but a more broad introduction to using :::no-loc(Q#)::: Jupyter Notebooks is provided at [Intro to :::no-loc(Q#)::: and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span></span>

### <a name="defining-operations"></a><span data-ttu-id="e294f-285">Definição de operações</span><span class="sxs-lookup"><span data-stu-id="e294f-285">Defining operations</span></span>

<span data-ttu-id="e294f-286">Num :::no-loc(Q#)::: Caderno Jupyter, introduzes :::no-loc(Q#)::: código como nós de dentro do espaço de nome de um :::no-loc(Q#)::: ficheiro.</span><span class="sxs-lookup"><span data-stu-id="e294f-286">In a :::no-loc(Q#)::: Jupyter Notebook, you enter :::no-loc(Q#)::: code just as we would from inside the namespace of a :::no-loc(Q#)::: file.</span></span>

<span data-ttu-id="e294f-287">Assim, podemos permitir o acesso a callables a partir das [ :::no-loc(Q#)::: bibliotecas padrão](xref:microsoft.quantum.qsharplibintro) com `open` declarações para os respetivos espaços de nome.</span><span class="sxs-lookup"><span data-stu-id="e294f-287">So, we can enable access to callables from the [:::no-loc(Q#)::: standard libraries](xref:microsoft.quantum.qsharplibintro) with `open` statements for their respective namespaces.</span></span>
<span data-ttu-id="e294f-288">Ao executar uma célula com tal afirmação, as definições desses espaços de nome estão disponíveis em todo o espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e294f-288">Upon running a cell with such a statement, the definitions from those namespaces are available throughout the workspace.</span></span>

> [!NOTE]
> <span data-ttu-id="e294f-289">Os callables da [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic) e [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon) (por exemplo, [`H`](xref:Microsoft.Quantum.Intrinsic.H) e ) [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) estão automaticamente disponíveis para operações definidas dentro de células em :::no-loc(Q#)::: Cadernos Jupyter.</span><span class="sxs-lookup"><span data-stu-id="e294f-289">Callables from [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic) and [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon) (for example, [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach)) are automatically available to operations defined within cells in :::no-loc(Q#)::: Jupyter Notebooks.</span></span>
> <span data-ttu-id="e294f-290">No entanto, isso não é verdade para o código trazido a partir de ficheiros de origem externa :::no-loc(Q#)::: (um processo mostrado na Introdução e na [ :::no-loc(Q#)::: Jupyter Notebooks).](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)</span><span class="sxs-lookup"><span data-stu-id="e294f-290">However, this is not true for code brought in from external :::no-loc(Q#)::: source files (a process shown at [Intro to :::no-loc(Q#)::: and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span></span> 
> 

<span data-ttu-id="e294f-291">Da mesma forma, a definição de operações requer apenas escrever o :::no-loc(Q#)::: código e executar a célula.</span><span class="sxs-lookup"><span data-stu-id="e294f-291">Similarly, defining operations requires only writing the :::no-loc(Q#)::: code and running the cell.</span></span>

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining :::no-loc(Q#)::: operations" width="773">

<span data-ttu-id="e294f-292">A saída enumera então essas operações, que podem ser chamadas de futuras células.</span><span class="sxs-lookup"><span data-stu-id="e294f-292">The output then lists those operations, which can then be called from future cells.</span></span>

### <a name="target-machines"></a><span data-ttu-id="e294f-293">Computadores de destino</span><span class="sxs-lookup"><span data-stu-id="e294f-293">Target machines</span></span>

<span data-ttu-id="e294f-294">A funcionalidade para executar operações em máquinas-alvo específicas é fornecida através de [I :::no-loc(Q#)::: Comandos Mágicos](xref:microsoft.quantum.guide.quickref.iqsharp).</span><span class="sxs-lookup"><span data-stu-id="e294f-294">The functionality to run operations on specific target machines is provided via [I:::no-loc(Q#)::: Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp).</span></span>
<span data-ttu-id="e294f-295">Por exemplo, `%simulate` faz uso do , e usa o `QuantumSimulator` `%estimate` `ResourcesEstimator` :</span><span class="sxs-lookup"><span data-stu-id="e294f-295">For example, `%simulate` makes use of the `QuantumSimulator`, and `%estimate` uses the `ResourcesEstimator`:</span></span>

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Jupyter cell simulating a :::no-loc(Q#)::: operation and running resource estimation" width="773">

### <a name="passing-inputs-to-functions-and-operations"></a><span data-ttu-id="e294f-296">Passando entradas para funções e operações</span><span class="sxs-lookup"><span data-stu-id="e294f-296">Passing inputs to functions and operations</span></span>

<span data-ttu-id="e294f-297">Para passar entradas para as :::no-loc(Q#)::: operações, os argumentos podem ser passados como `key=value` pares para o comando mágico de corrida.</span><span class="sxs-lookup"><span data-stu-id="e294f-297">To pass inputs to the :::no-loc(Q#)::: operations, the arguments can be passed as `key=value` pairs to the run magic command.</span></span>
<span data-ttu-id="e294f-298">Então, para correr `MeasureSuperpositionArray` com quatro qubits, podemos `%simulate MeasureSuperpositionArray n=4` correr:</span><span class="sxs-lookup"><span data-stu-id="e294f-298">So, to run `MeasureSuperpositionArray` with four qubits, we can run `%simulate MeasureSuperpositionArray n=4`:</span></span>

<img src="../media/hostprograms_jupyter_args_sim_crop.png" alt="Jupyter cell simulating a :::no-loc(Q#)::: operation with arguments" width="773">

<span data-ttu-id="e294f-299">Este padrão pode ser usado da mesma forma com `%estimate` e outros comandos de execução.</span><span class="sxs-lookup"><span data-stu-id="e294f-299">This pattern can be used similarly with `%estimate` and other run commands.</span></span>

### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="e294f-300">Utilização :::no-loc(Q#)::: de código de outros projetos ou pacotes</span><span class="sxs-lookup"><span data-stu-id="e294f-300">Using :::no-loc(Q#)::: code from other projects or packages</span></span>

<span data-ttu-id="e294f-301">Por predefinição, um :::no-loc(Q#)::: Bloco de Notas Jupyter carrega todos os `.qs` ficheiros da pasta atual e disponibiliza as suas :::no-loc(Q#)::: operações e funções para utilização a partir de dentro do caderno.</span><span class="sxs-lookup"><span data-stu-id="e294f-301">By default, a :::no-loc(Q#)::: Jupyter Notebook loads all of the `.qs` files in the current folder and makes their :::no-loc(Q#)::: operations and functions available for use from inside the notebook.</span></span> <span data-ttu-id="e294f-302">O [ `%who` comando mágico](xref:microsoft.quantum.iqsharp.magic-ref.who) lista todas as operações e funções atualmente :::no-loc(Q#)::: disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e294f-302">The [`%who` magic command](xref:microsoft.quantum.iqsharp.magic-ref.who) lists all currently-available :::no-loc(Q#)::: operations and functions.</span></span>

<span data-ttu-id="e294f-303">Para carregar :::no-loc(Q#)::: código de outra pasta, o comando [ `%project` mágico](xref:microsoft.quantum.iqsharp.magic-ref.project) pode ser usado para adicionar uma referência a um `.csproj` ficheiro para um projeto :::no-loc(Q#)::: (isto é, um projeto que faz `Microsoft.Quantum.Sdk` referência).</span><span class="sxs-lookup"><span data-stu-id="e294f-303">To load :::no-loc(Q#)::: code from another folder, the [`%project` magic command](xref:microsoft.quantum.iqsharp.magic-ref.project) can be used to add a reference to a `.csproj` file for a :::no-loc(Q#)::: project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span> <span data-ttu-id="e294f-304">Este comando compilará quaisquer `.qs` ficheiros na pasta que contenha as `.csproj` (e sub-dobras).</span><span class="sxs-lookup"><span data-stu-id="e294f-304">This command will compile any `.qs` files in the folder containing the `.csproj` (and subfolders).</span></span> <span data-ttu-id="e294f-305">Também carregará novamente quaisquer pacotes referenciados através `PackageReference` ou :::no-loc(Q#)::: projetos referenciados através `ProjectReference` desse `.csproj` ficheiro.</span><span class="sxs-lookup"><span data-stu-id="e294f-305">It will also recursively load any packages referenced via `PackageReference` or :::no-loc(Q#)::: projects referenced via `ProjectReference` in that `.csproj` file.</span></span> 

<span data-ttu-id="e294f-306">Como exemplo, as seguintes células simulam uma :::no-loc(Q#)::: operação a partir de um projeto externo, onde o percurso do projeto é referenciado em relação à pasta atual:</span><span class="sxs-lookup"><span data-stu-id="e294f-306">As an example, the following cells simulate a :::no-loc(Q#)::: operation from an external project, where the project path is referenced relative to the current folder:</span></span>

<img src="../media/hostprograms_jupyter_project_crop.png" alt="Jupyter cell simulating a :::no-loc(Q#)::: operation from an external project" width="773">

<span data-ttu-id="e294f-307">Para carregar pacotes externos que contenham :::no-loc(Q#)::: código, utilize o [ `%package` comando mágico](xref:microsoft.quantum.iqsharp.magic-ref.package).</span><span class="sxs-lookup"><span data-stu-id="e294f-307">To load external packages containing :::no-loc(Q#)::: code, use the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="e294f-308">O carregamento de um pacote também disponibilizará quaisquer comandos mágicos personalizados ou codificadores de exibição que estejam contidos em quaisquer conjuntos que façam parte do pacote.</span><span class="sxs-lookup"><span data-stu-id="e294f-308">Loading a package will also make available any custom magic commands or display encoders that are contained in any assemblies that are part of the package.</span></span>

<span data-ttu-id="e294f-309">Para carregar pacotes ou projetos externos :::no-loc(Q#)::: no tempo de invisibilidade do portátil, certifique-se de que a pasta do portátil contém um `.csproj` ficheiro que faz referências `Microsoft.Quantum.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="e294f-309">To load external packages or :::no-loc(Q#)::: projects at notebook intialization time, ensure that the notebook folder contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="e294f-310">Nisso, `.csproj` adicione a propriedade ao `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` `<PropertyGroup>` .</span><span class="sxs-lookup"><span data-stu-id="e294f-310">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="e294f-311">Isto instrui-me :::no-loc(Q#)::: para carregar novamente qualquer `ProjectReference` ou `PackageReference` itens encontrados no `.csproj` tempo de carregamento do caderno.</span><span class="sxs-lookup"><span data-stu-id="e294f-311">This will instruct I:::no-loc(Q#)::: to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` at notebook load time.</span></span>

<span data-ttu-id="e294f-312">Por exemplo, aqui está um ficheiro simples `.csproj` que faz com que eu :::no-loc(Q#)::: carregue automaticamente a `Microsoft.Quantum.Chemistry` embalagem:</span><span class="sxs-lookup"><span data-stu-id="e294f-312">For example, here is a simple `.csproj` file that causes I:::no-loc(Q#)::: to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

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
> <span data-ttu-id="e294f-313">Atualmente esta propriedade personalizada `<IQSharpLoadAutomatically>` é exigida pelos :::no-loc(Q#)::: anfitriões do Jupyter Notebook, mas no futuro, este pode tornar-se o comportamento padrão para um `.csproj` ficheiro localizado na mesma pasta que o ficheiro do portátil.</span><span class="sxs-lookup"><span data-stu-id="e294f-313">Currently this custom `<IQSharpLoadAutomatically>` property is required by :::no-loc(Q#)::: Jupyter Notebook hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the notebook file.</span></span>

> [!NOTE]
> <span data-ttu-id="e294f-314">Atualmente, a `<QsharpCompile>` definição no `.csproj` é ignorada pelos :::no-loc(Q#)::: anfitriões do Jupyter Notebook, e todos os `.qs` ficheiros na pasta das `.csproj` sub-dobras (incluindo sub-24) são carregados e compilados.</span><span class="sxs-lookup"><span data-stu-id="e294f-314">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by :::no-loc(Q#)::: Jupyter Notebook hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="e294f-315">O suporte para `.csproj` definições será melhorado no futuro (ver [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) para mais detalhes).</span><span class="sxs-lookup"><span data-stu-id="e294f-315">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>
