---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: Aplicação Operação DePosição Internacional
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: 13e70b1ebd5e3bf0996e6a76f4bffe57ca2d2250
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191538"
---
# <a name="applyfixedpointamplification-operation"></a><span data-ttu-id="aa1d1-102">Aplicação Operação DePosição Internacional</span><span class="sxs-lookup"><span data-stu-id="aa1d1-102">ApplyFixedPointAmplification operation</span></span>

<span data-ttu-id="aa1d1-103">Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="aa1d1-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="aa1d1-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aa1d1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aa1d1-105">algoritmo de amplificação da amplitude Fixed-Point</span><span class="sxs-lookup"><span data-stu-id="aa1d1-105">Fixed-Point Amplitude Amplification algorithm</span></span>

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="aa1d1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="aa1d1-106">Input</span></span>

### <a name="statepreporacle--stateoracle"></a><span data-ttu-id="aa1d1-107">EstadoPrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="aa1d1-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="aa1d1-108">Oráculo unitário que prepara o estado de partida.</span><span class="sxs-lookup"><span data-stu-id="aa1d1-108">Unitary oracle that prepares the start state.</span></span>


### <a name="startqubits--qubit"></a><span data-ttu-id="aa1d1-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="aa1d1-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="aa1d1-110">Registo de qubits</span><span class="sxs-lookup"><span data-stu-id="aa1d1-110">Qubit register</span></span>



## <a name="output--unit"></a><span data-ttu-id="aa1d1-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa1d1-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="aa1d1-112">Observações</span><span class="sxs-lookup"><span data-stu-id="aa1d1-112">Remarks</span></span>

<span data-ttu-id="aa1d1-113">Os bits de arranque devem estar no estado $\ket{0 \cdots 0}$.</span><span class="sxs-lookup"><span data-stu-id="aa1d1-113">The startQubits must be in the $\ket{0 \cdots 0}$ state.</span></span> <span data-ttu-id="aa1d1-114">Esta operação itera sobre uma série de consultas em poderes de $2$ até que um número máximo de consultas seja alcançado, ou o estado alvo é encontrado.</span><span class="sxs-lookup"><span data-stu-id="aa1d1-114">This operation iterates over a number of queries in powers of $2$ until either a maximal number of queries is reached, or the target state is found.</span></span>