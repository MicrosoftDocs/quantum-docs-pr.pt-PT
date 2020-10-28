---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: Operação GetQubitsAvailableToBorrow
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow. This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.
ms.openlocfilehash: cb56ce4aefd7a03c0f0827b8d34688ef17988f56
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712585"
---
# <a name="getqubitsavailabletoborrow-operation"></a><span data-ttu-id="3492d-102">Operação GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="3492d-102">GetQubitsAvailableToBorrow operation</span></span>

<span data-ttu-id="3492d-103">Espaço de nome: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="3492d-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="3492d-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3492d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3492d-105">Devolve o número de qubits atualmente disponíveis para empréstimo.</span><span class="sxs-lookup"><span data-stu-id="3492d-105">Returns the number of qubits currently available to borrow.</span></span>
<span data-ttu-id="3492d-106">Isto inclui qubits não-reutilizados; isto inclui os qubits devolvidos por `GetQubitsAvailableToUse` .</span><span class="sxs-lookup"><span data-stu-id="3492d-106">This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.</span></span>

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a><span data-ttu-id="3492d-107">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3492d-107">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3492d-108">O número de qubits que poderiam ser atribuídos em `borrowing` comunicado.</span><span class="sxs-lookup"><span data-stu-id="3492d-108">The number of qubits that could be allocated in a `borrowing` statement.</span></span>
<span data-ttu-id="3492d-109">Se a máquina-alvo utilizada não fornecer estas informações, `-1` então é devolvida.</span><span class="sxs-lookup"><span data-stu-id="3492d-109">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="3492d-110">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3492d-110">See Also</span></span>

- [<span data-ttu-id="3492d-111">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span><span class="sxs-lookup"><span data-stu-id="3492d-111">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)