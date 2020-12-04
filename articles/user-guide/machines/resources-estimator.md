---
title: Estimador de recursos quânticos - Kit de Desenvolvimento Quântico
description: Conheça o estimador de recursos da Microsoft QDK, que estima os recursos necessários para executar uma determinada instância de uma Q# operação num computador quântico.
author: anpaz-msft
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: de425c2d91c6528b13c3bedd81acb4b4273ed711
ms.sourcegitcommit: 7c687495a79d75ae9e029e5a41baec84d9e07bb0
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 12/04/2020
ms.locfileid: "96604648"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a>Estimativa de recursos do Kit de Desenvolvimento Quântico (QDK)

Como o nome indica, a `ResourcesEstimator` classe estima os recursos necessários para executar uma determinada instância de uma Q# operação num computador quântico. Consegue-o executando a operação quântica sem simular o estado de um computador quântico; por esta razão, estima recursos para Q# operações que utilizam milhares de qubits, desde que a parte clássica do código seja executado num prazo razoável.

O estimador de recursos é construído em cima do simulador de [traços Quânticos,](xref:microsoft.quantum.machines.qc-trace-simulator.intro)que fornece um conjunto mais rico de métricas e ferramentas para ajudar a Q# depurar programas.

## <a name="invoking-and-running-the-resources-estimator"></a>Invocando e executando o estimador de recursos

Pode utilizar o estimador de recursos para executar qualquer Q# operação. Para mais detalhes, consulte [Formas de executar um Q# programa](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-resources-estimator-from-c"></a>Invocando o estimador de recursos de C # 

Tal como sucede com outros computadores de destino, vai criar primeiro uma instância da classe `ResourcesEstimator` e, depois, transmiti-la como o primeiro parâmetro do método `Run` de uma operação.

Tenha em conta que, ao contrário da classe `QuantumSimulator`, a classe `ResourcesEstimator` não implementa a interface <xref:System.IDisposable>, pelo que não precisa de a incluir dentro de uma instrução `using`.

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

Utilizar o método [estimate_resources da](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) biblioteca Python com a operação Q# importada:

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
|__Profundidade__|Profundidade do circuito quântico executado pela Q# operação (ver [abaixo](#depth-width-and-qubitcount)). Por predefinição, a métrica de profundidade apenas conta `T` portões. Para mais detalhes, consulte [o Contador de Profundidade.](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)   |
|__Width__|Largura do circuito quântico executado pela Q# operação (ver [abaixo](#depth-width-and-qubitcount)). Por predefinição, a métrica de profundidade apenas conta `T` portões. Para mais detalhes, consulte [o Contador de Largura](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).   |
|__QubitCount__    |O limite inferior para o número máximo de qubits atribuídos durante o Q# funcionamento. Esta métrica pode não ser compatível com __profundidade__ (ver abaixo).  |
|__Largura emprestada__    |O número máximo de qubits emprestados dentro da Q# operação.  |


## <a name="depth-width-and-qubitcount"></a>Profundidade, Largura e QubitCount

As estimativas reportadas de profundidade e largura são compatíveis entre si.
(Anteriormente, ambos os números eram alcançáveis, mas seriam necessários circuitos diferentes para profundidade e largura.) Atualmente ambas as métricas deste par podem ser alcançadas pelo mesmo circuito ao mesmo tempo.

São reportadas as seguintes métricas:

__Profundidade:__ Para a operação raiz - o tempo leva para executá-lo assumindo tempos específicos do portão.
Para operações chamadas ou operações subsequentes - diferença de tempo entre o tempo mais recente de disponibilidade de qubit no início e o fim da operação.

__Largura:__ Para a operação raiz - número de qubits realmente utilizados para executá-lo (e operação que chama).
Para operações convocadas ou operações subsequentes - quantos mais qubits foram utilizados para além dos qubits já utilizados no início da operação.

Por favor, note que os qubits reutilizados não contribuem para este número.
Ou seja, se alguns qubits foram lançados antes do início da operação A, e todos os qubits exigidos por esta operação A (e operações chamadas a partir de A) foram satisfeitos com a reutilização de qubits previamente lançados, a largura da operação A é reportada como 0. Os qubits emprestados com sucesso também não contribuem para a Largura.

__QubitCount:__ Para a operação raiz - número mínimo de qubits que seriam suficientes para executar esta operação (e operações chamadas a partir dela).
Para operações chamadas ou operações subsequentes - número mínimo de qubits que seriam suficientes para executar esta operação separadamente. Este número não inclui qubits de entrada. Inclui qubits emprestados.

Dois modos de funcionamento são suportados. O modo é selecionado definindo QCTraceSimulatorConfiguration.OptimizeDepth.

__OptimizeDepth=verdade:__ QubitManager é desencorajado de reutilização de qubit e atribui novo qubit cada vez que é solicitado um qubit. Para a operação raiz __A profundidade__ torna-se a profundidade mínima (limite inferior). A __largura__ compatível é reportada para esta profundidade (ambas podem ser alcançadas ao mesmo tempo). Note que esta largura provavelmente não será a melhor dada esta profundidade. __QubitCount__ pode ser inferior à largura para a operação da raiz porque assume a reutilização.

__OptimizeDepth=falso:__ QubitManager é encorajado a reutilizar qubits e reutilizar os qubits libertados antes de alocar novos. Para a operação raiz __A largura__ torna-se a largura mínima (limite inferior). É reportada __profundidade__ compatível na qual pode ser alcançado. __QubitCount__ será o mesmo __que width__ para a operação raiz assumindo que não há empréstimos.

## <a name="providing-the-probability-of-measurement-outcomes"></a>Fornecer a probabilidade de resultados de medições

Pode utilizar <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> a partir do espaço de nome para fornecer <xref:Microsoft.Quantum.Diagnostics> informações sobre a probabilidade esperada de uma operação de medição. Para mais informações, consulte [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)

## <a name="see-also"></a>Ver também

- [Simulador de vestígios quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Simulador Toffoli quântico](xref:microsoft.quantum.machines.toffoli-simulator)
- [Simulador de estado completo quântico](xref:microsoft.quantum.machines.full-state-simulator) 
