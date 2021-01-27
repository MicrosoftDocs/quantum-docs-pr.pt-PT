---
title: Estimador de recursos quânticos - Kit de Desenvolvimento Quântico
description: Conheça o estimador de recursos da Microsoft QDK, que estima os recursos necessários para executar uma determinada instância de uma Q# operação num computador quântico.
author: anpaz
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: c3aa94c8b34ad7247fbdeab4bf4dcb96ce746014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847469"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="7a7aa-103">Estimativa de recursos do Kit de Desenvolvimento Quântico (QDK)</span><span class="sxs-lookup"><span data-stu-id="7a7aa-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="7a7aa-104">Como o nome indica, a `ResourcesEstimator` classe estima os recursos necessários para executar uma determinada instância de uma Q# operação num computador quântico.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="7a7aa-105">Consegue-o executando a operação quântica sem simular o estado de um computador quântico; por esta razão, estima recursos para Q# operações que utilizam milhares de qubits, desde que a parte clássica do código seja executado num prazo razoável.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-105">It accomplishes this by running the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="7a7aa-106">O estimador de recursos é construído em cima do simulador de [traços Quânticos,](xref:microsoft.quantum.machines.qc-trace-simulator.intro)que fornece um conjunto mais rico de métricas e ferramentas para ajudar a Q# depurar programas.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="7a7aa-107">Invocando e executando o estimador de recursos</span><span class="sxs-lookup"><span data-stu-id="7a7aa-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="7a7aa-108">Pode utilizar o estimador de recursos para executar qualquer Q# operação.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="7a7aa-109">Para mais detalhes, consulte [Formas de executar um Q# programa](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="7a7aa-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="7a7aa-110">Invocando o estimador de recursos de C #</span><span class="sxs-lookup"><span data-stu-id="7a7aa-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="7a7aa-111">Tal como sucede com outros computadores de destino, vai criar primeiro uma instância da classe `ResourcesEstimator` e, depois, transmiti-la como o primeiro parâmetro do método `Run` de uma operação.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-111">As with other target machines, you first create an instance of the `ResourcesEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="7a7aa-112">Tenha em conta que, ao contrário da classe `QuantumSimulator`, a classe `ResourcesEstimator` não implementa a interface <xref:System.IDisposable>, pelo que não precisa de a incluir dentro de uma instrução `using`.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-112">Note that, unlike the `QuantumSimulator` class, the `ResourcesEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();
            Console.WriteLine(estimator.ToTSV());
        }
    }
}
```

<span data-ttu-id="7a7aa-113">Como mostra o exemplo, `ResourcesEstimator` fornece o `ToTSV()` método, que gera uma tabela com valores separados por separados por separados (TSV).</span><span class="sxs-lookup"><span data-stu-id="7a7aa-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="7a7aa-114">Pode guardar a tabela para um ficheiro ou exibi-la na consola para análise.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="7a7aa-115">Segue-se uma amostra do programa anterior:</span><span class="sxs-lookup"><span data-stu-id="7a7aa-115">The following is a sample output from the preceding program:</span></span>

```output
Metric          Sum
CNOT            1000
QubitClifford   1000
R               0
Measure         4002
T               0
Depth           0
Width           2
BorrowedWidth   0
```

> [!NOTE]
> <span data-ttu-id="7a7aa-116">Um `ResourcesEstimator` caso não repõe os seus cálculos em cada corrida.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="7a7aa-117">Se utilizar o mesmo caso para executar outra operação, agrega os novos resultados com os resultados existentes.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="7a7aa-118">Se precisar de redefinir os cálculos entre as execuções, crie uma nova instância para cada execução.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="7a7aa-119">Invocando o estimador de recursos da Python</span><span class="sxs-lookup"><span data-stu-id="7a7aa-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="7a7aa-120">Utilizar o método [estimate_resources da](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) biblioteca Python com a operação Q# importada:</span><span class="sxs-lookup"><span data-stu-id="7a7aa-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="7a7aa-121">Invocando o estimador de recursos da linha de comando</span><span class="sxs-lookup"><span data-stu-id="7a7aa-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="7a7aa-122">Ao executar um Q# programa a partir da linha de comando, utilize o parâmetro **-simulador** (ou **atalho -s** para especificar a `ResourcesEstimator` máquina-alvo.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="7a7aa-123">O seguinte comando executa um programa utilizando o estimador de recursos:</span><span class="sxs-lookup"><span data-stu-id="7a7aa-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="7a7aa-124">Invocando o estimador de recursos dos Cadernos Juptyer</span><span class="sxs-lookup"><span data-stu-id="7a7aa-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="7a7aa-125">Use o comando mágico I Q# [%estimativa](xref:microsoft.quantum.iqsharp.magic-ref.simulate) para executar a Q# operação.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="7a7aa-126">Recuperação programática dos dados estimados</span><span class="sxs-lookup"><span data-stu-id="7a7aa-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="7a7aa-127">Além de uma tabela de TSV, pode recuperar programáticamente os recursos estimados durante a execução através da `Data` propriedade do estimador de recursos.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="7a7aa-128">A `Data` propriedade fornece um exemplo com `System.DataTable` duas colunas: `Metric` `Sum` e, indexada pelos nomes das métricas.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="7a7aa-129">O seguinte código mostra como recuperar e imprimir o número total `QubitClifford` de, `T` e `CNOT` operações utilizadas por uma Q# operação:</span><span class="sxs-lookup"><span data-stu-id="7a7aa-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();

            var data = estimator.Data;
            Console.WriteLine($"QubitCliffords: {data.Rows.Find("QubitClifford")["Sum"]}");
            Console.WriteLine($"Ts: {data.Rows.Find("T")["Sum"]}");
            Console.WriteLine($"CNOTs: {data.Rows.Find("CNOT")["Sum"]}");
        }
    }
}
```

## <a name="metrics-reported"></a><span data-ttu-id="7a7aa-130">Métricas Reportadas</span><span class="sxs-lookup"><span data-stu-id="7a7aa-130">Metrics Reported</span></span>

<span data-ttu-id="7a7aa-131">O estimador de recursos acompanha as seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="7a7aa-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="7a7aa-132">Metric</span><span class="sxs-lookup"><span data-stu-id="7a7aa-132">Metric</span></span>|<span data-ttu-id="7a7aa-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="7a7aa-133">Description</span></span>|
|----|----|
|<span data-ttu-id="7a7aa-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="7a7aa-134">__CNOT__</span></span>    |<span data-ttu-id="7a7aa-135">A contagem de `CNOT` operações (também conhecida como operações controladas pauli X).</span><span class="sxs-lookup"><span data-stu-id="7a7aa-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="7a7aa-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="7a7aa-136">__QubitClifford__</span></span> |<span data-ttu-id="7a7aa-137">A contagem de qualquer qubit de operações de Clifford e Pauli.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="7a7aa-138">__Medir__</span><span class="sxs-lookup"><span data-stu-id="7a7aa-138">__Measure__</span></span>    |<span data-ttu-id="7a7aa-139">A contagem de quaisquer medições.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="7a7aa-140">__R__</span><span class="sxs-lookup"><span data-stu-id="7a7aa-140">__R__</span></span>    |<span data-ttu-id="7a7aa-141">A contagem de quaisquer rotações de um único qubit, `T` excluindo, operações Clifford e Pauli.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="7a7aa-142">__T__</span><span class="sxs-lookup"><span data-stu-id="7a7aa-142">__T__</span></span>    |<span data-ttu-id="7a7aa-143">A contagem de `T` operações e seus conjugatos, incluindo as `T` operações, T_x = H.T.H, e T_y = Hy.T.Hy.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="7a7aa-144">__Profundidade__</span><span class="sxs-lookup"><span data-stu-id="7a7aa-144">__Depth__</span></span>|<span data-ttu-id="7a7aa-145">Profundidade do circuito quântico executado pela Q# operação (ver [abaixo](#depth-width-and-qubitcount)).</span><span class="sxs-lookup"><span data-stu-id="7a7aa-145">Depth of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="7a7aa-146">Por predefinição, a métrica de profundidade apenas conta `T` portões.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="7a7aa-147">Para mais detalhes, consulte [o Contador de Profundidade.](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)</span><span class="sxs-lookup"><span data-stu-id="7a7aa-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="7a7aa-148">__Width__</span><span class="sxs-lookup"><span data-stu-id="7a7aa-148">__Width__</span></span>|<span data-ttu-id="7a7aa-149">Largura do circuito quântico executado pela Q# operação (ver [abaixo](#depth-width-and-qubitcount)).</span><span class="sxs-lookup"><span data-stu-id="7a7aa-149">Width of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="7a7aa-150">Por predefinição, a métrica de profundidade apenas conta `T` portões.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-150">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="7a7aa-151">Para mais detalhes, consulte [o Contador de Largura](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span><span class="sxs-lookup"><span data-stu-id="7a7aa-151">For more details, see [Width Counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span></span>   |
|<span data-ttu-id="7a7aa-152">__QubitCount__</span><span class="sxs-lookup"><span data-stu-id="7a7aa-152">__QubitCount__</span></span>    |<span data-ttu-id="7a7aa-153">O limite inferior para o número máximo de qubits atribuídos durante o Q# funcionamento.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-153">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="7a7aa-154">Esta métrica pode não ser compatível com __profundidade__ (ver abaixo).</span><span class="sxs-lookup"><span data-stu-id="7a7aa-154">This metric might not be compatible with __Depth__ (see below).</span></span>  |
|<span data-ttu-id="7a7aa-155">__Largura emprestada__</span><span class="sxs-lookup"><span data-stu-id="7a7aa-155">__BorrowedWidth__</span></span>    |<span data-ttu-id="7a7aa-156">O número máximo de qubits emprestados dentro da Q# operação.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-156">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |


## <a name="depth-width-and-qubitcount"></a><span data-ttu-id="7a7aa-157">Profundidade, Largura e QubitCount</span><span class="sxs-lookup"><span data-stu-id="7a7aa-157">Depth, Width, and QubitCount</span></span>

<span data-ttu-id="7a7aa-158">As estimativas reportadas de profundidade e largura são compatíveis entre si.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-158">Reported Depth and Width estimates are compatible with each other.</span></span>
<span data-ttu-id="7a7aa-159">(Anteriormente, ambos os números eram alcançáveis, mas seriam necessários circuitos diferentes para profundidade e largura.) Atualmente ambas as métricas deste par podem ser alcançadas pelo mesmo circuito ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-159">(Previously both numbers were achievable, but different circuits would be required for Depth and for Width.) Currently both metrics in this pair can be achieved by the same circuit at the same time.</span></span>

<span data-ttu-id="7a7aa-160">São reportadas as seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="7a7aa-160">The following metrics are reported:</span></span>

<span data-ttu-id="7a7aa-161">__Profundidade:__ Para a operação raiz - o tempo leva para executá-lo assumindo os tempos de portão configurados.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-161">__Depth:__ For the root operation - time it takes to execute it assuming configured gate times.</span></span>
<span data-ttu-id="7a7aa-162">Para operações chamadas ou operações subsequentes - diferença de tempo entre o último tempo de disponibilidade de qubit no início e o final da operação.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-162">For operations called or subsequent operations - time difference between the latest qubit availability time at the beginning and the end of the operation.</span></span>

<span data-ttu-id="7a7aa-163">__Largura:__ Para a operação raiz - número de qubits realmente utilizados para executá-lo (e operação que chama).</span><span class="sxs-lookup"><span data-stu-id="7a7aa-163">__Width:__ For the root operation - number of qubits actually used to execute it (and operation it calls).</span></span>
<span data-ttu-id="7a7aa-164">Para operações convocadas ou operações subsequentes - quantos mais qubits foram utilizados para além dos qubits já utilizados no início da operação.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-164">For operations called or subsequent operations - how many more qubits were used in addition to the qubits already used at the beginning of the operation.</span></span>

<span data-ttu-id="7a7aa-165">Por favor, note que os qubits reutilizados não contribuem para este número.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-165">Please note, that reused qubits do not contribute to this number.</span></span>
<span data-ttu-id="7a7aa-166">Ou seja, se alguns qubits foram lançados antes do início da operação A, e todos os qubits exigidos por esta operação A (e operações chamadas a partir de A) foram satisfeitos com a reutilização de qubits previamente lançados, a largura da operação A é reportada como 0.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-166">I.e. if a few qubits have been released before operation A starts, and all qubit demanded by this operation A (and operations called from A) were satisfied by reusing previously release qubits, the Width of operation A is reported as 0.</span></span> <span data-ttu-id="7a7aa-167">Os qubits emprestados com sucesso também não contribuem para a Largura.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-167">Successfully borrowed qubits do not contribute to the Width either.</span></span>

<span data-ttu-id="7a7aa-168">__QubitCount:__ Para a operação raiz - número mínimo de qubits que seriam suficientes para executar esta operação (e operações chamadas a partir dela).</span><span class="sxs-lookup"><span data-stu-id="7a7aa-168">__QubitCount:__ For the root operation - minimum number of qubits that would be sufficient to execute this operation (and operations called from it).</span></span>
<span data-ttu-id="7a7aa-169">Para operações chamadas ou operações subsequentes - número mínimo de qubits que seriam suficientes para executar esta operação separadamente.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-169">For operations called or subsequent operations - minimum number of qubits that would be sufficient to execute this operation separately.</span></span> <span data-ttu-id="7a7aa-170">Este número não inclui qubits de entrada.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-170">This number doesn't include input qubits.</span></span> <span data-ttu-id="7a7aa-171">Inclui qubits emprestados.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-171">It does include borrowed qubits.</span></span>

<span data-ttu-id="7a7aa-172">Dois modos de funcionamento são suportados.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-172">Two modes of operation are supported.</span></span> <span data-ttu-id="7a7aa-173">O modo é selecionado definindo QCTraceSimulatorConfiguration.OptimizeDepth.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-173">Mode is selected by setting QCTraceSimulatorConfiguration.OptimizeDepth.</span></span>

<span data-ttu-id="7a7aa-174">__OptimizeDepth=falso:__ Este é o modo predefinido.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-174">__OptimizeDepth=false:__ This is the default mode.</span></span> <span data-ttu-id="7a7aa-175">QubitManager é encorajado a reutilizar qubits e reutilizar os qubits libertados antes de alocar novos.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-175">QubitManager is encouraged to reuse qubits and will reuse released qubits before allocating new ones.</span></span> <span data-ttu-id="7a7aa-176">Para a operação raiz __A largura__ torna-se a largura mínima (limite inferior).</span><span class="sxs-lookup"><span data-stu-id="7a7aa-176">For the root operation __Width__ becomes the minimal width (lower bound).</span></span> <span data-ttu-id="7a7aa-177">É reportada __profundidade__ compatível na qual pode ser alcançado.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-177">Compatible __Depth__ is reported on which it can be achieved.</span></span> <span data-ttu-id="7a7aa-178">__QubitCount__ será o mesmo __que width__ para a operação raiz assumindo que não há empréstimos.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-178">__QubitCount__ will be the same as __Width__ for the root operation assuming no borrowing.</span></span>

<span data-ttu-id="7a7aa-179">__OptimizeDepth=verdade:__ QubitManager é desencorajado da reutilização de qubits e a otimização baseada em heurística para a reutilização de qubits é realizada durante e após a execução.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-179">__OptimizeDepth=true:__ QubitManager is discouraged from qubit reuse and heuristic-based optimization for qubit reuse is performed during and after execution.</span></span> <span data-ttu-id="7a7aa-180">Para a operação raiz __A profundidade__ torna-se a profundidade mínima (limite inferior).</span><span class="sxs-lookup"><span data-stu-id="7a7aa-180">For the root operation __Depth__ becomes the minimum depth (lower bound).</span></span> <span data-ttu-id="7a7aa-181">A __largura__ compatível é reportada para esta profundidade (ambas podem ser alcançadas ao mesmo tempo).</span><span class="sxs-lookup"><span data-stu-id="7a7aa-181">Compatible __Width__ is reported for this depth (both can be achieved at the same time).</span></span> <span data-ttu-id="7a7aa-182">Para otimizar a largura, os portões encontrados mais tarde no programa podem ser agendados antes dos portões encontrados no início do programa, mas os qubits estão programados para serem reutilizados de forma a que a profundidade permaneça mínima.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-182">To optimize width, gates encountered later in the program may be scheduled before the gates encountered earlier in the program, but qubits are scheduled to be reused in such a way that the depth remains minimal.</span></span> <span data-ttu-id="7a7aa-183">Uma vez que os qubits são reutilizados com base nos valores do tempo, recomenda-se que os tempos do portão sejam configurados para serem valores inteiros.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-183">As qubits are reused based on time values, it is recommended that the gate times are configured to be integer values.</span></span> <span data-ttu-id="7a7aa-184">__A largura__ não é garantida para ser o ideal.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-184">__Width__ is not guaranteed to be optimal.</span></span> <span data-ttu-id="7a7aa-185">Mais informações podem ser encontradas no papel branco [Largura e Profundidade no Tracer](https://github.com/microsoft/qsharp-runtime/tree/main/src/Simulation/Simulators/QCTraceSimulator/Docs).</span><span class="sxs-lookup"><span data-stu-id="7a7aa-185">More information can be found in the whitepaper [Width and Depth in the Tracer](https://github.com/microsoft/qsharp-runtime/tree/main/src/Simulation/Simulators/QCTraceSimulator/Docs).</span></span>

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="7a7aa-186">Fornecer a probabilidade de resultados de medições</span><span class="sxs-lookup"><span data-stu-id="7a7aa-186">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="7a7aa-187">Pode utilizar <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> a partir do espaço de nome para fornecer <xref:Microsoft.Quantum.Diagnostics> informações sobre a probabilidade esperada de uma operação de medição.</span><span class="sxs-lookup"><span data-stu-id="7a7aa-187">You can use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> from the <xref:Microsoft.Quantum.Diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="7a7aa-188">Para mais informações, consulte [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="7a7aa-188">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="7a7aa-189">Veja também</span><span class="sxs-lookup"><span data-stu-id="7a7aa-189">See also</span></span>

- [<span data-ttu-id="7a7aa-190">Simulador de vestígios quânticos</span><span class="sxs-lookup"><span data-stu-id="7a7aa-190">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="7a7aa-191">Simulador Toffoli quântico</span><span class="sxs-lookup"><span data-stu-id="7a7aa-191">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="7a7aa-192">Simulador de estado completo quântico</span><span class="sxs-lookup"><span data-stu-id="7a7aa-192">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 
