---
title: Kit de desenvolvimento do Quantum Toffoli simulador | Microsoft Docs
description: Visão geral do Toffoli Simulator do kit de desenvolvimento do quantum da Microsoft
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 26940d1a8fe31f1035e2d23a68940cd999517c6b
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442359"
---
# <a name="quantum-development-kit-toffoli-simulator"></a>Kit de desenvolvimento do Quantum Toffoli simulador

O kit de desenvolvimento Quantum fornece um simulador de Toffoli, que é um simulador de finalidade especial que pode simular algoritmos de Quantum que são limitados a operações de Quantum x, CNOT e X com vários controle (toda a lógica clássica e cálculos estão disponíveis).

Embora o simulador de Toffoli seja muito mais restrito em operação do que o [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator), ele pode simular muito mais qubits.
O simulador de Toffoli pode ser usado com milhões de qubits, enquanto o simulador de estado completo geralmente é limitado a cerca de 30.
Ele pode executar e depurar um conjunto limitado de algoritmos de Quantum escritos em Q # no seu computador; por exemplo, os Oracle que avaliam funções booleanas podem ser implementadas usando essas Gates e, portanto, são testadas para variar um grande número de qubits usando esse simulador.

Esse simulador Quantum é exposto por meio da classe `ToffoliSimulator`.
Para usar o simulador, basta criar uma instância dessa classe e passá-la para o método `Run` da operação Quantum que você deseja executar junto com o restante dos parâmetros:

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a>Outras operações

O `ToffoliSimulator` dá suporte a rotações e exponenciação Paulis, como `R` e `Exp`, quando a operação resultante é igual a `X` ou à identidade.

Há suporte para medição e Assert, mas apenas na base do Pauli `Z`.
Observe que a probabilidade de alguma medida é sempre 0 ou 1; Não há aleatoriedade no simulador de Toffoli.

Há suporte para `DumpMachine` e `DumpRegister`.
Ambos geram o estado de base `Z`atual de cada qubit, um qubit por linha.

## <a name="qubitcount"></a>QubitCount

Por padrão, a `ToffoliSimulator` aloca espaço para 65.536 qubits.
Se o algoritmo exigir mais do que isso, você poderá alterar a contagem de qubit fornecendo um valor para o parâmetro `qubitCount` para o construtor.
Cada qubit adicional requer um byte adicional de memória, portanto, não há nenhum custo significativo para a estimativa do número de qubits que você precisará.

Por exemplo:

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
