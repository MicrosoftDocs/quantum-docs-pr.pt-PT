---
title: Estimador de recursos quânticos - Kit de Desenvolvimento Quântico
description: Conheça o estimador de recursos do Microsoft QDK, que estima os recursos necessários para executar uma determinada instância de uma operação Q# num computador quântico.
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 0909a050e89d6295664e54ab63cfda5d407a8f12
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870550"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="349c9-103">Estimativa de recursos do Kit de Desenvolvimento Quântico (QDK)</span><span class="sxs-lookup"><span data-stu-id="349c9-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="349c9-104">Como o nome indica, a `ResourcesEstimator` classe estima os recursos necessários para executar uma determinada instância de uma operação Q# num computador quântico.</span><span class="sxs-lookup"><span data-stu-id="349c9-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="349c9-105">Consegue-o executando a operação quântica sem simular o estado de um computador quântico; por esta razão, estima recursos para operações Q# que usam milhares de qubits, desde que a parte clássica do código seja executado em um tempo razoável.</span><span class="sxs-lookup"><span data-stu-id="349c9-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="349c9-106">O estimador de recursos é construído em cima do simulador de [traços Quânticos,](xref:microsoft.quantum.machines.qc-trace-simulator.intro)que fornece um conjunto mais rico de métricas e ferramentas para ajudar a depurar programas Q#.</span><span class="sxs-lookup"><span data-stu-id="349c9-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="349c9-107">Invocando e executando o estimador de recursos</span><span class="sxs-lookup"><span data-stu-id="349c9-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="349c9-108">Pode utilizar o estimador de recursos para executar qualquer operação Q#.</span><span class="sxs-lookup"><span data-stu-id="349c9-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="349c9-109">Para mais detalhes, consulte [Formas de executar um programa Q#](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="349c9-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="349c9-110">Invocando o estimador de recursos de C #</span><span class="sxs-lookup"><span data-stu-id="349c9-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="349c9-111">Tal como acontece com outras máquinas-alvo, cria-se primeiro uma instância da `ResourceEstimator` classe e depois passa-a como o primeiro parâmetro do método de uma `Run` operação.</span><span class="sxs-lookup"><span data-stu-id="349c9-111">As with other target machines, you first create an instance of the `ResourceEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="349c9-112">Note que, ao contrário da `QuantumSimulator` classe, a `ResourceEstimator` classe não implementa a <xref:System.IDisposable> interface, pelo que não precisa de a incluir dentro de um `using` comunicado.</span><span class="sxs-lookup"><span data-stu-id="349c9-112">Note that, unlike the `QuantumSimulator` class, the `ResourceEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

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

<span data-ttu-id="349c9-113">Como mostra o exemplo, `ResourcesEstimator` fornece o `ToTSV()` método, que gera uma tabela com valores separados por separados por separados (TSV).</span><span class="sxs-lookup"><span data-stu-id="349c9-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="349c9-114">Pode guardar a tabela para um ficheiro ou exibi-la na consola para análise.</span><span class="sxs-lookup"><span data-stu-id="349c9-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="349c9-115">Segue-se uma amostra do programa anterior:</span><span class="sxs-lookup"><span data-stu-id="349c9-115">The following is a sample output from the preceding program:</span></span>

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
> <span data-ttu-id="349c9-116">Um `ResourcesEstimator` caso não repõe os seus cálculos em cada corrida.</span><span class="sxs-lookup"><span data-stu-id="349c9-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="349c9-117">Se utilizar o mesmo caso para executar outra operação, agrega os novos resultados com os resultados existentes.</span><span class="sxs-lookup"><span data-stu-id="349c9-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="349c9-118">Se precisar de redefinir os cálculos entre as execuções, crie uma nova instância para cada execução.</span><span class="sxs-lookup"><span data-stu-id="349c9-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="349c9-119">Invocando o estimador de recursos da Python</span><span class="sxs-lookup"><span data-stu-id="349c9-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="349c9-120">Utilize o método [estimate_resources()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) da biblioteca Python com a operação Q# importada:</span><span class="sxs-lookup"><span data-stu-id="349c9-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="349c9-121">Invocando o estimador de recursos da linha de comando</span><span class="sxs-lookup"><span data-stu-id="349c9-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="349c9-122">Quando executar um programa Q# a partir da linha de comando, utilize o parâmetro **simulador** (ou **atalho -s** para especificar a `ResourcesEstimator` máquina-alvo.</span><span class="sxs-lookup"><span data-stu-id="349c9-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="349c9-123">O seguinte comando executa um programa utilizando o estimador de recursos:</span><span class="sxs-lookup"><span data-stu-id="349c9-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="349c9-124">Invocando o estimador de recursos dos Cadernos Juptyer</span><span class="sxs-lookup"><span data-stu-id="349c9-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="349c9-125">Utilize o comando mágico IQ# [%estimativa](xref:microsoft.quantum.iqsharp.magic-ref.simulate) para executar a operação Q#.</span><span class="sxs-lookup"><span data-stu-id="349c9-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="349c9-126">Recuperação programática dos dados estimados</span><span class="sxs-lookup"><span data-stu-id="349c9-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="349c9-127">Além de uma tabela de TSV, pode recuperar programáticamente os recursos estimados durante a execução através da `Data` propriedade do estimador de recursos.</span><span class="sxs-lookup"><span data-stu-id="349c9-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="349c9-128">A `Data` propriedade fornece um exemplo com `System.DataTable` duas colunas: `Metric` `Sum` e, indexada pelos nomes das métricas.</span><span class="sxs-lookup"><span data-stu-id="349c9-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="349c9-129">O seguinte código mostra como recuperar e imprimir o número total de `QubitClifford` , `T` e `CNOT` operações utilizadas por uma operação Q#:</span><span class="sxs-lookup"><span data-stu-id="349c9-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="349c9-130">Métricas Reportadas</span><span class="sxs-lookup"><span data-stu-id="349c9-130">Metrics Reported</span></span>

<span data-ttu-id="349c9-131">O estimador de recursos acompanha as seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="349c9-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="349c9-132">Métrica</span><span class="sxs-lookup"><span data-stu-id="349c9-132">Metric</span></span>|<span data-ttu-id="349c9-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="349c9-133">Description</span></span>|
|----|----|
|<span data-ttu-id="349c9-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="349c9-134">__CNOT__</span></span>    |<span data-ttu-id="349c9-135">A contagem de `CNOT` operações (também conhecida como operações controladas pauli X).</span><span class="sxs-lookup"><span data-stu-id="349c9-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="349c9-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="349c9-136">__QubitClifford__</span></span> |<span data-ttu-id="349c9-137">A contagem de qualquer qubit de operações de Clifford e Pauli.</span><span class="sxs-lookup"><span data-stu-id="349c9-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="349c9-138">__Medida__</span><span class="sxs-lookup"><span data-stu-id="349c9-138">__Measure__</span></span>    |<span data-ttu-id="349c9-139">A contagem de quaisquer medições.</span><span class="sxs-lookup"><span data-stu-id="349c9-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="349c9-140">__R__</span><span class="sxs-lookup"><span data-stu-id="349c9-140">__R__</span></span>    |<span data-ttu-id="349c9-141">A contagem de quaisquer rotações de um único qubit, `T` excluindo, operações Clifford e Pauli.</span><span class="sxs-lookup"><span data-stu-id="349c9-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="349c9-142">__T__</span><span class="sxs-lookup"><span data-stu-id="349c9-142">__T__</span></span>    |<span data-ttu-id="349c9-143">A contagem de `T` operações e seus conjugatos, incluindo as `T` operações, T_x = H.T.H, e T_y = Hy.T.Hy.</span><span class="sxs-lookup"><span data-stu-id="349c9-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="349c9-144">__Profundidade__</span><span class="sxs-lookup"><span data-stu-id="349c9-144">__Depth__</span></span>|<span data-ttu-id="349c9-145">O limite inferior para a profundidade do circuito quântico executado pela operação Q#.</span><span class="sxs-lookup"><span data-stu-id="349c9-145">The lower bound for the depth of the quantum circuit run by the Q# operation.</span></span> <span data-ttu-id="349c9-146">Por predefinição, a métrica de profundidade apenas conta `T` portões.</span><span class="sxs-lookup"><span data-stu-id="349c9-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="349c9-147">Para mais detalhes, consulte [o Contador de Profundidade.](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)</span><span class="sxs-lookup"><span data-stu-id="349c9-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="349c9-148">__Width__</span><span class="sxs-lookup"><span data-stu-id="349c9-148">__Width__</span></span>    |<span data-ttu-id="349c9-149">O limite inferior para o número máximo de qubits atribuídos durante o funcionamento da operação Q#.</span><span class="sxs-lookup"><span data-stu-id="349c9-149">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="349c9-150">Pode não ser possível atingir simultaneamente os limites mais baixos de __profundidade__ e __largura.__</span><span class="sxs-lookup"><span data-stu-id="349c9-150">It might not be possible to achieve both __Depth__ and __Width__ lower bounds simultaneously.</span></span>  |
|<span data-ttu-id="349c9-151">__Largura emprestada__</span><span class="sxs-lookup"><span data-stu-id="349c9-151">__BorrowedWidth__</span></span>    |<span data-ttu-id="349c9-152">O número máximo de qubits emprestados dentro da operação Q#.</span><span class="sxs-lookup"><span data-stu-id="349c9-152">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="349c9-153">Fornecendo a probabilidade de resultados de medição</span><span class="sxs-lookup"><span data-stu-id="349c9-153">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="349c9-154">Pode utilizar <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> a partir do espaço de nome para fornecer <xref:microsoft.quantum.diagnostics> informações sobre a probabilidade esperada de uma operação de medição.</span><span class="sxs-lookup"><span data-stu-id="349c9-154">You can use <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> from the <xref:microsoft.quantum.diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="349c9-155">Para mais informações, consulte [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="349c9-155">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="349c9-156">Ver também</span><span class="sxs-lookup"><span data-stu-id="349c9-156">See also</span></span>

- [<span data-ttu-id="349c9-157">Simulador de vestígios quânticos</span><span class="sxs-lookup"><span data-stu-id="349c9-157">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="349c9-158">Simulador Quantum Toffoli</span><span class="sxs-lookup"><span data-stu-id="349c9-158">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="349c9-159">Simulador de estado completo quântico</span><span class="sxs-lookup"><span data-stu-id="349c9-159">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 