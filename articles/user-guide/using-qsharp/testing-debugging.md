---
title: Teste e depuração
description: Aprenda a usar testes unitários, factos e afirmações, e despeje funções para testar e depurar programas quânticos.
author: tcNickolas
ms.author: mamykhai@microsoft.com
ms.date: 06/01/2020
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
ms.openlocfilehash: db6e49e94e5ceb3b1b0b2d6ab57391618084072b
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870979"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="77619-103">Teste e depuração</span><span class="sxs-lookup"><span data-stu-id="77619-103">Testing and debugging</span></span>

<span data-ttu-id="77619-104">Tal como acontece com a programação clássica, é essencial poder verificar se os programas quânticos funcionam como pretendido, e ser capaz de diagnosticar comportamentos incorretos.</span><span class="sxs-lookup"><span data-stu-id="77619-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose incorrect behavior.</span></span>
<span data-ttu-id="77619-105">Nesta secção, cobrimos as ferramentas oferecidas pela Q# para testar e depurar programas quânticos.</span><span class="sxs-lookup"><span data-stu-id="77619-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="77619-106">Testes de Unidade</span><span class="sxs-lookup"><span data-stu-id="77619-106">Unit Tests</span></span>

<span data-ttu-id="77619-107">Uma abordagem comum para testar programas clássicos é escrever pequenos programas chamados *testes unitários*, que executam código numa biblioteca e comparam a sua saída com alguma saída esperada.</span><span class="sxs-lookup"><span data-stu-id="77619-107">One common approach to testing classical programs is to write small programs called *unit tests*, which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="77619-108">Por exemplo, pode garantir que `Square(2)` os `4` retornos, uma vez que conhece um *priori* que $2^2 = 4$.</span><span class="sxs-lookup"><span data-stu-id="77619-108">For example, you can ensure that `Square(2)` returns `4` since you know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="77619-109">Q# suporta a criação de testes unitários para programas quânticos, e que podem ser executados como testes dentro da estrutura de testes da unidade [xUnit.](https://xunit.github.io/)</span><span class="sxs-lookup"><span data-stu-id="77619-109">Q# supports creating unit tests for quantum programs, and which can run as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="77619-110">Criação de um Projeto de Teste</span><span class="sxs-lookup"><span data-stu-id="77619-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="77619-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="77619-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="77619-112">Open Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="77619-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="77619-113">Vá ao menu **'Arquivo'** e selecione **New > Project...**. No canto superior direito, procure `Q#` e selecione o modelo **de Projeto de Teste Q.**</span><span class="sxs-lookup"><span data-stu-id="77619-113">Go to the **File** menu and select **New > Project...**. In the upper right corner, search for `Q#`, and select the **Q# Test Project** template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="77619-114">Linha de Comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="77619-114">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="77619-115">Da sua linha de comando favorita, executar o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="77619-115">From your favorite command line, run the following command:</span></span>
```dotnetcli
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="77619-116">O seu novo projeto tem um único `Tests.qs` ficheiro, que fornece um local conveniente para definir novos testes de unidade Q#.</span><span class="sxs-lookup"><span data-stu-id="77619-116">Your new project has a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="77619-117">Inicialmente, este ficheiro contém um teste de unidade de amostra `AllocateQubit` que verifica se um qubit recém-atribuído está no estado de $\ket $ e {0} imprime uma mensagem:</span><span class="sxs-lookup"><span data-stu-id="77619-117">Initially, this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="77619-118">Qualquer operação ou função Q# que tenha um argumento de tipo `Unit` e devoluções `Unit` pode ser marcada como um teste de unidade através do `@Test("...")` atributo.</span><span class="sxs-lookup"><span data-stu-id="77619-118">Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="77619-119">No exemplo anterior, o argumento a esse atributo, `"QuantumSimulator"` especifica o alvo em que o teste é executado.</span><span class="sxs-lookup"><span data-stu-id="77619-119">In the previous example, the argument to that attribute, `"QuantumSimulator"`, specifies the target on which the test runs.</span></span> <span data-ttu-id="77619-120">Um único teste pode ser executado em vários alvos.</span><span class="sxs-lookup"><span data-stu-id="77619-120">A single test can run on multiple targets.</span></span> <span data-ttu-id="77619-121">Por exemplo, adicione um atributo `@Test("ResourcesEstimator")` antes `AllocateQubit` .</span><span class="sxs-lookup"><span data-stu-id="77619-121">For example, add an attribute `@Test("ResourcesEstimator")` before `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="77619-122">Guarde o ficheiro e faça todos os testes.</span><span class="sxs-lookup"><span data-stu-id="77619-122">Save the file and run all tests.</span></span> <span data-ttu-id="77619-123">Deve haver agora dois testes de unidade, um em `AllocateQubit` que corre no , e outro onde corre no `QuantumSimulator` `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="77619-123">There should now be two unit tests, one where `AllocateQubit` runs on the `QuantumSimulator`, and one where it runs in the `ResourcesEstimator`.</span></span> 

<span data-ttu-id="77619-124">O compilador Q# reconhece os alvos `"QuantumSimulator"` incorporados, `"ToffoliSimulator"` e como `"ResourcesEstimator"` alvos de execução válidos para testes de unidade.</span><span class="sxs-lookup"><span data-stu-id="77619-124">The Q# compiler recognizes the built-in targets `"QuantumSimulator"`, `"ToffoliSimulator"`, and `"ResourcesEstimator"` as valid execution targets for unit tests.</span></span> <span data-ttu-id="77619-125">Também é possível especificar qualquer nome totalmente qualificado para definir um alvo de execução personalizado.</span><span class="sxs-lookup"><span data-stu-id="77619-125">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-q-unit-tests"></a><span data-ttu-id="77619-126">Executando testes de unidade Q#</span><span class="sxs-lookup"><span data-stu-id="77619-126">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="77619-127">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="77619-127">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="77619-128">Como configuração única por solução, vá ao menu **de Teste** e selecione **Definições de Teste > Arquitetura do Processador Padrão > X64**.</span><span class="sxs-lookup"><span data-stu-id="77619-128">As a one-time per-solution setup, go to the **Test** menu and select **Test Settings > Default Processor Architecture > X64**.</span></span>

> [!TIP]
> <span data-ttu-id="77619-129">A definição de arquitetura de processador padrão para o Visual Studio está armazenada nas opções de solução `.suo` () ficheiro para cada solução.</span><span class="sxs-lookup"><span data-stu-id="77619-129">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="77619-130">Se eliminar este ficheiro, terá de selecionar **o X64** como arquitetura do processador novamente.</span><span class="sxs-lookup"><span data-stu-id="77619-130">If you delete this file, then you need to select **X64** as your processor architecture again.</span></span>

<span data-ttu-id="77619-131">Construa o projeto, abra o menu **Test** e selecione **Windows > Test Explorer**.</span><span class="sxs-lookup"><span data-stu-id="77619-131">Build the project, open the **Test** menu, and select **Windows > Test Explorer**.</span></span> <span data-ttu-id="77619-132">**Aloque os** ecrãs Debit na lista de testes no grupo **Testes de Não Execução.**</span><span class="sxs-lookup"><span data-stu-id="77619-132">**AllocateQubit** displays in the list of tests in the **Not Run Tests** group.</span></span> <span data-ttu-id="77619-133">Selecione **Executar Tudo** ou executar este teste individual.</span><span class="sxs-lookup"><span data-stu-id="77619-133">Select **Run All** or run this individual test.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="77619-134">Linha de Comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="77619-134">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="77619-135">Para realizar testes, navegue na pasta do projeto (a pasta que `Tests.csproj` contém), e execute o comando:</span><span class="sxs-lookup"><span data-stu-id="77619-135">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and run the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="77619-136">Deve obter uma saída semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="77619-136">You should get output similar to the following:</span></span>

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

<span data-ttu-id="77619-137">Os testes de unidade podem ser filtrados de acordo com o seu nome ou o alvo de execução:</span><span class="sxs-lookup"><span data-stu-id="77619-137">Unit tests can be filtered according to their name or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="77619-138">A função intrínseca <xref:microsoft.quantum.intrinsic.message> tem o tipo e permite a `(String -> Unit)` criação de mensagens de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="77619-138">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="77619-139">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="77619-139">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="77619-140">Depois de realizar um teste no Test Explorer e clicar no teste, um painel apresenta informações sobre a execução do teste: Estado de passagem/falha, tempo decorrido e uma ligação à saída.</span><span class="sxs-lookup"><span data-stu-id="77619-140">After you run a test in Test Explorer and click on the test, a panel displays with information about test execution: Pass/fail status, elapsed time, and a link to the output.</span></span> <span data-ttu-id="77619-141">Clique em **Saída** para abrir a saída do teste numa nova janela.</span><span class="sxs-lookup"><span data-stu-id="77619-141">Click **Output** to open the test output in a new window.</span></span>

![saída de teste](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="77619-143">Linha de Comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="77619-143">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="77619-144">O estado de passe/falha de cada teste é impresso na consola por `dotnet test` .</span><span class="sxs-lookup"><span data-stu-id="77619-144">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="77619-145">Para testes falhados, as saídas também são impressas na consola para ajudar a diagnosticar a falha.</span><span class="sxs-lookup"><span data-stu-id="77619-145">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="77619-146">Factos e Afirmações</span><span class="sxs-lookup"><span data-stu-id="77619-146">Facts and Assertions</span></span>

<span data-ttu-id="77619-147">Como as funções em Q# não têm efeitos colaterais _lógicos,_ nunca poderá observar, a partir de um programa Q#, quaisquer outros tipos de efeitos de execução de uma função cujo tipo de saída é a tuple vazia `()` .</span><span class="sxs-lookup"><span data-stu-id="77619-147">Because functions in Q# have no _logical_ side effects, you can never observe, from within a Q# program, any other kinds of effects from running a function whose output type is the empty tuple `()`.</span></span>
<span data-ttu-id="77619-148">Ou seja, uma máquina-alvo pode optar por não executar qualquer função que retorne `()` com a garantia de que esta omissão não modificará o comportamento de qualquer código Q# seguinte.</span><span class="sxs-lookup"><span data-stu-id="77619-148">That is, a target machine can choose not to run any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="77619-149">Este comportamento faz com que as funções retornem `()` (tais `Unit` como) uma ferramenta útil para incorporar afirmações e depurar lógica em programas Q#.</span><span class="sxs-lookup"><span data-stu-id="77619-149">This behavior makes functions returning `()` (such as `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="77619-150">Vamos considerar um exemplo simples:</span><span class="sxs-lookup"><span data-stu-id="77619-150">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="77619-151">Aqui, a palavra-chave `fail` indica que o cálculo não deve prosseguir, e levanta uma exceção na máquina-alvo que executa o programa Q.</span><span class="sxs-lookup"><span data-stu-id="77619-151">Here, the keyword `fail` indicates that the computation should not proceed, and raises an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="77619-152">Por definição, uma falha deste tipo não pode ser observada a partir de Q#, uma vez que a máquina-alvo já não executa o código Q# depois de alcançar uma `fail` declaração.</span><span class="sxs-lookup"><span data-stu-id="77619-152">By definition, a failure of this kind cannot be observed from within Q#, as the target machine no longer runs the Q# code after reaching a `fail` statement.</span></span>
<span data-ttu-id="77619-153">Assim, se avançarmos para além de um `PositivityFact` apelo, podemos ter a certeza de que o seu contributo foi positivo.</span><span class="sxs-lookup"><span data-stu-id="77619-153">Thus, if we proceed past a call to `PositivityFact`, we can be assured that its input was positive.</span></span>

<span data-ttu-id="77619-154">Note que podemos implementar o mesmo comportamento `PositivityFact` que usar a [`Fact`](xref:microsoft.quantum.diagnostics.fact) função a partir do espaço de <xref:microsoft.quantum.diagnostics> nomes:</span><span class="sxs-lookup"><span data-stu-id="77619-154">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="77619-155">*As afirmações*, por outro lado, são usadas da mesma forma aos factos, mas podem depender do estado da máquina-alvo.</span><span class="sxs-lookup"><span data-stu-id="77619-155">*Assertions*, on the other hand, are used similarly to facts but may depend on the state of the target machine.</span></span> <span data-ttu-id="77619-156">Consequentemente, são definidas como operações, enquanto os factos são definidos como funções (como no exemplo anterior).</span><span class="sxs-lookup"><span data-stu-id="77619-156">Correspondingly, they are defined as operations, whereas facts are defined as functions (as in the previous example).</span></span>
<span data-ttu-id="77619-157">Para compreender a distinção, considere a seguinte utilização de um facto dentro de uma afirmação:</span><span class="sxs-lookup"><span data-stu-id="77619-157">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="77619-158">Aqui, estamos a usar a operação <xref:microsoft.quantum.environment.getqubitsavailabletouse> para devolver o número de qubits disponíveis para usar.</span><span class="sxs-lookup"><span data-stu-id="77619-158">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="77619-159">Como isto depende do estado global do programa e do seu ambiente de execução, a nossa definição `AssertQubitsAreAvailable` deve ser também uma operação.</span><span class="sxs-lookup"><span data-stu-id="77619-159">As this depends on the global state of the program and its execution environment, our definition of `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="77619-160">No entanto, podemos usar esse estado global para produzir um valor simples `Bool` como entrada para a `Fact` função.</span><span class="sxs-lookup"><span data-stu-id="77619-160">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="77619-161">[O prelúdio](xref:microsoft.quantum.libraries.standard.prelude), baseado nestas ideias, oferece duas afirmações especialmente úteis, <xref:microsoft.quantum.diagnostics.assertmeasurement> e ambas <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> modeladas como operações `()` em.</span><span class="sxs-lookup"><span data-stu-id="77619-161">[The prelude](xref:microsoft.quantum.libraries.standard.prelude), building on these ideas, offers two especially useful assertions, <xref:microsoft.quantum.diagnostics.assertmeasurement> and <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> both modeled as operations onto `()`.</span></span> <span data-ttu-id="77619-162">Estas afirmações cada uma delas leva um operador Pauli descrevendo uma determinada medição de interesse, um registo quântico no qual é realizada uma medição, e um resultado hipotético.</span><span class="sxs-lookup"><span data-stu-id="77619-162">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="77619-163">As máquinas-alvo que funcionam por simulação não estão ligadas [pelo teorema da não clonagem](https://en.wikipedia.org/wiki/No-cloning_theorem), e podem efetuar tais medições sem perturbar o registo que passa para tais afirmações.</span><span class="sxs-lookup"><span data-stu-id="77619-163">Target machines which work by simulation are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register that passes to such assertions.</span></span>
<span data-ttu-id="77619-164">Um simulador pode então, semelhante à `PositivityFact` função anterior, parar a computação se o resultado hipotético não for observado na prática:</span><span class="sxs-lookup"><span data-stu-id="77619-164">A simulator can then, similar to the `PositivityFact` function previous, stop computation if the hypothetical outcome is not observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    AssertMeasurement([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="77619-165">No hardware quântico físico, onde o teorema de não clonagem impede o exame de um estado quântico, as `AssertMeasurement` `AssertMeasurementProbability` operações simplesmente regressam `()` sem outro efeito.</span><span class="sxs-lookup"><span data-stu-id="77619-165">On physical quantum hardware, where the no-cloning theorem prevents examination of a quantum state, the `AssertMeasurement` and `AssertMeasurementProbability` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="77619-166">O <xref:microsoft.quantum.diagnostics> espaço de nomes proporciona várias outras funções da família, com as `Assert` quais pode verificar condições mais avançadas.</span><span class="sxs-lookup"><span data-stu-id="77619-166">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family, with which you can check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="77619-167">Funções de despejo</span><span class="sxs-lookup"><span data-stu-id="77619-167">Dump Functions</span></span>

<span data-ttu-id="77619-168">Para ajudar a resolver os programas quânticos, o <xref:microsoft.quantum.diagnostics> espaço de nome oferece duas funções que podem despejar num ficheiro o estado atual da máquina-alvo: e <xref:microsoft.quantum.diagnostics.dumpmachine> <xref:microsoft.quantum.diagnostics.dumpregister> .</span><span class="sxs-lookup"><span data-stu-id="77619-168">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="77619-169">A saída gerada de cada uma depende da máquina-alvo.</span><span class="sxs-lookup"><span data-stu-id="77619-169">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="77619-170">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="77619-170">DumpMachine</span></span>

<span data-ttu-id="77619-171">O simulador quântico de estado completo distribuído como parte do Kit de Desenvolvimento Quântico escreve no ficheiro a [função](https://en.wikipedia.org/wiki/Wave_function) de onda de todo o sistema quântico, como uma matriz unidimensional de números complexos, em que cada elemento representa a amplitude da probabilidade de medir o estado de base computacional $\ket{n}$, onde $\ket{n} = \ket{b_{n-1}... b_1b_0}$ por bits $ \{ b_i \} $.</span><span class="sxs-lookup"><span data-stu-id="77619-171">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="77619-172">Por exemplo, numa máquina com apenas dois qubits atribuídos e no estado quântico $$ \start{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} - \frac{(1 + i)} {2} \ket, {10} \end{align} $$ chamando <xref:microsoft.quantum.diagnostics.dumpmachine> gera esta saída:</span><span class="sxs-lookup"><span data-stu-id="77619-172">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="77619-173">A primeira linha fornece um comentário com os ids dos qubits correspondentes na sua ordem significativa.</span><span class="sxs-lookup"><span data-stu-id="77619-173">The first row provides a comment with the ids of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="77619-174">As restantes linhas descrevem a amplitude de probabilidade de medir o vetor de estado base $\ket{n}$ em formatos cartesianos e polares.</span><span class="sxs-lookup"><span data-stu-id="77619-174">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="77619-175">Em detalhe para a primeira linha:</span><span class="sxs-lookup"><span data-stu-id="77619-175">In detail for the first row:</span></span>

* <span data-ttu-id="77619-176">**`∣0❭:`** esta linha corresponde ao `0` estado de base computacional</span><span class="sxs-lookup"><span data-stu-id="77619-176">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="77619-177">**`0.707107 +  0.000000 i`**: a amplitude de probabilidade no formato cartesiano.</span><span class="sxs-lookup"><span data-stu-id="77619-177">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="77619-178">**` == `**: o `equal` sinal separa ambas as representações equivalentes.</span><span class="sxs-lookup"><span data-stu-id="77619-178">**` == `**: the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="77619-179">**`**********  `**: Uma representação gráfica da magnitude, o número `*` de é proporcional à probabilidade de medir este vetor de estado.</span><span class="sxs-lookup"><span data-stu-id="77619-179">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="77619-180">**`[ 0.500000 ]`**: o valor numérico da magnitude</span><span class="sxs-lookup"><span data-stu-id="77619-180">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="77619-181">**`    ---`**: Representação gráfica da fase da amplitude (ver seguinte saída).</span><span class="sxs-lookup"><span data-stu-id="77619-181">**`    ---`**: A graphical representation of the amplitude's phase (see the following output).</span></span>
* <span data-ttu-id="77619-182">**`[ 0.0000 rad ]`**: o valor numérico da fase (em radianos).</span><span class="sxs-lookup"><span data-stu-id="77619-182">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="77619-183">Tanto a magnitude como a fase são exibidas com uma representação gráfica.</span><span class="sxs-lookup"><span data-stu-id="77619-183">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="77619-184">A representação de magnitude é direta: mostra uma barra de `*` , quanto maior for a probabilidade, maior será a fasquia.</span><span class="sxs-lookup"><span data-stu-id="77619-184">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="77619-185">Para a fase, mostramos os seguintes símbolos para representar o ângulo baseado em intervalos:</span><span class="sxs-lookup"><span data-stu-id="77619-185">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="77619-186">Os seguintes exemplos mostram `DumpMachine` alguns Estados comuns:</span><span class="sxs-lookup"><span data-stu-id="77619-186">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="77619-187">O id de um qubit é atribuído em tempo de execução e não está necessariamente alinhado com a ordem em que o qubit foi atribuído ou a sua posição dentro de um registo qubit.</span><span class="sxs-lookup"><span data-stu-id="77619-187">The id of a qubit is assigned at runtime and is not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="77619-188">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="77619-188">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="77619-189">Pode localizar um id qubit no Visual Studio colocando um ponto de rutura no seu código e inspecionando o valor de uma variável qubit, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="77619-189">You can locate a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![mostrar qubit id no Estúdio Visual](~/media/qubit_id.png)
  >
  > <span data-ttu-id="77619-191">o qubit com índice `0` em `register2` tem id= `3` , o qubit com índice tem `1` id= `2` .</span><span class="sxs-lookup"><span data-stu-id="77619-191">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="77619-192">Linha de Comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="77619-192">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="77619-193">Pode localizar um id qubit utilizando a <xref:microsoft.quantum.intrinsic.message> função e passando a variável qubit na mensagem, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="77619-193">You can locate a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="77619-194">que poderia gerar esta saída:</span><span class="sxs-lookup"><span data-stu-id="77619-194">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="77619-195">o que significa que o qubit com índice `0` em `register2` tem id= `3` , o qubit com índice tem `1` id= `2` .</span><span class="sxs-lookup"><span data-stu-id="77619-195">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="77619-196">Uma <xref:microsoft.quantum.diagnostics.dumpmachine> vez que faz parte do espaço de <xref:microsoft.quantum.diagnostics> nomes, deve adicionar uma `open` declaração para aceder a ele:</span><span class="sxs-lookup"><span data-stu-id="77619-196">Since <xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, you must add an `open` statement to access it:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="77619-197">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="77619-197">DumpRegister</span></span>

<span data-ttu-id="77619-198"><xref:microsoft.quantum.diagnostics.dumpregister>funciona como <xref:microsoft.quantum.diagnostics.dumpmachine> , exceto que também é preciso uma matriz de qubits para limitar a quantidade de informação apenas à relevante para os qubits correspondentes.</span><span class="sxs-lookup"><span data-stu-id="77619-198"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except that it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="77619-199">Tal como <xref:microsoft.quantum.diagnostics.dumpmachine> acontece, a informação gerada depende <xref:microsoft.quantum.diagnostics.dumpregister> da máquina-alvo.</span><span class="sxs-lookup"><span data-stu-id="77619-199">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="77619-200">Para o simulador quântico de estado completo, escreve no ficheiro a função de onda até uma fase global do subsistil quântico gerado pelos qubits fornecidos no mesmo formato que <xref:microsoft.quantum.diagnostics.dumpmachine> .</span><span class="sxs-lookup"><span data-stu-id="77619-200">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="77619-201">Por exemplo, tomar novamente uma máquina com apenas dois qubits atribuídos e no estado quântico $$ \start{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} - \frac{(1 + i)} {2} \ket {10} = - e^{-i\pi/4} (\frac {1} {\sqrt {2} } \ket {0} - \frac{(1 + i)} {2} {1} \ket ) \otimes \otimes \frac{-(1 + i)}{\sqrt {2} } \ket {0} ) , \end{align} $} chamando <xref:microsoft.quantum.diagnostics.dumpregister> para gerar esta `qubit[0]` saída:</span><span class="sxs-lookup"><span data-stu-id="77619-201">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="77619-202">e apelar <xref:microsoft.quantum.diagnostics.dumpregister> para `qubit[1]` gerar esta saída:</span><span class="sxs-lookup"><span data-stu-id="77619-202">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="77619-203">Em geral, o estado de um registo que está emaranhado com outro registo é um estado misto e não um estado puro.</span><span class="sxs-lookup"><span data-stu-id="77619-203">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="77619-204">Neste caso, <xref:microsoft.quantum.diagnostics.dumpregister> produz a seguinte mensagem:</span><span class="sxs-lookup"><span data-stu-id="77619-204">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="77619-205">O exemplo a seguir mostra como pode utilizar ambos <xref:microsoft.quantum.diagnostics.dumpregister> e no seu código <xref:microsoft.quantum.diagnostics.dumpmachine> Q#:</span><span class="sxs-lookup"><span data-stu-id="77619-205">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="77619-206">Depurar</span><span class="sxs-lookup"><span data-stu-id="77619-206">Debugging</span></span>

<span data-ttu-id="77619-207">Além de `Assert` `Dump` funções e operações, q# suporta um subconjunto de capacidades padrão de depuração do Estúdio Visual: [definir pontos](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)de rutura de linha, [passar pelo código usando F10,](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)e [inspecionar valores de variáveis clássicas](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) são todos possíveis durante a execução de código no simulador.</span><span class="sxs-lookup"><span data-stu-id="77619-207">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger), and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="77619-208">Depurar em Visual Studio Code aproveita as capacidades de depuração fornecidas pela extensão C# para Código de Estúdio Visual alimentada pela OmniSharp e requer a instalação da [versão mais recente](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span><span class="sxs-lookup"><span data-stu-id="77619-208">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 
