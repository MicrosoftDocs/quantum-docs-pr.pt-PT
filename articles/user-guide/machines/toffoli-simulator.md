---
title: Simulador Quantum Toffoli - Kit de Desenvolvimento Quântico
description: Saiba mais sobre o simulador Microsoft QDK Toffoli, um simulador quântico de propósito especial que pode ser usado com milhões de qubits.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: a6ceee592e628215511ec83475d9e25bf54674f7
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870622"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a><span data-ttu-id="526ed-103">Kit de Desenvolvimento Quântico (QDK) Simulador toffoli</span><span class="sxs-lookup"><span data-stu-id="526ed-103">Quantum Development Kit (QDK) Toffoli simulator</span></span>

<span data-ttu-id="526ed-104">O simulador QDK Toffoli é um simulador de propósito especial com um âmbito limitado e apenas suporta `X` `CNOT` `X` operações quânticas multi-controladas.</span><span class="sxs-lookup"><span data-stu-id="526ed-104">The QDK Toffoli simulator is a special-purpose simulator with a limited scope and only supports `X`, `CNOT`, and multi-controlled `X` quantum operations.</span></span> <span data-ttu-id="526ed-105">Toda a lógica clássica e computações estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="526ed-105">All classical logic and computations are available.</span></span>

<span data-ttu-id="526ed-106">Embora o simulador Toffoli seja mais restrito na funcionalidade do que o [simulador de estado completo,](xref:microsoft.quantum.machines.full-state-simulator)tem a vantagem de ser capaz de simular muito mais qubits.</span><span class="sxs-lookup"><span data-stu-id="526ed-106">While the Toffoli simulator is more restricted in functionality than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it has the advantage of being able to simulate far more qubits.</span></span> <span data-ttu-id="526ed-107">O simulador Toffoli pode ser usado com milhões de qubits, enquanto o simulador de estado completo está limitado a cerca de 30 qubits.</span><span class="sxs-lookup"><span data-stu-id="526ed-107">The Toffoli simulator can be used with millions of qubits, while the full state simulator is limited to about 30 qubits.</span></span> <span data-ttu-id="526ed-108">Isto é útil, por exemplo, com oráculos que avaliam as funções booleanas - podem ser implementados usando o conjunto limitado de algoritmos suportados e testados em um grande número de qubits.</span><span class="sxs-lookup"><span data-stu-id="526ed-108">This is useful, for example, with oracles that evaluate Boolean functions - they can be implemented using the limited set of supported algorithms and tested on a large number of qubits.</span></span>

## <a name="invoking-the-toffoli-simulator"></a><span data-ttu-id="526ed-109">Invocando o simulador toffoli</span><span class="sxs-lookup"><span data-stu-id="526ed-109">Invoking the Toffoli simulator</span></span>

<span data-ttu-id="526ed-110">Expões o simulador toffoli através da `ToffoliSimulator` aula.</span><span class="sxs-lookup"><span data-stu-id="526ed-110">You expose the Toffoli simulator via the `ToffoliSimulator` class.</span></span> <span data-ttu-id="526ed-111">Para mais detalhes, consulte [Formas de executar um programa Q#](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="526ed-111">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-toffoli-simulator-from-c"></a><span data-ttu-id="526ed-112">Invocando o simulador Toffoli de C #</span><span class="sxs-lookup"><span data-stu-id="526ed-112">Invoking the Toffoli simulator from C#</span></span>

<span data-ttu-id="526ed-113">Tal como acontece com outras máquinas-alvo, cria-se primeiro uma instância da `ToffoliSimulator` classe e depois passa-a como o primeiro parâmetro do método de uma `Run` operação.</span><span class="sxs-lookup"><span data-stu-id="526ed-113">As with other target machines, you first create an instance of the `ToffoliSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="526ed-114">Note que, ao contrário da `QuantumSimulator` classe, a `ToffoliSimulator` classe não implementa a <xref:System.IDisposable> interface, pelo que não precisa de a incluir dentro de um `using` comunicado.</span><span class="sxs-lookup"><span data-stu-id="526ed-114">Note that, unlike the `QuantumSimulator` class, the `ToffoliSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a><span data-ttu-id="526ed-115">Invocando o simulador Toffoli de Python</span><span class="sxs-lookup"><span data-stu-id="526ed-115">Invoking the Toffoli simulator from Python</span></span>

<span data-ttu-id="526ed-116">Utilize o método [toffoli_simulate()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) da biblioteca Python com a operação Q# importada:</span><span class="sxs-lookup"><span data-stu-id="526ed-116">Use the [toffoli_simulate()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a><span data-ttu-id="526ed-117">Invocando o simulador Toffoli da linha de comando</span><span class="sxs-lookup"><span data-stu-id="526ed-117">Invoking the Toffoli simulator from the command line</span></span>

<span data-ttu-id="526ed-118">Ao executar um programa Q# a partir da linha de comando, utilize o parâmetro **simulador** (ou **atalho -s** para especificar a máquina alvo do simulador Toffoli.</span><span class="sxs-lookup"><span data-stu-id="526ed-118">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the Toffoli simulator target machine.</span></span> <span data-ttu-id="526ed-119">O seguinte comando executa um programa utilizando o estimador de recursos:</span><span class="sxs-lookup"><span data-stu-id="526ed-119">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a><span data-ttu-id="526ed-120">Invocando o simulador Toffoli dos Cadernos Juptyer</span><span class="sxs-lookup"><span data-stu-id="526ed-120">Invoking the Toffoli simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="526ed-121">Utilize o comando mágico IQ# [%toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) para executar a operação Q# .</span><span class="sxs-lookup"><span data-stu-id="526ed-121">Use the IQ# magic command [%toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) to run the Q# operation.</span></span>

```
%toffoli myOperation
```

## <a name="supported-operations"></a><span data-ttu-id="526ed-122">Operações apoiadas</span><span class="sxs-lookup"><span data-stu-id="526ed-122">Supported operations</span></span>

<span data-ttu-id="526ed-123">O simulador Toffoli suporta:</span><span class="sxs-lookup"><span data-stu-id="526ed-123">The Toffoli simulator supports:</span></span>

* <span data-ttu-id="526ed-124">Rotações e Paulis exponencial, tais como `R` `Exp` e, quando a operação resultante é igual `X` ou a matriz identitária.</span><span class="sxs-lookup"><span data-stu-id="526ed-124">Rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation equals `X` or the identity matrix.</span></span>
* <span data-ttu-id="526ed-125">Medição e [afirmação](xref:microsoft.quantum.diagnostics.assertmeasurement) de operações, mas apenas na base de `Z` Pauli.</span><span class="sxs-lookup"><span data-stu-id="526ed-125">Measurement and [assert](xref:microsoft.quantum.diagnostics.assertmeasurement) operations, but only in the Pauli `Z` basis.</span></span> <span data-ttu-id="526ed-126">Note que a probabilidade de uma operação de medição é sempre **0** ou **1;** não há aleatoriedade no simulador toffoli.</span><span class="sxs-lookup"><span data-stu-id="526ed-126">Note that a measurement operation's probability is always either **0** or **1**; there is no randomness in the Toffoli simulator.</span></span>
* <span data-ttu-id="526ed-127">`DumpMachine`e `DumpRegister` funções.</span><span class="sxs-lookup"><span data-stu-id="526ed-127">`DumpMachine` and `DumpRegister` functions.</span></span>
<span data-ttu-id="526ed-128">Ambas as funções funcionam o estado de base atual `Z` de cada qubit, um qubit por linha.</span><span class="sxs-lookup"><span data-stu-id="526ed-128">Both functions output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="specifying-the-number-of-qubits"></a><span data-ttu-id="526ed-129">Especificando o número de qubits</span><span class="sxs-lookup"><span data-stu-id="526ed-129">Specifying the number of qubits</span></span>

<span data-ttu-id="526ed-130">Por padrão, um `ToffoliSimulator` caso atribui espaço para 65.536 qubits.</span><span class="sxs-lookup"><span data-stu-id="526ed-130">By default, a `ToffoliSimulator` instance allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="526ed-131">Se o seu algoritmo necessitar de mais qubits do que este, pode especificar a contagem de qubits fornecendo um valor para o `qubitCount` parâmetro ao construtor.</span><span class="sxs-lookup"><span data-stu-id="526ed-131">If your algorithm requires more qubits than this, you can specify the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="526ed-132">Cada qubit adicional requer apenas um byte de memória, por isso não há um custo significativo para sobrestimar o número de qubits que você precisará.</span><span class="sxs-lookup"><span data-stu-id="526ed-132">Each additional qubit requires only one byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="526ed-133">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="526ed-133">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a><span data-ttu-id="526ed-134">Ver também</span><span class="sxs-lookup"><span data-stu-id="526ed-134">See also</span></span>

- [<span data-ttu-id="526ed-135">Estimador de Recursos Quânticos</span><span class="sxs-lookup"><span data-stu-id="526ed-135">Quantum Resources Estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="526ed-136">Simulador de vestígios quânticos</span><span class="sxs-lookup"><span data-stu-id="526ed-136">Quantum Trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="526ed-137">Simulador de Estado Completo Quântico</span><span class="sxs-lookup"><span data-stu-id="526ed-137">Quantum Full State simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 