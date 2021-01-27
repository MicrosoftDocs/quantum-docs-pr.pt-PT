---
title: Simulador Quantum Toffoli - Kit de Desenvolvimento Quântico
description: Saiba mais sobre o simulador Microsoft QDK Toffoli, um simulador quântico de propósito especial que pode ser usado com milhões de qubits.
author: alan-geller
ms.author: ageller
ms.date: 6/25/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.toffoli-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 84b958912ab5116a3181c8eff4f331fc8394604c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858573"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a>Kit de Desenvolvimento Quântico (QDK) Simulador toffoli

O simulador QDK Toffoli é um simulador de propósito especial com um âmbito limitado e apenas suporta `X` `CNOT` `X` operações quânticas multi-controladas. Toda a lógica clássica e computações estão disponíveis.

Embora o simulador Toffoli seja mais restrito na funcionalidade do que o [simulador de estado completo,](xref:microsoft.quantum.machines.full-state-simulator)tem a vantagem de ser capaz de simular muito mais qubits. O simulador Toffoli pode ser usado com milhões de qubits, enquanto o simulador de estado completo está limitado a cerca de 30 qubits. Isto é útil, por exemplo, com oráculos que avaliam as funções booleanas - podem ser implementados usando o conjunto limitado de algoritmos suportados e testados em um grande número de qubits.

## <a name="invoking-the-toffoli-simulator"></a>Invocando o simulador toffoli

Expões o simulador toffoli através da `ToffoliSimulator` aula. Para mais detalhes, consulte [Formas de executar um Q# programa](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-toffoli-simulator-from-c"></a>Invocando o simulador Toffoli de C #

Tal como sucede com outros computadores de destino, vai criar primeiro uma instância da classe `ToffoliSimulator` e, depois, transmiti-la como o primeiro parâmetro do método `Run` de uma operação.

Tenha em conta que, ao contrário da classe `QuantumSimulator`, a classe `ToffoliSimulator` não implementa a interface <xref:System.IDisposable>, pelo que não precisa de a incluir dentro de uma instrução `using`.

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a>Invocando o simulador Toffoli de Python

Utilize o método [toffoli_simulate](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) da biblioteca Python com a Q# operação importada:

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a>Invocando o simulador Toffoli da linha de comando

Ao executar um Q# programa a partir da linha de comando, utilize o parâmetro **-simulador** (ou **atalho -s** para especificar a máquina alvo do simulador de Toffoli. O seguinte comando executa um programa utilizando o estimador de recursos: 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a>Invocando o simulador Toffoli dos Cadernos Juptyer

Use o comando mágico I Q# [%toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) para executar a Q# operação.

```
%toffoli myOperation
```

## <a name="supported-operations"></a>Operações apoiadas

O simulador Toffoli suporta:

* Rotações e Paulis exponencial, tais como `R` `Exp` e, quando a operação resultante é igual `X` ou a matriz identitária.
* Medição e [afirmação](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement) de operações, mas apenas na base de `Z` Pauli. Note que a probabilidade de uma operação de medição é sempre **0** ou **1;** não há aleatoriedade no simulador toffoli.
* `DumpMachine` e `DumpRegister` funções.
Ambas as funções funcionam o estado de base atual `Z` de cada qubit, um qubit por linha.

## <a name="specifying-the-number-of-qubits"></a>Especificando o número de qubits

Por padrão, um `ToffoliSimulator` caso atribui espaço para 65.536 qubits.
Se o seu algoritmo necessitar de mais qubits do que este, pode especificar a contagem de qubits fornecendo um valor para o `qubitCount` parâmetro ao construtor.
Cada qubit adicional requer apenas um byte de memória, por isso não há um custo significativo para sobrestimar o número de qubits que você precisará.

Por exemplo:

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a>Veja também

- [Estimador de Recursos Quânticos](xref:microsoft.quantum.machines.resources-estimator)
- [Simulador de vestígios quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Simulador de Estado Completo Quântico](xref:microsoft.quantum.machines.full-state-simulator) 