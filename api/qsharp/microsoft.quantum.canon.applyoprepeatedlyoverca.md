---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverCA
title: Aplicação Operação OpRepeatedlyOverCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverCA
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 970acfbc63bc95542827988c5c81387e8812f289
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717821"
---
# <a name="applyoprepeatedlyoverca-operation"></a><span data-ttu-id="d832b-102">Aplicação Operação OpRepeatedlyOverCA</span><span class="sxs-lookup"><span data-stu-id="d832b-102">ApplyOpRepeatedlyOverCA operation</span></span>

<span data-ttu-id="d832b-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d832b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d832b-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d832b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d832b-105">Aplica a mesma operação num registo de qubits várias vezes.</span><span class="sxs-lookup"><span data-stu-id="d832b-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOverCA (op : (Qubit[] => Unit is Adj + Ctl), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="d832b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d832b-106">Input</span></span>

### <a name="op--qubit--unit-adj--ctl"></a><span data-ttu-id="d832b-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="d832b-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="d832b-108">Uma operação a ser aplicada várias vezes no registo qubit</span><span class="sxs-lookup"><span data-stu-id="d832b-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="d832b-109">alvos : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span><span class="sxs-lookup"><span data-stu-id="d832b-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="d832b-110">Matrizes aninhadas descrevendo os alvos da operação.</span><span class="sxs-lookup"><span data-stu-id="d832b-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="d832b-111">Cada matriz deve conter uma lista de ints descrevendo os qubits a serem usados.</span><span class="sxs-lookup"><span data-stu-id="d832b-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="d832b-112">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d832b-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d832b-113">Registo qubit para ser agido.</span><span class="sxs-lookup"><span data-stu-id="d832b-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d832b-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d832b-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="d832b-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d832b-115">See Also</span></span>

- [<span data-ttu-id="d832b-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="d832b-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)