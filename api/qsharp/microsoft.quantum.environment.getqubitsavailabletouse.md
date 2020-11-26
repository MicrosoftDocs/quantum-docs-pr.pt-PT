---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: Obter Operação GetQubits DisponívelToUse
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: ce461b03a08b4c83b9de142c957ce5c590fe9659
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201415"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="df923-102">Obter Operação GetQubits DisponívelToUse</span><span class="sxs-lookup"><span data-stu-id="df923-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="df923-103">Espaço de nome: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="df923-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="df923-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="df923-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="df923-105">Devolve o número de qubits atualmente disponíveis para utilização.</span><span class="sxs-lookup"><span data-stu-id="df923-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="df923-106">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="df923-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="df923-107">O número de qubits que poderiam ser atribuídos em `using` comunicado.</span><span class="sxs-lookup"><span data-stu-id="df923-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="df923-108">Se a máquina-alvo utilizada não fornecer estas informações, `-1` então é devolvida.</span><span class="sxs-lookup"><span data-stu-id="df923-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="df923-109">Consulte também</span><span class="sxs-lookup"><span data-stu-id="df923-109">See Also</span></span>

- [<span data-ttu-id="df923-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="df923-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)