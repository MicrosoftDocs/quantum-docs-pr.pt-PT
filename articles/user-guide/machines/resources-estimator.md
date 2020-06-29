---
title: Estimativa de recursos do kit de desenvolvimento quântico
description: Conheça o Estimativa de Recursos, que estima os recursos necessários para executar uma determinada instância de uma operação Q# num computador quântico.
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: cbb1c274b64738cc4b47869563d7d02eb717afbc
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415267"
---
# <a name="the-resources-estimator-target-machine"></a><span data-ttu-id="10662-103">A Máquina-Alvo do Estimador de Recursos</span><span class="sxs-lookup"><span data-stu-id="10662-103">The Resources Estimator Target Machine</span></span>

<span data-ttu-id="10662-104">Como o nome indica, `ResourcesEstimator` estima os recursos necessários para executar uma determinada instância de uma operação Q# num computador quântico.</span><span class="sxs-lookup"><span data-stu-id="10662-104">As the name implies, the `ResourcesEstimator` estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>
<span data-ttu-id="10662-105">Consegue-o executando a operação quântica sem simular o estado de um computador quântico; por esta razão, pode estimar recursos para operações Q# que usam milhares de qubits, se a parte clássica do código pode ser executada em um tempo razoável.</span><span class="sxs-lookup"><span data-stu-id="10662-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it can estimate resources for Q# operations that use thousands of qubits, if the classical part of the code can be run in a reasonable time.</span></span>

## <a name="usage"></a><span data-ttu-id="10662-106">Utilização</span><span class="sxs-lookup"><span data-stu-id="10662-106">Usage</span></span>

<span data-ttu-id="10662-107">Este `ResourcesEstimator` é apenas mais um tipo de máquina alvo, portanto pode ser usado para executar qualquer operação Q#.</span><span class="sxs-lookup"><span data-stu-id="10662-107">The `ResourcesEstimator` is just another type of target machine, thus it can be used to run any Q# operation.</span></span> 

<span data-ttu-id="10662-108">Como outras máquinas-alvo, usá-lo num programa de anfitrião C# criar uma instância e passá-la como o primeiro parâmetro do método da `Run` operação:</span><span class="sxs-lookup"><span data-stu-id="10662-108">As other target machines, to use it on a C# host program create an instance and pass it as the first parameter of the operation's `Run` method:</span></span>

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

<span data-ttu-id="10662-109">Como mostra o exemplo, `ResourcesEstimator` o método fornece um método para gerar uma tabela com `ToTSV()` valores separados por separados (TSV) que pode ser guardado num ficheiro ou escrito na consola para análise.</span><span class="sxs-lookup"><span data-stu-id="10662-109">As the example shows, the `ResourcesEstimator` provides a `ToTSV()` method to generate a table with tab-separated-values (TSV) that can be saved into a file or written to the console for analysis.</span></span> <span data-ttu-id="10662-110">A saída do programa acima deve ser algo assim:</span><span class="sxs-lookup"><span data-stu-id="10662-110">The output of the above program should look something like this:</span></span>

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
> <span data-ttu-id="10662-111">O `ResourcesEstimator` não reinicia os seus cálculos em cada execução, se for utilizado o mesmo caso para executar outra operação, manterá as contagens agregadas para além dos resultados existentes.</span><span class="sxs-lookup"><span data-stu-id="10662-111">The `ResourcesEstimator` does not reset its calculations on every run, if the same instance is used to execute another operation it will keep aggregating counts on top of existing results.</span></span>
> <span data-ttu-id="10662-112">Se precisar de redefinir os cálculos entre as execuções, crie uma nova instância para cada execução.</span><span class="sxs-lookup"><span data-stu-id="10662-112">If you need to reset calculations between runs, create a new instance for every execution.</span></span>


## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="10662-113">Recuperação programática dos dados estimados</span><span class="sxs-lookup"><span data-stu-id="10662-113">Programmatically Retrieving the Estimated Data</span></span>

<span data-ttu-id="10662-114">Além de uma tabela de TSV, os recursos estimados podem ser recuperados programáticamente através `ResourcesEstimator` da `Data` propriedade.</span><span class="sxs-lookup"><span data-stu-id="10662-114">In addition to a TSV table, the resources estimated can be retrieved programmatically via the `ResourcesEstimator`'s `Data` property.</span></span> <span data-ttu-id="10662-115">`Data`fornece um `System.DataTable` caso com duas colunas: `Metric` `Sum` e, indexado pelos nomes das métricas.</span><span class="sxs-lookup"><span data-stu-id="10662-115">`Data` provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics names.</span></span>

<span data-ttu-id="10662-116">O seguinte código mostra como recuperar e imprimir o número total de `QubitClifford` , `T` e `CNOT` portões utilizados por uma operação Q#:</span><span class="sxs-lookup"><span data-stu-id="10662-116">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` gates used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="10662-117">Métricas Reportadas</span><span class="sxs-lookup"><span data-stu-id="10662-117">Metrics Reported</span></span>

<span data-ttu-id="10662-118">Segue-se a lista de métricas estimadas pelo `ResourcesEstimator` seguinte:</span><span class="sxs-lookup"><span data-stu-id="10662-118">The following is the list of metrics estimated by the `ResourcesEstimator`:</span></span>

* <span data-ttu-id="10662-119">__CNOT__: A contagem dos portões CNOT (também conhecido como portão Controlado Pauli X) executada.</span><span class="sxs-lookup"><span data-stu-id="10662-119">__CNOT__: The count of CNOT (also known as the Controlled Pauli X gate) gates executed.</span></span>
* <span data-ttu-id="10662-120">__QubitClifford:__ A contagem de qualquer qubit Clifford e pauli portões executados.</span><span class="sxs-lookup"><span data-stu-id="10662-120">__QubitClifford__: The count of any single qubit Clifford and Pauli gates executed.</span></span>
* <span data-ttu-id="10662-121">__Medida__: A contagem de quaisquer medições executadas.</span><span class="sxs-lookup"><span data-stu-id="10662-121">__Measure__:  The count of any measurements executed.</span></span>
* <span data-ttu-id="10662-122">__R__: A contagem de quaisquer rotações de qubit executadas, excluindo os portões T, Clifford e Pauli.</span><span class="sxs-lookup"><span data-stu-id="10662-122">__R__: The count of any single qubit rotations executed, excluding T, Clifford and Pauli gates.</span></span>
* <span data-ttu-id="10662-123">__T__: A contagem de portões T e seus conjugados, incluindo o portão T, T_x = H.T.H, e T_y = Hy.T.Hy, executado.</span><span class="sxs-lookup"><span data-stu-id="10662-123">__T__: The count of T gates and their conjugates, including the T gate, T_x = H.T.H, and T_y = Hy.T.Hy, executed.</span></span>
* <span data-ttu-id="10662-124">__Profundidade__: O limite inferior para a profundidade do circuito quântico executado pela operação Q#.</span><span class="sxs-lookup"><span data-stu-id="10662-124">__Depth__: The lower bound for the depth of the quantum circuit executed by the Q# operation.</span></span> <span data-ttu-id="10662-125">Por predefinição, apenas os portões T são contados na profundidade, consulte o [contador de profundidade](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="10662-125">By default, only T gates are counted in the depth, see [depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) for details.</span></span>
* <span data-ttu-id="10662-126">__Largura__: O limite inferior para o número máximo de qubits atribuídos durante a execução da operação Q#.</span><span class="sxs-lookup"><span data-stu-id="10662-126">__Width__: The lower bound for the maximum number of qubits allocated during the execution of the Q# operation.</span></span> <span data-ttu-id="10662-127">Pode não ser possível atingir simultaneamente os limites mais baixos de __profundidade__ e __largura.__</span><span class="sxs-lookup"><span data-stu-id="10662-127">It might not be possible to achieve both __Depth__ and __Width__ lower bounds simultaneously.</span></span>
* <span data-ttu-id="10662-128">__BorrowedWidth__: Número máximo de qubits emprestados dentro da operação Q#.</span><span class="sxs-lookup"><span data-stu-id="10662-128">__BorrowedWidth__: Maximum number of qubits borrowed inside the Q# operation.</span></span>


## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="10662-129">Fornecer a Probabilidade de Resultados de Medição</span><span class="sxs-lookup"><span data-stu-id="10662-129">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="10662-130"><xref:microsoft.quantum.intrinsic.assertprob>a partir do <xref:microsoft.quantum.intrinsic> espaço de nomes pode ser usado para fornecer informações sobre a probabilidade esperada de uma medição para ajudar a impulsionar a execução do programa Q#.</span><span class="sxs-lookup"><span data-stu-id="10662-130"><xref:microsoft.quantum.intrinsic.assertprob> from the <xref:microsoft.quantum.intrinsic> namespace can be used to provide information about the expected probability of a measurement to help drive the execution of the Q# program.</span></span> <span data-ttu-id="10662-131">O exemplo seguinte ilustra isso mesmo:</span><span class="sxs-lookup"><span data-stu-id="10662-131">The following example illustrates this:</span></span>

```qsharp
operation Teleport(source : Qubit, target : Qubit) : Unit {

    using (qubit = Qubit()) {

        H(q);
        CNOT(qubit, target);

        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [qubit], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(qubit) == One) { X(target); X(qubit); }
    }
}
```

<span data-ttu-id="10662-132">Quando os `ResourcesEstimator` encontros `AssertProb` registarem essa medição `PauliZ` e deve ser dado um resultado com probabilidade de `source` `q` `Zero` 0,5.</span><span class="sxs-lookup"><span data-stu-id="10662-132">When the `ResourcesEstimator` encounters `AssertProb` it will record that measuring `PauliZ` on `source` and `q` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="10662-133">Quando executar `M` mais tarde, encontrará os valores registados das probabilidades de resultado e `M` regressará `Zero` ou com probabilidade `One` 0.5.</span><span class="sxs-lookup"><span data-stu-id="10662-133">When it executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span>


## <a name="see-also"></a><span data-ttu-id="10662-134">Ver também</span><span class="sxs-lookup"><span data-stu-id="10662-134">See also</span></span>

<span data-ttu-id="10662-135">O `ResourcesEstimator` é construído em cima do simulador de [traços](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de computador quântico, que fornece um conjunto mais rico de métricas, a capacidade de reportar métricas no gráfico de chamada completo, e apresenta características como [verificador de entradas distintas](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) para ajudar a encontrar bugs em programas Q#.</span><span class="sxs-lookup"><span data-stu-id="10662-135">The `ResourcesEstimator` is built on top of the quantum computer [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics, the ability to report metrics on the full call-graph, and features like [distinct inputs checker](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) to help find bugs on Q# programs.</span></span> <span data-ttu-id="10662-136">Consulte a documentação do [simulador de rastreios](xref:microsoft.quantum.machines.qc-trace-simulator.intro) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="10662-136">Please refer to the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) documentation for more information.</span></span>

