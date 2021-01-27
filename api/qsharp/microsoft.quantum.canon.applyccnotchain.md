---
uid: Microsoft.Quantum.Canon.ApplyCCNOTChain
title: AplicaÇÃO Operação CCTChain
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCCNOTChain
qsharp.summary: Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers. Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.
ms.openlocfilehash: 53fdd59b06d542494647acb665f248fc18de93d9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845130"
---
# <a name="applyccnotchain-operation"></a><span data-ttu-id="dd155-102">AplicaÇÃO Operação CCTChain</span><span class="sxs-lookup"><span data-stu-id="dd155-102">ApplyCCNOTChain operation</span></span>

<span data-ttu-id="dd155-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dd155-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dd155-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dd155-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dd155-105">Implementa uma cascata de portões CCNOT controlados em bits correspondentes de dois registos qubit, atuando no próximo qubit de um dos registos.</span><span class="sxs-lookup"><span data-stu-id="dd155-105">Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers.</span></span>
<span data-ttu-id="dd155-106">Partindo dos qubits na posição 0 em ambos os registos como controlos, o CCNOT é aplicado ao qubit na posição 1 do registo-alvo, sendo depois controlado pelos qubits na posição 1, atuando no qubit na posição 2 do registo-alvo, etc., terminando com uma ação sobre o qubit alvo na posição `Length(nQubits)-1` .</span><span class="sxs-lookup"><span data-stu-id="dd155-106">Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.</span></span>

```qsharp
operation ApplyCCNOTChain (register : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="dd155-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="dd155-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="dd155-108">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dd155-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dd155-109">Registo qubit, apenas utilizado para controlos.</span><span class="sxs-lookup"><span data-stu-id="dd155-109">Qubit register, only used for controls.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="dd155-110">alvos : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dd155-110">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dd155-111">Registo qubit, usado para controlos e como alvo.</span><span class="sxs-lookup"><span data-stu-id="dd155-111">Qubit register, used for controls and as target.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dd155-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dd155-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="dd155-113">Observações</span><span class="sxs-lookup"><span data-stu-id="dd155-113">Remarks</span></span>

<span data-ttu-id="dd155-114">O registo de qubits-alvo deve ter um qubit mais do que o outro registo.</span><span class="sxs-lookup"><span data-stu-id="dd155-114">The target qubit register must have one qubit more than the other register.</span></span>