---
title: Simuladores quânticos e programas Q#
description: Descreve os simuladores quânticos disponíveis como máquinas de destino para programas Q#.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 6/17/2020
ms.topic: article
uid: microsoft.quantum.machines
no-loc:
- Q#
- $$v
ms.openlocfilehash: 77401ca3642b89d708f338f852dc60bf7346b87b
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868309"
---
# <a name="quantum-simulators"></a>Simuladores quânticos

Os simuladores quânticos são programas de software que funcionam em computadores clássicos e que atuam como o *computador de destino* de um programa Q#, possibilitando a execução e a testagem de programas quânticos num ambiente que prevê a reação dos qubits a diferentes operações. Este artigo descreve que simuladores quânticos estão incluídos no Quantum Development kit (QDK) e as várias formas através das quais pode transmitir um programa Q# para os simuladores quânticos, como, por exemplo, com a linha de comandos ou com código de controlador escrito numa linguagem clássica.  



## <a name="the-quantum-development-kit-qdk-quantum-simulators"></a>Os simuladores do Quantum Development kit (QDK)

O simulador quântico é responsável por fornecer implementações de primitivos quânticos para um algoritmo. Essas implementações incluem operações primitivas como `H`, `CNOT` e `Measure`, bem como gestão e monitorização de qubits. O QDK inclui diferentes classes de simuladores quânticos que representam modelos de execução distintos para o mesmo algoritmo quântico. 


Cada tipo de simulador quântico pode fornecer diferentes implementações desses primitivos. Por exemplo, o [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator) executa o algoritmo quântico ao simular na íntegra o [vetor de estado quântico](xref:microsoft.quantum.glossary#quantum-state), ao passo que o [simulador de rastreio de computador quântico](xref:microsoft.quantum.machines.qc-trace-simulator.intro) não tem minimamente em conta o estado quântico atual. Em vez disso, rastreia a porta, o qubit e outras utilizações dos recursos para o algoritmo.

### <a name="quantum-machine-classes"></a>Classes de computadores quânticos

No futuro, o QDK vai definir classes adicionais de computadores quânticos para suportar outros tipos de simulações e para suportar a execução em hardware quântico. Permitir que o algoritmo se mantenha constante enquanto se varia a implementação do computador subjacente facilita testar e depurar um algoritmo na simulação e, em seguida, executá-lo em hardware real com a confiança de que o algoritmo não mudou.

O QDK inclui várias classes de computadores quânticos, todas definidas no espaço de nomes `Microsoft.Quantum.Simulation.Simulators`.

|Simulador |Classe|Descrição|
|-----|------|---|
|[Simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator)| `QuantumSimulator` | Executa e depura os algoritmos quânticos e está limitado a cerca de 30 qubits. |
|[Avaliador de recursos simples](xref:microsoft.quantum.machines.resources-estimator)| `ResourcesEstimator` | Realiza uma análise de nível superior dos recursos necessários para executar um algoritmo quântico e suporta milhares de qubits.|
|[Avaliador de recursos com base em rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro)|  `QCTraceSimulator` |Executa uma análise avançada dos consumos de recursos para todo o grafo de chamada do algoritmo e suporta milhares de qubits.|
|[Simulador Toffoli](xref:microsoft.quantum.machines.toffoli-simulator)| `ToffoliSimulator` |Simula os algoritmos quânticos que estão limitados a operações quânticas `X`, `CNOT` e multicontroladas `X` e suporta milhões de qubits. |

## <a name="invoking-the-quantum-simulator"></a>Invocar o simulador quântico

Em [Formas de executar programas Q#](xref:microsoft.quantum.guide.host-programs), são demonstradas três formas de transmitir o código Q# ao simulador quântico: 

* Através da linha de comandos
* Através de um programa anfitrião Python
* Através de um programa anfitrião C#

Os computadores quânticos são instâncias de classes .NET normais, por isso, são criados ao invocar o construtor, como em qualquer classe .NET. A forma como o faz depende de como o programa Q# é executado.

## <a name="next-steps"></a>Passos seguintes

* Para obter detalhes relativos à invocação de computadores de destino para programas Q# em diferentes ambientes, veja [Formas de executar programas Q#](xref:microsoft.quantum.guide.host-programs).
