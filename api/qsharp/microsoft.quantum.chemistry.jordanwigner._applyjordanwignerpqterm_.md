---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerPQTerm_
title: _Aplicação operação JordanWignerPQTerm_
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerPQTerm_
qsharp.summary: Applies time-evolution by a PQ term described by a `GeneratorIndex`.
ms.openlocfilehash: 6e7d3e422ea751371eeb3111dce88acc6eaf3b62
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851719"
---
# <a name="_applyjordanwignerpqterm_-operation"></a><span data-ttu-id="44b11-102">_Aplicação operação JordanWignerPQTerm_</span><span class="sxs-lookup"><span data-stu-id="44b11-102">_ApplyJordanWignerPQTerm_ operation</span></span>

<span data-ttu-id="44b11-103">Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="44b11-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="44b11-104">Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="44b11-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="44b11-105">Aplica a evolução temporal por um termo PQ descrito por um `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="44b11-105">Applies time-evolution by a PQ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerPQTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, extraParityQubits : Qubit[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="44b11-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="44b11-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="44b11-107">termo : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="44b11-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="44b11-108">`GeneratorIndex` representando um termo PQ.</span><span class="sxs-lookup"><span data-stu-id="44b11-108">`GeneratorIndex` representing a PQ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="44b11-109">stepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="44b11-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="44b11-110">Duração da evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="44b11-110">Duration of time-evolution.</span></span>


### <a name="extraparityqubits--qubit"></a><span data-ttu-id="44b11-111">extraParityQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="44b11-111">extraParityQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="44b11-112">Qubits de paridade opcional que invertem o sinal da evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="44b11-112">Optional parity qubits that flip the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="44b11-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="44b11-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="44b11-114">Qubits de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="44b11-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="44b11-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="44b11-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

