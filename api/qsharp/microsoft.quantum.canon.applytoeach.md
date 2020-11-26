---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: AplicarToach
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 11f9363feb38676df3f805496c74036aa96160c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217871"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="d0703-102">AplicarToach</span><span class="sxs-lookup"><span data-stu-id="d0703-102">ApplyToEach operation</span></span>

<span data-ttu-id="d0703-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d0703-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d0703-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d0703-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d0703-105">Aplica uma operação de um único qubit a cada elemento num registo.</span><span class="sxs-lookup"><span data-stu-id="d0703-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="d0703-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d0703-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="d0703-107">singleElementOperação : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="d0703-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d0703-108">Operação a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="d0703-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="d0703-109">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="d0703-109">register : 'T[]</span></span>

<span data-ttu-id="d0703-110">Matriz de qubits para aplicar a operação dada.</span><span class="sxs-lookup"><span data-stu-id="d0703-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d0703-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d0703-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d0703-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="d0703-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d0703-113">'T</span><span class="sxs-lookup"><span data-stu-id="d0703-113">'T</span></span>

<span data-ttu-id="d0703-114">O alvo no qual a operação atua.</span><span class="sxs-lookup"><span data-stu-id="d0703-114">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0703-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d0703-115">See Also</span></span>

- [<span data-ttu-id="d0703-116">Microsoft.Quantum.Canon.ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="d0703-116">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="d0703-117">Microsoft.quantum.canon.applyToEacha</span><span class="sxs-lookup"><span data-stu-id="d0703-117">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="d0703-118">Microsoft.Quantum.Canon.ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="d0703-118">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)