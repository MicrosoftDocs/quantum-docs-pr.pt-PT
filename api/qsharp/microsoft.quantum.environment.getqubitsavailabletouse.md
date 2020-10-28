---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: Obter Operação GetQubits DisponívelToUse
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 25d43d369193fc7453fd5ce9c50769c438a69afb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712582"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="1e50b-102">Obter Operação GetQubits DisponívelToUse</span><span class="sxs-lookup"><span data-stu-id="1e50b-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="1e50b-103">Espaço de nome: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="1e50b-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="1e50b-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1e50b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1e50b-105">Devolve o número de qubits atualmente disponíveis para utilização.</span><span class="sxs-lookup"><span data-stu-id="1e50b-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="1e50b-106">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1e50b-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1e50b-107">O número de qubits que poderiam ser atribuídos em `using` comunicado.</span><span class="sxs-lookup"><span data-stu-id="1e50b-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="1e50b-108">Se a máquina-alvo utilizada não fornecer estas informações, `-1` então é devolvida.</span><span class="sxs-lookup"><span data-stu-id="1e50b-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e50b-109">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1e50b-109">See Also</span></span>

- [<span data-ttu-id="1e50b-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="1e50b-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)