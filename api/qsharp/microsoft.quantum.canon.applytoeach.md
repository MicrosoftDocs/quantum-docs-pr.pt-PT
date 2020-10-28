---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: AplicarToach
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: e1625829e2e9efd9d39fe0692f01c1cbbffc651c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717594"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="20fa8-102">AplicarToach</span><span class="sxs-lookup"><span data-stu-id="20fa8-102">ApplyToEach operation</span></span>

<span data-ttu-id="20fa8-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="20fa8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="20fa8-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="20fa8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="20fa8-105">Aplica uma operação de um único qubit a cada elemento num registo.</span><span class="sxs-lookup"><span data-stu-id="20fa8-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="20fa8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="20fa8-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="20fa8-107">singleElementOperação : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="20fa8-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="20fa8-108">Operação a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="20fa8-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="20fa8-109">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="20fa8-109">register : 'T[]</span></span>

<span data-ttu-id="20fa8-110">Matriz de qubits para aplicar a operação dada.</span><span class="sxs-lookup"><span data-stu-id="20fa8-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="20fa8-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="20fa8-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="20fa8-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="20fa8-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="20fa8-113">'T</span><span class="sxs-lookup"><span data-stu-id="20fa8-113">'T</span></span>

<span data-ttu-id="20fa8-114">O alvo no qual a operação atua.</span><span class="sxs-lookup"><span data-stu-id="20fa8-114">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="20fa8-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="20fa8-115">See Also</span></span>

- [<span data-ttu-id="20fa8-116">Microsoft.Quantum.Canon.ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="20fa8-116">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="20fa8-117">Microsoft.quantum.canon.applyToEacha</span><span class="sxs-lookup"><span data-stu-id="20fa8-117">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="20fa8-118">Microsoft.Quantum.Canon.ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="20fa8-118">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)