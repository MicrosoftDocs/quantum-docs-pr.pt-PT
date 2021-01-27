---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver
title: AplicarOperação OpRepeatedlyOver
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOver
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 263eff8ec31f5ee36485eb1d2ed52bf15cef4bef
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844789"
---
# <a name="applyoprepeatedlyover-operation"></a><span data-ttu-id="e71c9-102">AplicarOperação OpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="e71c9-102">ApplyOpRepeatedlyOver operation</span></span>

<span data-ttu-id="e71c9-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e71c9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e71c9-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e71c9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e71c9-105">Aplica a mesma operação num registo de qubits várias vezes.</span><span class="sxs-lookup"><span data-stu-id="e71c9-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOver (op : (Qubit[] => Unit), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e71c9-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e71c9-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="e71c9-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="e71c9-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e71c9-108">Uma operação a ser aplicada várias vezes no registo qubit</span><span class="sxs-lookup"><span data-stu-id="e71c9-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="e71c9-109">alvos : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span><span class="sxs-lookup"><span data-stu-id="e71c9-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="e71c9-110">Matrizes aninhadas descrevendo os alvos da operação.</span><span class="sxs-lookup"><span data-stu-id="e71c9-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="e71c9-111">Cada matriz deve conter uma lista de ints descrevendo os qubits a serem usados.</span><span class="sxs-lookup"><span data-stu-id="e71c9-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="e71c9-112">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e71c9-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e71c9-113">Registo qubit para ser agido.</span><span class="sxs-lookup"><span data-stu-id="e71c9-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e71c9-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e71c9-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="e71c9-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e71c9-115">See Also</span></span>

- [<span data-ttu-id="e71c9-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="e71c9-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)