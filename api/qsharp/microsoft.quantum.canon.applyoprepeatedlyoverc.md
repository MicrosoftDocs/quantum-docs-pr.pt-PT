---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverC
title: Aplicação Operação OpRepeatedlyOverC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverC
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: effd61e6c012dcf81a83383c3fd43cf745d18117
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717832"
---
# <a name="applyoprepeatedlyoverc-operation"></a><span data-ttu-id="5611c-102">Aplicação Operação OpRepeatedlyOverC</span><span class="sxs-lookup"><span data-stu-id="5611c-102">ApplyOpRepeatedlyOverC operation</span></span>

<span data-ttu-id="5611c-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5611c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5611c-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5611c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5611c-105">Aplica a mesma operação num registo de qubits várias vezes.</span><span class="sxs-lookup"><span data-stu-id="5611c-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOverC (op : (Qubit[] => Unit is Ctl), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="5611c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5611c-106">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="5611c-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="5611c-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="5611c-108">Uma operação a ser aplicada várias vezes no registo qubit</span><span class="sxs-lookup"><span data-stu-id="5611c-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="5611c-109">alvos : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span><span class="sxs-lookup"><span data-stu-id="5611c-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="5611c-110">Matrizes aninhadas descrevendo os alvos da operação.</span><span class="sxs-lookup"><span data-stu-id="5611c-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="5611c-111">Cada matriz deve conter uma lista de ints descrevendo os qubits a serem usados.</span><span class="sxs-lookup"><span data-stu-id="5611c-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="5611c-112">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5611c-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5611c-113">Registo qubit para ser agido.</span><span class="sxs-lookup"><span data-stu-id="5611c-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5611c-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5611c-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="5611c-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5611c-115">See Also</span></span>

- [<span data-ttu-id="5611c-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="5611c-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)