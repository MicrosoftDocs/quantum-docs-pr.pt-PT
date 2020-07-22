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
# <a name="quantum-development-kit-qdk-resources-estimator"></a>Estimativa de recursos do Kit de Desenvolvimento Quântico (QDK)

Como o nome indica, a `ResourcesEstimator` classe estima os recursos necessários para executar uma determinada instância de uma operação Q# num computador quântico. Consegue-o executando a operação quântica sem simular o estado de um computador quântico; por esta razão, estima recursos para operações Q# que usam milhares de qubits, desde que a parte clássica do código seja executado em um tempo razoável.

O estimador de recursos é construído em cima do simulador de [traços Quânticos,](xref:microsoft.quantum.machines.qc-trace-simulator.intro)que fornece um conjunto mais rico de métricas e ferramentas para ajudar a depurar programas Q#.

## <a name="invoking-and-running-the-resources-estimator"></a>Invocando e executando o estimador de recursos

Pode utilizar o estimador de recursos para executar qualquer operação Q#. Para mais detalhes, consulte [Formas de executar um programa Q#](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-resources-estimator-from-c"></a>Invocando o estimador de recursos de C # 

Tal como acontece com outras máquinas-alvo, cria-se primeiro uma instância da `ResourceEstimator` classe e depois passa-a como o primeiro parâmetro do método de uma `Run` operação.

Note que, ao contrário da `QuantumSimulator` classe, a `ResourceEstimator` classe não implementa a <xref:System.IDisposable> interface, pelo que não precisa de a incluir dentro de um `using` comunicado.

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

Como mostra o exemplo, `ResourcesEstimator` fornece o `ToTSV()` método, que gera uma tabela com valores separados por separados por separados (TSV). Pode guardar a tabela para um ficheiro ou exibi-la na consola para análise. Segue-se uma amostra do programa anterior:

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
> Um `ResourcesEstimator` caso não repõe os seus cálculos em cada corrida. Se utilizar o mesmo caso para executar outra operação, agrega os novos resultados com os resultados existentes. Se precisar de redefinir os cálculos entre as execuções, crie uma nova instância para cada execução.

### <a name="invoking-the-resources-estimator-from-python"></a>Invocando o estimador de recursos da Python

Utilize o método [estimate_resources()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) da biblioteca Python com a operação Q# importada:

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a>Invocando o estimador de recursos da linha de comando

Quando executar um programa Q# a partir da linha de comando, utilize o parâmetro **simulador** (ou **atalho -s** para especificar a `ResourcesEstimator` máquina-alvo. O seguinte comando executa um programa utilizando o estimador de recursos: 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a>Invocando o estimador de recursos dos Cadernos Juptyer

Utilize o comando mágico IQ# [%estimativa](xref:microsoft.quantum.iqsharp.magic-ref.simulate) para executar a operação Q#.

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a>Recuperação programática dos dados estimados

Além de uma tabela de TSV, pode recuperar programáticamente os recursos estimados durante a execução através da `Data` propriedade do estimador de recursos. A `Data` propriedade fornece um exemplo com `System.DataTable` duas colunas: `Metric` `Sum` e, indexada pelos nomes das métricas.

O seguinte código mostra como recuperar e imprimir o número total de `QubitClifford` , `T` e `CNOT` operações utilizadas por uma operação Q#:

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

## <a name="metrics-reported"></a>Métricas Reportadas

O estimador de recursos acompanha as seguintes métricas:

|Métrica|Descrição|
|----|----|
|__CNOT__    |A contagem de `CNOT` operações (também conhecida como operações controladas pauli X).|
|__QubitClifford__ |A contagem de qualquer qubit de operações de Clifford e Pauli.|
|__Medida__    |A contagem de quaisquer medições.  |
|__R__    |A contagem de quaisquer rotações de um único qubit, `T` excluindo, operações Clifford e Pauli.  |
|__T__    |A contagem de `T` operações e seus conjugatos, incluindo as `T` operações, T_x = H.T.H, e T_y = Hy.T.Hy.  |
|__Profundidade__|O limite inferior para a profundidade do circuito quântico executado pela operação Q#. Por predefinição, a métrica de profundidade apenas conta `T` portões. Para mais detalhes, consulte [o Contador de Profundidade.](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)   |
|__Width__    |O limite inferior para o número máximo de qubits atribuídos durante o funcionamento da operação Q#. Pode não ser possível atingir simultaneamente os limites mais baixos de __profundidade__ e __largura.__  |
|__Largura emprestada__    |O número máximo de qubits emprestados dentro da operação Q#.  |

## <a name="providing-the-probability-of-measurement-outcomes"></a>Fornecendo a probabilidade de resultados de medição

Pode utilizar <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> a partir do espaço de nome para fornecer <xref:microsoft.quantum.diagnostics> informações sobre a probabilidade esperada de uma operação de medição. Para mais informações, consulte [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)

## <a name="see-also"></a>Ver também

- [Simulador de vestígios quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Simulador Quantum Toffoli](xref:microsoft.quantum.machines.toffoli-simulator)
- [Simulador de estado completo quântico](xref:microsoft.quantum.machines.full-state-simulator) 