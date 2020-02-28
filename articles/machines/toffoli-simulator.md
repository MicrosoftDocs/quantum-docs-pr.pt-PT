---
title: Simulador de Kit de Desenvolvimento Quântico Toffoli
description: Saiba mais sobre o Microsoft QDK Toffoli Simulator, um simulador quântico de propósito especial que pode ser usado com milhões de qubits.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 8a29caaa0fa058600a74e7d130e644374cbfa19c
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907023"
---
# <a name="quantum-development-kit-toffoli-simulator"></a>Simulador de Kit de Desenvolvimento Quântico Toffoli

O Kit de Desenvolvimento Quântico fornece um simulador Toffoli, que é um simulador de propósito especial que pode simular algoritmos quânticos que estão limitados a Operações Quânticas X, CNOT e multi-controladas (todas as lógicas clássicas e computações estão disponíveis).

Embora o simulador Toffoli seja muito mais restrito em funcionamento do que todo o [simulador de estado,](xref:microsoft.quantum.machines.full-state-simulator)pode simular muito mais qubits.
O simulador Toffoli pode ser usado com milhões de qubits, enquanto o simulador de estado completo é geralmente limitado a cerca de 30.
Pode executar e depurar um conjunto limitado de algoritmos quânticos escritos em Q# no seu computador; por exemplo, os oráculos que avaliam as funções booleanas podem ser implementados usando estes portões e assim testados em grande número de qubits usando este simulador.

Este simulador quântico é exposto através da classe `ToffoliSimulator`.
Para utilizar o simulador, basta criar uma instância desta classe e passá-la para o método `Run` da operação quântica que pretende executar juntamente com o resto dos parâmetros:

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a>Outras Operações

O `ToffoliSimulator` suporta rotações e Paulis exponenciados, como `R` e `Exp`, quando a operação resultante é igual a `X` ou à identidade.

A medição e a afirmação são suportadas, mas apenas na base pauli `Z`.
Note que a probabilidade de alguma medição é sempre 0 ou 1; não há aleatoriedade no simulador de Toffoli.

`DumpMachine` e `DumpRegister` são apoiados.
Ambos eles outputam o estado atual `Z`-base de cada qubit, um qubit por linha.

## <a name="qubitcount"></a>QubitCount

Por predefinição, o `ToffoliSimulator` atribui espaço para 65.536 qubits.
Se o seu algoritmo necessitar de mais do que isso, pode alterar a contagem de qubit fornecendo um valor para o parâmetro `qubitCount` para o construtor.
Cada qubit adicional requer um byte adicional de memória, por isso não há um custo significativo para sobrestimar o número de qubits que você precisará.

Por exemplo:

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
