---
title: Testar e depurar programas Q#
description: Aprenda a usar testes unitários, factos e afirmações, e despeje funções para testar e depurar programas quânticos.
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 8131c2ec9320b5075c37370e12ad39a4df5bd3d5
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/10/2020
ms.locfileid: "79022847"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="67eac-103">Testes e Depuração</span><span class="sxs-lookup"><span data-stu-id="67eac-103">Testing and Debugging</span></span>

<span data-ttu-id="67eac-104">Tal como na programação clássica, é essencial poder verificar se os programas quânticos funcionam como pretendido, e ser capaz de diagnosticar um programa quântico que é incorreto.</span><span class="sxs-lookup"><span data-stu-id="67eac-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="67eac-105">Nesta secção, cobrimos as ferramentas oferecidas pela Q# para testar e depurar programas quânticos.</span><span class="sxs-lookup"><span data-stu-id="67eac-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="67eac-106">Testes unitários</span><span class="sxs-lookup"><span data-stu-id="67eac-106">Unit Tests</span></span>

<span data-ttu-id="67eac-107">Uma abordagem comum para testar programas clássicos é escrever pequenos programas chamados *testes unitários* que executam código numa biblioteca e comparar a sua produção com alguma saída esperada.</span><span class="sxs-lookup"><span data-stu-id="67eac-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="67eac-108">Por exemplo, podemos querer garantir que `Square(2)` retorno `4`, uma vez que sabemos *um priori* que $2^2 = 4$.</span><span class="sxs-lookup"><span data-stu-id="67eac-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="67eac-109">Q# suporta a criação de testes unitários para programas quânticos, e que podem ser executados como testes dentro da estrutura de teste da unidade [xUnit.](https://xunit.github.io/)</span><span class="sxs-lookup"><span data-stu-id="67eac-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="67eac-110">Criação de um Projeto de Teste</span><span class="sxs-lookup"><span data-stu-id="67eac-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="67eac-111">Estúdio Visual 2019</span><span class="sxs-lookup"><span data-stu-id="67eac-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="67eac-112">Open Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="67eac-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="67eac-113">Vá ao menu `File` e selecione `New` > `Project...`.</span><span class="sxs-lookup"><span data-stu-id="67eac-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="67eac-114">No canto superior direito, procure `Q#`e selecione o modelo `Q# Test Project`.</span><span class="sxs-lookup"><span data-stu-id="67eac-114">In the upper right corner, search for `Q#`, and select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="67eac-115">Linha de Comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="67eac-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="67eac-116">A partir da sua linha de comando favorita, corra o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="67eac-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="67eac-117">O seu novo projeto terá um único ficheiro `Tests.qs`, que fornece um local conveniente para definir novos testes da unidade Q#.</span><span class="sxs-lookup"><span data-stu-id="67eac-117">Your new project will have a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="67eac-118">Inicialmente, este ficheiro contém um teste de unidade de amostra `AllocateQubit` que verifica que um qubit recém-atribuído está no estado de $\ket{0}$ e imprime uma mensagem:</span><span class="sxs-lookup"><span data-stu-id="67eac-118">Initially this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

:novo: <span data-ttu-id="67eac-119">Qualquer operação ou função Q# que tenha um argumento de tipo `Unit` e devoluções `Unit` pode ser marcado como um teste de unidade através do atributo `@Test("...")`.</span><span class="sxs-lookup"><span data-stu-id="67eac-119">Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="67eac-120">O argumento desse atributo, `"QuantumSimulator"` acima, especifica o alvo em que o teste é executado.</span><span class="sxs-lookup"><span data-stu-id="67eac-120">The argument to that attribute, `"QuantumSimulator"` above, specifies the target on which the test is executed.</span></span> <span data-ttu-id="67eac-121">Um único teste pode ser executado em vários alvos.</span><span class="sxs-lookup"><span data-stu-id="67eac-121">A single test can be executed on multiple targets.</span></span> <span data-ttu-id="67eac-122">Por exemplo, adicione um atributo `@Test("ResourcesEstimator")` acima `AllocateQubit`.</span><span class="sxs-lookup"><span data-stu-id="67eac-122">For example, add an attribute `@Test("ResourcesEstimator")` above `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="67eac-123">Guarde o ficheiro e execute todos os testes.</span><span class="sxs-lookup"><span data-stu-id="67eac-123">Save the file and execute all tests.</span></span> <span data-ttu-id="67eac-124">Deve agora haver dois testes unitários, um em que o AllocateQubit é executado no QuantumSimulator, e outro onde é executado no ResourceEstimator.</span><span class="sxs-lookup"><span data-stu-id="67eac-124">There should now be two unit tests, one where AllocateQubit is executed on the QuantumSimulator, and one where it is executed in the ResourceEstimator.</span></span> 

<span data-ttu-id="67eac-125">O compilador Q# reconhece os alvos incorporados "QuantumSimulator", "ToffoliSimulator" e "ResourcesEstimator" como alvos de execução válidos para testes unitários.</span><span class="sxs-lookup"><span data-stu-id="67eac-125">The Q# compiler recognizes the built-in targets "QuantumSimulator", "ToffoliSimulator", and "ResourcesEstimator" as valid execution targets for unit tests.</span></span> <span data-ttu-id="67eac-126">Também é possível especificar qualquer nome totalmente qualificado para definir um alvo de execução personalizado.</span><span class="sxs-lookup"><span data-stu-id="67eac-126">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-q-unit-tests"></a><span data-ttu-id="67eac-127">Testes de unidade Q# em execução</span><span class="sxs-lookup"><span data-stu-id="67eac-127">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="67eac-128">Estúdio Visual 2019</span><span class="sxs-lookup"><span data-stu-id="67eac-128">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="67eac-129">Como uma configuração única por solução, vá ao menu `Test` e selecione `Test Settings` > `Default Processor Architecture` > `X64`.</span><span class="sxs-lookup"><span data-stu-id="67eac-129">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="67eac-130">A definição de arquitetura de processador padrão para Visual Studio é armazenada no ficheiro de solução (`.suo`) para cada solução.</span><span class="sxs-lookup"><span data-stu-id="67eac-130">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="67eac-131">Se apagar este ficheiro, terá de selecionar `X64` como arquitetura do seu processador novamente.</span><span class="sxs-lookup"><span data-stu-id="67eac-131">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="67eac-132">Construa o projeto, vá ao menu `Test` e selecione `Windows` > `Test Explorer`.</span><span class="sxs-lookup"><span data-stu-id="67eac-132">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="67eac-133">`AllocateQubit` aparecerão na lista de testes do grupo `Not Run Tests`.</span><span class="sxs-lookup"><span data-stu-id="67eac-133">`AllocateQubit` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="67eac-134">Selecione `Run All` ou execute este teste individual, e deve passar!</span><span class="sxs-lookup"><span data-stu-id="67eac-134">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="67eac-135">Linha de Comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="67eac-135">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="67eac-136">Para executar testes, navegue para a pasta do projeto (a pasta que contém `Tests.csproj`), e execute o comando:</span><span class="sxs-lookup"><span data-stu-id="67eac-136">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="67eac-137">Deve obter uma saída semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="67eac-137">You should get output similar to the following:</span></span>

```
Build started, please wait...
Build completed.

Test run for C:\Users\chgranad.REDMOND\tmp\Tests\bin\Debug\netcoreapp2.0\Tests.dll(.NETCoreApp,Version=v2.0)
Microsoft (R) Test Execution Command Line Tool Version 15.3.0-preview-20170628-02
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.5864002]   Discovering: Tests
[xUnit.net 00:00:00.7073844]   Discovered:  Tests
[xUnit.net 00:00:00.7453826]   Starting:    Tests
[xUnit.net 00:00:00.9590439]   Finished:    Tests

Total tests: 1. Passed: 1. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.9607 Seconds
```

<span data-ttu-id="67eac-138">Os ensaios unitários podem ser filtrados de acordo com o seu nome e/ou o alvo de execução:</span><span class="sxs-lookup"><span data-stu-id="67eac-138">Unit tests can be filtered according to their name and/or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="67eac-139">A função intrínseca <xref:microsoft.quantum.intrinsic.message> tem tipo `(String -> Unit)` e permite a criação de mensagens de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="67eac-139">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="67eac-140">Estúdio Visual 2019</span><span class="sxs-lookup"><span data-stu-id="67eac-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="67eac-141">Depois de executar um teste no Test Explorer e clicar no teste, aparecerá um painel com informações sobre a execução do teste: Estado passado/falhado, tempo decorrido e uma ligação "Output".</span><span class="sxs-lookup"><span data-stu-id="67eac-141">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="67eac-142">Se clicar no link "Output", a saída de teste abrirá numa nova janela.</span><span class="sxs-lookup"><span data-stu-id="67eac-142">If you click the "Output" link, test output will open in a new window.</span></span>

![saída de teste](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="67eac-144">Linha de Comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="67eac-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="67eac-145">O estado de passagem/falha de cada teste é impresso na consola por `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="67eac-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="67eac-146">Para testes falhados, as saídas também são impressas na consola para ajudar a diagnosticar a falha.</span><span class="sxs-lookup"><span data-stu-id="67eac-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="67eac-147">Factos e Afirmações</span><span class="sxs-lookup"><span data-stu-id="67eac-147">Facts and Assertions</span></span>

<span data-ttu-id="67eac-148">Como as funções em Q# não têm efeitos secundários _lógicos,_ quaisquer _outros tipos_ de efeitos de executar uma função cujo tipo de saída é a tuple vazia `()` nunca podem ser observados dentro de um programa Q#.</span><span class="sxs-lookup"><span data-stu-id="67eac-148">Because functions in Q# have no _logical_ side effects, any _other kinds_ of effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="67eac-149">Ou seja, uma máquina-alvo pode optar por não executar qualquer função que desfaça `()` com a garantia de que esta omissão não modificará o comportamento de qualquer código Q# seguinte.</span><span class="sxs-lookup"><span data-stu-id="67eac-149">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="67eac-150">Isto torna as funções de retornar `()` (ou seja, `Unit`) uma ferramenta útil para incorporar afirmações e depurar lógica em programas Q#.</span><span class="sxs-lookup"><span data-stu-id="67eac-150">This makes functions returning `()` (i.e. `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="67eac-151">Vamos considerar um exemplo simples:</span><span class="sxs-lookup"><span data-stu-id="67eac-151">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="67eac-152">Aqui, a palavra-chave `fail` indica que o cálculo não deve prosseguir, elevando uma exceção na máquina-alvo que executa o programa Q#.</span><span class="sxs-lookup"><span data-stu-id="67eac-152">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="67eac-153">Por definição, uma falha deste tipo não pode ser observada a partir de Q#, uma vez que nenhum outro código Q# é executado após uma declaração `fail` ser alcançado.</span><span class="sxs-lookup"><span data-stu-id="67eac-153">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="67eac-154">Assim, se passarmos por um apelo à `PositivityFact`, podemos ter a certeza de que o seu contributo foi positivo.</span><span class="sxs-lookup"><span data-stu-id="67eac-154">Thus, if we proceed past a call to `PositivityFact`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="67eac-155">Note que podemos implementar o mesmo comportamento que `PositivityFact` usando a função [`Fact`](xref:microsoft.quantum.diagnostics.fact) a partir do espaço de nome <xref:microsoft.quantum.diagnostics>:</span><span class="sxs-lookup"><span data-stu-id="67eac-155">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value <= 0, "Expected a positive number.");
```

<span data-ttu-id="67eac-156">*As afirmações,* por outro lado, são usadas da mesma forma aos factos, mas podem estar dependentes do estado da máquina-alvo.</span><span class="sxs-lookup"><span data-stu-id="67eac-156">*Assertions*, on the other hand, are used similarly to facts, but may be dependent on the state of the target machine.</span></span> <span data-ttu-id="67eac-157">Consequentemente, são definidos como operações, enquanto os factos são definidos como funções (como acima).</span><span class="sxs-lookup"><span data-stu-id="67eac-157">Correspondingly, they are defined as operations, whereas facts are defined as functions (as above).</span></span>
<span data-ttu-id="67eac-158">Para compreender a distinção, considere o seguinte uso de um facto dentro de uma afirmação:</span><span class="sxs-lookup"><span data-stu-id="67eac-158">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="67eac-159">Aqui, estamos a utilizar a operação <xref:microsoft.quantum.environment.getqubitsavailabletouse> para devolver o número de qubits disponíveis para utilização.</span><span class="sxs-lookup"><span data-stu-id="67eac-159">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="67eac-160">Como isto depende claramente do estado global do programa e do seu ambiente de execução, a nossa definição de `AssertQubitsAreAvailable` também deve ser uma operação.</span><span class="sxs-lookup"><span data-stu-id="67eac-160">As this clearly depends on the global state of the program and its execution environment, our definition of  `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="67eac-161">No entanto, podemos usar esse estado global para produzir um valor simples `Bool` como contributo para a função `Fact`.</span><span class="sxs-lookup"><span data-stu-id="67eac-161">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="67eac-162">Com base nestas ideias, [o prelúdio](xref:microsoft.quantum.libraries.standard.prelude) oferece duas afirmações especialmente úteis, <xref:microsoft.quantum.intrinsic.assert> e <xref:microsoft.quantum.intrinsic.assertprob> ambas modeladas como operações para `()`.</span><span class="sxs-lookup"><span data-stu-id="67eac-162">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="67eac-163">Estas afirmações tomam cada um um operador Pauli descrevendo uma medição particular de interesse, um registo quântico sobre o qual deve ser feita uma medição e um resultado hipotético.</span><span class="sxs-lookup"><span data-stu-id="67eac-163">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="67eac-164">Nas máquinas-alvo que funcionam por simulação, não estamos ligados ao [teorema de não clonagem,](https://en.wikipedia.org/wiki/No-cloning_theorem)e podemos efetuar tais medições sem perturbar o registo passado a tais afirmações.</span><span class="sxs-lookup"><span data-stu-id="67eac-164">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="67eac-165">Um simulador pode então, semelhante à função `PositivityFact` acima, abortar a computação se o resultado hipotético não for observado na prática:</span><span class="sxs-lookup"><span data-stu-id="67eac-165">A simulator can then, similar to the `PositivityFact` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    Assert([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="67eac-166">No hardware quântico físico, onde o teorema de não clonagem impede o exame do estado quântico, as operações `Assert` e `AssertProb` simplesmente devolvem `()` sem outro efeito.</span><span class="sxs-lookup"><span data-stu-id="67eac-166">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="67eac-167">O espaço de <xref:microsoft.quantum.diagnostics> fornece várias mais funções da família `Assert` que nos permitem verificar condições mais avançadas.</span><span class="sxs-lookup"><span data-stu-id="67eac-167">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="67eac-168">Funções de despejo</span><span class="sxs-lookup"><span data-stu-id="67eac-168">Dump Functions</span></span>

<span data-ttu-id="67eac-169">Para ajudar a resolver problemas em programas quânticos, o espaço de nome <xref:microsoft.quantum.diagnostics> oferece duas funções que podem despejar num ficheiro o estado atual da máquina-alvo: <xref:microsoft.quantum.diagnostics.dumpmachine> e <xref:microsoft.quantum.diagnostics.dumpregister>.</span><span class="sxs-lookup"><span data-stu-id="67eac-169">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="67eac-170">A saída gerada de cada um depende da máquina-alvo.</span><span class="sxs-lookup"><span data-stu-id="67eac-170">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="67eac-171">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="67eac-171">DumpMachine</span></span>

<span data-ttu-id="67eac-172">O simulador quântico de estado inteiro distribuído como parte do Kit de Desenvolvimento Quântico escreve no ficheiro a função de [onda](https://en.wikipedia.org/wiki/Wave_function) de todo o sistema quântico, como uma matriz unidimensional de números complexos, em que cada elemento representa a amplitude da probabilidade de medir a base computacional estado $\ket{n}$, onde $\ket{n} = \ket{b_{{n-1}... b_1b_0}$ por bits $\{b_i\}$.</span><span class="sxs-lookup"><span data-stu-id="67eac-172">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="67eac-173">Por exemplo, numa máquina com apenas dois qubits atribuídos e no estado quântico $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> gera esta saída:</span><span class="sxs-lookup"><span data-stu-id="67eac-173">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="67eac-174">A primeira linha fornece um comentário com os IDs dos qubits correspondentes na sua ordem significativa.</span><span class="sxs-lookup"><span data-stu-id="67eac-174">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="67eac-175">O resto das linhas descrevem a amplitude da probabilidade de medir o vetor de estado base $\ket{n}$ em ambos os formatos cartesianos e polares.</span><span class="sxs-lookup"><span data-stu-id="67eac-175">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="67eac-176">Em detalhe para a primeira fila:</span><span class="sxs-lookup"><span data-stu-id="67eac-176">In detail for the first row:</span></span>

* <span data-ttu-id="67eac-177">**`∣0❭:`** esta linha corresponde ao estado de base computacional `0`</span><span class="sxs-lookup"><span data-stu-id="67eac-177">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="67eac-178">**`0.707107 +  0.000000 i`:** a amplitude da probabilidade em formato cartesiano.</span><span class="sxs-lookup"><span data-stu-id="67eac-178">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="67eac-179">**` == `** : o sinal de `equal` sepeiza ambas as representações equivalentes.</span><span class="sxs-lookup"><span data-stu-id="67eac-179">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="67eac-180">**`**********  `** : Uma representação gráfica da magnitude, o número de `*` é proporcional à probabilidade de medir este vetor de estado.</span><span class="sxs-lookup"><span data-stu-id="67eac-180">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="67eac-181">**`[ 0.500000 ]`:** o valor numérico da magnitude</span><span class="sxs-lookup"><span data-stu-id="67eac-181">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="67eac-182">**`    ---`** : Uma representação gráfica da fase da amplitude (ver abaixo).</span><span class="sxs-lookup"><span data-stu-id="67eac-182">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="67eac-183">**`[ 0.0000 rad ]`:** o valor numérico da fase (em radianos).</span><span class="sxs-lookup"><span data-stu-id="67eac-183">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="67eac-184">Tanto a magnitude como a fase são exibidas com uma representação gráfica.</span><span class="sxs-lookup"><span data-stu-id="67eac-184">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="67eac-185">A representação de magnitude é direta: mostra uma barra de `*`, maior a probabilidade maior será a barra.</span><span class="sxs-lookup"><span data-stu-id="67eac-185">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="67eac-186">Para a fase, mostramos os seguintes símbolos para representar o ângulo com base nas gamas:</span><span class="sxs-lookup"><span data-stu-id="67eac-186">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

```
[ -π/16,   π/16)       ---
[  π/16,  3π/16)        /-
[ 3π/16,  5π/16)        / 
[ 5π/16,  7π/16)       +/ 
[ 7π/16,  9π/16)      ↑   
[ 8π/16, 11π/16)    \-    
[ 7π/16, 13π/16)    \     
[ 7π/16, 15π/16)   +\     
[15π/16, 19π/16)   ---    
[17π/16, 19π/16)   -/     
[19π/16, 21π/16)    /     
[21π/16, 23π/16)    /+    
[23π/16, 25π/16)      ↓   
[25π/16, 27π/16)       -\ 
[27π/16, 29π/16)        \ 
[29π/16, 31π/16)        \+
[31π/16,   π/16)       ---
```

<span data-ttu-id="67eac-187">Os seguintes exemplos mostram `DumpMachine` para alguns Estados comuns:</span><span class="sxs-lookup"><span data-stu-id="67eac-187">The following examples show `DumpMachine` for some common states:</span></span>

### `∣0❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

### `∣1❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣1❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
```

### `∣+❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
```

### `∣-❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:    -0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]  ---     [  3.14159 rad ]
```


  > [!NOTE]
  > <span data-ttu-id="67eac-188">O id de um qubit é atribuído no tempo de funcionamento e não está necessariamente alinhado com a ordem em que o qubit foi atribuído ou a sua posição dentro de um registo qubit.</span><span class="sxs-lookup"><span data-stu-id="67eac-188">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="67eac-189">Estúdio Visual 2019</span><span class="sxs-lookup"><span data-stu-id="67eac-189">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="67eac-190">Você pode descobrir um qubit id no Estúdio Visual colocando um ponto de rutura no seu código e inspecionando o valor de uma variável qubit, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="67eac-190">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![mostrar qubit id no Estúdio Visual](~/media/qubit_id.png)
  >
  > <span data-ttu-id="67eac-192">o qubit com `0` de índice na `register2` tem id=`3`, o qubit com índice `1` tem id=`2`.</span><span class="sxs-lookup"><span data-stu-id="67eac-192">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="67eac-193">Linha de Comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="67eac-193">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="67eac-194">Pode descobrir um id qubit utilizando a função <xref:microsoft.quantum.intrinsic.message> e passando a variável qubit na mensagem, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="67eac-194">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="67eac-195">que poderia gerar esta saída:</span><span class="sxs-lookup"><span data-stu-id="67eac-195">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="67eac-196">o que significa que o qubit com índice `0` em `register2` tem id=`3`, o qubit com índice `1` tem id=`2`.</span><span class="sxs-lookup"><span data-stu-id="67eac-196">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="67eac-197"><xref:microsoft.quantum.diagnostics.dumpmachine> faz parte do espaço de nome <xref:microsoft.quantum.diagnostics>, por isso, para o utilizar, deve adicionar uma declaração `open`:</span><span class="sxs-lookup"><span data-stu-id="67eac-197"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

```qsharp
namespace Samples {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {
        using (qubits = Qubit[2]) {
            H(qubits[1]);
            DumpMachine("dump.txt");
        }
    }
}
```


### <a name="dumpregister"></a><span data-ttu-id="67eac-198">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="67eac-198">DumpRegister</span></span>

<span data-ttu-id="67eac-199"><xref:microsoft.quantum.diagnostics.dumpregister> funciona como <xref:microsoft.quantum.diagnostics.dumpmachine>, só que é preciso também um conjunto de qubits para limitar a quantidade de informação apenas a que seja relevante para os qubits correspondentes.</span><span class="sxs-lookup"><span data-stu-id="67eac-199"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="67eac-200">Tal como acontece com <xref:microsoft.quantum.diagnostics.dumpmachine>, a informação gerada por <xref:microsoft.quantum.diagnostics.dumpregister> depende da máquina-alvo.</span><span class="sxs-lookup"><span data-stu-id="67eac-200">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="67eac-201">Para o simulador quântico de todo o estado, escreve no ficheiro a função de onda até uma fase global do subsistema quântico gerado pelos qubits fornecidos no mesmo formato que <xref:microsoft.quantum.diagnostics.dumpmachine>.</span><span class="sxs-lookup"><span data-stu-id="67eac-201">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="67eac-202">Por exemplo, tome novamente uma máquina com apenas dois qubits atribuídos e no estado quântico $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 +i)}{2} \ket{10} = - e^{-i\pi/4} (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ), \end{align} $$ chamando <xref:microsoft.quantum.diagnostics.dumpregister> para `qubit[0]` gera esta saída gera esta saída :</span><span class="sxs-lookup"><span data-stu-id="67eac-202">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="67eac-203">e chamar <xref:microsoft.quantum.diagnostics.dumpregister> para `qubit[1]` gera esta saída:</span><span class="sxs-lookup"><span data-stu-id="67eac-203">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="67eac-204">Em geral, o estado de um registo que está enredado com outro registo é um estado misto e não um estado puro.</span><span class="sxs-lookup"><span data-stu-id="67eac-204">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="67eac-205">Neste caso, <xref:microsoft.quantum.diagnostics.dumpregister> produz a seguinte mensagem:</span><span class="sxs-lookup"><span data-stu-id="67eac-205">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="67eac-206">O exemplo que se segue mostra como pode usar tanto <xref:microsoft.quantum.diagnostics.dumpregister> como <xref:microsoft.quantum.diagnostics.dumpmachine> no seu código Q# :</span><span class="sxs-lookup"><span data-stu-id="67eac-206">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

```qsharp
namespace app
{
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {

        using (qubits = Qubit[2]) {
            X(qubits[1]);
            H(qubits[1]);
            R1Frac(1, 2, qubits[1]);
            
            DumpMachine("dump.txt");
            DumpRegister("q0.txt", qubits[0..0]);
            DumpRegister("q1.txt", qubits[1..1]);

            ResetAll(qubits);
        }
    }
}
```

## <a name="debugging"></a><span data-ttu-id="67eac-207">Depurar</span><span class="sxs-lookup"><span data-stu-id="67eac-207">Debugging</span></span>

<span data-ttu-id="67eac-208">Além das funções e operações de `Assert` e `Dump`, a Q# suporta um subconjunto de capacidades padrão de depuração do Estúdio Visual: definição de breakpoints de [linha,](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)passo através do [código usando F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) e [inspecionar valores de variáveis clássicas](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) são todos possíveis durante a execução de código no simulador.</span><span class="sxs-lookup"><span data-stu-id="67eac-208">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="67eac-209">Depuração em Código de Estúdio Visual aproveita as C# capacidades de depuração fornecidas pela extensão visual do Código do Estúdio powered pela OmniSharp e requer a instalação da [versão mais recente](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="67eac-209">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span> 
