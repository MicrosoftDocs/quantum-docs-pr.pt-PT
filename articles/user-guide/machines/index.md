---
title: Simuladores quânticos e aplicações anfitriãs | Microsoft Docs
description: Descreve como controlar simuladores quânticos com uma linguagem de computação .NET clássica, normalmente C# ou Q#.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines
ms.openlocfilehash: 14aed75ed0ed192f88699b1c7dbacfae23f74642
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273806"
---
# <a name="quantum-simulators-and-host-applications"></a><span data-ttu-id="ddf8e-103">Simuladores quânticos e aplicações anfitriãs</span><span class="sxs-lookup"><span data-stu-id="ddf8e-103">Quantum simulators and host applications</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="ddf8e-104">O que irá aprender</span><span class="sxs-lookup"><span data-stu-id="ddf8e-104">What You'll Learn</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="ddf8e-105">Como se executam algoritmos quânticos</span><span class="sxs-lookup"><span data-stu-id="ddf8e-105">How quantum algorithms are executed</span></span>
> * <span data-ttu-id="ddf8e-106">Simuladores quânticos incluídos nesta versão</span><span class="sxs-lookup"><span data-stu-id="ddf8e-106">What quantum simulators are included in this release</span></span>
> * <span data-ttu-id="ddf8e-107">Como escrever um controlador em C# para o algoritmo quântico</span><span class="sxs-lookup"><span data-stu-id="ddf8e-107">How to write a C# driver for your quantum algorithm</span></span>

## <a name="the-quantum-development-kit-execution-model"></a><span data-ttu-id="ddf8e-108">O Modelo de Execução do Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="ddf8e-108">The Quantum Development Kit Execution Model</span></span>

<span data-ttu-id="ddf8e-109">Em [Escrever um programa quântico](xref:microsoft.quantum.write-program), executámos o nosso algoritmo quântico ao transmitir um objeto `QuantumSimulator` para o método `Run` da classe de algoritmo.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-109">In [Writing a quantum program](xref:microsoft.quantum.write-program), we executed our quantum algorithm by passing a `QuantumSimulator` object to the algorithm class's `Run` method.</span></span>
<span data-ttu-id="ddf8e-110">A classe `QuantumSimulator` executa o algoritmo quântico ao simular na íntegra o vetor de estado quântico, que é ideal para executar e testar `Teleport`.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-110">The `QuantumSimulator` class executes the quantum algorithm by fully simulating the quantum state vector, which is perfect for running and testing `Teleport`.</span></span>
<span data-ttu-id="ddf8e-111">Veja o [Guia de conceitos](xref:microsoft.quantum.concepts.intro) para obter mais informações sobre os vetores quânticos.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-111">See the [Concepts guide](xref:microsoft.quantum.concepts.intro) for more on quantum state vectors.</span></span>

<span data-ttu-id="ddf8e-112">Outros computadores de destino podem ser utilizados para executar um algoritmo quântico.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-112">Other target machines may be used to run a quantum algorithm.</span></span>
<span data-ttu-id="ddf8e-113">O computador é responsável por fornecer implementações de primitivos quânticos para o algoritmo.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-113">The machine is responsible for providing implementations of quantum primitives for the algorithm.</span></span>
<span data-ttu-id="ddf8e-114">Tal inclui operações primitivas como H, CNOT e Medição, bem como gestão e monitorização de qubits.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-114">This includes primitive operations such as H, CNOT, and Measure, as well as qubit management and tracking.</span></span>
<span data-ttu-id="ddf8e-115">Classes diferentes de computadores quânticos representam diferentes modelos de execução para o mesmo algoritmo quântico.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-115">Different classes of quantum machines represent different execution models for the same quantum algorithm.</span></span>

<span data-ttu-id="ddf8e-116">Cada tipo de computador quântico pode fornecer diferentes implementações desses primitivos.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-116">Each type of quantum machine may provide different implementations of these primitives.</span></span>
<span data-ttu-id="ddf8e-117">Por exemplo, o simulador de rastreio do computador quântico incluído no development kit não faz nenhuma simulação.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-117">For instance, the quantum computer trace simulator included in the development kit doesn't do any simulation at all.</span></span>
<span data-ttu-id="ddf8e-118">Em vez disso, rastreia a porta, o qubit e outras utilizações dos recursos para o algoritmo.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-118">Rather, it tracks gate, qubit, and other resource usage for the algorithm.</span></span>

### <a name="quantum-machines"></a><span data-ttu-id="ddf8e-119">Computadores Quânticos</span><span class="sxs-lookup"><span data-stu-id="ddf8e-119">Quantum Machines</span></span>

<span data-ttu-id="ddf8e-120">Posteriormente, vamos definir classes adicionais de computadores quânticos para suportar outros tipos de simulações e para suportar a execução em computadores quânticos topológicos.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-120">In the future, we will define additional quantum machine classes to support other types of simulation and to support execution on topological quantum computers.</span></span>
<span data-ttu-id="ddf8e-121">Permitir que o algoritmo se mantenha constante enquanto se varia a implementação do computador subjacente facilita testar e depurar um algoritmo na simulação e, em seguida, executá-lo em hardware real com a confiança de que o algoritmo não mudou.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-121">Allowing the algorithm to stay constant while varying the underlying machine implementation makes it easy to test and debug an algorithm in simulation and then run it on real hardware with confidence that the algorithm hasn't changed.</span></span>

### <a name="whats-included-in-this-release"></a><span data-ttu-id="ddf8e-122">O que está Incluído nesta Versão</span><span class="sxs-lookup"><span data-stu-id="ddf8e-122">What's Included in this Release</span></span>

<span data-ttu-id="ddf8e-123">Esta versão do kit de programador quântico inclui diversas classes de computadores quânticos.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-123">This release of the quantum developer kit includes several quantum machine classes.</span></span>
<span data-ttu-id="ddf8e-124">Todas estão definidas no espaço de nomes `Microsoft.Quantum.Simulation.Simulators`.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-124">All of them are defined in the `Microsoft.Quantum.Simulation.Simulators` namespace.</span></span>

* <span data-ttu-id="ddf8e-125">Um [simulador de vetor de estado completo](xref:microsoft.quantum.machines.full-state-simulator), a classe `QuantumSimulator`.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-125">A [full state vector simulator](xref:microsoft.quantum.machines.full-state-simulator), the `QuantumSimulator` class.</span></span>
* <span data-ttu-id="ddf8e-126">Um [simulador de recursos simples](xref:microsoft.quantum.machines.resources-estimator), a classe `ResourcesEstimator`, permite uma análise de nível superior dos recursos necessários para executar um algoritmo quântico.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-126">A [simple resources estimator](xref:microsoft.quantum.machines.resources-estimator), the `ResourcesEstimator` class, it allows a top level analysis of the resources needed to run a quantum algorithm.</span></span>
* <span data-ttu-id="ddf8e-127">Um [simulador de recursos baseado em rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro), a classe `QCTraceSimulator`, que permite uma análise avançada doe consumos de recursos para todo o grafo de chamada do algoritmo.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-127">A [trace-based resource estimator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), the `QCTraceSimulator` class, it allows advanced analysis of resources consumptions for the algorithm's entire call-graph.</span></span>
* <span data-ttu-id="ddf8e-128">Um [simulador Toffoli](xref:microsoft.quantum.machines.toffoli-simulator), a classe `ToffoliSimulator`.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-128">A [Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator), the `ToffoliSimulator` class.</span></span>

## <a name="writing-a-host-application"></a><span data-ttu-id="ddf8e-129">Escrever uma aplicação anfitriã</span><span class="sxs-lookup"><span data-stu-id="ddf8e-129">Writing a host application</span></span>

<span data-ttu-id="ddf8e-130">Em [Escrever um programa quântico](xref:microsoft.quantum.write-program), escrevemos um controlador C# simples para o nosso algoritmo teleport.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-130">In [Writing a quantum program](xref:microsoft.quantum.write-program), we wrote a simple C# driver for our teleport algorithm.</span></span> <span data-ttu-id="ddf8e-131">Um controlador C# tem quatro objetivos principais:</span><span class="sxs-lookup"><span data-stu-id="ddf8e-131">A C# driver has 4 main purposes:</span></span>

* <span data-ttu-id="ddf8e-132">Construir o computador de destino</span><span class="sxs-lookup"><span data-stu-id="ddf8e-132">Constructing the target machine</span></span>
* <span data-ttu-id="ddf8e-133">Calcular todos os argumentos necessários do algoritmo quântico</span><span class="sxs-lookup"><span data-stu-id="ddf8e-133">Computing any arguments required for the quantum algorithm</span></span>
* <span data-ttu-id="ddf8e-134">Executar o algoritmo quântico com o simulador</span><span class="sxs-lookup"><span data-stu-id="ddf8e-134">Running the quantum algorithm using the simulator</span></span>
* <span data-ttu-id="ddf8e-135">Processar o resultado da operação</span><span class="sxs-lookup"><span data-stu-id="ddf8e-135">Processing the result of the operation</span></span>

<span data-ttu-id="ddf8e-136">Aqui, vamos falar de cada passo mais detalhadamente.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-136">Here we'll discuss each step in more detail.</span></span>

### <a name="constructing-the-target-machine"></a><span data-ttu-id="ddf8e-137">Construir o Computador de Destino</span><span class="sxs-lookup"><span data-stu-id="ddf8e-137">Constructing the Target Machine</span></span>

<span data-ttu-id="ddf8e-138">Os computadores quânticos são instâncias de classes .NET normais, por isso, são criados ao invocar o construtor, como em qualquer classe .NET.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-138">Quantum machines are instances of normal .NET classes, so they are created by invoking their constructor, just like any .NET class.</span></span>
<span data-ttu-id="ddf8e-139">Alguns simuladores, como o `QuantumSimulator`, implementam a interface .NET <xref:System.IDisposable?displayProperty=nameWithType> e por isso devem ser encapsulados numa instrução C# `using`.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-139">Some simulators, including the `QuantumSimulator`, implement the .NET <xref:System.IDisposable?displayProperty=nameWithType> interface, and so should be wrapped in a C# `using` statement.</span></span>

### <a name="computing-arguments-for-the-algorithm"></a><span data-ttu-id="ddf8e-140">Argumentos de Computação para o Algoritmo</span><span class="sxs-lookup"><span data-stu-id="ddf8e-140">Computing Arguments for the Algorithm</span></span>

<span data-ttu-id="ddf8e-141">No nosso exemplo `Teleport`, calculámos alguns argumentos relativamente artificiais para transmitir para o nosso algoritmo quântico.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-141">In our `Teleport` example, we computed some relatively artificial arguments to pass to our quantum algorithm.</span></span>
<span data-ttu-id="ddf8e-142">No entanto, é mais frequente que o algoritmo requeira dados significativos, e o mais fácil é fornecê-los do controlador clássico.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-142">More typically, however, there is significant data required by the quantum algorithm, and it is easiest to provide it from the classical driver.</span></span>

<span data-ttu-id="ddf8e-143">Por exemplo, ao trabalhar em soluções químicas, o algoritmo quântico requer uma grande tabela de integrantes de interação orbital molecular.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-143">For instance, when doing chemical simulations, the quantum algorithm requires a large table of molecular orbital interaction integrals.</span></span>
<span data-ttu-id="ddf8e-144">Geralmente, são lidos a partir de um ficheiro fornecido ao executar o algoritmo.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-144">Generally these are read in from a file that is provided when running the algorithm.</span></span>
<span data-ttu-id="ddf8e-145">Uma vez que o Q# não tem um mecanismo para aceder ao sistema de ficheiros, a melhor forma de recolher este tipo de dados é utilizar o controlador clássico e transmitir para o método `Run` do algoritmo quântico.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-145">Since Q# does not have a mechanism for accessing the file system, this sort of data is best collected by the classical driver and then passed to the quantum algorithm's `Run` method.</span></span>

<span data-ttu-id="ddf8e-146">Outro caso em que o controlador clássico desempenha um papel fundamental é em métodos de variação.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-146">Another case where the classical driver plays a key role is in variational methods.</span></span>
<span data-ttu-id="ddf8e-147">Nesta classe de algoritmos, um estado quântico é preparado com base em parâmetros clássicos e esse estado utiliza-se para calcular um valor de interesse.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-147">In this class of algorithms, a quantum state is prepared based on some classical parameters, and that state is used to compute some value of interest.</span></span>
<span data-ttu-id="ddf8e-148">Os parâmetros ajustam-se com base num tipo de algoritmo de aprendizagem automática ou “hill climbing” e o algoritmo quântico é executado novamente.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-148">The parameters are adjusted based on some type of hill climbing or machine learning algorithm and the quantum algorithm run again.</span></span>
<span data-ttu-id="ddf8e-149">Nestes algoritmos, o algoritmo “hill climbing” propriamente dito é mais bem implementado como uma função estritamente clássica que é chamada pelo controlador clássico; os resultados do “hill climbing” são depois transmitidos para a execução seguinte do algoritmo quântico.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-149">For such algorithms, the hill climbing algorithm itself is best implemented as a purely classical function that is called by the classical driver; the results of the hill climbing are then passed to the next execution of the quantum algorithm.</span></span>

### <a name="running-the-quantum-algorithm"></a><span data-ttu-id="ddf8e-150">Executar o Algoritmo Quântico</span><span class="sxs-lookup"><span data-stu-id="ddf8e-150">Running the Quantum Algorithm</span></span>

<span data-ttu-id="ddf8e-151">Esta parte é geralmente muito simples.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-151">This part is generally very straightforward.</span></span>
<span data-ttu-id="ddf8e-152">Todas as operações Q# são compiladas numa classe que fornece um método `Run` estático.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-152">Each Q# operation is compiled into a class that provides a static `Run` method.</span></span>
<span data-ttu-id="ddf8e-153">Os argumentos deste método são dados pela cadeia de identificação de argumento aplanado da operação propriamente dita, além de um primeiro argumento adicional, que é o simulador com o qual executar.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-153">The arguments to this method are given by the flattened argument tuple of the operation itself, plus an additional first argument which is the simulator to execute with.</span></span> <span data-ttu-id="ddf8e-154">Para uma operação que espera a cadeia de identificação com nome do tipo `(a: String, (b: Double, c: Double))`, o seu equivalente aplanado é do tipo `(String a, Double b, Double c)`.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-154">For an operation that expects the named tuple of type `(a: String, (b: Double, c: Double))` its flattened counterpart is of type `(String a, Double b, Double c)`.</span></span>


<span data-ttu-id="ddf8e-155">Existem determinadas nuances ao transmitir argumentos para o método `Run`:</span><span class="sxs-lookup"><span data-stu-id="ddf8e-155">There are some subtleties when passing arguments to a `Run` method:</span></span>

* <span data-ttu-id="ddf8e-156">As matrizes têm de ser encapsuladas num objeto `Microsoft.Quantum.Simulation.Core.QArray<T>`.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-156">Arrays must be wrapped in a `Microsoft.Quantum.Simulation.Core.QArray<T>` object.</span></span>
    <span data-ttu-id="ddf8e-157">Uma classe `QArray` tem um construtor que pode assumir qualquer coleção ordenada (`IEnumerable<T>`) de objetos apropriados.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-157">A `QArray` class has a constructor that can take any ordered collection (`IEnumerable<T>`) of appropriate objects.</span></span>
* <span data-ttu-id="ddf8e-158">A cadeia de identificação, `()` em Q#, é representada por `QVoid.Instance` em C#.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-158">The empty tuple, `()` in Q#, is represented by `QVoid.Instance` in C#.</span></span>
* <span data-ttu-id="ddf8e-159">As cadeias de identificação não vazias são representadas como instâncias .NET `ValueTuple`.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-159">Non-empty tuples are represented as .NET `ValueTuple` instances.</span></span>
* <span data-ttu-id="ddf8e-160">Os tipos definidos pelo utilizador Q# são transmitidos como o respetivo tipo de base.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-160">Q# user-defined types are passed as their base type.</span></span>
* <span data-ttu-id="ddf8e-161">Para transmitir uma operação ou função para um método `Run`, tem de obter uma instância da classe da função ou operação através do método `Get<>` do simulador.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-161">To pass an operation or a function to a `Run` method, you have to obtain an   instance of the operation's or function's class, using the simulator's `Get<>` method.</span></span>

### <a name="processing-the-results"></a><span data-ttu-id="ddf8e-162">Processar os Resultados</span><span class="sxs-lookup"><span data-stu-id="ddf8e-162">Processing the Results</span></span>

<span data-ttu-id="ddf8e-163">Os resultados do algoritmo quântico são devolvidos do método `Run`.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-163">The results of the quantum algorithm are returned from the `Run` method.</span></span>
<span data-ttu-id="ddf8e-164">O método `Run` é executado de forma assíncrona, pelo que devolve uma instância de <xref:System.Threading.Tasks.Task`1>.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-164">The `Run` method executes asynchronously thus it returns an instance of <xref:System.Threading.Tasks.Task`1>.</span></span>
<span data-ttu-id="ddf8e-165">Existem várias formas de obter os resultados reais da operação.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-165">There are multiple ways to get the actual operation's results.</span></span> <span data-ttu-id="ddf8e-166">A forma mais simples é utilizar, em `Task`, a propriedade [`Result`](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result):</span><span class="sxs-lookup"><span data-stu-id="ddf8e-166">The simplest is by using the `Task`'s [`Result` property](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result):</span></span>

```csharp
    var res = BellTest.Run(sim, 1000, initial).Result;
```
<span data-ttu-id="ddf8e-167">Mas outras técnicas, como utilizar o método [`Wait`](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) ou a palavra-chave C# [`await`](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) também funcionam.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-167">but other techniques, like using the [`Wait` method](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) or C# [`await` keyword](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) will also work.</span></span>

<span data-ttu-id="ddf8e-168">Como acontece em argumentos, as cadeias de identificação Q# são representadas como instâncias `ValueTuple` e as matrizes Q# são representadas como instâncias `QArray`.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-168">As with arguments, Q# tuples are represented as `ValueTuple` instances and Q# arrays are represented as `QArray` instances.</span></span>
<span data-ttu-id="ddf8e-169">Os tipos definidos pelo utilizador são devolvidos como o respetivo tipo de base.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-169">User-defined types are returned as their base types.</span></span>
<span data-ttu-id="ddf8e-170">A cadeia de identificação vazia, `()`, é devolvida como uma instância da classe `QVoid`.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-170">The empty tuple, `()`, is returned as an instance of the `QVoid` class.</span></span>

<span data-ttu-id="ddf8e-171">Muitos algoritmos quânticos requerem uma quantidade substancial de pós-processamento para gerar respostas úteis.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-171">Many quantum algorithms require substantial post-processing to derive useful answers.</span></span>
<span data-ttu-id="ddf8e-172">Por exemplo, a parte quântica do algoritmo de Shor é apenas o início de um cálculo que obtém os fatores de um número.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-172">For instance, the quantum part of Shor's algorithm is just the beginning of a computation that finds the factors of a number.</span></span>

<span data-ttu-id="ddf8e-173">Na maioria dos casos, o mais simples e fácil é fazer este tipo de pós-processamento no controlador clássico.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-173">In most cases, it is simplest and easiest to do this sort of post-processing in the classical driver.</span></span>
<span data-ttu-id="ddf8e-174">Apenas o controlador clássico pode reportar resultados ao utilizador ou escrever os mesmos no disco.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-174">Only the classical driver can report results to the user or write them to disk.</span></span>
<span data-ttu-id="ddf8e-175">O controlador clássico terá acesso a bibliotecas analíticas e outras funções matemáticas que não estão expostas em Q#.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-175">The classical driver will have access to analytical libraries and other mathematical functions that are not exposed in Q#.</span></span>


## <a name="failures"></a><span data-ttu-id="ddf8e-176">Falhas</span><span class="sxs-lookup"><span data-stu-id="ddf8e-176">Failures</span></span>

<span data-ttu-id="ddf8e-177">Quando a instrução Q# `fail` for atingida durante a execução de uma operação, será lançada uma `ExecutionFailException`.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-177">When the Q# `fail` statement is reached during the execution of an operation, an `ExecutionFailException` is thrown.</span></span>

<span data-ttu-id="ddf8e-178">Devido à utilização de `System.Task` no método `Run`, a exceção lançada como resultado de uma instrução `fail` será encapsulada num `System.AggregateException`.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-178">Due to the use of `System.Task` in the `Run` method, the exception thrown as a result of a `fail` statement will be wrapped into a `System.AggregateException`.</span></span>
<span data-ttu-id="ddf8e-179">Para descobrir o verdadeiro motivo da falha, terá de iterar em `AggregateException` 
`InnerExceptions`, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ddf8e-179">To find the actual reason for the failure, you need to iterate into the `AggregateException` 
`InnerExceptions`, for example:</span></span>

```csharp

            try
            {
                using(var sim = new QuantumSimulator())
                {
                    /// call your operations here...
                }
            }
            catch (AggregateException e)
            {
                // Unwrap AggregateException to get the message from Q# fail statement.
                // Go through all inner exceptions.
                foreach (Exception inner in e.InnerExceptions)
                {
                    // If the exception of type ExecutionFailException
                    if (inner is ExecutionFailException failException)
                    {
                        // Print the message it contains
                        Console.WriteLine($" {failException.Message}");
                    }
                }
            }
```

## <a name="other-classical-languages"></a><span data-ttu-id="ddf8e-180">Outras Linguagens Clássicas</span><span class="sxs-lookup"><span data-stu-id="ddf8e-180">Other Classical Languages</span></span>

<span data-ttu-id="ddf8e-181">Apesar de os exemplos que fornecemos estarem em C#, F# e Python, o Development Kit Quantum suporta também a escrita de programas anfitriões clássicos noutras linguagens.</span><span class="sxs-lookup"><span data-stu-id="ddf8e-181">While the samples we have provided are in C#, F#, and Python, the Quantum Development Kit also supports writing classical host programs in other languages.</span></span>
<span data-ttu-id="ddf8e-182">Por exemplo, se quiser escrever um programa anfitrião no Visual Basic, [este deverá funcionar bem](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).</span><span class="sxs-lookup"><span data-stu-id="ddf8e-182">For example, if you want to write a host program in Visual Basic, [it should work just fine](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).</span></span>
