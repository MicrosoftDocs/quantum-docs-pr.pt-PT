---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: Operação GetQubitsAvailableToBorrow
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow.
ms.openlocfilehash: f2294fadb9c10d800b7a743fbfe0810f36f18516
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853254"
---
# <a name="getqubitsavailabletoborrow-operation"></a><span data-ttu-id="3a15f-102">Operação GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="3a15f-102">GetQubitsAvailableToBorrow operation</span></span>

<span data-ttu-id="3a15f-103">Espaço de nome: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="3a15f-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="3a15f-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3a15f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3a15f-105">Devolve o número de qubits atualmente disponíveis para empréstimo.</span><span class="sxs-lookup"><span data-stu-id="3a15f-105">Returns the number of qubits currently available to borrow.</span></span>

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a><span data-ttu-id="3a15f-106">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3a15f-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3a15f-107">O número de qubits que podem ser emprestados e não serão atribuídos como parte de uma `borrowing` declaração.</span><span class="sxs-lookup"><span data-stu-id="3a15f-107">The number of qubits that could be borrowed and won't be allocated as part of a `borrowing` statement.</span></span>
<span data-ttu-id="3a15f-108">Se a máquina-alvo utilizada não fornecer estas informações, `-1` então é devolvida.</span><span class="sxs-lookup"><span data-stu-id="3a15f-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a15f-109">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3a15f-109">See Also</span></span>

- [<span data-ttu-id="3a15f-110">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span><span class="sxs-lookup"><span data-stu-id="3a15f-110">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)