---
title: 'Técnicas de Q # – testando e Depurando | Microsoft Docs'
description: 'Técnicas de Q # – teste e depuração'
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 25679331f1bed9f98b86c6eb20f511c891bac1af
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183493"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="f1aab-103">Testando e Depurando</span><span class="sxs-lookup"><span data-stu-id="f1aab-103">Testing and Debugging</span></span>

<span data-ttu-id="f1aab-104">Assim como acontece com a programação clássica, é essencial poder verificar se os programas Quantum atuam como pretendidos e ser capaz de diagnosticar um programa Quantum incorreto.</span><span class="sxs-lookup"><span data-stu-id="f1aab-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="f1aab-105">Nesta seção, abordaremos as ferramentas oferecidas por Q # para testar e depurar programas Quantum.</span><span class="sxs-lookup"><span data-stu-id="f1aab-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="f1aab-106">Testes de unidade</span><span class="sxs-lookup"><span data-stu-id="f1aab-106">Unit Tests</span></span>

<span data-ttu-id="f1aab-107">Uma abordagem comum para testar programas clássicos é escrever programas pequenos chamados *testes de unidade* que executam código em uma biblioteca e comparam sua saída a alguma saída esperada.</span><span class="sxs-lookup"><span data-stu-id="f1aab-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="f1aab-108">Por exemplo, talvez queiramos garantir que `Square(2)` retorna `4`, já que sabemos *um priori* de que $2 ^ 2 = $4.</span><span class="sxs-lookup"><span data-stu-id="f1aab-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="f1aab-109">O Q # dá suporte à criação de testes de unidade para programas Quantum e que pode ser executado como testes dentro da estrutura de teste de unidade do [xUnit](https://xunit.github.io/) .</span><span class="sxs-lookup"><span data-stu-id="f1aab-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="f1aab-110">Criando um projeto de teste</span><span class="sxs-lookup"><span data-stu-id="f1aab-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="f1aab-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f1aab-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="f1aab-112">Abra o Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="f1aab-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="f1aab-113">Vá para o menu `File` e selecione `New` > `Project...`.</span><span class="sxs-lookup"><span data-stu-id="f1aab-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="f1aab-114">No explorador de modelos de projeto, em `Installed` > `Visual C#`, selecione o modelo `Q# Test Project`.</span><span class="sxs-lookup"><span data-stu-id="f1aab-114">In the project template explorer, under `Installed` > `Visual C#`, select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="f1aab-115">Linha de comando/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f1aab-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="f1aab-116">Na sua linha de comando favorita, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f1aab-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="f1aab-117">Em ambos os casos, seu novo projeto terá dois arquivos abertos.</span><span class="sxs-lookup"><span data-stu-id="f1aab-117">In either case, your new project will have two files open.</span></span>
<span data-ttu-id="f1aab-118">O primeiro arquivo, `Tests.qs`, fornece um local conveniente para definir novos testes de unidade Q #.</span><span class="sxs-lookup"><span data-stu-id="f1aab-118">The first file, `Tests.qs`, provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="f1aab-119">Inicialmente, esse arquivo contém um teste de unidade de exemplo `AllocateQubitTest` que verifica se um qubit alocado recentemente está no estado $ \ket{0}$ e imprime uma mensagem:</span><span class="sxs-lookup"><span data-stu-id="f1aab-119">Initially this file contains one sample unit test `AllocateQubitTest` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    operation AllocateQubitTest () : Unit {
        using (q = Qubit()) {
            Assert([PauliZ], [q], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="f1aab-120">Qualquer operação de Q # compatível com o tipo `(Unit => Unit)` ou função compatível com `(Unit -> Unit)` pode ser executada como um teste de unidade.</span><span class="sxs-lookup"><span data-stu-id="f1aab-120">Any Q# operation compatible with the type `(Unit => Unit)` or function compatible with `(Unit -> Unit)` can be executed as a unit test.</span></span> 

<span data-ttu-id="f1aab-121">O segundo arquivo, `TestSuiteRunner.cs` contém um método que descobre e executa os testes de unidade Q #.</span><span class="sxs-lookup"><span data-stu-id="f1aab-121">The second file, `TestSuiteRunner.cs` contains a method that discovers and runs Q# unit tests.</span></span> <span data-ttu-id="f1aab-122">Este é o método `TestTarget` anotado com `OperationDriver` atributo.</span><span class="sxs-lookup"><span data-stu-id="f1aab-122">This is the method `TestTarget` annotated with `OperationDriver` attribute.</span></span>
<span data-ttu-id="f1aab-123">O atributo `OperationDriver` é uma parte da biblioteca de extensão xUnit Microsoft. Quantum. Simulation. xUnit.</span><span class="sxs-lookup"><span data-stu-id="f1aab-123">The `OperationDriver` attribute is a part of the Xunit extension library Microsoft.Quantum.Simulation.Xunit.</span></span>
<span data-ttu-id="f1aab-124">A estrutura de testes de unidade chama `TestTarget` método para cada teste de unidade Q # descoberto.</span><span class="sxs-lookup"><span data-stu-id="f1aab-124">The unit testing framework calls `TestTarget` method for every Q# unit test it has discovered.</span></span>
<span data-ttu-id="f1aab-125">A estrutura passa a descrição do teste de unidade para o método por meio de `op` argumento.</span><span class="sxs-lookup"><span data-stu-id="f1aab-125">The framework passes the unit test description to the method through `op` argument.</span></span> <span data-ttu-id="f1aab-126">A seguinte linha de código:</span><span class="sxs-lookup"><span data-stu-id="f1aab-126">The following line of code:</span></span>
```csharp
op.TestOperationRunner(sim);
```
<span data-ttu-id="f1aab-127">executa o teste de unidade no `QuantumSimulator`.</span><span class="sxs-lookup"><span data-stu-id="f1aab-127">executes the unit test on `QuantumSimulator`.</span></span>

<span data-ttu-id="f1aab-128">Por padrão, o mecanismo de descoberta de teste de unidade procura todas as funções Q # ou operações do tipo compatível que atendam às seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="f1aab-128">By default, the unit test discovery mechanism looks for all Q# functions or operations of compatible type that satisfy the following properties:</span></span>
* <span data-ttu-id="f1aab-129">Localizado no mesmo assembly que o método anotado com o atributo `OperationDriver`.</span><span class="sxs-lookup"><span data-stu-id="f1aab-129">Located in the same assembly as the method annotated with the `OperationDriver` attribute.</span></span>
* <span data-ttu-id="f1aab-130">Localizado no mesmo namespace que o método anotado com o atributo `OperationDriver`.</span><span class="sxs-lookup"><span data-stu-id="f1aab-130">Located in the same namespace as the method annotated with the `OperationDriver` attribute.</span></span>
* <span data-ttu-id="f1aab-131">Tem um nome que termina com `Test`.</span><span class="sxs-lookup"><span data-stu-id="f1aab-131">Has a name ending with `Test`.</span></span>

<span data-ttu-id="f1aab-132">Um assembly, um namespace e um sufixo para funções e operações de teste de unidade podem ser definidos usando parâmetros opcionais do atributo `OperationDriver`:</span><span class="sxs-lookup"><span data-stu-id="f1aab-132">An assembly, a namespace, and a suffix for unit test functions and operations can be set using optional parameters of the `OperationDriver` attribute:</span></span>
* <span data-ttu-id="f1aab-133">`AssemblyName` parâmetro define o nome do assembly que está sendo pesquisado para testes.</span><span class="sxs-lookup"><span data-stu-id="f1aab-133">`AssemblyName` parameter sets the name of the assembly which is being searched for tests.</span></span>
* <span data-ttu-id="f1aab-134">`TestNamespace` parâmetro define o nome do namespace que está sendo pesquisado para testes.</span><span class="sxs-lookup"><span data-stu-id="f1aab-134">`TestNamespace` parameter sets the name of the namespace which is being searched for tests.</span></span>
* <span data-ttu-id="f1aab-135">`Suffix` define o sufixo dos nomes de operação ou de função que são considerados como testes de unidade.</span><span class="sxs-lookup"><span data-stu-id="f1aab-135">`Suffix` sets the suffix of operation or function names that are considered to be unit tests.</span></span>

<span data-ttu-id="f1aab-136">Além disso, o `TestCasePrefix` parâmetro opcional permite que você defina um prefixo para o nome do caso de teste.</span><span class="sxs-lookup"><span data-stu-id="f1aab-136">In addition, the `TestCasePrefix` optional parameter lets you set a prefix for the name of the test case.</span></span> <span data-ttu-id="f1aab-137">O prefixo na frente do nome da operação aparecerá na lista de casos de teste.</span><span class="sxs-lookup"><span data-stu-id="f1aab-137">The prefix in front of the operation name will appear in the list of test cases.</span></span> <span data-ttu-id="f1aab-138">Por exemplo, `TestCasePrefix = "QSim:"` fará com que `AllocateQubitTest` apareça como `QSim:AllocateQubitTest` na lista de testes encontrados.</span><span class="sxs-lookup"><span data-stu-id="f1aab-138">For example, `TestCasePrefix = "QSim:"` will cause `AllocateQubitTest` to appear as `QSim:AllocateQubitTest` in the list of found tests.</span></span> <span data-ttu-id="f1aab-139">Isso pode ser útil para indicar, por exemplo, qual simulador é usado para executar um teste.</span><span class="sxs-lookup"><span data-stu-id="f1aab-139">This can be useful to indicate, for instance, which simulator is used to run a test.</span></span>

### <a name="running-q-unit-tests"></a><span data-ttu-id="f1aab-140">Executando os testes de unidade de Q #</span><span class="sxs-lookup"><span data-stu-id="f1aab-140">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="f1aab-141">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f1aab-141">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="f1aab-142">Como configuração única por solução, vá para `Test` menu e selecione `Test Settings` > `Default Processor Architecture` > `X64`.</span><span class="sxs-lookup"><span data-stu-id="f1aab-142">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="f1aab-143">A configuração de arquitetura de processador padrão para o Visual Studio é armazenada no arquivo de opções de solução (`.suo`) para cada solução.</span><span class="sxs-lookup"><span data-stu-id="f1aab-143">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="f1aab-144">Se você excluir esse arquivo, será necessário selecionar `X64` como a arquitetura do processador novamente.</span><span class="sxs-lookup"><span data-stu-id="f1aab-144">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="f1aab-145">Compile o projeto, vá para o menu de `Test` e selecione `Windows` > `Test Explorer`.</span><span class="sxs-lookup"><span data-stu-id="f1aab-145">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="f1aab-146">`AllocateQubitTest` aparecerá na lista de testes no grupo de `Not Run Tests`.</span><span class="sxs-lookup"><span data-stu-id="f1aab-146">`AllocateQubitTest` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="f1aab-147">Selecione `Run All` ou execute este teste individual e ele deve passar!</span><span class="sxs-lookup"><span data-stu-id="f1aab-147">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="f1aab-148">Linha de comando/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f1aab-148">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="f1aab-149">Para executar testes, navegue até a pasta do projeto (a pasta que contém `Tests.csproj`) e execute o comando:</span><span class="sxs-lookup"><span data-stu-id="f1aab-149">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="f1aab-150">Você deve obter uma saída semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="f1aab-150">You should get output similar to the following:</span></span>

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

***

## <a name="logging-and-assertions"></a><span data-ttu-id="f1aab-151">Registro em log e asserções</span><span class="sxs-lookup"><span data-stu-id="f1aab-151">Logging and Assertions</span></span>

<span data-ttu-id="f1aab-152">Uma consequência importante do fato de que as funções em Q # não têm efeitos colaterais é que os efeitos da execução de uma função cujo tipo de saída é a tupla vazia `()` nunca podem ser observados em um programa Q #.</span><span class="sxs-lookup"><span data-stu-id="f1aab-152">One important consequence of the fact that functions in Q# have no side effects is that any effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="f1aab-153">Ou seja, um computador de destino pode optar por não executar nenhuma função que retorne `()` com a garantia de que essa omissão não modificará o comportamento de qualquer código Q # a seguir.</span><span class="sxs-lookup"><span data-stu-id="f1aab-153">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="f1aab-154">Isso faz com que as funções retornem `()` uma ferramenta útil para incorporar asserções e depurar a lógica em programas Q #.</span><span class="sxs-lookup"><span data-stu-id="f1aab-154">This makes functions returning `()` a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

### <a name="logging"></a><span data-ttu-id="f1aab-155">Registo</span><span class="sxs-lookup"><span data-stu-id="f1aab-155">Logging</span></span>

<span data-ttu-id="f1aab-156">A função intrínseca <xref:microsoft.quantum.intrinsic.message> tem o tipo `(String -> Unit)` e habilita a criação de mensagens de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="f1aab-156">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

<span data-ttu-id="f1aab-157">A ação `onLog` de `QuantumSimulator` pode ser usada para definir ações executadas quando o código de Q # chama `Message`.</span><span class="sxs-lookup"><span data-stu-id="f1aab-157">The `onLog` action of `QuantumSimulator` can be used to define actions performed when Q# code calls `Message`.</span></span> <span data-ttu-id="f1aab-158">Por padrão, as mensagens registradas são impressas para a saída padrão.</span><span class="sxs-lookup"><span data-stu-id="f1aab-158">By default logged messages are printed to standard output.</span></span>

<span data-ttu-id="f1aab-159">Ao definir um conjunto de testes de unidade, as mensagens registradas podem ser direcionadas para a saída de teste.</span><span class="sxs-lookup"><span data-stu-id="f1aab-159">When defining a unit test suite, the logged messages can be directed to the test output.</span></span> <span data-ttu-id="f1aab-160">Quando um projeto é criado a partir do modelo de projeto de teste Q #, esse redirecionamento é pré-configurado para o pacote e criado por padrão da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f1aab-160">When a project is created from Q# Test Project template, this redirection is pre-configured for the suite and created by default as follows:</span></span>

```qsharp
using (var sim = new QuantumSimulator())
{
    // OnLog defines action(s) performed when Q# test calls operation Message
    sim.OnLog += (msg) => { output.WriteLine(msg); };
    op.TestOperationRunner(sim);
}
```

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="f1aab-161">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f1aab-161">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="f1aab-162">Depois de executar um teste no Test Explorer e clicar no teste, um painel será exibido com informações sobre a execução do teste: passou/falha no status, tempo decorrido e um link de "saída".</span><span class="sxs-lookup"><span data-stu-id="f1aab-162">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="f1aab-163">Se você clicar no link "saída", a saída de teste será aberta em uma nova janela.</span><span class="sxs-lookup"><span data-stu-id="f1aab-163">If you click the "Output" link, test output will open in a new window.</span></span>

![saída de teste](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="f1aab-165">Linha de comando/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f1aab-165">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="f1aab-166">O status de aprovação/reprovação de cada teste é impresso no console do por `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="f1aab-166">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="f1aab-167">Para testes com falha, as saídas registradas como resultado da chamada de `output.WriteLine(msg)` acima também são impressas no console para ajudar a diagnosticar a falha.</span><span class="sxs-lookup"><span data-stu-id="f1aab-167">For failing tests, the outputs logged as a result of the `output.WriteLine(msg)` call above are also printed to the console to help diagnose the failure.</span></span>

***

### <a name="assertions"></a><span data-ttu-id="f1aab-168">Declarações</span><span class="sxs-lookup"><span data-stu-id="f1aab-168">Assertions</span></span>

<span data-ttu-id="f1aab-169">A mesma lógica pode ser aplicada à implementação de asserções.</span><span class="sxs-lookup"><span data-stu-id="f1aab-169">The same logic can be applied to implementing assertions.</span></span> <span data-ttu-id="f1aab-170">Vamos considerar um exemplo simples:</span><span class="sxs-lookup"><span data-stu-id="f1aab-170">Let's consider a simple example:</span></span>

```qsharp
function AssertPositive(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="f1aab-171">Aqui, a palavra-chave `fail` indica que a computação não deve continuar, gerando uma exceção no computador de destino que executa o programa Q #.</span><span class="sxs-lookup"><span data-stu-id="f1aab-171">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="f1aab-172">Por definição, uma falha desse tipo não pode ser observada em Q #, pois nenhum código Q # adicional é executado depois que uma instrução `fail` é atingida.</span><span class="sxs-lookup"><span data-stu-id="f1aab-172">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="f1aab-173">Portanto, se continuarmos passando por uma chamada para `AssertPositive`, poderemos ter certeza de que sua entrada era positiva.</span><span class="sxs-lookup"><span data-stu-id="f1aab-173">Thus, if we proceed past a call to `AssertPositive`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="f1aab-174">Com base nessas ideias, [o prelúdio](xref:microsoft.quantum.libraries.standard.prelude) oferece duas declarações especialmente úteis, <xref:microsoft.quantum.intrinsic.assert> e <xref:microsoft.quantum.intrinsic.assertprob> modeladas como operações em `()`.</span><span class="sxs-lookup"><span data-stu-id="f1aab-174">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="f1aab-175">Cada declaração assume um operador Pauli que descreve uma medida de interesse específica, um registro Quantum no qual uma medida deve ser executada e um resultado hipotético.</span><span class="sxs-lookup"><span data-stu-id="f1aab-175">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="f1aab-176">Em computadores de destino que funcionam por simulação, não estamos vinculados pelo [teorema no-Cloning](https://en.wikipedia.org/wiki/No-cloning_theorem)e podem executar essas medições sem perturbar o registro passado para tais asserções.</span><span class="sxs-lookup"><span data-stu-id="f1aab-176">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="f1aab-177">Um simulador pode, assim, semelhante à função `AssertPositive` acima, anular a computação se o resultado hipotético não fosse observado na prática:</span><span class="sxs-lookup"><span data-stu-id="f1aab-177">A simulator can then, similar to the `AssertPositive` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

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

<span data-ttu-id="f1aab-178">Em hardware Quantum físico, em que o teorema sem clonagem impede o exame do estado Quantum, as operações `Assert` e `AssertProb` simplesmente retornam `()` sem nenhum outro efeito.</span><span class="sxs-lookup"><span data-stu-id="f1aab-178">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="f1aab-179">O namespace <xref:microsoft.quantum.diagnostics> fornece várias outras funções da família `Assert`, que nos permitem verificar condições mais avançadas.</span><span class="sxs-lookup"><span data-stu-id="f1aab-179">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="f1aab-180">Funções de despejo</span><span class="sxs-lookup"><span data-stu-id="f1aab-180">Dump Functions</span></span>

<span data-ttu-id="f1aab-181">Para ajudar a solucionar problemas de programas Quantum, o namespace <xref:microsoft.quantum.diagnostics> oferece duas funções que podem ser despejadas em um arquivo o status atual da máquina de destino: <xref:microsoft.quantum.diagnostics.dumpmachine> e <xref:microsoft.quantum.diagnostics.dumpregister>.</span><span class="sxs-lookup"><span data-stu-id="f1aab-181">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="f1aab-182">A saída gerada de cada uma depende do computador de destino.</span><span class="sxs-lookup"><span data-stu-id="f1aab-182">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="f1aab-183">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="f1aab-183">DumpMachine</span></span>

<span data-ttu-id="f1aab-184">O simulador de Quantum completo distribuído como parte do kit de desenvolvimento Quantum grava no arquivo a [função de onda](https://en.wikipedia.org/wiki/Wave_function) de todo o sistema Quantum, como uma matriz unidimensional de números complexos, na qual cada elemento representa a amplitude do probabilidade de medir o estado de base computacional $ \ket{n} $, em que $ \ket{n} = \ket{b_{n-1}... b_1b_0} $ para bits $\{b_i\}$.</span><span class="sxs-lookup"><span data-stu-id="f1aab-184">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="f1aab-185">Por exemplo, em um computador com apenas dois qubits alocados e no estado Quantum $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10}, \end{align} $ $ chamando <xref:microsoft.quantum.diagnostics.dumpmachine> gera essa saída :</span><span class="sxs-lookup"><span data-stu-id="f1aab-185">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="f1aab-186">A primeira linha fornece um comentário com as IDs do qubits correspondente em sua ordem significativa.</span><span class="sxs-lookup"><span data-stu-id="f1aab-186">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="f1aab-187">O restante das linhas descreve a amplitude de probabilidade de medir o vetor de estado base $ \ket{n} $ nos formatos cartesianas e polar.</span><span class="sxs-lookup"><span data-stu-id="f1aab-187">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="f1aab-188">Em detalhes para a primeira linha:</span><span class="sxs-lookup"><span data-stu-id="f1aab-188">In detail for the first row:</span></span>

* <span data-ttu-id="f1aab-189">**`∣0❭:`** essa linha corresponde ao estado de base computacional `0`</span><span class="sxs-lookup"><span data-stu-id="f1aab-189">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="f1aab-190">**`0.707107 +  0.000000 i`** : a amplitude de probabilidade no formato cartesiano.</span><span class="sxs-lookup"><span data-stu-id="f1aab-190">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="f1aab-191">**` == `** : o sinal de `equal` separa as representações equivalentes.</span><span class="sxs-lookup"><span data-stu-id="f1aab-191">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="f1aab-192">**`**********  `** : uma representação gráfica da magnitude, o número de `*` é proporcionalmente à probabilidade de medir esse vetor de estado.</span><span class="sxs-lookup"><span data-stu-id="f1aab-192">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="f1aab-193">**`[ 0.500000 ]`** : o valor numérico da magnitude</span><span class="sxs-lookup"><span data-stu-id="f1aab-193">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="f1aab-194">**`    ---`** : uma representação gráfica da fase da amplitude (veja abaixo).</span><span class="sxs-lookup"><span data-stu-id="f1aab-194">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="f1aab-195">**`[ 0.0000 rad ]`** : o valor numérico da fase (em radianos).</span><span class="sxs-lookup"><span data-stu-id="f1aab-195">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="f1aab-196">A magnitude e a fase são exibidas com uma representação gráfica.</span><span class="sxs-lookup"><span data-stu-id="f1aab-196">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="f1aab-197">A representação de magnitude é direta: ela mostra uma barra de `*`, quanto maior a probabilidade maior será a barra.</span><span class="sxs-lookup"><span data-stu-id="f1aab-197">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="f1aab-198">Para a fase, mostramos os seguintes símbolos para representar o ângulo com base em intervalos:</span><span class="sxs-lookup"><span data-stu-id="f1aab-198">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="f1aab-199">Os exemplos a seguir mostram `DumpMachine` para alguns Estados comuns:</span><span class="sxs-lookup"><span data-stu-id="f1aab-199">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="f1aab-200">A ID de um qubit é atribuída em tempo de execução e não está necessariamente alinhada com a ordem na qual o qubit foi alocado ou sua posição em um registro qubit.</span><span class="sxs-lookup"><span data-stu-id="f1aab-200">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="f1aab-201">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f1aab-201">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="f1aab-202">Você pode descobrir uma ID de qubit no Visual Studio colocando um ponto de interrupção em seu código e inspecionando o valor de uma variável qubit, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f1aab-202">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![Mostrar ID do qubit no Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="f1aab-204">o qubit com o `0` de índice em `register2` tem ID =`3`, o qubit com `1` de índice tem a ID =`2`.</span><span class="sxs-lookup"><span data-stu-id="f1aab-204">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="f1aab-205">Linha de comando/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f1aab-205">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="f1aab-206">Você pode descobrir uma ID de qubit usando a função <xref:microsoft.quantum.intrinsic.message> e passando a variável qubit na mensagem, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f1aab-206">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="f1aab-207">que pode gerar essa saída:</span><span class="sxs-lookup"><span data-stu-id="f1aab-207">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="f1aab-208">Isso significa que o qubit com o índice `0` em `register2` tem a ID =`3`, o qubit com `1` de índice tem a ID =`2`.</span><span class="sxs-lookup"><span data-stu-id="f1aab-208">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="f1aab-209"><xref:microsoft.quantum.diagnostics.dumpmachine> faz parte do namespace <xref:microsoft.quantum.diagnostics>, portanto, para usá-lo, você deve adicionar uma instrução `open`:</span><span class="sxs-lookup"><span data-stu-id="f1aab-209"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="f1aab-210">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="f1aab-210">DumpRegister</span></span>

<span data-ttu-id="f1aab-211"><xref:microsoft.quantum.diagnostics.dumpregister> funciona como <xref:microsoft.quantum.diagnostics.dumpmachine>, exceto que ele também usa uma matriz de qubits para limitar a quantidade de informações apenas às relevantes para o qubits correspondente.</span><span class="sxs-lookup"><span data-stu-id="f1aab-211"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="f1aab-212">Assim como ocorre com <xref:microsoft.quantum.diagnostics.dumpmachine>, as informações geradas pelo <xref:microsoft.quantum.diagnostics.dumpregister> dependem da máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="f1aab-212">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="f1aab-213">Para o simulador de Quantum de estado completo, ele grava no arquivo a função de onda até uma fase global do subsistema Quantum gerado pelo qubits fornecido no mesmo formato que <xref:microsoft.quantum.diagnostics.dumpmachine>.</span><span class="sxs-lookup"><span data-stu-id="f1aab-213">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="f1aab-214">Por exemplo, use novamente um computador com apenas dois qubits alocados e no estado Quantum $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10} =-e ^ {-i \ pi/4} ((\frac{1}{\sqrt{2}} \ ket{0}-\frac{(1 + i)}{2} \ket{1}) \otimes \frac{-(1 + i)} {\sqrt{2}} \ket{0}), \end{align} $ $ chamando <xref:microsoft.quantum.diagnostics.dumpregister> para `qubit[0]` gera essa saída:</span><span class="sxs-lookup"><span data-stu-id="f1aab-214">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="f1aab-215">e chamar <xref:microsoft.quantum.diagnostics.dumpregister> para `qubit[1]` gera essa saída:</span><span class="sxs-lookup"><span data-stu-id="f1aab-215">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="f1aab-216">Em geral, o estado de um registro que é confusas com outro registro é um estado misto em vez de um estado puro.</span><span class="sxs-lookup"><span data-stu-id="f1aab-216">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="f1aab-217">Nesse caso, <xref:microsoft.quantum.diagnostics.dumpregister> gera a seguinte mensagem:</span><span class="sxs-lookup"><span data-stu-id="f1aab-217">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="f1aab-218">O exemplo a seguir mostra como você pode usar <xref:microsoft.quantum.diagnostics.dumpregister> e <xref:microsoft.quantum.diagnostics.dumpmachine> no código de Q #:</span><span class="sxs-lookup"><span data-stu-id="f1aab-218">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="f1aab-219">Depurar</span><span class="sxs-lookup"><span data-stu-id="f1aab-219">Debugging</span></span>

<span data-ttu-id="f1aab-220">Além das funções e operações de `Assert` e `Dump`, o Q # dá suporte a um subconjunto de recursos de depuração padrão do Visual Studio: [definindo pontos de interrupção de linha](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [percorrendo código usando F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) e [inspecionando valores de variáveis clássicas ](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)todos são possíveis durante a execução de código no simulador.</span><span class="sxs-lookup"><span data-stu-id="f1aab-220">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="f1aab-221">Ainda não há suporte para a depuração no Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="f1aab-221">Debugging in Visual Studio Code is not yet supported.</span></span>

