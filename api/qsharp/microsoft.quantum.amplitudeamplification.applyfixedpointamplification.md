---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: Aplicação Operação DePosição Internacional
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: fa19c3bb06ae91a2fa18acb6f853020830e749f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847222"
---
# <a name="applyfixedpointamplification-operation"></a><span data-ttu-id="84d0d-102">Aplicação Operação DePosição Internacional</span><span class="sxs-lookup"><span data-stu-id="84d0d-102">ApplyFixedPointAmplification operation</span></span>

<span data-ttu-id="84d0d-103">Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="84d0d-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="84d0d-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="84d0d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="84d0d-105">algoritmo de amplificação da amplitude Fixed-Point</span><span class="sxs-lookup"><span data-stu-id="84d0d-105">Fixed-Point Amplitude Amplification algorithm</span></span>

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="84d0d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="84d0d-106">Input</span></span>

### <a name="statepreporacle--stateoracle"></a><span data-ttu-id="84d0d-107">EstadoPrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="84d0d-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="84d0d-108">Oráculo unitário que prepara o estado de partida.</span><span class="sxs-lookup"><span data-stu-id="84d0d-108">Unitary oracle that prepares the start state.</span></span>


### <a name="startqubits--qubit"></a><span data-ttu-id="84d0d-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="84d0d-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="84d0d-110">Registo de qubits</span><span class="sxs-lookup"><span data-stu-id="84d0d-110">Qubit register</span></span>



## <a name="output--unit"></a><span data-ttu-id="84d0d-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="84d0d-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="84d0d-112">Observações</span><span class="sxs-lookup"><span data-stu-id="84d0d-112">Remarks</span></span>

<span data-ttu-id="84d0d-113">Os bits de arranque devem estar no estado $\ket{0 \cdots 0}$.</span><span class="sxs-lookup"><span data-stu-id="84d0d-113">The startQubits must be in the $\ket{0 \cdots 0}$ state.</span></span> <span data-ttu-id="84d0d-114">Esta operação itera sobre uma série de consultas em poderes de $2$ até que um número máximo de consultas seja alcançado, ou o estado alvo é encontrado.</span><span class="sxs-lookup"><span data-stu-id="84d0d-114">This operation iterates over a number of queries in powers of $2$ until either a maximal number of queries is reached, or the target state is found.</span></span>