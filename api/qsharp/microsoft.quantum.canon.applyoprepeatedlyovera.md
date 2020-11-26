---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverA
title: Aplicação Operação OpRepeatedlyOverA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverA
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 65675a3a83f0ac730b9e3a58f80f77c096c1ce57
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209150"
---
# <a name="applyoprepeatedlyovera-operation"></a><span data-ttu-id="6f235-102">Aplicação Operação OpRepeatedlyOverA</span><span class="sxs-lookup"><span data-stu-id="6f235-102">ApplyOpRepeatedlyOverA operation</span></span>

<span data-ttu-id="6f235-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6f235-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6f235-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6f235-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6f235-105">Aplica a mesma operação num registo de qubits várias vezes.</span><span class="sxs-lookup"><span data-stu-id="6f235-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOverA (op : (Qubit[] => Unit is Adj), targets : Int[][], register : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="6f235-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6f235-106">Input</span></span>

### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="6f235-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="6f235-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="6f235-108">Uma operação a ser aplicada várias vezes no registo qubit</span><span class="sxs-lookup"><span data-stu-id="6f235-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="6f235-109">alvos : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span><span class="sxs-lookup"><span data-stu-id="6f235-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="6f235-110">Matrizes aninhadas descrevendo os alvos da operação.</span><span class="sxs-lookup"><span data-stu-id="6f235-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="6f235-111">Cada matriz deve conter uma lista de ints descrevendo os qubits a serem usados.</span><span class="sxs-lookup"><span data-stu-id="6f235-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="6f235-112">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6f235-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6f235-113">Registo qubit para ser agido.</span><span class="sxs-lookup"><span data-stu-id="6f235-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6f235-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6f235-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="6f235-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="6f235-115">See Also</span></span>

- [<span data-ttu-id="6f235-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="6f235-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)