---
title: Estimador de recursos do kit de desenvolvimento Quantum | Microsoft Docs
description: Visão geral do estimador de recursos do kit de desenvolvimento Quantum da Microsoft
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 591e306b3001934bd81342a533e3f6ca25129781
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184989"
---
# <a name="the-resourcesestimator-target-machine"></a><span data-ttu-id="a35b7-103">O computador de destino ResourcesEstimator</span><span class="sxs-lookup"><span data-stu-id="a35b7-103">The ResourcesEstimator Target Machine</span></span>

<span data-ttu-id="a35b7-104">Como o nome indica, o `ResourcesEstimator` estima os recursos necessários para executar uma determinada instância de uma operação Q # em um computador Quantum.</span><span class="sxs-lookup"><span data-stu-id="a35b7-104">As the name implies, the `ResourcesEstimator` estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>
<span data-ttu-id="a35b7-105">Ele realiza isso executando a operação Quantum sem realmente simular o estado de um computador Quantum; por esse motivo, ele pode estimar recursos para operações Q # que usam milhares de qubits.</span><span class="sxs-lookup"><span data-stu-id="a35b7-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it can estimate resources for Q# operations that use thousands of qubits.</span></span>

## <a name="usage"></a><span data-ttu-id="a35b7-106">Utilização</span><span class="sxs-lookup"><span data-stu-id="a35b7-106">Usage</span></span>

<span data-ttu-id="a35b7-107">O `ResourcesEstimator` é apenas outro tipo de computador de destino, portanto, ele pode ser usado para executar qualquer operação Q #.</span><span class="sxs-lookup"><span data-stu-id="a35b7-107">The `ResourcesEstimator` is just another type of target machine, thus it can be used to run any Q# operation.</span></span> 

<span data-ttu-id="a35b7-108">Como outros computadores de destino, para usá-lo C# em um programa de host, crie uma instância e passe-a como o primeiro parâmetro do método de `Run` da operação:</span><span class="sxs-lookup"><span data-stu-id="a35b7-108">As other target machines, to use it on a C# host program create an instance and pass it as the first parameter of the operation's `Run` method:</span></span>

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

<span data-ttu-id="a35b7-109">Como mostra o exemplo, o `ResourcesEstimator` fornece um método `ToTSV()` para gerar uma tabela com TSV (valores separados por tabulação) que podem ser salvos em um arquivo ou gravados no console para análise.</span><span class="sxs-lookup"><span data-stu-id="a35b7-109">As the example shows, the `ResourcesEstimator` provides a `ToTSV()` method to generate a table with tab-seperated-values (TSV) that can be saved into a file or written to the console for analysis.</span></span> <span data-ttu-id="a35b7-110">A saída do programa acima deve ser semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="a35b7-110">The output of the above program should look something like this:</span></span>

```Output
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
> <span data-ttu-id="a35b7-111">O `ResourcesEstimator` não redefine seus cálculos em todas as execuções, se a mesma instância for usada para executar outra operação, ele continuará agregando contagens sobre os resultados existentes.</span><span class="sxs-lookup"><span data-stu-id="a35b7-111">The `ResourcesEstimator` does not reset its calculations on every run, if the same instance is used to execute another operation it will keep aggregating counts on top of existing results.</span></span>
> <span data-ttu-id="a35b7-112">Se você precisar redefinir cálculos entre execuções, crie uma nova instância para cada execução.</span><span class="sxs-lookup"><span data-stu-id="a35b7-112">If you need to reset calculations between runs, create a new instance for every execution.</span></span>


## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="a35b7-113">Recuperando programaticamente os dados estimados</span><span class="sxs-lookup"><span data-stu-id="a35b7-113">Programmatically Retrieving the Estimated Data</span></span>

<span data-ttu-id="a35b7-114">Além de uma tabela TSV, os recursos estimados podem ser recuperados programaticamente por meio da propriedade `Data` do `ResourcesEstimator`.</span><span class="sxs-lookup"><span data-stu-id="a35b7-114">In addition to a TSV table, the resources estimated can be retrieved programmatically via the `ResourcesEstimator`'s `Data` property.</span></span> <span data-ttu-id="a35b7-115">`Data` fornece uma instância de `System.DataTable` com duas colunas: `Metric` e `Sum`, indexadas pelos nomes de métricas.</span><span class="sxs-lookup"><span data-stu-id="a35b7-115">`Data` provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics names.</span></span>

<span data-ttu-id="a35b7-116">O código a seguir mostra como recuperar e imprimir o número total de `QubitClifford`, `T` e `CNOT` Gates usados por uma operação Q #:</span><span class="sxs-lookup"><span data-stu-id="a35b7-116">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` gates used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="a35b7-117">Métricas relatadas</span><span class="sxs-lookup"><span data-stu-id="a35b7-117">Metrics Reported</span></span>

<span data-ttu-id="a35b7-118">A seguir está a lista de métricas estimadas pelo `ResourcesEstimator`:</span><span class="sxs-lookup"><span data-stu-id="a35b7-118">The following is the list of metrics estimated by the `ResourcesEstimator`:</span></span>

* <span data-ttu-id="a35b7-119">__CNOT__: a contagem de CNOT (também conhecida como a porta controlada de Pauli X) de Gates executada.</span><span class="sxs-lookup"><span data-stu-id="a35b7-119">__CNOT__: The count of CNOT (also known as the Controlled Pauli X gate) gates executed.</span></span>
* <span data-ttu-id="a35b7-120">__QubitClifford__: a contagem de uma única qubit Clifford e Pauli Gates executadas.</span><span class="sxs-lookup"><span data-stu-id="a35b7-120">__QubitClifford__: The count of any single qubit Clifford and Pauli gates executed.</span></span>
* <span data-ttu-id="a35b7-121">__Medida__: a contagem de qualquer medida executada.</span><span class="sxs-lookup"><span data-stu-id="a35b7-121">__Measure__:  The count of any measurements executed.</span></span>
* <span data-ttu-id="a35b7-122">__R__: a contagem de qualquer rotação qubit única executada, excluindo T, Clifford e Pauli Gates.</span><span class="sxs-lookup"><span data-stu-id="a35b7-122">__R__: The count of any single qubit rotations executed, excluding T, Clifford and Pauli gates.</span></span>
* <span data-ttu-id="a35b7-123">__T__: a contagem de t Gates e seus conjugados, incluindo o t Gate, T_x = h. T. H e T_y = hipótese. T. hipótese, executado.</span><span class="sxs-lookup"><span data-stu-id="a35b7-123">__T__: The count of T gates and their conjugates, including the T gate, T_x = H.T.H, and T_y = Hy.T.Hy, executed.</span></span>
* <span data-ttu-id="a35b7-124">__Profundidade__: profundidade do circuito Quantum executado pela operação Q #.</span><span class="sxs-lookup"><span data-stu-id="a35b7-124">__Depth__: Depth of the quantum circuit executed by the Q# operation.</span></span> <span data-ttu-id="a35b7-125">Por padrão, somente T Gates são contadas na profundidade, consulte o [contador de profundidade](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="a35b7-125">By default, only T gates are counted in the depth, see [depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) for details.</span></span>
* <span data-ttu-id="a35b7-126">__Largura__: o número máximo de qubits alocadas durante a execução da operação Q #.</span><span class="sxs-lookup"><span data-stu-id="a35b7-126">__Width__: Maximum number of qubits allocated during the execution of the Q# operation.</span></span>
* <span data-ttu-id="a35b7-127">__BorrowedWidth__: número máximo de qubits emprestados dentro da operação Q #.</span><span class="sxs-lookup"><span data-stu-id="a35b7-127">__BorrowedWidth__: Maximum number of qubits borrowed inside the Q# operation.</span></span>


## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="a35b7-128">Fornecendo a probabilidade de resultados de medida</span><span class="sxs-lookup"><span data-stu-id="a35b7-128">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="a35b7-129"><xref:microsoft.quantum.primitive.assertprob> do namespace <xref:microsoft.quantum.primitive> pode ser usado para fornecer informações sobre a probabilidade esperada de uma medida para ajudar a conduzir a execução do programa Q #.</span><span class="sxs-lookup"><span data-stu-id="a35b7-129"><xref:microsoft.quantum.primitive.assertprob> from the <xref:microsoft.quantum.primitive> namespace can be used to provide information about the expected probability of a measurement to help drive the execution of the Q# program.</span></span> <span data-ttu-id="a35b7-130">O exemplo a seguir ilustra isso:</span><span class="sxs-lookup"><span data-stu-id="a35b7-130">The following example illustrates this:</span></span>

```qsharp
operation Teleportation (source : Qubit, target : Qubit) : Unit {

    using (ancilla = Qubit()) {

        H(ancilla);
        CNOT(ancilla, target);

        CNOT(source, ancilla);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [ancilla], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(ancilla) == One) { X(target); X(ancilla); }
    }
}
```

<span data-ttu-id="a35b7-131">Quando o `ResourcesEstimator` encontrar `AssertProb` ele gravará que medir `PauliZ` em `source` e `ancilla` deverá receber um resultado de `Zero` com a probabilidade 0,5.</span><span class="sxs-lookup"><span data-stu-id="a35b7-131">When the `ResourcesEstimator` encounters `AssertProb` it will record that measuring `PauliZ` on `source` and `ancilla` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="a35b7-132">Quando ele for executado `M` mais tarde, ele encontrará os valores gravados das probabilidades de resultado e `M` retornará `Zero` ou `One` com a probabilidade 0,5.</span><span class="sxs-lookup"><span data-stu-id="a35b7-132">When it executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span>


## <a name="see-also"></a><span data-ttu-id="a35b7-133">Ver também</span><span class="sxs-lookup"><span data-stu-id="a35b7-133">See also</span></span>

<span data-ttu-id="a35b7-134">O `ResourcesEstimator` é criado sobre o [simulador de rastreamento](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de computador Quantum, que fornece um conjunto mais rico de métricas, a capacidade de relatar métricas no grafo de Call completo e recursos como o [Verificador de entradas distintos](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) para ajudar a encontrar bugs em programas de Q #.</span><span class="sxs-lookup"><span data-stu-id="a35b7-134">The `ResourcesEstimator` is built on top of the quantum computer [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics, the ability to report metrics on the full call-graph, and features like [distinct inputs checker](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) to help find bugs on Q# programs.</span></span> <span data-ttu-id="a35b7-135">Consulte a documentação do [simulador de rastreamento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a35b7-135">Please refer to the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) documentation for more information.</span></span>

