---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: Obter Operação GetQubits DisponívelToUse
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 2ed8c3789331a15b351769be960d06f6364d8047
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827807"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="bc2a4-102">Obter Operação GetQubits DisponívelToUse</span><span class="sxs-lookup"><span data-stu-id="bc2a4-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="bc2a4-103">Espaço de nome: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="bc2a4-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="bc2a4-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="bc2a4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="bc2a4-105">Devolve o número de qubits atualmente disponíveis para utilização.</span><span class="sxs-lookup"><span data-stu-id="bc2a4-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="bc2a4-106">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bc2a4-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bc2a4-107">O número de qubits que poderiam ser atribuídos em `using` comunicado.</span><span class="sxs-lookup"><span data-stu-id="bc2a4-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="bc2a4-108">Se a máquina-alvo utilizada não fornecer estas informações, `-1` então é devolvida.</span><span class="sxs-lookup"><span data-stu-id="bc2a4-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc2a4-109">Consulte também</span><span class="sxs-lookup"><span data-stu-id="bc2a4-109">See Also</span></span>

- [<span data-ttu-id="bc2a4-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="bc2a4-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)