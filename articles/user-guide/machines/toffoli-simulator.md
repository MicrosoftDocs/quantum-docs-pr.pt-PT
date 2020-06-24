---
title: Simulador de kit de desenvolvimento quântico Toffoli
description: Saiba mais sobre o Microsoft QDK Toffoli Simulator, um simulador quântico de propósito especial que pode ser usado com milhões de qubits.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 8a29caaa0fa058600a74e7d130e644374cbfa19c
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276030"
---
# <a name="quantum-development-kit-toffoli-simulator"></a>Simulador de kit de desenvolvimento quântico Toffoli

O Kit de Desenvolvimento Quântico fornece um simulador Toffoli, que é um simulador de propósito especial que pode simular algoritmos quânticos que se limitam a X, CNOT e operações quânticas X multi-controladas (todas as lógicas clássicas e computações estão disponíveis).

Embora o simulador Toffoli seja muito mais restrito em funcionamento do que o [simulador de estado completo,](xref:microsoft.quantum.machines.full-state-simulator)pode simular muito mais qubits.
O simulador Toffoli pode ser usado com milhões de qubits, enquanto o simulador de estado completo é geralmente limitado a cerca de 30.
Pode executar e depurar um conjunto limitado de algoritmos quânticos escritos em Q# no seu computador; por exemplo, os oráculos que avaliam as funções booleanas podem ser implementados usando estes portões e assim testados em um grande número de qubits usando este simulador.

Este simulador quântico é exposto através da `ToffoliSimulator` aula.
Para utilizar o simulador, basta criar uma instância desta classe e passá-la para o `Run` método da operação quântica que pretende executar juntamente com o resto dos parâmetros:

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a>Outras Operações

Os `ToffoliSimulator` suportes rotações e Paulis exponenciados, tais como `R` `Exp` e, quando a operação resultante é igual `X` ou à identidade.

A medição e a afirmação são apoiadas, mas apenas na base de `Z` Pauli.
Note que a probabilidade de alguma medição é sempre 0 ou 1; não há aleatoriedade no simulador toffoli.

`DumpMachine`e `DumpRegister` são apoiados.
Ambos desemodam o `Z` estado atual de base de cada qubit, um qubit por linha.

## <a name="qubitcount"></a>QubitCount

Por predefinição, o `ToffoliSimulator` espaço aloca 65.536 qubits.
Se o seu algoritmo necessitar de mais do que isto, pode alterar a contagem de qubits fornecendo um valor para o `qubitCount` parâmetro ao construtor.
Cada qubit adicional requer um byte adicional de memória, por isso não há um custo significativo para sobrestimar o número de qubits que você precisará.

Por exemplo:

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
