---
title: Estimador de recursos quânticos - Kit de Desenvolvimento Quântico
description: Conheça o estimador de recursos da Microsoft QDK, que estima os recursos necessários para executar uma determinada instância de uma Q# operação num computador quântico.
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: d5338eb740716d9d7f408703347f572688bbccb2
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868190"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a>Estimativa de recursos do Kit de Desenvolvimento Quântico (QDK)

Como o nome indica, a `ResourcesEstimator` classe estima os recursos necessários para executar uma determinada instância de uma Q# operação num computador quântico. Consegue-o executando a operação quântica sem simular o estado de um computador quântico; por esta razão, estima recursos para Q# operações que utilizam milhares de qubits, desde que a parte clássica do código seja executado num prazo razoável.

O estimador de recursos é construído em cima do simulador de [traços Quânticos,](xref:microsoft.quantum.machines.qc-trace-simulator.intro)que fornece um conjunto mais rico de métricas e ferramentas para ajudar a Q# depurar programas.

## <a name="invoking-and-running-the-resources-estimator"></a>Invocando e executando o estimador de recursos

Pode utilizar o estimador de recursos para executar qualquer Q# operação. Para mais detalhes, consulte [Formas de executar um Q# programa](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-resources-estimator-from-c"></a>Invocando o estimador de recursos de C # 

Tal como sucede com outros computadores de destino, vai criar primeiro uma instância da classe `ResourceEstimator` e, depois, transmiti-la como o primeiro parâmetro do método `Run` de uma operação.

Tenha em conta que, ao contrário da classe `QuantumSimulator`, a classe `ResourceEstimator` não implementa a interface <xref:System.IDisposable>, pelo que não precisa de a incluir dentro de uma instrução `using`.

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

Utilizar o método [estimate_resources da](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) biblioteca Python com a operação Q# importada:

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a>Invocando o estimador de recursos da linha de comando

Ao executar um Q# programa a partir da linha de comando, utilize o parâmetro **-simulador** (ou **atalho -s** para especificar a `ResourcesEstimator` máquina-alvo. O seguinte comando executa um programa utilizando o estimador de recursos: 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a>Invocando o estimador de recursos dos Cadernos Juptyer

Use o comando mágico I Q# [%estimativa](xref:microsoft.quantum.iqsharp.magic-ref.simulate) para executar a Q# operação.

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a>Recuperação programática dos dados estimados

Além de uma tabela de TSV, pode recuperar programáticamente os recursos estimados durante a execução através da `Data` propriedade do estimador de recursos. A `Data` propriedade fornece um exemplo com `System.DataTable` duas colunas: `Metric` `Sum` e, indexada pelos nomes das métricas.

O seguinte código mostra como recuperar e imprimir o número total `QubitClifford` de, `T` e `CNOT` operações utilizadas por uma Q# operação:

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
|__Profundidade__|O limite inferior para a profundidade do circuito quântico executado pela Q# operação. Por predefinição, a métrica de profundidade apenas conta `T` portões. Para mais detalhes, consulte [o Contador de Profundidade.](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)   |
|__Width__    |O limite inferior para o número máximo de qubits atribuídos durante o Q# funcionamento. Pode não ser possível atingir simultaneamente os limites mais baixos de __profundidade__ e __largura.__  |
|__Largura emprestada__    |O número máximo de qubits emprestados dentro da Q# operação.  |

## <a name="providing-the-probability-of-measurement-outcomes"></a>Fornecer a probabilidade de resultados de medições

Pode utilizar <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> a partir do espaço de nome para fornecer <xref:microsoft.quantum.diagnostics> informações sobre a probabilidade esperada de uma operação de medição. Para mais informações, consulte [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)

## <a name="see-also"></a>Ver também

- [Simulador de vestígios quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Simulador Toffoli quântico](xref:microsoft.quantum.machines.toffoli-simulator)
- [Simulador de estado completo quântico](xref:microsoft.quantum.machines.full-state-simulator) 