---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: Operação CCNOT
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: a9186269a868c2ac9d2f15727a3b0ed1bfec3fa4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98819035"
---
# <a name="ccnot-operation"></a><span data-ttu-id="924ef-102">Operação CCNOT</span><span class="sxs-lookup"><span data-stu-id="924ef-102">CCNOT operation</span></span>

<span data-ttu-id="924ef-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="924ef-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="924ef-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="924ef-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="924ef-105">Aplica o portão duplamente controlado -NÃO (CCNOT) a três qubits.</span><span class="sxs-lookup"><span data-stu-id="924ef-105">Applies the doubly controlled–NOT (CCNOT) gate to three qubits.</span></span>

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="924ef-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="924ef-106">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="924ef-107">controle1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="924ef-107">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="924ef-108">Primeiro qubit de controlo para o portão CCNOT.</span><span class="sxs-lookup"><span data-stu-id="924ef-108">First control qubit for the CCNOT gate.</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="924ef-109">controlo2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="924ef-109">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="924ef-110">Segundo qubit de controlo para o portão CCNOT.</span><span class="sxs-lookup"><span data-stu-id="924ef-110">Second control qubit for the CCNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="924ef-111">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="924ef-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="924ef-112">Qubit de alvo para o portão CCNOT.</span><span class="sxs-lookup"><span data-stu-id="924ef-112">Target qubit for the CCNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="924ef-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="924ef-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="924ef-114">Observações</span><span class="sxs-lookup"><span data-stu-id="924ef-114">Remarks</span></span>

<span data-ttu-id="924ef-115">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="924ef-115">Equivalent to:</span></span>

```qsharp
Controlled X([control1, control2], target);
```